2022-10-03
# Apple Notifications.Name


## Foundation

### NSLocale
* `Foundation.NSLocale.currentLocaleDidChangeNotification`

### NSBundle/Bundle
* `Foundation.Bundle.didLoadNotification`
* `NSNotification.Name.NSBundleResourceRequestLowDiskSpace`

### NSCalendar
* `NSNotification.Name.NSCalendarDayChanged`

### NSDate
* `NSNotification.Name.NSSystemClockDidChange`


### NSFileHandle/FileHandle
* `Foundation.FileHandle.readCompletionNotification`
* `NSNotification.Name.NSFileHandleReadToEndOfFileCompletion`
* `NSNotification.Name.NSFileHandleConnectionAccepted`
* `NSNotification.Name.NSFileHandleDataAvailable`

### NSFileManager
* `NSNotification.Name.NSUbiquityIdentityDidChange`

### NSHTTPCookieStorage/HTTPCookieStorage
* `NSNotification.Name.NSHTTPCookieManagerAcceptPolicyChanged`
* `NSNotification.Name.NSHTTPCookieManagerCookiesChanged`


### NSMetadata
* `NSNotification.Name.NSMetadataQueryDidStartGathering`
* `NSNotification.Name.NSMetadataQueryGatheringProgress`
* `NSNotification.Name.NSMetadataQueryDidFinishGathering`
* `NSNotification.Name.NSMetadataQueryDidUpdate`



### NSPort/Port
* `Foundation.Port.didBecomeInvalidNotification`


### NSTimeZone
* `NSNotification.Name.NSSystemTimeZoneDidChange`


### NSUndoManager
* `NSNotification.Name.NSUndoManagerCheckpoint`
* `NSNotification.Name.NSUndoManagerWillUndoChange`
* `NSNotification.Name.NSUndoManagerWillRedoChange`
* `NSNotification.Name.NSUndoManagerDidUndoChange`
* `NSNotification.Name.NSUndoManagerDidRedoChange`
* `NSNotification.Name.NSUndoManagerDidOpenUndoGroup`
* `NSNotification.Name.NSUndoManagerWillCloseUndoGroup`
* `NSNotification.Name.NSUndoManagerDidCloseUndoGroup`



### UserDefaults
* `Foundation.UserDefaults.sizeLimitExceededNotification`
* `Foundation.UserDefaults.noCloudAccountNotification`
* `Foundation.UserDefaults.didChangeCloudAccountsNotification`
* `Foundation.UserDefaults.completedInitialCloudSyncNotification`
* `Foundation.UserDefaults.didChangeNotification`

### NSUbiquitousKeyValueStore
* `Foundation.NSUbiquitousKeyValueStore.didChangeExternallyNotification`


## UIKIT

### UIApplication
* `UIKit.UIApplication.willChangeStatusBarOrientationNotification`
    * deprecated: 13.0 
* `UIKit.UIApplication.didChangeStatusBarOrientationNotification`
    * deprecated: 13.0 
* `UIKit.UIApplication.statusBarOrientationUserInfoKey`
    * deprecated: 13.0 
* `UIKit.UIApplication.willChangeStatusBarFrameNotification`
    * deprecated: 13.0 
* `UIKit.UIApplication.didChangeStatusBarFrameNotification`
    * deprecated: 13.0 
* `UIKit.UIApplication.statusBarFrameUserInfoKey`
    * deprecated: 13.0 
* `UIKit.UIApplication.userDidTakeScreenshotNotification`
* `UIKit.UIApplication.didEnterBackgroundNotification`
* `UIKit.UIApplication.willEnterForegroundNotification`
* `UIKit.UIApplication.didFinishLaunchingNotification`
* `UIKit.UIApplication.didBecomeActiveNotification`
* `UIKit.UIApplication.willResignActiveNotification`
* `UIKit.UIApplication.didReceiveMemoryWarningNotification`
* `UIKit.UIApplication.willTerminateNotification`
* `UIKit.UIApplication.significantTimeChangeNotification`
* `UIKit.UIApplication.backgroundRefreshStatusDidChangeNotification`
* `UIKit.UIApplication.protectedDataWillBecomeUnavailableNotification`
* `UIKit.UIApplication.protectedDataDidBecomeAvailableNotification`

### UIResponder
* `UIKit.UIResponder.keyboardWillShowNotification`
* `UIKit.UIResponder.keyboardDidShowNotification`
* `UIKit.UIResponder.keyboardWillHideNotification`
* `UIKit.UIResponder.keyboardDidHideNotification`
* `UIKit.UIResponder.keyboardWillChangeFrameNotification`
* `UIKit.UIResponder.keyboardDidChangeFrameNotification`

