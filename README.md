# Adiabatic Bragg Grating Spiral

This code was made as an addon component for the SiEPIC PDK (https://github.com/lukasc-ubc/SiEPIC_EBeam_PDK). The code can generate polygons for spirals with gratings.

#Requirements
-Klayout

#Technical Details
The spiral is drawn based on the Integrated Bragg gratings in spiral waveguides[1] by Alexandre D. Simard. The gratings are drawn by creating 'clone' spirals with radius that match the waveguide widths and then scaling them via a scalar (found by calculating the inverse of the slope of the whole grating)
The drawn length of the spiral is calculated by a step size based on the angle. Therefore it is possible the lengths could differ by a miniscule amount from expected.

#References
[1] https://www.osapublishing.org/oe/fulltext.cfm?uri=oe-21-7-8953&id=252032