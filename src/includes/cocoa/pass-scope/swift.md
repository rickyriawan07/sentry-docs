```swift
let exception = NSException(name: NSExceptionName("My Custom exeption"), reason: "User clicked the button", userInfo: nil)
let scope = Scope()
scope.setLevel(.fatal)
// By explicity just passing the scope, only the data in this scope object will be added to the event
// The global scope (calls to configureScope) will be ignored
// Only do this if you have mastered this SDK, otherwise, you risk losing useful info
// If you just want to mutate what's in the scope use the callback, see: captureError
SentrySDK.capture(exception: exception, scope: scope)
```
