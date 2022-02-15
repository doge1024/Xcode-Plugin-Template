# Original Repository [Xcode-Plugin-Template](https://github.com/kattrali/Xcode-Plugin-Template.git)

# Xcode Plugin Template

Basic template for creating a plugin for Xcode 13.

## Installation

- Install using [Alcatraz](http://alcatraz.io/)
- Copy Xcode Plugin.xctemplate to ~/Library/Developer/Xcode/Templates/Project\ Templates/Xcode\ Plugin/Xcode\ Plugin.xctemplate

## Usage

The default plugin file links against `AppKit` and `Foundation`, and, when built (and Xcode is restarted), creates a menu item labeled "Do Action" in the Edit menu. Pressing the menu item should open an alert. Customize at will!

**Note:** Compiling the template with Swift requires Xcode 6.1 or greater.


## Notes

- Add the build UUIDs for the versions of Xcode you wish to support to `DVTPlugInCompatibilityUUIDs` in `Info.plist`. This can be found by running:

  <pre>defaults read /Applications/Xcode.app/Contents/Info DVTPlugInCompatibilityUUID</pre>
