## About

<a href="/assets/img/VSeeFaceScreenshot.png"><img src="/assets/img/VSeeFaceScreenshot500px.png" alt="VSeeFace screenshot"></a>

VSeeFace is a highly configurable face and hand tracking VRM avatar puppeteering program for virtual youtubers with a focus on robust tracking and high image quality. VSeeFace offers functionality similar to Luppet, 3tene, Wakaru and similar programs. VSeeFace runs on Windows 8 and above (64 bit only). It probably runs on Windows 7 too.

Face tracking, including gaze and mouth tracking, is done through a regular webcam. For hand tracking, a Leap Motion device is required. You can see a comparison of the face tracking performance compared to other popular vtuber applications [here](https://twitter.com/emiliana_vt/status/1275424412167221248). In this comparison, VSeeFace is still listed under its former name OpenSeeFaceDemo.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Running four face tracking programs (OpenSeeFaceDemo, Luppet, Wakaru, Hitogata) at once with the same camera input. 😊 <a href="https://t.co/ioO2pofpMx">pic.twitter.com/ioO2pofpMx</a></p>&mdash; Emiliana (@emiliana_vt) <a href="https://twitter.com/emiliana_vt/status/1275424412167221248?ref_src=twsrc%5Etfw">June 23, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

If you have any questions or suggestions, please contact me, @[Emiliana_vt](https://twitter.com/emiliana_vt)!

## Download

**The only legitimate and correct way to download VSeeFace is as described below. OpenSeeFace is not VSeeFace. VSeeFace does not cost money.**

VSeeFace is currently in open beta and can be found for download in the latest pinned message of the `#tech-dev` channel of @[Virtual_Deat](https://twitter.com/Virtual_Deat)'s [discord server](https://discord.gg/BjBgk7k). The latest release notes can be found [here](https://gist.github.com/emilianavt/90bc0b73e2713276e6f630db09977eae). I post news about new versions and the development process in Twitter with the `#VSeeFace` hashtag.

The reason it is currently only released in this way, is to make sure that everybody who tries it out has an easy channel to give me feedback.

## Terms of use

You can use VSeeFace to stream or do pretty much anything you like. Please just do not give anybody a copy directly or pass the download link around. It's still very much in development, so I want every user to be able to find updates and give feedback easily. If somebody is interested, you can just point them to this page.

## Credits

VSeeFace is being created by @[Emiliana_vt](https://twitter.com/emiliana_vt) and @[Virtual_Deat](https://twitter.com/VirtualDeat).

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

### Network tracking

It is possible to perform the face tracking on a separate PC. This can, for example, help reduce CPU load. This process is a bit advanced and requires some general knowledge about the use of commandline programs and batch files. To do this, copy either the whole VSeeFace folder or the `VSeeFace_Data\StreamingAssets\Binary\` folder to the second PC, which should have the camera attached. Inside this folder is a file called `run.bat`. Running this file will open first ask for some information to set up the camera and then run the tracker process that is usually run in the background of VSeeFace. If you entered the correct information, it will show an image of the camera feed with overlaid tracking points, so do not run it while streaming your desktop. This can also be useful to figure out issues with the camera or tracking in general. The tracker can be stopped with the `q`, while the image display window is active.

In the following, the PC running VSeeFace will be called PC A, and the PC running the face tracker will be called PC B.

To use it for network tracking, edit the `run.bat` file or create a new batch file with the following content:

    %ECHO OFF
    
    facetracker -l 1
    
    
    set /p cameraNum=Select your camera from the list above and enter the corresponding number:
    set /p width=Select the width:
    set /p height=Select the height:
    set /p fps=Select the FPS:
    set /p ip=Enter the LAN IP of the PC running VSeeFace:
    
    facetracker -c %cameraNum% -W %width% -H %height% -F %fps% -v 3 -P 1 -i %ip% --discard-after 0 --scan-every 0 --no-3d-adapt 1 --max-feature-updates 900
    
    pause

If the webcam is not detected or does not work, on both `facetracker` lines add `--use-escapi 0` at the end. If you would like to disable the webcam image display, you can change `-v 3` to `-v 0`.

When starting this modified file, in addition to the camera information, you will also have to enter the local network IP address of the PC A. You can start and stop the tracker process on PC B and VSeeFace on PC A independently. When no tracker process is running, the avatar in VSeeFace will simply not move.

On the VSeeFace side, select `[Network tracking]` in the camera dropdown menu of the starting screen. Also, enter this PC's (PC A) local network IP address in the `Listen IP` field. Do **not** enter the IP address of PC B or it will not work. Press the start button. PC A should now be able to receive tracking data from PC B, while the tracker is running on PC B.

If you are sure that the camera number will not change and know a bit about batch files, you can also modify the batch file to remove the interactive input and just hard code the values.

#### Troubleshooting

If things don't work as expected, check the following things:

* Starting `run.bat` should open a window with black background and grey text. Make sure you entered the necessary information and pressed enter.
* While running, many lines showing something like `Took 20ms` at the beginning should appear. While a face is in the view of the camera, lines with `Confidence` should appear too. A second window should show the camera view and red and yellow tracking points overlaid on the face. If this is not the case, something is wrong on this side of the process.
* If the face tracker is running correctly, but the avatar does not move, confirm that the Windows firewall is not blocking the connection and that on both sides the IP address of PC A (the PC running VSeeFace) was entered.

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

If tracking randomly stops and you are using Streamlabs OBS, you could see if it works properly with regular OBS. Another issue could be that Windows is putting the webcam's USB port to sleep. You can disable this behaviour as follow:

1. Open the Windows `Control Panel`
2. Press Ctrl+F, search for `Device Manager` and open it
3. Click the `+` at `Universal Serial Bus Controllers`
4. Right click `USB Root Hub` and select `Properties`
5. Open the `Power Management` tab
6. Clear the checkmark from `Allow the computer to turn off this device to save power` and click OK
7. Repeat this procedure for the USB 2.0 Hub and any other USB Hub devices

Alternatively or in addition, you can try the following approach:

1. Open the Windows `Control Panel`
2. Press Ctrl+F, search for `Power Options` and open them
3. Click on `Change plan settings` for your currently selected plan
4. Click on `Change advcanced power settings`
5. In the window that opens, click the `+` in front of `USB settings`
6. Click the `+` in front of `USB selective suspend setting`
7. Change the setting to `Disabled` and click OK

Please note that this is not a guaranteed fix by far, but it might help. If you are using a laptop where battery life is important, I recommend only following the second set of steps and setting them up for a power plan that is only active while the laptop is charging.

#### Lipsync issues

If you change your audio output device in Windows, the lipsync function may stop working. If this happens, it should be possible to get it working again by changing the selected microphone in the `General settings` or toggling the lipsync option off and on.

Lipsync and mouth animation relies on the model having VRM blendshape clips for the A, I, U, E, O mouth shapes. Jaw bones are not supported and known to cause trouble during VRM export, so it is recommended to unassign them from Unity's humanoid avatar configuration if present.

If a stereo audio device is used for recording, please make sure that the voice data is on the left channel. If the voice is only on the right channel, it will not be detected. In this case, software like [Equalizer APO](https://sourceforge.net/projects/equalizerapo/) or [Voicemeeter](https://www.vb-audio.com/Voicemeeter/potato.htm) can be used to respectively either copy the right channel to the left channel or provide a mono device that can be used as a mic in VSeeFace. In my experience Equalizer APO can work with less delay and is more stable, but harder to set up.

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

### Performance tuning

Here are some suggestions on how you can improve the performance of VSeeFace.

#### CPU

CPU usage is mainly caused by the separate face tracking process `facetracker.exe` that runs alongside VSeeFace.

There are two ways to reduce the amount of CPU used by the tracker. The first and recommended way is to reduce the webcam frame rate on the starting screen of VSeeFace. VSeeFace interpolates between tracking frames, so even low frame rates like 15 or 10 frames per second might look acceptable. The webcam resolution has almost no impact on CPU usage.

The second way is to use a lower quality tracking model. The tracking models can also be selected on the starting screen of VSeeFace. Here is a list of the different models:

* `High quality`: The default model with the best tracking and highest CPU utilization.
* `Medium quality`: Slightly faster and slightly worse tracking quality.
* `Barely okay quality`: Noticably faster than the first two models, but also noticably worse tracking. The worse tracking mainly results in worse eye blink and eyebrow tracking, as well as highly reduced expression detection performance. I recommend using auto blinking with this and the `Low quality` model.
* `Low quality`: Slightly faster and noticably worse tracking quality.

##### Models with many meshes

Certain models with a high number of meshes in them can cause significant slowdown. Starting with 1.23.25c, there is an option in the `Advanced` section of the `General settings` called `Disable updates`. By turning on this option, this slowdown can be mostly prevented. However, while this option is enabled, parts of the avatar may disappear when looked at from certain angles. Only enable it when necessary.

In some cases it has been found that enabling this option and disabling again mostly eliminates the slowdown as well, so give that a try if you encounter this issue. This should prevent any issues with disappearing avatar parts. However, in this case, enabling and disabling the checkbox has to be done each time after loading the model.

#### GPU

GPU usage is mainly dictated by frame rate and anti-aliasing. These options can be found in the `General settings`.

Most of the anti-aliasing options should not be too heavy, but the `Really nice` option causes very heavy CPU load.

If VSeeFace causes too much load on the CPU, you can also try reducing the frame rate by changing the frame rate cap from 60 to something lower like 30 or 24.