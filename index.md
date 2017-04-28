This program performs basic image processing operations and is run using the command line, not unlike ImageMagick. Simple operations include brightness, gamma, and saturation, while more complex operations range from blur to anti-aliased image resizing.

[You can download the command line executable here!]()

P.S. The GitHub repo is purely website assets. No source code here!

## Basic Operations
### Brighten

Brightness is controlled using a black image. Interpolation darkens it. Extrapolation brightens it.

0.0 | 0.5 | 1.0 (original) | 1.5 | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness1.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/brightness2.0.bmp)

### ChangeContrast

Contrast is controlled using a grey image; the value of grey is the averaged luminance of the original image. Interpolation decreases contrast. Extrapolation increases it. Negative alpha factor inverts the hue.

-0.5 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast-0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/contrast2.0.bmp)

### ChangeSaturation

Saturation is controlled using the greyscale version of the original image. Each pixel is the luminance of the original image. Interpolation decreases saturation. Extrapolation increases it. Negative factor inverts the hue.

-0.5 | 0.0 | 0.5 | 1.0 (original) | 2.0
--- | --- | --- | --- | ---
[![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation-0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation0.5.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation1.0.bmp) | [![](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)](https://raw.githubusercontent.com/rnlee0054/163.1Website/master/images/saturation2.0.bmp)

### ChangeGamma
### Crop
