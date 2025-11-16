# roots

## Introduction

You will find that much of the thoery in your undergraduate degree involves the discovery and application of analytical equations that model problems of interest. However, there exists large classes of problems where analytical solutions simply do not exist or are otherwise intractable due to complexity/scope. These problems can often be easily solved via methods of numerical computation and can provide us with usable solutions with precision limted only by computational power and our algorithms. Numerical computation is a course in an of itself, but here we will touch a basic, but common problem; root-finding.

Root finding can be described as finding all the zero-crossings of an analytical function. By applying root finding to 1st or 2nd derivatives one can also find minima, maxima and inflection points of analytical functions.  For our purposes we will define root-finding as follows: If, for a given function `f(x)` defined at all points on the interval `x ∈ [a, b]` and `f(x) = 0` has 0 or 1 solutions for `x ∈ [a, b]`, find the value of x if it exists. Most root finders algorithms work by iteratively evaluating `f(x)` at various points on the interval `[a, b]` until they can estimate `x` within some predefined precision.

## Requirements

- Provided a function pointer that evaluates `f(x)`
  - Implement a root finding algorithm that can find the root of `f(x)`
  - Utilize the root finding algorithm to find a local maxima of `f(x)`

### Hints

- [Regular Falsi Method for solving equations](https://www.geeksforgeeks.org/interview-experiences/program-for-method-of-false-position)
- You can approximate differentiation by taking the difference between consecutive values of `f(x)` at some small, constant interval

## Building

```shell
cmake -S . -B build
cmake --build build --config Debug
build\Debug\hello_world.exe
```

## Testing

[Build](#building)

```shell
ctest --test-dir build -C Debug
Add -V for verbose testing
```
