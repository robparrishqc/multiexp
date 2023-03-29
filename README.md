# MultiExp Quadratures

This repository contains the numerical data obtained in our recent campaign to
produce Gill and Chien's MultiExp Gaussian quadratures for N <= 1000.

# Data

`data/multiexp-N1000-Q1E5-gamma2.npz` - the preferred MultiExp quadrature rules for 1
<= N <= 1000 obtained with our most-accurate Q=1x10^5, gamma=2 treatment.
Preference date Mar 28, 2023.

`data/multiexp-N100-Q2E8-gamma1.npz` - the MultiExp quadrature rules for 1
<= N <= 100 obtained with the older and slower-converging Q=2x10^8, gamma=1
treatment. Preference date Mar 27, 2023.

These grids can be extracted with a simple python script:

```
import numpy as np

dat = np.load('data/multiexp-N1000-Q1E5-gamma2.npz')

# The MultiExp roots and weights for the example of N=13
x = dat['x013']
w = dat['w013']

print(x)
print(w)

# The (1001, 1001) tridiagonal Boley-Golub matrix
T = dat['T']
```
