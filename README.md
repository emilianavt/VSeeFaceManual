## About

<a href="/assets/img/VSeeFaceScreenshot.png"><img src="/assets/img/VSeeFaceScreenshot500px.png" alt="VSeeFace screenshot"></a>

VSeeFace is a highly configurable face and hand tracking VRM avatar puppeteering program for virtual youtubers with a focus on robust tracking and high image quality. VSeeFace runs on Windows 8 and above (64 bit only). It probably runs on Windows 7 too.

Face tracking, including gaze and mouth tracking, is done through a regular webcam. For hand tracking, a Leap Motion device is required. You can see a comparison of the face tracking performance compared to other popular vtuber applications [here](https://twitter.com/emiliana_vt/status/1275424412167221248). In this comparison, VSeeFace is still listed under its former name OpenSeeFaceDemo.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Running four face tracking programs (OpenSeeFaceDemo, Luppet, Wakaru, Hitogata) at once with the same camera input. 😊 <a href="https://t.co/ioO2pofpMx">pic.twitter.com/ioO2pofpMx</a></p>&mdash; Emiliana (@emiliana_vt) <a href="https://twitter.com/emiliana_vt/status/1275424412167221248?ref_src=twsrc%5Etfw">June 23, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

If you have any questions or suggestions, please contact me, @[Emiliana_vt](https://twitter.com/emiliana_vt)!

## Download

**The only legitimate and correct way to download VSeeFace is as described below. OpenSeeFace is not VSeeFace. VSeeFace does not cost money.**

VSeeFace is currently in open beta and can be found for download in the latest pinned message of the `#tech-dev` channel of @[Virtual_Deat](https://twitter.com/Virtual_Deat)'s [discord server](https://discord.gg/BjBgk7k). The latest release notes can be found [here](https://gist.github.com/emilianavt/90bc0b73e2713276e6f630db09977eae). I post news about new versions and the development process in Twitter with the `#VSeeFace` hashtag.

The reason it is currently only released in this way, is to make sure that everybody who tries it out has an easy channel to give me feedback.

## Terms of use

You can use VSeeFace to stream or do pretty much anything you like. Please just do not give anybody a copy directly or pass the download link around. It's still very much in development, so I want every user to be able to find updates and give feedback easily. If somebody is interested, you can just point them to this page.

## Manual

This section is still a work in progress. For help with common issues, please refer to the [troubleshooting](#troubleshooting) section.

The most important information can be found by reading through the help screen as well as the usage notes inside the program.

### Virtual camera

The virtual camera can be used to use VSeeFace for teleconferences, Discord calls and similar. It can also be used in situations where using a game capture is not possible or very slow, due to specific laptop hardware setups.

To use the virtual camera, you have to enable it in the `General settings`. For performance reasons, it is disabled again after closing the program. Please note that the video camera will only output a picture while the UI of VSeeFace is hidden using the small ※ button in the lower right corner.

When using it for the first time, you first have to install the camera driver by clicking the installation button in the virtual camera section of the `General settings`. This should open an UAC prompt asking for permission to make changes to your computer, which is required to set up the virtual camera. If no such prompt appears and the installation fails, starting VSeeFace with administrator permissions may fix this, but it is not generally recommended. After a successful installation, the button will change to an uninstall button that allows you to remove the virtual camera from your system.

After installation, it should appear as a regular webcam. The virtual camera only supports the resolution 1280x720. Changing the window size will most likely lead to undesirable results, so it is recommended that the `Allow window resizing` option be disabled while using the virtual camera.

The virtual camera supports loading background images, which can be useful for vtuber collabs over discord calls, by setting a unicolored background.

If supported by the capture program, the virtual camera can be used to output video with alpha transparency. To make use if this a fully transparent PNG needs to be loaded as the background. Starting with version 1.13.25, such an image can be found in `VSeeFace_Data\StreamingAssets`. Partially transparent backgrounds are supported as well. Please note that using (partially) transparent background images with a capture program, which does not support RGBA webcams can lead to color errors. OBS and Streamlabs OBS support ARGB video camera capture, but require some additional setup. Apparently, the Twitch video capturing app supports it by default.

To setup OBS or Streamlabs OBS to capture video from the virtual camera with transparency, please follow [these](assets/img/ARGBCamera.png) settings. The important settings are:

* Resolution/FPS: Custom
* Resolution: 1280x720
* Video Format: ARGB

Should you encounter strange issues with with the virtual camera and have previously used it with a version of VSeeFace earlier than 1.13.22, please try uninstalling it using the `UninstallAll.bat`, which can be found in `VSeeFace_Data\StreamingAssets\UnityCapture`.

### Troubleshooting

This section lists common issues and possible solutions for them.

#### Startup issues

If an error appears after pressing the `Start` button, please confirm that the VSeeFace folder is correctly unpacked. Previous causes have included:

* A full disk caused the unpacking process to file, so files were missing from the VSeeFace folder. Solution: Free up additional space, delete the VSeeFace folder and unpack it again.
* A corrupted download caused missing files. Solution: Download the archive again, delete the VSeeFace folder and unpack a fresh copy of VSeeFace.
* An anti virus software has deleted `VSeeFace_Data\StreamingAssets\Binary\facetracker.exe`, which is necessary for the correct operation of VSeeFace. Please confirm that this file exists and, if not, check whether it has been removed by anti virus software.

If no window with a graphical user interface appears, please confirm that you have downloaded VSeeFace and not OpenSeeFace, which is just a backend library.

#### Webcam issues

Currently, certain cameras cause issues with VSeeFace. In many cases, where the camera seemingly simply doesn't switch on, this can be fixed by ticking the `Try this if your webcam won't turn on` box in the `General settings`.

If, after ticking this box an error message appears, it may be necessary to restart the program an enter a different camera resolution and/or frame rate that is known to be supported by the camera.

Should the tracking still not work, one possible workaround is to capture the actual webcam using OBS and then re-export it as a camera using OBS-VirtualCam.

#### Game capture in OBS is slow or not working

This is usually caused by laptops where OBS runs on the integrated graphics chip, while VSeeFace runs on a separate discrete one. Enabling the `SLI/Crossfire Capture Mode` option may enable it to work, but is usually slow. Further information can be found [here](https://obsproject.com/forum/threads/laptop-black-screen-when-capturing-read-here-first.5965/).

Another workaround is to use the [virtual camera](#virtual-camera) with a fully transparent background image and an ARGB video capture source, as described above.

#### Settings and log file location

The VSeeFace settings are not stored within the VSeeFace folder, so you can easily delete it or overwrite it when a new version comes around. If you wish to access the settings file or any of the log files produced by VSeeFace, you can find them as follows:

* Copy the following location to your clipboard (Ctrl + C): `%APPDATA%\..\LocalLow\Emiliana_vt\VSeeFace`
* Open an Explorer window (Windows key + E)
* Press Ctrl + L or click into the location bar, so you can paste the directory name from your clipboard
* Paste it, using Ctrl + V and press enter

The settings file is called `settings.ini`. If you performed a factory reset, the settings before the last factory reset can be found in a file called `settings.factoryreset`. There are also some other files in this directory:

* `avatarList.ini`: Starting with VSeeFace 1.13.25, this file contains the list of VRM files listed in the avatar switcher.
* `error.txt`: This contains error output from the `facetracker.exe` background process.
* `output.txt`: This contains additional output from the `facetracker.exe` background process.
* `Player.log`: This contains the Unity player log of VSeeFace.
* `Player-prev.log`: This contains the Unity player log of VSeeFace from the previous run.
