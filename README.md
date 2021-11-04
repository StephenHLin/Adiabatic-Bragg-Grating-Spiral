# Adiabatic Bragg Grating Spiral

This code was made as an addon component for the [SiEPIC PDK](https://github.com/lukasc-ubc/SiEPIC_EBeam_PDK/). The code can generate polygons for spirals with gratings.
<img src="/images/spiralcdc.JPG" alt="drawing" width="400"/>
<img src="/images/gratings.JPG" alt="drawing" width="400"/>

## Requirements
- [SiEPIC PDK](https://github.com/lukasc-ubc/SiEPIC_EBeam_PDK)
- [Klayout](https://www.klayout.de/)

## Installation
- Install the SiEPIC PDK into Klayout
- Place *PCM_Spiral_Pcells.lym* in your KLayout/tech/EBeam/pymacros folder
- Place *Layout_PCMSpirals.lym* in your KLayout/pymacros

## How to use
You can create individual devices via the *instance* button in Klayout. This button will only show up after the SiEPIC PDK is installed and you have enabled *editing mode*.

To use the layout script to create automatic designs, open the macro development window (F5) and then locate the *Layout_PCMSpirals* file. The script can take in arrays of parameters and iterates a whole layout for each combination.

## Technical Details
- The spiral is drawn based on the Integrated Bragg grating in spiral waveguides[1] by Alexandre D. Simard. The gratings are drawn by creating 'clone' spirals with radius that match the waveguide widths and then scaling them via a scalar (found by calculating the inverse of the slope of the whole grating)
- The drawn length of the spiral is calculated by a step size based on the angle. Therefore it is possible the lengths could differ by a miniscule amount from expected.

Below is an image of the parameters to clear up confusion:

![Alt text](/images/Parameters.PNG)

## Features
- [x] Orthogonal Gratings
- [ ] Chirping of grating period
- [ ] Waveguide width increase/decrease from input to output
- [x] Slab waveguide
- [x] CDC Structure

## Known Issues
- Gap: The gap is smaller than designated in the first rotation as the spiral is still growing. Suggested solution: set the gap bigger than intended
- Rounding: Spirals are drawn via dpoints (double points) and thus sometimes it results in rounding errors of the smallest dbu set (0.001 default). Suggested: Overlap the areas that have these errors

## References
[1] https://www.osapublishing.org/oe/fulltext.cfm?uri=oe-21-7-8953&id=252032
