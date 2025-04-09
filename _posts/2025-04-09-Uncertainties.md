---
title: Working with uncertainties
author: Anders Kaestner
date: 2025-04-09 05:00:00
---

Uncertainties are present in any experiment and it is often hard to specify and propagate them in the calculations.

The [uncertainties package](https://pythonhosted.org/uncertainties/) is very helpful because it allows you to define variables with uncertainties that automatically propagates the uncertainties when you do your calculations.

```bash
conda install uncertainties
```

or 

```bash
pip install uncertainties
```

Then, in python you import
```python
from uncertainties import ufloat
from uncertainties import numpy as unp # for numpy support
```

## Example

### Beer-Lamberts law
We want to compute the thickness of an item in transmission imaging. We know
- The attenuation coefficient $\mu=4.3\pm 0.1$
- The open beam intensity $I_0=10356\pm112$
- The open beam intensity $I=7654\pm80$

#### Define the variables
```python
I0=ufloat(10356,112)
I=ufloat(7654,80)
mu=ufloat(4.3,0.1)
```

#### A basic calculation
```python
T=I/I0
print(T)
```
Result: 0.739+/-0.011

#### Using numpy
Numpy is not directly supported in its normal form, but the uncertainty package has an alternative that can handle the new data type
```python
d=-unp.log(T)/mu
print(d)
```
Result: 0.070+/-0.004

#### Accesing nominal and uncertainty values
This can be used to compute the relative uncertainty of a variable
```python
d.std_dev/d.nominal_value
```


<a href="https://colab.research.google.com/github/neutronimaging/coding-recipes/blob/main/python/Uncertainties.ipynb" target="_blank">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>

