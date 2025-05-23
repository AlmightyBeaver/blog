---
layout: post
title: App Group Storage
published: true
category: Swift
tags: UserDefaults NSUbiquitousKeyValueStore CoreData AppGroup Storage
---



Usage of the same data storage in an app group.

All Targets of the app group (e.g. app extensions like Widget, Intents (Siri), ...) shall access the same data storages.
They have access to the same app group directory, where the storage files should be located. The app group url can be found here: `FileManager.default.containerURL(forSecurityApplicationGroupIdentifier: "YourAppGroupIdHere")`

All Targets must have the `Capability` `App Groups` enabled and must use the same app group identifier e.g. `"group.com.yourCompany.yourApp"` to access the common directory.

Different kinds of apples native storage possibilities are considered here.



## UserDefaults

To use UserDefaults in an app group use the following initializer

- `UserDefaults(suiteName: "YourAppGroupIdHere")`

It will create a `*.plist` in the app group directory, all targets of the app group have access to

Be aware of the the `.synchronize()` method. I'm not sure if it's necessary to call the `.synchronize()` method of your UserDefaults instance after each change to avoid data corruption.

For migration from a non app group UserDefaults to an app group UserDefaults see e.g. [https://gist.github.com/dougdiego/945fd2e33769cf5f1338](https://gist.github.com/dougdiego/945fd2e33769cf5f1338)



## NSUbiquitousKeyValueStore

To use NSUbiquitousKeyValueStore in an app group you must have the same `iCloud Key_Value Store` (`com.apple.developer.ubiquity-kvstore-identifier`) value in the `*.entitlements` file in each target.

In my app entitlement file the standard value was
`$(TeamIdentifierPrefix)$(CFBundleIdentifier)`. This won't work in another target because each target has its own bundle identifier. 

A shared store could use e.g. `$(TeamIdentifierPrefix)com.yourCompany.app`. Each target has use this value.

You can read your CFBundleIdentifier programmatically with 
```swift
let bundleID = Bundle.main.bundleIdentifier
print(bundleId)
```
Then use the value in all other targets. (See chapter "Configuring Common Key-Value Storage for Multiple Apps" in [https://developer.apple.com/library/archive/documentation/General/Conceptual/iCloudDesignGuide/Chapters/iCloudFundametals.html#//apple_ref/doc/uid/TP40012094-CH6-SW1](https://developer.apple.com/library/archive/documentation/General/Conceptual/iCloudDesignGuide/Chapters/iCloudFundametals.html#//apple_ref/doc/uid/TP40012094-CH6-SW1)) 


Be aware of the the `.synchronize()` method. I'm not sure if it's necessary to call the `.synchronize()` method of your NSUbiquitousKeyValueStore instance after each change to avoid data corruption.



## CoreData

When the persistent container (`NSPersistentContainer` or `NSPersistentCloudKitContainer`) is set up you can change the urls of its descriptions (`NSPersistentContainer.persistentStoreDescriptions`) to the app group url.

- App-group folder url to use for the persistent stores (`NSPersistentStoreDescription.url`)
    - `FileManager.default.containerURL(forSecurityApplicationGroupIdentifier: "YourAppGroupIdHere")`

I use e.g. 
 
```swift 
let container: NSPersistentContainer = NSPersistentContainer(name: "yourDataModelName",
                                                             managedObjectModel: yourDataModel)
                                                            
guard let defaultDescription = container.persistentStoreDescriptions.first else {
    // handle error
}

guard let appGroupURL = FileManager.default
    .containerURL(forSecurityApplicationGroupIdentifier: "YourAppGroupId") else {
        // handle error
}

// This is optional. I add ./Library/Application Support/ to have the same structure as in the app sandbox
var appGroupStoreURL: URL = appGroupURL
    .appendingPathComponent("Library")
    .appendingPathComponent("Application Support")
do {
    try FileManager.default.createDirectory(atPath: appGroupStoreURL.relativePath,
                                            withIntermediateDirectories: true)
}catch {
    // handle error
}
print("CoreData Store App Group URL: `\(appGroupStoreURL)`")

let appGroupStoreFileURL = appGroupStoreURL.appendingPathComponent("\("yourDataModelName")_private.sqlite")
defaultDescription.url = appGroupStoreFileURL
```


For migration from a non app group store to an app group store see [https://menuplan.app/coding/2021/10/27/core-data-store-path-migration.html](https://menuplan.app/coding/2021/10/27/core-data-store-path-migration.html).


## Keychain

I didn't use it but maybe here is an indication if you have to use it across targets/apps

[https://developer.apple.com/library/archive/technotes/tn2311/_index.html](https://developer.apple.com/library/archive/technotes/tn2311/_index.html)


## Ressources
- [https://developer.apple.com/library/archive/documentation/General/Conceptual/ExtensibilityPG/ExtensionScenarios.html#//apple_ref/doc/uid/TP40014214-CH21-SW1](https://developer.apple.com/library/archive/documentation/General/Conceptual/ExtensibilityPG/ExtensionScenarios.html#//apple_ref/doc/uid/TP40014214-CH21-SW1)
- [https://stackoverflow.com/a/61967892/11536071](https://stackoverflow.com/a/61967892/11536071)
- [https://menuplan.app/coding/2021/10/27/core-data-store-path-migration.html](https://menuplan.app/coding/2021/10/27/core-data-store-path-migration.html)
- [https://gist.github.com/dougdiego/945fd2e33769cf5f1338](https://gist.github.com/dougdiego/945fd2e33769cf5f1338)
- [https://developer.apple.com/library/archive/technotes/tn2311/_index.html](https://developer.apple.com/library/archive/technotes/tn2311/_index.html)

