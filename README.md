# FDTD3dCUDA

## About FDTD3d
The Finite-Difference Time-Domain (FDTD) method is a rigorous and powerful tool for modeling nano-scale optical devices. FDTD solves Maxwell's equations directly without any physical approximation, and the maximum problem size is limited only by the extent of the computing power available.

## Introduction
Sample: FDTD3d
Minimum spec: SM 3.5
This sample applies a finite differences time domain progression stencil on a 3D surface.
Key concepts:
Performance Strategies

## Build
```
mkdir build-linux
cd build-linux
cmake
```

## Executation
./FDTD3dCUDA

## Expected output
```
./FDTD3dCUDA Starting...

Set-up, based upon target device GMEM size...
 getTargetDeviceGlobalMemSize
 cudaGetDeviceCount
 cudaGetDeviceProperties
 generateRandomData

FDTD on 376 x 376 x 376 volume with symmetric filter radius 4 for 5 timesteps...

fdtdReference...
 calloc intermediate
 Host FDTD loop
        t = 0
        t = 1
        t = 2
        t = 3
        t = 4

fdtdReference complete
fdtdGPU...
 set block size to 32x16
 set grid size to 12x24
 GPU FDTD loop
        t = 0 launch kernel
        t = 1 launch kernel
        t = 2 launch kernel
        t = 3 launch kernel
        t = 4 launch kernel

fdtdGPU complete

CompareData (tolerance 0.000100)...
```