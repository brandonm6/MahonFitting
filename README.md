# MahonFitting v2.0
<!--toc-->

## Introduction

This routine performs linear regressions to a set of measurement that have uncertainties in both axes, which we subsequently call *x* and *y*. The regression is based on the approach by Mahon (1996) and is the same regression as used by York (1969), however, with the corrected calculation for the uncertainties. The code presented here accompanies the publication of Trappitsch et al. (2018). If you want, please cite Trappitsch et al. (2018) as a reference for pointing at this tool.

The original program has been reduced to only the class Mahon (without the GUI), which performs the calculations.

## Usage
### Preparing your data set
Mahon requires a dataframe as a parameter. The column format must be:

| Column 1 | Column 2 | Column 3 | Column 4 | Column 5 |
|----------|----------|----------|----------|----------|
|    x     |   x unc 	|    y     |   y unc  |   corr   |

where:
- [x ] are the x values 
- [x unc] are the uncertainties for x
- [y] are the y values
- [y unc] are the uncertainties for y
- [corr] are the correlation values

The testfile that is provided comes from the dataset published in Mahon (1996) and can be used for validation.

### Attributes
  * slope: Slope
  * yinter: Y-Intercept
  * xinter: X-Intercept
  * slopeunc: Slope uncertainty
  * yinterunc: Y-Intercept uncertainty
  * xinterunc: X-Intercept uncertainty
  * MSWD: Mean Square Weighted Deviation

### Problems
Since the slope of the regression is calculated iteratively (see equation (9) in Mahon, 1996), there is a chance that the iterative process does not converge. In this case, the python routine stops after 10<sup>6</sup> iterations and will give you an error message such that you can see how well it converged and decide for yourself if it is acceptable or not. Please also have a look at the regression and see if it looks reasonable, check if the configuration that you want to have regressed is reasonable. If the problem consists, you find another problem, or have problems using this software, feel free to contact me.

## Required packages:
* numpy

## Contact
If you find a bug or problem with the software or if you can't get it to run on your machine (and have read this readme file), feel free to contact me (Reto Trappitsch) at <trappitsch1@llnl.gov>.

## References
Mahon K. I. (1996) The New "York" Regression: Application of an Improved Statistical Method to Geochemistry, *International Geology Review*, 38:293-303.

York D. (1969) Least squares fitting of a straight line with correlated errors, *Earth & Planetary Science Letters*, 5:320-324.

Trappitsch R., Boehnke P., Stephan T., Telus M., Savina M. R., Pardo O., Davis A. M., Dauphas N., Pellin M. J., adn Huss G. (2018) New Constraints for the Low Abundance of <sup>60</sup>Fe in the Early Solar System, *The Astrophysical Journal Letters*, in prep.

## Release
Copyright (c) 2018, Lawrence Livermore National Security, LLC. Produced at the Lawrence Livermore National Laboratory. Written by Reto Trappitsch <trappitsch1@llnl.gov>

LLNL-CODE-745740 All rights reserved. This file is part of MahonFitting v1.0

Please also read this link – Our [Disclaimer](https://github.com/LLNL/MahonFitting/blob/master/DISCLAIMER) and [GNU General Public License](https://github.com/LLNL/MahonFitting/blob/master/LICENSE).

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License (as published by the Free Software Foundation) version 2, dated June 1991.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the IMPLIED WARRANTY OF MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the terms and conditions of the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA 02111-1307 USA
