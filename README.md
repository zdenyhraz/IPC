# Iterative phase correlation algorithm for high precision subpixel image registration
Zdenek Hrazdira, Brno University of Technology
2019

The IPC.exe file computes the geometric misalignment 
(rotation, scale, X/Y shift) between two input images, 
as described in the IPC paper, by Zdenek Hrazdira, Miloslav
Druckmuller & Shadia Habbal. Example IPC calculation 
with images "input1.png" and "input2.png" can be run
by simply executing .exe file.

The IPC method of image alignment is an integral part of a workflow, 
which is routinely used for the creation of SDO AIA PM-NAFE processed videos. 
The archive of these videos can be found at \url{http://www.zam.fme.vutbr.cz/~druck/Sdo/Pm-nafe/0-info.htm}.

![alt text](https://raw.githubusercontent.com/zdenyhraz/IPC/master/demo.PNG "demo picture")

A) .exe file arguments:
	1) path to input image 1
	2) path to input image 2
	3) (optional) path to a config file,
	containing IPC parameters

B) config file parameters:
Not all parameters need to be specified - all
parameters have default values. Order of variables 
in the config file does not matter.
For more elaborate IPC parameters description,
read the original IPC paper.

B1) NUMERICAL PARAMETERS

1) L2size - size of the L2 region

2) L1ratio - ratio of L1 region
	(L1size=L1ratio * L2size * UC)

3) UC - L2 region upsampling coefficient

4) stdevL - band pass low passing coefficient

5) stdevH - band pass high passing coefficient


B2) BOOLEAN PARAMETERS

6) interpolate - use bilinear interpolation

7) window - use Hann window, instead of
	Rectangular (no) window

8) bandpass - apply frequency band pass 
	filtering (with parameters 4, 5)

9) subpixel - calculate the shift with subpixel
	precision

10) iterate - refine the resulting subpixel shift
	iteratively

C) Dependencies
The .exe file needs the "opencv_world343.dll"
dynamic library file in the directory the .exe 
is executed from, or the path to the .dll needs
to be added to the system environment variable
PATH, to run it from anywhere. The executable
was made with C++ OpenCV and STL libraries.
