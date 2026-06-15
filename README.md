# MilkFuoresence
# Optical Spectrometer Simulation Using POPPY

Overview

This project simulates the complete optical chain of a compact fluorescence spectrometer:
Fluorescent Source (sum of three Gaussian light sources Blue (460 nm), Green (530 nm), and Red (650nm)) -> Rectangular Slit -> Diffraction Grating -> Camera Lens -> Image Sensor

Program automatically selects the computational method based on the calculated Fresnel number (N_F) at each individual wavelength:
+ N_F < 0.1 (Fraunhofer Regime)
+ 0.1 <= N_F < 1.0 Near-Fresnel Convolution
+ 1.0 <= N_F < 10.0 Angular Spectrum Method
+ N_F >= 10.0 Geometric Optics Approximation

Input parameters:

a: slit width (default a = 6e-3  #6mm)
h: slit hight (default h = 10e-3 #1cm)
L: distance from slit to grating (default L = 50e-3 #5cm)
d: grating period (default d = 1e-3 / 1600     #mm)
f: camera lens focal length (default f = 25e-3 #m)
λ0: wavelength at which you want to be at the center of camera sensor (nm) (default λ0 = 530.0 nm)
alpha_deg: incident angle (default alpha_deg = 70.0 degrees)
m: diffraction order (default at first order m = 1)

Output:
+ A 2D spatial intensity slice displaying the light distribution in millimeters ($\text{mm}$) across the sensor plane.
+ An intensity map where the spatial dispersion axis is directly mapped to the physical wavelength scale (nm).
+ A normalized 1D spectral reconstruction plot
+ A plot of optical setup

Installation

Package requirements:
+ python 3.11.9
+ poppy (https://poppy-optics.readthedocs.io/en/latest/installation.html)
+ numpy
+ matplotlib
+ scipy

Create Virtual Environment:
$ python -m venv .venv
Activate the Virtual Environment (Linux/MacOS):
$ source .venv/bin/activate

Install Dependencies:
$ pip install numpy scipy matplotlib jupyter ipykernel

Runinning in VS Code:
+ Open FluoresenceMilk.ipynb in VS Code
+ Select Kernel (top right coner of VS Code window) -> Select Another Kernel -> Python Environment -> poppy-env311 -> Execute Cell (triangle sign on the left side) or press ctrl+alt+enter



