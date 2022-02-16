
# Xcode Plugin Template

Basic template for creating a plugin for Xcode 13.

## Original Repository [Xcode-Plugin-Template](https://github.com/kattrali/Xcode-Plugin-Template.git)

## Installation

1. git clone repository
2. run `cd Xcode-Plugin-Template`
3. run `mkdir -p ~/Library/Developer/Xcode/Templates/Project\ Templates && cp -R ./Project\ Templates/Application\ Plug-in/Xcode\ Plugin.xctemplate ~/Library/Developer/Xcode/Templates/Project\ Templates/`
4. restart Xcode, use macOS - `Xcode Plugin` template create new project

## Usage

The default plugin file links against `AppKit` and `Foundation`, and, when built (and Xcode is restarted), creates a menu item labeled "Do Action" in the Edit menu. Pressing the menu item should open an alert. Customize at will!

#### 因为最新 Xcode 已经不支持插件，请先按照下面步骤为 Xcode 重新签名，Xcode 才能加载插件：

1. 打开 `钥匙串访问` app
2. 打开 钥匙串访问/证书助理/创建证书...
3. 创建一个名为 `XcodeSigner` ，证书类型为 `代码签名` 的根证书
4. 执行 `sudo codesign -f -s XcodeSigner /Applications/Xcode.app` 将 Xcode 重新签名 （过程较长，中间会提示输入密码）
5. 加载插件时会有弹窗提示点击 `Load Bundle` 就可以了
6. 重新签名后，运行项目时，系统会再启动一个 Xcode ，并可以打断点，方便你调试解决问题

## Notes
  
- 如果你想支持其他版本的 Xcode ，请添加 Xcode 的 build UUIDs 到项目 `Info.plist` 的 `DVTPlugInCompatibilityUUIDs` 里面。 可以通过执行命令读取: `defaults read /Applications/Xcode.app/Contents/Info DVTPlugInCompatibilityUUID`
- 如果你的 Xcode 改名字了，运行项目保存，请修改 `Edit Scheme` 里面的 `Executable` 为重签后的 Xcode
- ❤️如果有用，Star 一下⭐️ 

