layout: page
title: "Spout2 capture support"
permalink: /spout2/

# Spout2 capture support

Starting with version v1.13.37b, it's possible to capture the image from VSeeFace in OBS by using the Spout2 interface.

This allows capturing the image without any bits of the user interface leaking into the image while not incurring the resolution restrictions and performance impact of the virtual camera.

Do make use of this functionality, ensure that `Spout2 image capture support` is enabled in the `General settings`. This option is enabled by default.

Then install the Spout2 OBS plugin and add a `Spout2 Capture` source to your scene. On the `Spout2 Capture`, make sure to set the `Composite mode` to `Default` to ensure that transparency works correctly. The source will automatically adapt to the resolution of your VSeeFace window.

If you have multiple instances of VSeeFace, they should show up as separate entries under `Spout Senders`.

If the image appears flipped vertically, right click on your capture source, select `Transform` and then `Flip Vertical` to make it show up correctly.
