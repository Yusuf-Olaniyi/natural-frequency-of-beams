# Beam Mode Shape and Natural Frequency Analysis

This repository contains Python code for calculating and visualizing the **mode shapes** and **natural frequencies** of beams with various boundary conditions, including:

- **Clamped-Free (Cantilever Beam)**
- **Clamped-Clamped (Both Ends Fixed Beam)**
- **Simply-Supported (Pinned-Pinned Beam)**

The code uses numerical methods to solve the characteristic equations associated with each type of beam configuration, then plots the corresponding mode shapes and calculates the natural frequencies.

## Features

1. **Calculation of Mode Shapes**: 
    - The mode shapes for beams under different boundary conditions are computed using analytical solutions to the governing differential equations.
    - The boundary conditions covered include:
        - Clamped-Free (Cantilever Beam)
        - Clamped-Clamped (Both Ends Fixed)
        - Simply-Supported (Pinned-Pinned)
      
2. **Natural Frequency Calculation**:
    - The natural frequencies for each mode are computed using the characteristic roots obtained from the boundary condition equations.
    - These frequencies provide insight into the vibration behavior of the beams.

3. **Visualization of Mode Shapes**:
    - Mode shapes for the first few modes (up to 3) are plotted for each boundary condition.
    - These plots are useful for understanding the deflection of the beams at different frequencies.

## How It Works

The code primarily relies on:
- **Scipy** for root finding (to determine the frequency parameters, \(\beta\), from the characteristic equations).
- **Numpy** for numerical computations and creation of the mode shapes.
- **Matplotlib** for visualizing the mode shapes of the beams.

### Key Functions

1. **Mode Shape Calculation Functions**:
   - `mode_shape_cf(x, beta)`: Calculates the mode shape for a **Clamped-Free (Cantilever)** beam.
   - `mode_shape_clamped_clamped(x, beta)`: Calculates the mode shape for a **Clamped-Clamped (Both Ends Fixed)** beam.
   - `mode_shape_ss(x, n)`: Calculates the mode shape for a **Simply-Supported (Pinned-Pinned)** beam.

2. **Root Finding Functions**:
   - `find_beta_cf()`: Solves the characteristic equation for **Clamped-Free** beams to find \(\beta\).
   - `find_beta_cc()`: Solves the characteristic equation for **Clamped-Clamped** beams to find \(\beta\).

3. **Natural Frequency Calculation**:
   - `natural_frequency(n, L, E, I, rho, A)`: Computes the natural frequency for a given mode number, beam length, material properties, and cross-sectional properties.

4. **Normalization**:
   - `normalize_mode_shape(Y)`: Normalizes the mode shapes to ensure that the maximum absolute value of deflection is 1. This makes it easier to compare the mode shapes across different modes and configurations.

### Usage

1. **Mode Shapes Calculation**:
   - The code calculates mode shapes based on the boundary conditions of the beam. To visualize the mode shapes, simply run the code, and plots will be generated for each beam type (Clamped-Free, Clamped-Clamped, Simply-Supported).
   
2. **Natural Frequency Calculation**:
   - Natural frequencies are computed as part of the output, and they are printed to the console. The calculated natural frequencies are for the first few modes of vibration.

3. **Exporting Results**:
   - The calculated mode shapes are saved to an Excel file (`simply_supported_beam_modes.xlsx`) for further analysis. You can modify the file name and add export functionality for other beam configurations if needed.

### Code Example

Here’s a basic example of how to calculate and plot mode shapes:

```python
# Plot mode shapes for Clamped-Free, Clamped-Clamped, and Simply-Supported beams
plot_mode_shapes()
