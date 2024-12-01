## Hand tracking with Unreal Engine 5.4 and Quest 3, 2.




Video sources used: 
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
https://www.youtube.com/watch?v=NfI_WlKFUak&ab_channel=UnrealEngineVR
 
                              


