# Apple Watch Integration with Flutter - Issue Report

This repository demonstrates an integration issue between Flutter and Apple Watch targets that occurs with the following environment:

- Flutter 3.27
- Xcode 16.2
- VS Code

## Issue Description

While the initial Flutter setup and Apple Watch integration work independently, there's a conflict when trying to run the Flutter app through VS Code after adding an Apple Watch target.

## Steps to Reproduce

1. Create a new Flutter project:
   ```bash
   flutter create apple_watch
   ```

2. Configure VS Code launch settings and verify the initial Flutter app runs successfully

3. Add an Apple Watch target in Xcode

4. Modify Build Settings in Xcode to resolve cyclic dependency errors

5. Verify that both iOS app and Apple Watch app run successfully in Xcode

6. Attempt to run the Flutter app in VS Code using an iOS simulator
   - **Result**: Build fails with errors

## Current Status

- ✅ Flutter app runs successfully in VS Code (before Watch integration)
- ✅ iOS + Apple Watch apps run successfully in Xcode
- ❌ Flutter app fails to run in VS Code after Watch integration

```
Launching lib/main.dart on iPhone 16 Pro Max in debug mode...
Xcode build done.                                           14.7s
Failed to build iOS app
Swift Compiler Error (Xcode): 'View' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:10:19

Swift Compiler Error (Xcode): 'Preview(_:body:)' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:21:1

Swift Compiler Error (Xcode): 'main()' is only available in iOS 14.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/RunnerWatchApp.swift:9:0

Swift Compiler Error (Xcode): 'Scene' is only available in iOS 14.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/RunnerWatchApp.swift:11:19

Swift Compiler Error (Xcode): 'VStack' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:11:8

Swift Compiler Error (Xcode): 'Image' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:12:12

Swift Compiler Error (Xcode): 'init(systemName:)' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:12:12

Swift Compiler Error (Xcode): 'imageScale' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:13:17

Swift Compiler Error (Xcode): 'foregroundStyle' is only available in iOS 15.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:14:17

Swift Compiler Error (Xcode): 'tint' is only available in iOS 15.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:14:34

Swift Compiler Error (Xcode): 'Text' is only available in iOS 13.0 or newer
/Users/udi/work/moinsen/apps/test/apple_watch/ios/RunnerWatch%20Watch%20App/ContentView.swift:15:12

```

## Help Needed

If you have experience with Flutter and Apple Watch integration or have encountered similar issues, please help by:

1. Checking if you can reproduce this issue
2. Suggesting potential solutions or workarounds
3. Providing insights into what might be causing the conflict between Flutter's build process and the Apple Watch target

Please create an issue or submit a pull request if you have any solutions or suggestions.

## Getting Started with Flutter

For those new to Flutter, here are some helpful resources:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)
- [Online documentation](https://docs.flutter.dev/)

## Environment Details

- Flutter: 3.27
- Xcode: 16.2
- Editor: VS Code
- Platform: iOS with Apple Watch target
