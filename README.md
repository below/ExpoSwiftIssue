# ExpoSwiftIssue
Demostrate an issue with the automatically generated Swift Header and Objective-C++, here in the case of an Expo App.

## Primary Objective

In an Expo Project, I want to access Swift Code that is local to the native iOS application in the AppDelegate. When using `#import "SwiftIssue-Swift.h` the following error is reported:

```
Cannot find interface declaration for 'ModulesProvider', superclass of 'ExpoModulesProvider'
```

## Apparent reason

This happens, because `AppDelegate.mm` is an Objective-C++ file. Importing the header in a different, pure Objective-C file is [not an issue](https://github.com/below/ExpoSwiftIssue/tree/working).

## Running the sample

To run the sample and see the error, you will have to do the usualy Expo schenanigans (it hurts me more than it hurts you). In the main project directory, execute in the terminal:

```shell
npm install
(cd ios & pod install)
```

After this, you can `xed ios` and build like usual
