Starting with version v1.13.37b, it's possible to capture the image from VSeeFace in OBS by using the [Spout2](https://spout.zeal.co/) interface. This allows capturing the image without any bits of the user interface leaking into the image while not incurring the resolution restrictions and performance impact of the virtual camera.

# Spout2 capture usage

<img src="/assets/img/Spout2.png" alt="VSeeFace screenshot">

To make use of this functionality:

1) Ensure that `Spout2 image capture support` is enabled in the `General settings`. This option is disabled by default.
2) Then install the [Spout2 OBS plugin](https://github.com/Off-World-Live/obs-spout2-plugin/releases).
3) Add a `Spout2 Capture` source to your scene.
4) On the `Spout2 Capture`, make sure to set the `Composite mode` to `Default` to ensure that transparency works correctly. The source will automatically adapt to the resolution of your VSeeFace window.
5) If you have multiple instances of VSeeFace, they should show up as separate entries under `Spout Senders`. Select the one you want to capture.

If the image appears flipped vertically, right click on your capture source, select `Transform` and then `Flip Vertical` to make it show up correctly.

Please note that Spout2 might not work on certain GPUs (e.g. many integrated Intel graphics).

# VSeeFace SDK usage

The VSeeFace SDK allows using the SpoutSender and SpoutReceiver components from [Spout4Unity](https://github.com/sloopidoopi/Spout4Unity/tree/5cb448f30b807aa08d98269fef04d59547c201bd) ([download](https://github.com/sloopidoopi/Spout4Unity/archive/5cb448f30b807aa08d98269fef04d59547c201bd.zip)) to import and export texture data with low overhead.

Adding a SpoutReceiver could for example be used to export a desktop capture from OBS to VSeeFace and display it on a screen. This is most likely more efficient than using uWindowCapture through the SDK. To export a capture from OBS, add a Spout filter to it, set the name under which you want to send the texture and press the button to apply it. On the SpoutReceiver component, enter the name set this way to receive the texture data.

The SpoutSender can be added to cameras rendering to render textures to export their view. This can allow importing multiple views from VSeeFace into OBS at the same time. Of course it will incur some overhead to render the scene multiple times. When creating a render texture, make sure to set it to `R8G8B8A8_SRGB` format.
