## About

<a href="/assets/img/VSeeFaceScreenshot.png"><img src="/assets/img/VSeeFaceScreenshot500px.png" alt="VSeeFace screenshot"></a>

<a href="#japanese-info">日本語</a>

VSeeFace is a free, highly configurable face and hand tracking VRM avatar puppeteering program for virtual youtubers with a focus on robust tracking and high image quality. VSeeFace offers functionality similar to Luppet, 3tene, Wakaru and similar programs. VSeeFace runs on Windows 8 and above (64 bit only). It probably runs on Windows 7 too.

Face tracking, including eye gaze, blink, eyebrow and mouth tracking, is done through a regular webcam. For the optional hand tracking, a Leap Motion device is required. You can see a comparison of the face tracking performance compared to other popular vtuber applications [here](https://twitter.com/emiliana_vt/status/1275424412167221248). In this comparison, VSeeFace is still listed under its former name OpenSeeFaceDemo.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Running four face tracking programs (OpenSeeFaceDemo, Luppet, Wakaru, Hitogata) at once with the same camera input. 😊 <a href="https://t.co/ioO2pofpMx">pic.twitter.com/ioO2pofpMx</a></p>&mdash; Emiliana (@emiliana_vt) <a href="https://twitter.com/emiliana_vt/status/1275424412167221248?ref_src=twsrc%5Etfw">June 23, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

If you have any questions or suggestions, please contact me, @[Emiliana_vt](https://twitter.com/emiliana_vt)!

## Download

**To update VSeeFace, just delete the old folder or overwrite it when unpacking the new version.**

<a href="https://github.com/emilianavt/VSeeFaceReleases/releases/download/v1.13.34b/VSeeFace-v1.13.34b.zip" class="download">Download<br>v1.13.34b</a>

Old versions can be found in the release archive [here](https://github.com/emilianavt/VSeeFaceReleases/releases/). This website, the #vseeface-updates channel on Deat's discord and the release archive are the only official download locations for VSeeFace.

If you have any issues, questions or feedback, please come to the `#vseeface` channel of @[Virtual_Deat](https://twitter.com/Virtual_Deat)'s [discord server](https://discord.gg/BjBgk7k). I post news about new versions and the development process in Twitter with the `#VSeeFace` hashtag. Feel free to also use this hashtag for anything VSeeFace related. Starting with 1.13.26, VSeeFace will also check for updates and display a green message in the upper left corner when a new version is available, so please make sure to update if you are still on an older version.

The latest release notes can be found <a href="https://gist.github.com/emilianavt/90bc0b73e2713276e6f630db09977eae">here</a>.

The reason it is currently only released in this way, is to make sure that everybody who tries it out has an easy channel to give me feedback.

<span lang="ja" id="japanese-info">VSeeFaceはVTuber向けのフェーストラッキングソフトです。Webカメラで簡単にVRMアバターを動かすことができます。Leap Motionによる手と指のトラッキング機能もあります。ダウンロードは<a href="https://github.com/emilianavt/VSeeFaceReleases/releases/download/v1.13.34b/VSeeFace-v1.13.34b.zip">こちら</a>。リリースノートは<a href="https://gist.github.com/emilianavt/90bc0b73e2713276e6f630db09977eae">こちら</a>。まだベータ版です。</span>

<span lang="ja">@[Virtual_Deat](https://twitter.com/Virtual_Deat)さんの[ディスコードサーバー](https://discord.gg/BjBgk7k)に入るとルールズチャンネルで👌にクリックでルールを同意して他のチャンネルも表示されます。#vseefaceと日本語チャンネルもあります。</span>

<span lang="ja">VSeeFaceはカラーキーで録画が出来ないけどOBSのGame CaptureでAllow transparencyをチェックしてVSeeFaceで右下の※ボタンでUIを見えないにすれば綺麗な透明の背景になります。</span>

<span lang="ja">UIはほとんど英語のままですが`VSeeFace_Data\StreamingAssets\Strings.json`で翻訳が出来ます。</span>

<span lang="ja">ライセンス：基本的にご自由に使用可（個人用可も商用利用可も）</span>

## Terms of use

You can use VSeeFace to stream or do pretty much anything you like. Just don't modify it (other than Strings.json) or claim you made it.

VSeeFace is beta software. There may be bugs and new versions may change things around. It is offered without any kind of warrenty, so use it at your own risk. It should generally work fine, but it may be a good idea to keep the previous version around when updating.

## Credits

VSeeFace is being created by @[Emiliana_vt](https://twitter.com/emiliana_vt) and @[Virtual_Deat](https://twitter.com/Virtual_Deat).

## Manual

This section is still a work in progress. For help with common issues, please refer to the [troubleshooting](#troubleshooting) section.

The most important information can be found by reading through the help screen as well as the usage notes inside the program.

### FAQ

#### How can I move my character?

You can rotate, zoom and move the camera by holding the Alt key and using the different mouse buttons. The exact controls are given on the help screen.

Once you've found a camera position you like and would like for it to be the initial camera position, you can set the default camera setting in the `General settings` to `Custom`. You can now move the camera into the desired position and press `Save` next to it, to save a custom camera position. Please note that these custom camera positions to not adapt to avatar size, while the regular default positions do.

#### How do I do chroma keying with a gray background?

VSeeFace does not support chroma keying. Instead, capture it in OBS using a game capture and enable the `Allow transparency` option on it. Once you press the tiny ※ button in the lower right corner, the UI will become hidden and the background will turn transparent in OBS. You can hide and show the ※ button using the space key.

#### What's the best way to set up a collab then?

You can set up the virtual camera function, load a background image and do a Discord (or similar) call using the virtual VSeeFace camera.

#### Can I get rid of the ※ button in the corner somehow? It shows on OBS.

You can hide and show the ※ button using the space key.

#### Sometimes blue bars appear at the edge of the screen, what's up with that and how do I get rid of them?

Those bars are there to let you know that you are close to the edge of your webcam's field of view and should stop moving that way, so you don't lose tracking due to being out of sight. If you have set the UI to be hidden using the ※ button in the lower right corner, blue bars will still appear, but they will be invisible in OBS as long as you are using a `Game Capture` with `Allow transparency` enabled.

#### How do I adjust the Leap Motion's position? My arms are stiff and stretched out?

First, hold the alt key and right click to zoom out until you can see the Leap Motion model in the scene. Then use the sliders to adjust the model's position to match its location relative to yourself in the real world. You can refer to [this](https://twitter.com/emiliana_vt/status/1313431152045293568) video to see how the sliders work.

#### I moved my Leap Motion from the desk to a neck holder, changed the position to chest and now my arms are in the sky?

Changing the position also changes the height of the Leap Motion in VSeeFace, so just pull the Leap Motion position's height slider way down. Zooming out may also help.

#### My Leap Motion complains that I need to update its software, but I'm already on the newest version of V2?

To fix this error, please install the [V4 (Orion) SDK](https://developer.leapmotion.com/setup/desktop). It says it's used for VR, but it is also used by desktop applications.

#### Do hotkeys work even while VSeeFace is in the background?

All configurable hotkeys also work while it is in the background or minimized, so the expression hotkeys, the audio lipsync toggle hotkey and the configurable position reset hotkey all work from any other program as well. On some systems it might be necessary to run VSeeFace as admin to get this to work properly for some reason.

#### I get an error when starting the tracking with DroidCam (or some other camera)?

Try switching the camera settings from `Camera defaults` to something else. The camera might be using an unsupported video format by default.

#### Where can I find avatars I can use?

Many people make their own using [VRoid Studio](https://vroid.com/en/studio/) or commission someone. [Vita](Vita.vrm) is one of the included sample characters. You can also find VRM models on [VRoid Hub](https://hub.vroid.com/en/) and [Niconi Solid](https://3d.nicovideo.jp/search?work_type=vrm), just make sure to follow the terms of use.

#### I have a model in a different format, how do I convert it to VRM?

Follow the [official guide](https://vrm.dev/en/how_to_make_vrm/). The important thing to note is that it is a two step process. First, you export a base VRM file, which you then import back into Unity to configure things like blend shape clips. After that, you export the final VRM. If you look around, there are probably other resources out there too.

#### My model's arms/hair/whatever looks weirdly twisted?

This is most likely caused by not properly normalizing the model during the first [VRM conversion](https://vrm.dev/en/how_to_make_vrm/). To properly normalize the avatar during the first VRM export, make sure that `Pose Freeze` and `Force T Pose` is ticked on the `ExportSettings` tab of the VRM export dialog. I also recommend making sure that no jaw bone is set in [Unity's humanoid avatar configuration](https://docs.unity3d.com/560/Documentation/Manual/ConfiguringtheAvatar.html) before the first export, since often a hair bone gets assigned by Unity as a jaw bone by mistake. If a jaw bone is set in the head section, click on it and unset it using the backspace key on your keyboard. If your model does have a jaw bone that you want to use, make sure it is correctly assigned instead.

Note that re-exporting a VRM will not work to for properly normalizing the model. Instead the original model (usually FBX) has to be exported with the correct options set.

#### How can I get my eyebrows to work on a custom model?

You can add two custom VRM blend shape clips called "Brows up" and "Brows down" and they will be used for the eyebrow tracking. You can also add them on VRoid and Cecil Henshin models to customize how the eyebrow tracking looks. Also refer to the [special blendshapes](#special-blendshapes) section.

#### Where does VSeeFace put screenshots?

The screenshots are saved to a folder called `VSeeFace` inside your `Pictures` folder.

#### I converted my model to VRM format, but the mouth doesn't move and the eyes don't blink?

VRM conversion is a two step process. After the first export, you have to put the VRM file back into your Unity project to actually set up the VRM blend shape clips and other things. You can follow the [guide](https://vrm.dev/en/how_to_make_vrm/) on the VRM website, which is very detailed with many screenshots.

#### Why does Windows give me a warning that the publisher is unknown?

Because I don't want to pay a high yearly fee for a code signing certificate.

#### How do I install a zip file?

Right click it, select `Extract All...` and press next. You should have a new folder called VSeeFace. Inside there should be a file called `VSeeFace` with a blue icon, like the logo on this site. Double click on that to run VSeeFace. There's a video [here](Install.mp4).

If Windows 10 won't run the file and complains that the file may be a threat because it is not signed, you can try the following: Right click it -> Properties -> Unblock -> Apply or select exe file -> Select More Info -> Run Anyways

#### Is VSeeFace open source? I heard it was open source.

No. It uses paid assets from the Unity asset store that cannot be freely redistributed. However, the actual face tracking and avatar animation code is open source. You can find it [here](https://github.com/emilianavt/OpenSeeFace) and [here](https://gist.github.com/emilianavt/b211073096a4484fb92e6550212c2f48).

### Virtual camera

The virtual camera can be used to use VSeeFace for teleconferences, Discord calls and similar. It can also be used in situations where using a game capture is not possible or very slow, due to specific laptop hardware setups.

To use the virtual camera, you have to enable it in the `General settings`. For performance reasons, it is disabled again after closing the program. Starting with version 1.13.27, the virtual camera will always provide a clean (no UI) image, even while the UI of VSeeFace is not hidden using the small ※ button in the lower right corner.

When using it for the first time, you first have to install the camera driver by clicking the installation button in the virtual camera section of the `General settings`. This should open an UAC prompt asking for permission to make changes to your computer, which is required to set up the virtual camera. If no such prompt appears and the installation fails, starting VSeeFace with administrator permissions may fix this, but it is not generally recommended. After a successful installation, the button will change to an uninstall button that allows you to remove the virtual camera from your system.

After installation, it should appear as a regular webcam. The virtual camera only supports the resolution 1280x720. Changing the window size will most likely lead to undesirable results, so it is recommended that the `Allow window resizing` option be disabled while using the virtual camera.

The virtual camera supports loading background images, which can be useful for vtuber collabs over discord calls, by setting a unicolored background.

Should you encounter strange issues with with the virtual camera and have previously used it with a version of VSeeFace earlier than 1.13.22, please try uninstalling it using the `UninstallAll.bat`, which can be found in `VSeeFace_Data\StreamingAssets\UnityCapture`. If the camera outputs a strange green/yellow pattern, please do this as well.

#### Transparent virtual camera

If supported by the capture program, the virtual camera can be used to output video with alpha transparency. To make use of this, a fully transparent PNG needs to be loaded as the background image. Starting with version 1.13.25, such an image can be found in `VSeeFace_Data\StreamingAssets`. Partially transparent backgrounds are supported as well. Please note that using (partially) transparent background images with a capture program that do not support RGBA webcams can lead to color errors. OBS and Streamlabs OBS support ARGB video camera capture, but require some additional setup. Apparently, the Twitch video capturing app supports it by default.

To setup OBS or Streamlabs OBS to capture video from the virtual camera with transparency, please follow [these](assets/img/ARGBCamera.png) settings. The important settings are:

* Resolution/FPS: Custom
* Resolution: 1280x720
* Video Format: ARGB

As the virtual camera keeps running even while the UI is shown, using it instead of a game capture can be useful if you often make changes to settings during a stream.

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

### Special blendshapes

VSeeFace has special support for certain custom VRM blend shape clips:

* `Surprised` is supported by the simple and experimental expression detection features.
* `Brows up` and `Brows down` will be used for eyebrow tracking if present on a model.
* Starting with v1.13.34, if all of the following custom VRM blend shape clips are present on a model, they will be used for audio based lip sync in addition to the regular `A`, `I`, `U`, `E` and `O` blend shapes: `SIL`, `CH`, `DD`, `FF`, `KK`, `NN`, `PP`, `RR`, `SS`, `TH`
    You can refer to [this](https://developer.oculus.com/documentation/unity/audio-ovrlipsync-viseme-reference/) reference for how the mouth should look for each of these visemes. The existing VRM blend shape clips `A`, `I`, `U`, `E` and `O` are mapped to `aa`, `ih`, `ou`, `E` and `oh` respectively.
    I do not recommend using the Blender CATS plugin to automatically generate shapekeys for these blendshapes, because VSeeFace will already follow a similar approach in mixing the `A`, `I`, `U`, `E` and `O` shapes by itself, so setting up custom VRM blend shape clips would be unnecessary effort. In this case it is better to have only the standard `A`, `I`, `U`, `E` and `O` VRM blend shape clips on the model.

### Expression detection

You can set up VSeeFace to recognize your facial expressions and automatically trigger VRM blendshape clips in response. There are two different modes that can be selected in the `General settings`.

#### Simple expression detection

This mode is easy to use, but it is limited to the `Fun`, `Angry` and `Surprised` expressions. Simply enable it and it should work. There are two sliders at the bottom of the `General settings` that can be used to adjust how it works.

To trigger the `Fun` expression, smile, moving the corners of your mouth upwards. To trigger the `Angry` expression, do not smile and move your eyebrows down. To trigger the `Surprised` expression, move your eyebrows up.

#### Experimental expression detection

This mode supports the `Fun`, `Angry`, `Joy`, `Sorrow` and `Surprised` VRM expressions. To use it, you first have to teach the program how your face will look for each expression, which can be tricky and take a bit of time. What kind of face you make for each of them is completely up to you, but it's usually a good idea to enable the tracking point display in the `General settings`, so you can see how well the tracking can recognize the face you are making. The following [video](https://www.youtube.com/watch?v=-Y2JyGLxuyo) will explain the process:

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/-Y2JyGLxuyo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

When the `Calibrate` button is pressed, most of the recorded data is used to train a detection system. The rest of the data will be used to verify the accuracy. This will result in a number between 0 (everything was misdetected) and 1 (everything was detected correctly) and is displayed above the calibration button. A good rule of thumb is to aim for a value between 0.95 and 0.98. While this might be unexpected, a value of 1 or very close to 1 is not actually a good thing and usually indicates that you need to record more data. A value significantly below 0.95 indicates that, most likely, some mixup occurred during recording (e.g. your sorrow expression was recorded for your surprised expression). If this happens, either reload your last saved calibration or restart from the beginning.

It is also possible to set up only a few of the possible expressions. This usually improves detection accuracy. However, make sure to always set up the `Neutral` expression. This expression should contain any kind of expression that should not as one of the other expressions. To remove an already set up expression, press the corresponding `Clear` button and then `Calibrate`.

Having an expression detection setup loaded can increase the startup time of VSeeFace even if expression detection is disabled or set to simple mode. To avoid this, press the `Clear calibration` button, which will clear out all calibration data and preventing it from being loaded at startup. You can always load your detection setup again using the `Load calibration` button.

### Model preview in Unity

If you are working on an avatar, it can be useful to get an accurate idea of how it will look in VSeeFace before exporting the VRM. You can load [this](https://github.com/emilianavt/VSeeFacePreview/archive/v1.13.34b.zip) example project into Unity 2019.4.12f1 and load the included preview scene to preview your model with VSeeFace like lighting settings. This project also allows posing an avatar and sending the pose to VSeeFace using the VMC protocol starting with VSeeFace v1.13.34b.

After loading the project in Unity, load the provided scene inside the Scenes folder. If you press play, it should show some instructions on how to use it.

If you prefer settings things up yourself, the following settings in Unity should allow you to get an accurate idea of how the avatar will look with default settings in VSeeFace:

* ([Screenshot](/assets/img/LightingLinear.png)) `Edit -> Project Settings... -> Player -> Other Settings -> Color Space: Linear`
* ([Screenshot](/assets/img/LightingLight.png)) Directional light: Color: FFFFFF (Hexadecimal), Intensity: 0.975, Rotation: 16, -146, -7.8, Shadow Type: No shadows
* ([Screenshot](/assets/img/LightingSceneCamera.png)) Camera icon next to Gizmos: Field of View: 16.1 (default focal length of 85mm) or 10.2 (135mm)
* ([Screenshot](/assets/img/LightingCamera.png)) Optional, Main Camera: Clear Flags: Solid Color, Background: 808080 (Hexadecimal), Field of View: as above
* ([Screenshot](/assets/img/LightingQuality.png)) `Edit -> Project Settings... -> Quality`, select `Ultra` and set the anti-aliasing to 8x

If you enabled shadows in the VSeeFace light settings, set the shadow type on the directional light to soft.

To see the model with better light and shadow quality, use the `Game` view. You can align the camera with the current scene view by pressing `Ctrl+Shift+F` or using `Game Object -> Align with view` from the menu.

### Translations

It is possible to translate VSeeFace into different languages and I am happy to add contributed translations! To add a new language, first make a new entry in `VSeeFace_Data\StreamingAssets\Strings\Languages.json` with a new language code and the name of the language in that language. The language code should usually be given in two lowercase letters, but can be longer in special cases. For a partial reference of language codes, you can refer to [this list](https://github.com/nohamelin/simple-locale-switcher/wiki/Language-Names-for-Locale-Codes). Afterwards, make a copy of `VSeeFace_Data\StreamingAssets\Strings\en.json` and rename it to match the language code of the new language. Now you can edit this new file and translate the `"text"` parts of each entry into your language. The `"comment"` might help you find where the text is used, so you can more easily understand the context, but it otherwise doesn't matter.

New languages should automatically appear in the language selection menu in VSeeFace, so you can check how your translation looks inside the program. Note that a JSON syntax error might lead to your whole file not loading correctly. In this case, you may be able to find the position of the error, by looking into the `Player.log`, which can be found by using the button all the way at the bottom of the general settings.

Generally, your translation has to be enclosed by doublequotes `"like this"`. If double quotes occur in your text, put a \ in front, for example `"like \"this\""`. Line breaks can be written as `\n`.

### Running on Linux and maybe Mac

Some people have gotten VSeeFace to run on Linux through wine and it might be possible on Mac as well, but nobody tried, to my knowledge. However, reading webcams is not possible through wine. As a workaround, you can set the camera in VSeeFace to `[Network tracking]` and run the `facetracker.py` script from [OpenSeeFace](https://github.com/emilianavt/OpenSeeFace) manually. To do this, you will need a Python 3.7 or newer installation. To set up everything for the `facetracker.py`, you can try something like this on Debian based distributions:

    sudo apt-get install python3 python3-pip python3-virtualenv git
    git clone https://github.com/emilianavt/OpenSeeFace
    cd OpenSeeFace
    virtualenv -p python3 env
    source env/bin/activate
    pip3 install onnxruntime opencv-python pillow numpy

To run the tracker, first enter the `OpenSeeFace` directory and activate the virtual environment for the current session:

    source env/bin/activate

Then you can run the tracker:

    python facetracker.py -c 0 -W 1280 -H 720 --discard-after 0 --scan-every 0 --no-3d-adapt 1 --max-feature-updates 900

Running this command, will send the tracking data to a UDP port on localhost, on which VSeeFace will listen to receive the tracking data. The `-c` argument specifies which camera should be used, with the first being `0`, while `-W` and `-H` let you specify the resolution. To see the webcam image with tracking points overlaid on your face, you can add the arguments `-v 3 -P 1` somewhere.

Notes on running wine: First make sure you have the Arial font installed. You can put `Arial.ttf` in your wine prefix's `C:\Windows\Fonts` folder and it should work. Secondly, make sure you have the 64bit version of wine installed. It often comes in a package called `wine64`. Also make sure that you are using a 64bit wine prefix. After installing `wine64`, you can set one up using `WINEARCH=win64 WINEPREFIX=~/.wine64 wine whatever`, then unzip VSeeFace in `~/.wine64/drive_c/VSeeFace` and run it with `WINEARCH=win64 WINEPREFIX=~/.wine64 wine VSeeFace.exe`.

Starting with VSeeFace v1.13.33f, while running under wine `--background-color '#00FF00'` can be used to set a window background color. To disable wine mode and make things work like on Windows, `--disable-wine-mode` can be used.

### Troubleshooting

This section lists common issues and possible solutions for them.

#### Startup issues

If an error appears after pressing the `Start` button, please confirm that the VSeeFace folder is correctly unpacked. Previous causes have included:

* A full disk caused the unpacking process to file, so files were missing from the VSeeFace folder. Solution: Free up additional space, delete the VSeeFace folder and unpack it again.
* A corrupted download caused missing files. Solution: Download the archive again, delete the VSeeFace folder and unpack a fresh copy of VSeeFace.
* An anti virus software has deleted `VSeeFace_Data\StreamingAssets\Binary\facetracker.exe`, which is necessary for the correct operation of VSeeFace. Please confirm that this file exists and, if not, check whether it has been removed by anti virus software.

If no window with a graphical user interface appears, please confirm that you have downloaded VSeeFace and not OpenSeeFace, which is just a backend library.

#### Webcam and tracking issues

If tracking doesn't work, you can actually test what the camera sees by running the `run.bat` in the `VSeeFace_Data\StreamingAssets\Binary` folder. Before running it, make sure that no other program, including VSeeFace, is using the camera. After starting it, you will first see a list of cameras, each with a number in front of it. Enter the number of the camera you would like to check and press enter. Next, it will ask you to enter a horizontal and vertical resolution as well as a frame rate. You can enter the default values VSeeFace uses (1280, 720, 24 respectively). Press enter after entering each value. After this, a second window should open, showing the image captured by your camera. If your face is visible on the image, you should see red and yellow tracking dots marked on your face. You can use this to make sure your camera is working as expected, your room has enough light, there is no strong light from the background messing up the image and so on. If the tracking points accurately track your face, the tracking should work in VSeeFace as well. To close the window, either press `q` in the window showing the camera image or press Ctrl+C in the console window.

If you would like to see the camera image while your avatar is being animated, you can start VSeeFace while `run.bat` is running and select `[Network tracking]` in the camera option. It should receive the tracking data from the active `run.bat` process.

If an error message about the tracker process appears, it may be necessary to restart the program and, on the first screen of the program, enter a different camera resolution and/or frame rate that is known to be supported by the camera. To figure out a good combination, you can try adding your webcam as a video source in OBS and play with the parameters (resolution and frame rate) to find something that works.

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

#### Virtual camera issues

If, after installing it from the `General settings`, the virtual camera is still not listed as a webcam under the name `VSeeFaceCamera` in other programs or if it displays an odd green and yellow pattern while VSeeFace is not running, run the `UninstallAll.bat` inside the folder `VSeeFace_Data\StreamingAssets\UnityCapture` as administrator. Afterwards, run the `Install.bat` inside the same folder as administrator. After installing the virtual camera in this way, it may be necessary to restart other programs like Discord before they recognize the virtual camera.

If the virtual camera is listed, but only shows a black picture, make sure that VSeeFace is running and that the virtual camera is enabled in the `General settings`. It automatically disables itself when closing VSeeFace to reduce its performance impact, so it has to be manually re-enabled the next time it is used.

#### Lipsync issues

First, make sure you have your microphone selected on the starting screen. You can also change it in the `General settings`.

If you change your audio output device in Windows, the lipsync function may stop working. If this happens, it should be possible to get it working again by changing the selected microphone in the `General settings` or toggling the lipsync option off and on.

Lipsync and mouth animation relies on the model having VRM blendshape clips for the A, I, U, E, O mouth shapes. Jaw bones are not supported and known to cause trouble during VRM export, so it is recommended to unassign them from Unity's humanoid avatar configuration if present.

If a stereo audio device is used for recording, please make sure that the voice data is on the left channel. If the voice is only on the right channel, it will not be detected. In this case, software like [Equalizer APO](https://sourceforge.net/projects/equalizerapo/) or [Voicemeeter](https://www.vb-audio.com/Voicemeeter/potato.htm) can be used to respectively either copy the right channel to the left channel or provide a mono device that can be used as a mic in VSeeFace. In my experience Equalizer APO can work with less delay and is more stable, but harder to set up.

If no microphones are displayed in the list, please check the `Player.log` in the [log folder](#settings-and-log-file-location). Look for `FMOD` errors. They might list some information on how to fix the issue. [This](https://forum.unity.com/threads/fmod-failed-to-initialize.602845/) thread on the Unity forums might contain helpful information.

In one case, having a microphone with a 192kHz sample rate installed on the system could make lip sync fail, even when using a different microphone. In this case setting it to 48kHz allowed lip sync to work.

#### Game capture in OBS is slow or not working

This is usually caused by laptops where OBS runs on the integrated graphics chip, while VSeeFace runs on a separate discrete one. Enabling the `SLI/Crossfire Capture Mode` option may enable it to work, but is usually slow. Further information can be found [here](https://obsproject.com/forum/threads/laptop-black-screen-when-capturing-read-here-first.5965/).

In one case, Streamlabs OBS could only capture VSeeFace when both Streamlabs OBS and VSeeFace where running with admin privileges, which is very odd and should not usually happen, but if you can't get the game capture to work, you could give it a try.

Another workaround is to use the [virtual camera](#virtual-camera) with a fully transparent background image and an ARGB video capture source, as described above.

#### Settings and log file location

The VSeeFace settings are not stored within the VSeeFace folder, so you can easily delete it or overwrite it when a new version comes around. If you wish to access the settings file or any of the log files produced by VSeeFace, starting with version 1.13.32g, you can click the `Show log and settings folder` button at the bottom of the `General settings`. Otherwise, you can find them as follows:

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

This section contains some suggestions on how you can improve the performance of VSeeFace.

If VSeeFace becomes laggy while the window is in the background, you can try enabling the increased priority option from the `General settings`, but this can impact the responsiveness of other programs running at the same time.

#### CPU

CPU usage is mainly caused by the separate face tracking process `facetracker.exe` that runs alongside VSeeFace.

The first thing to try for performance tuning should be the `Recommend Settings` button on the starting screen, which will run a system benchmark to adjust tracking quality and webcam frame rate automatically to a level that balances CPU usage with quality. This usually provides a reasonable starting point that you can adjust further to your needs.

One way to slightly reduce the face tracking process's CPU usage is to turn on the synthetic gaze option in the `General settings` which will cause the tracking process to skip running the gaze tracking model starting with version 1.13.31.

There are two other ways to reduce the amount of CPU used by the tracker. The first and most recommended way is to reduce the webcam frame rate on the starting screen of VSeeFace. Tracking at a frame rate of 15 should still give acceptable results. VSeeFace interpolates between tracking frames, so even low frame rates like 15 or 10 frames per second might look acceptable. The webcam resolution has almost no impact on CPU usage.

The tracking rate is the TR value given in the lower right corner. Please note that the tracking rate may already be lower than the webcam framerate entered on the starting screen. This can be either caused by the webcam slowing down due to insufficient lighting or hardware limitations, or because the CPU cannot keep up with the face tracking. Lowering the webcam frame rate on the starting screen will only lower CPU usage if it is set below the current tracking rate.

The second way is to use a lower quality tracking model. The tracking models can also be selected on the starting screen of VSeeFace. Please note you might not see a change in CPU usage, even if you reduce the tracking quality, if the tracking still runs slower than the webcam's frame rate. For this reason, it is recommended to first reduce the frame rate until you can observe a reduction in CPU usage. At that point, you can reduce the tracking quality to further reduce CPU usage.

Here is a list of the different models:

* `High quality`: The default model with the best tracking and highest CPU utilization.
* `Medium quality`: Slightly faster and slightly worse tracking quality.
* `Barely okay quality`: Noticably faster than the first two models, but also noticably worse tracking. The worse tracking mainly results in worse eye blink and eyebrow tracking, as well as highly reduced expression detection performance. I recommend using auto blinking with this and the `Low quality` model.
* `Low quality`: Slightly faster and noticably worse tracking quality.
* `Toaster`: This model is specifically intended for old PCs and is much faster than all the others, but it also offers noticably lower tracking quality. Eye blink and gaze tracking as well as expression detection are disabled when using this model.

##### Models with many meshes

Certain models with a high number of meshes in them can cause significant slowdown. Starting with 1.23.25c, there is an option in the `Advanced` section of the `General settings` called `Disable updates`. By turning on this option, this slowdown can be mostly prevented. However, while this option is enabled, parts of the avatar may disappear when looked at from certain angles. Only enable it when necessary.

In some cases it has been found that enabling this option and disabling it again mostly eliminates the slowdown as well, so give that a try if you encounter this issue. This should prevent any issues with disappearing avatar parts. However, in this case, enabling and disabling the checkbox has to be done each time after loading the model.

#### GPU

GPU usage is mainly dictated by frame rate and anti-aliasing. These options can be found in the `General settings`.

Most of the anti-aliasing options should not be too heavy, but the `Really nice` option causes very heavy CPU load.

If VSeeFace causes too much load on the GPU, you can also try reducing the frame rate by changing the frame rate cap from 60 to something lower like 30 or 24.

## Donations

A surprising number of people have asked if it's possible to support the development of VSeeFace, so I figured I'd add this section.

### Deat

If you appreciate Deat's contributions to VSeeFace, his amazing [Tracking World](http://deatrathias.net/TW/) or just him being him overall, you can buy him a [Ko-fi](https://ko-fi.com/deatrathias), tip him through [Streamlabs](https://streamlabs.com/virtual_deat/tip) or subscribe to his [Twitch](https://www.twitch.tv/virtual_deat) channel.

### Emiliana

I don't really accept monetary donations, but getting [fanart](https://twitter.com/search?q=%23emivt_art&f=live), you can find a [reference](/assets/img/Ref.png) here, makes me really, really happy and getting vtuber gift subs on [Twitch](https://www.twitch.tv/Emiliana_vt) is nice too, because it both helps the community and I get some cute emotes to use as well.

<span style="width:100%;word-wrap:break-word; display:inline-block;color: #bbbbbb;">You really don't have to at all, but if you really, really insist and happen to have Monero (XMR), you can send something to: 8AWmb7CTB6sMhvW4FVq6zh1yo7LeJdtGmR7tyofkcHYhPstQGaKEDpv1W2u1wokFGr7Q9RtbWXBmJZh7gAy6ouDDVqDev2t</span>
