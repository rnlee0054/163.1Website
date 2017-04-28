This program performs basic image processing operations and is run using the command line, not unlike ImageMagick. Simple operations include brightness, gamma, and saturation, while more complex operations range from blur to anti-aliased image resizing.

[You can download the command line executable here!]()

P.S. The GitHub repo is purely website assets. No source code here!

# Basic Operations
## Brighten

_.exe -brightness factor_

Brightness is controlled using a constant black image. Interpolation darkens it. Extrapolation brightens it. Only non-negative numbers are allowed.

0.0 | 0.5 | 1.0 (original) | 1.5 | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)

## ChangeContrast

_.exe -contrast factor_

Contrast is controlled using a constant grey image; the value of grey is the mean luminance of the original image. Interpolation decreases contrast. Extrapolation increases it. Negative factor inverts the hue.

-0.5 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)

## ChangeSaturation

_.exe -saturation factor_

Saturation is controlled using the greyscale version of the original image. Each pixel is the luminance of the original image's respective pixel. Interpolation decreases saturation. Extrapolation increases it. Negative factor inverts the hue.

-1.0 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)

## ChangeGamma

_.exe -gamma gamma_

Performs gamma correction on the image. Each pixel's color is changed using the formula C_{new} = C_{old}^(1/gamma), where C_{old} is a value [0,1] and gamma is (0,infinity).

## Crop

_.exe -crop x y width height _

Crops the image, starting the new top-left corner at coordinate (x,y) of the original image. width and height are the size dimensions of the new image. x is [0,width-1] and y is [0,height-1]. width and height must be positive.
