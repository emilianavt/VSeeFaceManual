Starting with version v1.13.37b, it's possible to capture the image from VSeeFace in OBS by using the [Spout2](https://spout.zeal.co/) interface. This allows capturing the image without any bits of the user interface leaking into the image while not incurring the resolution restrictions and performance impact of the virtual camera.

<span lang="ja">VSeeFace v1.13.37bからSpout2はメニューが描画される前に、VSeeFaceカメラのレンダーテクスチャをGPU上で共有します。OBSはプラグインでそのテクスチャを直接読み取ることが出来ます。メニューを写すことなくて自由に設定をいじられる軽いキャプチャー方法です。もっと詳しい情報が@narou_rielさんの[メモサイト](https://scrapbox.io/riel-tech/VSeeFace%E3%81%A7Spout2%E3%82%92%E4%BD%BF%E3%81%86)にはあります。</span>

**Note:** Version 28 of OBS may not be compatible with the Spout2 OBS plugin v1.3 anymore. If you are using Spout2 with OBS, it may be good to hold off on OBS updates until the plugin is updated.

# Spout2 capture usage

<img src="/assets/img/Spout2.png" alt="VSeeFace screenshot">

To make use of this functionality:

0) Make sure that the [Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/en-us/download/details.aspx?id=26999) is installed.

1) Ensure that `Spout2 image capture support` is enabled in the `General settings`. This option is disabled by default.

2) Then install the [Spout2 OBS plugin](https://github.com/Off-World-Live/obs-spout2-plugin/releases).

3) Add a `Spout2 Capture` source to your scene.

4) On the `Spout2 Capture`, make sure to set the `Composite mode` to `Default` to ensure that transparency works correctly. The source will automatically adapt to the resolution of your VSeeFace window.

5) If you have multiple instances of VSeeFace, they should show up as separate entries under `Spout Senders`. Select the one you want to capture.

6) **It is still recommended to use the ※ button to disable the UI when possible, as this will avoid the background from leaking into anti-aliased and transparent pixels, causing white outlines and similar issues.**

If the image appears flipped vertically, right click on your capture source, select `Transform` and then `Flip Vertical` to make it show up correctly.

Please note that Spout2 might not work on certain GPUs (e.g. many integrated Intel graphics).

StreamLabs [does](https://streamlabs.com/content-hub/post/vtuber-support-on-streamlabs-desktop) also support Spout2.

## Why use Spout2 to capture VSeeFace?

The main reason to use Spout2 for capturing VSeeFace is capture it without any menus or other UI elements showing up. It can also be more reliable than using a game capture. The performance is about the same as capturing with a game capture, but it is much better than that of the virtual camera which was previously the only way to capture VSeeFace without any menus showing up. Another issue with the virtual camera, which does not exist with Spout2, is that it is limited to a resolution of 1280x720 and will stretch or squish the image if the window's aspect ratio does not match it.

Note that Spout2 only works locally on one PC, there is no network functionality.

## PrprLive plugin conflict

Reportedly the α-Channel OBS plugin provided by PrprLive can cause a conflict with the Spout2 OBS plugin. As there is no uninstallation option, if you have this plugin installed, you may have to manually remove `prpr-library.dll` from the OBS plugins folder, before the `Spout2 Capture` shows up in OBS. You should also be able to capture PrprLive with the Spout2 plugin after this.

# VSeeFace SDK usage

The VSeeFace SDK allows using the SpoutSender and SpoutReceiver components from [Spout4Unity](https://github.com/sloopidoopi/Spout4Unity/tree/5cb448f30b807aa08d98269fef04d59547c201bd) ([download](https://github.com/sloopidoopi/Spout4Unity/archive/5cb448f30b807aa08d98269fef04d59547c201bd.zip)) to import and export texture data with low overhead.

Adding a SpoutReceiver could for example be used to export a desktop capture from OBS to VSeeFace and display it on a screen. This is most likely more efficient than using uWindowCapture through the SDK. To export a capture from OBS, add a Spout filter to it, set the name under which you want to send the texture and press the button to apply it. On the SpoutReceiver component, enter the name set this way to receive the texture data.

The SpoutSender can be added to cameras rendering to render textures to export their view. This can allow importing multiple views from VSeeFace into OBS at the same time. Of course it will incur some overhead to render the scene multiple times. When creating a render texture, make sure to set it to `R8G8B8A8_SRGB` format.
