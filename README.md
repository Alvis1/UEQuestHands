# Guide for setting up Unreal Engine 5.5.4 for Meta Quest on a pristine Windows installation.
Source - https://dev.epicgames.com/community/learning/tutorials/PYP7/unreal-engine-5-5-x-for-meta-quest-vr
## Download the following:

Unreal Engine Launcher: https://www.unrealengine.com/en-US/download
Android Studio Flamingo | 2022.2.1 Patch 2 May 24, 2023: https://developer.android.com/studio/archive
Scroll down to "Java SE Development Kit 17.0.10" Windows x64 Compressed Archive https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
Meta Quest Link App (Desktop): https://www.meta.com/quest/setup/
Meta Quest Developer Hub for Windows: https://developer.oculus.com/downloads/package/oculus-developer-hub-win
Unreal Engine 5 Integration v78 (Meta XR Plugin): https://developer.oculus.com/downloads/package/unreal-engine-5-integration/
Unreal Engine 5 Platform v78 (Meta XR Platform): https://developer.oculus.com/downloads/package/unreal-5-platform-sdk-plugin
Meta XR Simulator v78: https://developer.oculus.com/downloads/package/meta-xr-simulator/

I recommend installing all this to "C: drive", as some of these tools are crazy.

## JDK 17.0.10

Unzip "Java SE Development Kit 17.0.10" into "C:/Program Files"Epic recommend "Java SE Development Kit 17.0.6", but 17.0.10 has been tested as working

## Android Studio Flamingo

1. Run the installer
2. Open Android Studio and install required components
3. Relaunch Android Studio, click "More Actions" on the right menu
4. Select "SDK Manager"
5. Ignore the left menu
6. At bottom right, tick "Hide Obsolete Packages" and "Show Package Details"
7. Under "SDK Platform," tick Android API 34 and Android 12L (Sv2)
8. Under "SDK Tools," expand "Android SDK Build-Tools 36-rc5"
9. Tick 34.0.0 and 33.0.1
10. Expand "NDK (Side by Side)"
11. Tick 25.1.8937393
12. Expand "Android SDK Command-line Tools"
13. Tick the latest version (currently 13)
14. Expand "CMake"
15. Tick 3.10.2.4988404
16. Also tick: Android Emulator, Android Emulator Hypervisor Driver, and Android SDK Platform-Tools
17. Apply and accept licenses
18. Close Android Studio
19. Reboot computer

## JAVA_HOME

1. Press Start on Windows
2. Type "Environment Var..."
3. Open "Edit the system environment variables"
4. Click "Environment Variables"
5. Under User variables, locate "JAVA_HOME"
6. Change to C:\Program Files\jdk-17.0.10
7. Reboot computer

## Create Meta Developer Account

1. Create a developer account: https://developer.oculus.com/
2. Install the Meta Quest app on your phone (App Store or Play Store)
3. In the app, select Menu > Devices
4. Select/add the device to enable developer mode
5. Tap "Headset settings"
6. Turn on Developer Settings/Debug Mode

## Meta Quest Mobile App
You'll need to create an organization account

1. Install the Meta Quest mobile app
2. Follow the app instructions to connect your Quest
3. Tap the headset icon
4. Select your Quest
5. Go to Manage Device > Headset Settings > Developer Mode
6. Enable Developer Mode

## Meta Quest Link Desktop App

1. Install
2. Launch
3. Update drivers if prompted
4. Set as default OpenXR runtime if prompted
5. Under Settings > General, enable Unknown Sources
6. Under Settings > Beta, enable Public Test Channel and Developer Runtime Features
7. Connect Quest to PC with USB
8. Follow linking instructions
9. Accept USB permissions on the Quest
10. On Quest: Settings > Advanced > Developer > enable all

## Meta Quest Developer Hub
You'll need to create an organization account /sigh

1. Install
2. Launch
3. App detects 2 ADB installs
4. Select the non-Meta one (use Android Studio ADB)
5. In Meta Hub, go to Device Manager
6. Update MQDH if needed
7. Reboot computer

## Unreal Engine

1. Install Unreal Engine Launcher
2. Launch
3. Sign in / Create Account
4. Select Unreal Engine from left menu
5. Go to Library tab
6. Next to Engine Versions, click "+"
7. Select 5.5.4 and install
8. Under Target Platforms, enable Android (if missed)
9. Click Launch

## Unreal Engine Android Setup

1. Locate you Unreal Engine 5.5.4 install folder
2. Run “UE_5.5\Engine\Extras\Android\SetupAndroid.bat”

## First Unreal Project

1. At Create New Project screen
2. Select Games
3. Select Virtual Reality template
4. Untick Starter Content
5. Name project
6. Click Create
7. Wait for project creation
8. Exit Unreal

