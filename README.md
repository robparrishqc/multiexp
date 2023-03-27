# MultiExp Quadratures

This repository contains the numerical data obtained in our recent campaign to
produce Gill and Chien's MultiExp Gaussian quadratures for N <= 100.

The MultiExp quadratures were defined in P. M. Gill and S.-H. Chien, Journal of computational chemistry 24, 732 (2003).

The MultiExp quadratures are widely used in DFT grids in the context of the small but efficient SG-0 grid defined in S.-H. Chien and P. M. Gill, Journal of computational chemistry 27, 730 (2006).

The grids obtained in this paper were built with a Boley-Golub + Golub-Welsch procedure, and are posited (but not guaranteed) to be accurate to a maximum absolute deviation of at least 14(13) decimal digits in the roots(weights). A crucial step in the procedure was the use of extremely high order Gauss-Legendre quadratures of order Q=2x10^8 to seed the Boley-Golub algorithm. These Gauss-Legendre grids were obtained from the remarkable procedure of I. Bogaert, SIAM Journal on Scientific Computing 36, A1008 (2014). If you find these grids to be useful, please consider citing Bogaert, as Bogaert's grids were absolutely necessary to obtain these grids. 

A detailed description of the procedure used to obtain these MultiExp grids is presented at TODO 

# Data

`data/multiexp-N100-Q2E8.npz` - the preferred MultiExp quadrature rules for 1
<= N <= 100 obtained with our most-accurate Q=2x10^8 treatment. Preference date: Mar 27, 2023

These grids can be extracted with a simple python script:

```
import numpy as np

dat = np.load('data/multiexp-N100-Q2E8.npz')

# The MultiExp roots and weights for the example of N=13
x = dat['x013']
w = dat['w013']

print(x)
print(w)

# The (101, 101) tridiagonal Boley-Golub matrix
T = dat['T']
```
