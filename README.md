# Adiabatic Bragg Grating Spiral

This code was made as an addon component for the [SiEPIC PDK](https://github.com/lukasc-ubc/SiEPIC_EBeam_PDK/). The code can generate polygons for spirals with gratings.

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
- The spiral is drawn based on the Integrated Bragg gratings in spiral waveguides[1] by Alexandre D. Simard. The gratings are drawn by creating 'clone' spirals with radius that match the waveguide widths and then scaling them via a scalar (found by calculating the inverse of the slope of the whole grating)
- The drawn length of the spiral is calculated by a step size based on the angle. Therefore it is possible the lengths could differ by a miniscule amount from expected.

## Features
- [x] Orthogonal Gratings
- [ ] Chirping of grating period
- [ ] Waveguide width increase/decrease from input to output
- [ ] Slab waveguide

##Issues being investigated
- best gap: to avoid coupling whilst the spiral is growing.

## References
[1] https://www.osapublishing.org/oe/fulltext.cfm?uri=oe-21-7-8953&id=252032