## Meta XR Plugins

1. Locate your project folder
2. Create "Plugins" folder
3. Unzip UnrealMetaXRPlugin.78.zip into Plugins
4. Confirm "MetaXR" folder exists
5. Unzip Unreal5PlatformSDKPlugin.78.zip into Plugins
6. Confirm "MetaXRPlatform" folder exists
7. Launch .uproject

## Unreal Engine Plugins

1. In Unreal: Edit > Plugins
2. Under Installed/Virtual Reality, enable Meta XR
3. Under Installed/Online Platform, enable Meta XR Platform
4. Close Plugins window

## Unreal Project Settings

1. Edit > Project Settings
2. Go to Platforms > Android
3. Minimum SDK: 29
4. Target SDK: 32
5. Install Location: auto
6. Orientation: Landscape
7. Package game data inside .apk: ticked
8. Resolve all red warnings

## Unreal SDK Setup; SDKConfig

1. Project Settings > Platforms > Android SDK
2. SDK: C:/Users/name/AppData/Local/Android/Sdk
3. NDK: C:/Users/name/AppData/Local/Android/Sdk/ndk/25.1.8937393
4. Java: C:\Program Files\jdk-17.0.10
5. SDK API Level: android-34
6. NDK API Level: android-29

## Meta XR Setup

1. Project Settings > Plugins > Meta XR
2. XR API: Oculus OVRPlugin + OpenXR back-end (recommended)
3. Color Space: P3
4. Controller Pose Alignment: Default
5. Supported Devices: add your Quest
6. File > Save All
7. Restart Unreal

## Unreal VR Preview

1. Open Meta Quest Link (Desktop app)
2. On Quest, Quick Settings > Quest Link
3. Connect to PC
4. In Unreal, open Transport controls
5. Click More
6. Select VR Preview

## Meta XR Simulator

If SDK is BELOW v76:
1. Unzip meta_xr_simulator_v78.zip to C:\Users\name\Documents\Unreal Projects
2. Extract .tgz inside meta_xr_simulator_v78
3. Set JSON path in Meta XR plugin: C:/Users/name/Documents/Unreal Projects/meta_xr_simulator_v78/com.meta.xr.simulator/package/MetaXRSimulator/meta_openxr_simulator.json
4. Download Synthetic Environments: https://securecdn.oculus.com/binaries/download/?id=8778927728892025
5. Unzip synth_env_win64_v74.zip
6. Set Meta XR Synthetic Environments to this folder
7. Close Project Settings
8. Save All

If SDK is v76 or ABOVE:
1. On the Viewport shelf, locate Meta XR Simulator > Check for Updates
2. Enable "Meta XR Simulator/Meta XR Simulator" check box
3. From Meta XR Simulator, select a Synthetic Environment Server
4. Press Play/Standalone Game or Play/VR Preview

## Build Quest APK

1. In VRTemplateMap, open Platforms menu
2. Select Android > Package Project
3. Create folder "Quest"
4. Select folder
5. Build starts (progress in Output Log)
6. Wait for build
7. Open Meta Quest Developer Hub
8. In Device Manager, click +Add Build under Apps
9. Select APK built in Unreal
10. Install to Quest
11. On Quest, open App Library
12. Tap All > Unknown Sources
13. Launch app

## Distribution

1. Open Command Prompt (Admin)
2. cd "C:\Program Files\jdk-17.0.10\bin"
3. Choose keystore name (e.g., Mumble)
4. Choose alias (e.g., innit)
5. Choose password (e.g., 123456)
6. Run: keytool -genkey -v -keystore Mumble.keystore -alias innit -keyalg RSA -keysize 2048 -validity 10000
7. Answer prompts
8. Copy Mumble.keystore to Unreal Projects\Build\Android
9. In Unreal: Edit > Project Settings > Android
10. Set Keystore: Mumble.keystore
11. Key Alias: innit
12. Keystore Password: 123456
13. Key Password: 123456
14. Go to Packaging
15. Build Configuration: Shipping
16. Full Rebuild: ticked
17. For Distribution: ticked
18. Close settings
19. Platforms > Build for Android
20. Open Meta Quest Hub
21. App Distribution > Upload

### Android File Server - (Optional) 

1. Project Settings > AndroidFileServer
2. Enable Include in Shipping
3. Enable Compile AFSProject
4. Build and run

Note: For shipping builds, delete Binaries, Intermediate, and Saved folders along with the dev APK. For development, reset Packaging (step 15) to avoid full rebuilds.

Why add Meta Plugin to the Project Plugins folder? Meta’s guide points to a non-existent Marketplace folder. Also creating a Plugins Folder for each Project allows you to update plugins without affecting the editor.
