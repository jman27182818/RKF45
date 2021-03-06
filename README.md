# General

A re-write of an old, badly written, program using templates.  I plan to use this program to practice C++20 concepts, coroutines, and ranges.

This quick program implements a Runge-Kutta-Fhelberg 
method with a rel_err=0.  Essentially this is the GSL method gsl_odeiv2_step_rkf45
with rel_err = 0.

Note, I still need to greatly refactor and optimize this program because it's mainly written to practice C++20 and use concepts (which is also in progress).

# Usage

The program solves the system:

```
dy_i(x_j)/dt = F_i(t, x_j, y_j)
```
see the example for how this is implemented.

# Compilation


## CLI

The code only compiles for compilers with c++20 support.  If you have gcc-10 the command to compile is:

```
g++-10 -O3 -std=c++20 newton_test.cpp
```

To verify the output should be run './a.out' and the last line should be:

```
-1.49956e+11,2.10468e+10,0,-4531.51,-29292.7,0,
```

## Cmake

Standard cmake commands

```
mkdir build
cd build
cmake ..
make
```

Will also run tests


# Performance

Currently it's a factor of 1.05 times slower than GSL runtimes (see gcc example) on a intel i7.

