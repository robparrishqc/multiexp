# MultiExp Quadratures

This repository contains the numerical data obtained in our recent campaign to
produce Gill and Chien's MultiExp Gaussian quadratures for N <= 100.

# Data

`data/multiexp-N100-Q2E8.npz` - the preferred MultiExp quadrature rules for 1
<= N <= 100 obtained with our most-accurate Q=2x10^8 treatment.

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
