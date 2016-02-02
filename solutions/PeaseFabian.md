# Fabian Pease Solutions

**Table of Contents**  
<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Pre-1993](#pre-1993)
- [2007](#2007)
- [2008](#2008)
- [2010](#2010)
- [2012](#2012)

<!-- /TOC -->

## Pre-1993


## 2007
A cathode-ray oscilloscope (CRO) operates by focusing and deflecting a beam of free electrons onto a screen. Outline the limitations to the sensitivity, resolution, and speed. You may assume the electron lens is free of aberrations.

**Speed**: Time for the beam to hit the screen, and for the screen to fluoresce are almost instantaneous. For CRTs this is < us, for LCD < 2-5ms. For CRTs, we are limited by the screen area and the speed of the lens circuitry. we ideally want 60Hz refresh rate per pixel.

**Resolution**: Size of each pixel is determined by the beam width, which is determined by the beam aperture, the packing density of flourescent molecules, and the resolution of the voltage you apply to the deflection lens. Eyes also have a limitation on the resolution we can see (1 um). Rayleigh criterion. So, resolution is eventually limited by our eyes.

**Sensitivity**: Limited by quantum efficiency of the flourescent screen. The number of electrons you need to focus on the screen to emit a photon from the flourescent molecule. Some energy will be dissipated as heat.

## 2008
1. Why do Heatsinks have fins?
  * To maximize their surface area.

2. Express the area advantage of the above finned structure over an unfinned structure in terms of *h, Lc, Lw*.
  * The unfinned surface area would be (length * depth) in his drawing.
  * For finned, A = (L/(Lw + Lc))(2h + Lc + Lw)(depth)

3. To maximize A, choose h, Lc, and Lw.
  * We want to maximize surface area,so we want to maximize h, and minimize Lc and Lw.

## 2010

The 2009 Nobel Prize in Physics was awarded for **the invention of an imaging semiconductor circuit (the CCD)**
1. How does the image sensor in your digital camera work?
  * They would use either a CCD or CMOS sensor (active pixel sensor or passive pixel sensor)
  * Passive Pixel Sensor:
    * 1 transistor per pixel
    * Small pixel, large fill factor (% of pixel area sensitive to light)
    * Slow, and low SNR
    * Readout speed limited by row transfer time
  * Active Pixel Sensor
    * 3-4 transistors per pixel
    * fast, high SNR
    * Larger pixels, lower fill factor
    * column readout limits readout speed
  * As technology has scaled, APS pixel size and fill factor were no longer problematic and have become the technology of choice.

2. Why did the CCD win the prize while other emerging tech did not?
  * The CCD gave rise to dramatic expansion of the field of digital imaging. They completely transformed image processing while other technologies were largely improvements of existing ideas.

3. Why has CMOS become more popular?
  * **Power**: CCDs consume approx. 100x more power than an equivalent CMOS sensor. For a CCD, the entire array is switching all the time.
  * **Cost**: CMOS chips can be fabricated very easily on a standard Si production line. CCDs require special processing.
  * **Speed**: CCDs, there is a tradeoff between transfer speed and transfer efficiency. This is not the case for CMOS, since each pixel is read individually.
  * **Ease of Integration** Digital logic circuits, counter, ADC, etc. can be placed on the same Si chip at the same time as the CMOS sensors. CMOS sensors can benefit from the continual shrinking of the CMOS processes.

## 2012
1. 