### UIWindow
* `UIKit.UIWindow.didBecomeVisibleNotification`
* `UIKit.UIWindow.didBecomeHiddenNotification`
* `UIKit.UIWindow.didBecomeKeyNotification`
* `UIKit.UIWindow.didResignKeyNotification`

### UIScreen
* `UIKit.UIScreen.didConnectNotification`
    * deprecated: 16.0 
* `UIKit.UIScreen.didDisconnectNotification`
    * deprecated: 16.0 
* `UIKit.UIScreen.modeDidChangeNotification`
* `UIKit.UIScreen.brightnessDidChangeNotification`
* `UIKit.UIScreen.capturedDidChangeNotification`
* `UIKit.UIScreen.referenceDisplayModeStatusDidChangeNotification`

### UIScene
* `UIKit.UIScreen.willConnectNotification`
* `UIKit.UIScreen.didDisconnectNotification`
* `UIKit.UIScreen.didActivateNotification`
* `UIKit.UIScreen.willDeactivateNotification`
* `UIKit.UIScreen.willEnterForegroundNotification`
* `UIKit.UIScreen.didEnterBackgroundNotification`

### UIViewController
* `UIKit.UIViewController.showDetailTargetDidChangeNotification`

### UITextView
* `UIKit.UITextView.textDidBeginEditingNotification`
* `UIKit.UITextView.textDidChangeNotification`
* `UIKit.UITextView.textDidEndEditingNotification`
* 
### UIDevice
* `UIKit.UIDevice.orientationDidChangeNotification`
* `UIKit.UIDevice.batteryStateDidChangeNotification`
* `UIKit.UIDevice.batteryLevelDidChangeNotification`
* `UIKit.UIDevice.proximityStateDidChangeNotification`


### UIDocument
* `UIKit.UIDocument.stateChangedNotification`


### UIFocus
* `UIKit.UIFocus.UIFocusSystem.didUpdateNotification`
* `UIKit.UIFocus.UIFocusSystem.movementDidFailNotification`
* `UIKit.UIFocus.UIFocusSystem.focusUpdateContextUserInfoKey`
* `UIKit.UIFocus.UIFocusSystem.animationCoordinatorUserInfoKey`

### UIPasteboard
* `UIKit.UIPasteboard.changedNotification`
* `UIKit.UIPasteboard.removedNotification`

### UIPointerLockState
* `UIKit.UIPointerLockState.didChangeNotification`

### UITableView
* `UIKit.UITableView.selectionDidChangeNotification`

### UITextField
* `UIKit.UITextField.textDidBeginEditingNotification`
* `UIKit.UITextField.textDidEndEditingNotification`
* `UIKit.UITextField.textDidChangeNotification`
* 
### UITextInputMode
* `UIKit.UITextInputMode.currentInputModeDidChangeNotification`


## CoreData
* `CoreData.NSManagedObjectContext.willSaveObjectsNotification`
* `CoreData.NSManagedObjectContext.didSaveObjectsNotification`
* `CoreData.NSManagedObjectContext.didChangeObjectsNotification`
* `CoreData.NSManagedObjectContext.didSaveObjectIDsNotification`
* `CoreData.NSManagedObjectContext.didMergeChangesObjectIDsNotification`
* `CoreData.NSCoreDataCoreSpotlightDelegate.indexDidUpdateNotification`
* `NSNotification.Name.NSManagedObjectContextWillSave`
* `NSNotification.Name.NSManagedObjectContextDidSave`
* `NSNotification.Name.NSManagedObjectContextObjectsDidChange`
* `NSNotification.Name.NSManagedObjectContextDidSaveObjectIDs`
* `NSNotification.Name.NSManagedObjectContextDidMergeChangesObjectIDs`
* `Notification.Name.NSPersistentStoreCoordinatorStoresWillChange`
* `Notification.Name.NSPersistentStoreCoordinatorStoresDidChange`
* `Notification.Name.NSPersistentStoreCoordinatorWillRemoveStore`
* `Notification.Name.NSPersistentStoreRemoteChange`
* `Notification.Name.NSPersistentStoreDidImportUbiquitousContentChanges`
    * deprecated: 10.0

## CloudKit
* `NSNotification.Name.CKAccountChanged`



## Ressources
A lot, but not all, are found here:
[https://developer.apple.com/documentation/foundation/nsnotification/name ](https://developer.apple.com/documentation/foundation/nsnotification/name )
Attention: Is not up to date!


