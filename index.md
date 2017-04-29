This program performs basic image processing operations and is run using the command line, not unlike ImageMagick. Simple operations include brightness, gamma, and saturation, while more complex operations range from blur to anti-aliased image resizing.

[You can download the command line executable here!]()

For any images below, you can press them to view its full resolution.
P.S. The GitHub repo is purely website assets. No source code here!

# Basic Operations
## Brighten

_.exe -brightness factor_

Brightness is controlled using a constant black image and performing linear interpolation between it and the original image. Interpolation darkens it. Extrapolation brightens it. Only non-negative numbers are allowed.

0.0 | 0.5 | 1.0 (original) | 1.5 | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)

## ChangeContrast

_.exe -contrast factor_

Contrast is controlled using a constant grey image and performing linear interpolation between it and the original image. The value of grey is the mean luminance of the original image. Interpolation decreases contrast. Extrapolation increases it. Negative factor inverts the hue.

-0.5 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)

## ChangeSaturation

_.exe -saturation factor_

Saturation is controlled using the greyscale version of the original image and performing linear interpolation between the greyscale image and the original image. Each pixel is the luminance of the original image's respective pixel. Interpolation decreases saturation. Extrapolation increases it. Negative factor inverts the hue.

-1.0 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)

## ChangeGamma

_.exe -gamma gamma_

Performs gamma correction on the image. Gamma correction is used to account for differences in device displays and human perception of brightness, which are both non-linear. Each pixel's color is changed using the formula C_new = C_old^(1/gamma), where C_old is a value [0,1] and gamma is (0,infinity). gamma of 1 yields the original image. Values lower than 1 darken the image. Values greater than 1 brighten it.

0.5 | 0.8 | 1.0 (original) | 1.5 | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma0.8.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma0.8.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma1.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma1.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/gamma2.0.bmp)

## Crop

_.exe -crop x y w h_

Crops the image, starting the new top-left corner at coordinate (x,y) of the original image. _w_ and _h_ are the width and height size dimensions of the new image. _x_ is [0,width-1] and _y_ is [0,height-1]. _w_ and _h_ must be positive. 

Our program is able to take _w_ and _h_ values that are greater than the original image's _width-x-1_ and _height-y-1_; values greater than these will result in keeping as many pixels as there are remaining on the respective dimension. A demonstration can be seen in the second example with the mandrill image, where the specified w=999 when the mandrill image is only 512 pixels wide. Because x=0 and w=999, the whole width of the image is preserved.

values | original | crop
--- | --- | ---
x=50, y=20, w=80, h=80; Original dimensions: 160x120 | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![What a pretty flower](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/crop50,20,80,80.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/crop50,20,80,80.bmp)
x=0, y=35, w=999, h=60; Original dimensions: 512x512 | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/mandrill.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/mandrill.bmp) | [![I C U](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/crop0,35,999,60.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/crop0,35,999,60.bmp)

# Quantization and Dithering

## Quantize

_.exe -quantize nbits_

Quantizes the image, using _nbits_ per channel. _nbits_ is [1,8]. With more bits, the image can represent more colors. With fewer bits, the images have fewer colors and it is easy to see the edges of when the colors change.

original (8 bits) | 1 | 2 | 3 | 4 | 5
--- | --- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize1.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize1.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize2.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize2.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize3.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize3.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize4.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize4.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/quantize5.bmp)

## Random Dither

_.exe -randomDither nbits_

Add random noise to the image while quantizing its pixels. The human eye is more tolerant of high frequency noise than it is to hard (low frequency) distracting edges or patterns. Again, _nbits_ is [1,8], which determines how many bits there are per color channel.

original (8 bits) | 1 | 2 | 3 | 4 | 5
--- | --- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither1.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither1.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither2.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither2.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither3.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither3.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither4.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither4.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/randomdither5.bmp)

## Floyd-Steinberg Dither

_.exe -FloydSteinbergDither nbits_

Diffuses the error of the original color versus the quantized color to pixels later in the image. This means later pixels share the error of the current pixel being processed. The color is still quantized.

For example, if the current pixel should be 255 luminance but is put into a quantum which is 200 luminance, the error is 55 because it will be displayed darker than it is originally. This positive error is added to some later pixels, which will tend to be brighter than original to make up for the darkened pixel.

original (8 bits) | 1 | 2 | 3 | 4 | 5
--- | --- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither1.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither1.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither2.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither2.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither3.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither3.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither4.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither4.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/fsdither5.bmp)

# Convolution and Edge Detection

## Blur

_.exe -blur n_

Blurs the image with a filter of width _n_. The width is the "diameter" of the kernel. The blur is done using convolution.

original | 3 | 5 | 7 | 11 | 15 | 21
--- | --- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur3.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur3.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur7.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur7.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur11.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur11.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur15.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur15.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur21.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/blur21.bmp)

## Sharpen

_.exe -sharpen_

Sharpens the image by increasing the high frequencies. The image is convolved using a sharpening filter.

original | sharpen
--- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/flower.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/sharpen.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/sharpen.bmp)


## Edge Detection

_.exe -edgeDetect threshold_

Draw the edges of the image's pixels, making the edges white and the rest black. This is done by convolving with a gradient (Soble) filter, normalizing the gradients, then thresholding with the _threshold_ value to detect edges. The pixel is set to white if its luminance is greater than the _threshold_, black if otherwise.

_Remember: Click the images below to view full resolution._

original | 50 | 100 | 150 | 250
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/wave.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/wave.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave50.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave50.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave100.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave100.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave150.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave150.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave250.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_wave250.bmp)
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/checkerboard.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/checkerboard.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard50.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard50.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard100.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard100.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard150.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard150.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard250.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/edgedetect_checkerboard250.bmp)
