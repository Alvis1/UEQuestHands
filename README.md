## Hand tracking with Unreal Engine 5.4.4 and Quest 3, 2.

## Recommendations on creating content for Quest3:
https://forums.unrealengine.com/t/how-to-game-development-best-practices-for-quest-3-using-unreal-engine-5/2056737


## Video sources for Hand Tracking used: 
### **GDXR:**

 #### **Meta XR Hand Tracking Part 1 - How To Set Up Hand Tracking In UE5**
      https://www.youtube.com/watch?v=HpVdLXc96a4&ab_channel=GDXR

## Requirements
### Meta XR plugin - 
   Epic Games marketplace -> install
   Unreal engine -> Edit -> Plugins -> Meta XR -> enable -> Restart Engine
   ## If does not work - Uninstall Leap Motion app or other app that deal with hand tracking src: 
   [https://developers.meta.com/horizon/downloads/package/unreal-engine-5-integration](https://www.youtube.com/watch?v=qMf-Lf1iG7c&ab_channel=GDXR)

   
  ### Meta Quest Link App
   -> Settings -> Beta -> Developer Runtime Features - Enable


## Unreal Engine
  -> Edit -> Project Settings -> Hand Tracking Support -> Hands Only
   


## Passtrough
src: https://youtu.be/hZu0Rg_1hyE?si=OV_x4jtGaq9TB94L

    -> Project Settings -> Rendering -> Postprocessing -> Enable alpha channel support ... -> Allow through tonemapper
    -> Project Settings -> Meta XR -> Mobile -> Supported Meta Quest devices -> + x3
    -> Composite Depth
    -> Hand Tracking Support -> Hands Only
    -> Hand Tracking Frequency -> HIGH
    -> Hand Tracking Version -> V2
    -> Passtrough enabled
    -> Anchor Support
    -> Anchor Sharing
    -> Scene Support
    -> Experimental -> Support Experimental Features - True
    -> General -> Control Pose Alignment -> Aim

Delete background, walls

## Unreal Android SDK setup:

Unreal documentation:
https://dev.epicgames.com/documentation/en-us/unreal-engine/android-support-for-unreal-engine?application_version=5.4

Youtube guide: 
https://www.youtube.com/watch?v=znvDJ9E-SFk&t=1941s&ab_channel=ShimmeringTrashpile

Google Doc:
https://docs.google.com/document/d/10JZ9Bs3-H0eeujtvEnGAHBXnOusnP6inLcJS7UXOnLg/edit?tab=t.0#heading=h.fo90sywkll5v

#### Summary: 

    -> Java runtime: OpenJDK 17.0.6 2023-01-17 
    -> Android Studio Version: Flamingo 2022.2.1 Patch 2 May 24, 2023
          - SDK Platforms Tab
             -> Uncheck Android API 35, Check Android 12L
          - SDK Tools Tab
             -> Android SDK Build-Tools 35-rc3 -> Uncheck 35.0.0, Check 32.0.0
          - NDK
             -> Check 25.1.8937393
          - Android SDK Command Line Tools (latest) 
             -> Android SDK Command-line Tools (latest) Version 13
          - CMake
             -> 3.22.1, 3.10.2.4988404
          -Android SDK Platform-Tools (The Version column will be 35.0.2)


#### -> Unreal settings

        -> Platforms -> Android -> 
       Minimum SDK Version (26=8.0.0, 27=8.1.0, 28=9, 29=10, 30=11, 31=12): 30
       Target SDK Version (26=8.0.0, 27=8.1.0, 28=9, 29=10, 30=11, 31=12): 32
        -> Package game data inside .apk? check
       
       -> Location of Android SDK
       C:/Users/006504390/AppData/Local/Android/Sdk
       -> Location of Android NDK
       C:/Users/006504390/AppData/Local/Android/Sdk/ndk/25.1.8937393
       -> Location of JAVA
       C:/Program Files/Java/jdk-17
       -> SDK API Level
       latest
       -> NDK API Level
       android-32


                              


