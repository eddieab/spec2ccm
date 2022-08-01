# Color Image Sensor Calibration: Spectral Response to Color Correction Matrix

## Description

This repo holds a short script/notebbook that finds two color correction matrices. One matrix will be under the Standard Light A illuminant and the other will be under D65. The code is meant to be as PnP as possible, so the only requirement for the user is the combined quantum efficiency or spectral sensitivity of their imaging system (color dyes, microlens, UR/IV, ND, etc.) in 10nm increments at 380 nm through 730 nm. There should be a total of 36 total measurements. The measurements should be formatted as one value per row as a file named `cam_qe.csv` with no trailing new line at the end of the file.



This repo already includes properly formatted spectral power distributions for illuminants A and D65, spectral reflectance ColorChecker Digital SG, and CIE XYZ 2º Observer color matching functions, and a 3x3 matrix for sRGB to CIE XYZ conversion. If you would like to see the results directly in the notebook, include an already demosaiced image that has had the white balance undone and name it `image.png`. The notebook includes a simple color pipeline that will white balance your image and apply a CCM based on a user given CCT/Duv pair. Otherwise you can just take the output of `iW1` and `iW2` and embed those in your software or raw file metadata.



## Contribution

While not required if you do decide to modify the code, it will be greatly appreciated if pull requests with changes are made. Some future work I have considered is white point preserving LS and luminance independent regression. Other changes might be inclusions beyond RGB (should not be a big change), like RGBW and RGBCMY sensors.
