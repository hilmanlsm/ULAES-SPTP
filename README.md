# ULAES-SPTP
Implementation of a modified Ultra-Lightweight AES (UL-AES) encryption algorithm with a dynamic S-Box generated using the Square Polynomial Transformation and Permutation (SPTP) method. This code supports the experiments and results presented in the manuscript submitted to PeerJ Computer Science.

# UL-AES with Dynamic S-Box (SPTP-based)

This repository contains the implementation of a modified **Ultra-Lightweight AES (UL–AES)** encryption algorithm that integrates a **dynamic S-Box** generated using the **Square Polynomial Transformation and Permutation (SPTP)** method. The code supports the experiments and results presented in the manuscript submitted to *PeerJ Computer Science*.

## Overview

Conventional UL–AES uses a static S-Box, which makes it vulnerable to algebraic and differential cryptanalysis.  
In this work, we propose a **dynamic 4×4 S-Box** derived from key-dependent parameters using the SPTP method.  
This dynamic design improves security while maintaining low memory usage and execution efficiency, making it suitable for **resource-constrained IoT environments**.

The S-Box was evaluated against seven major cryptographic criteria:
- Bijectivity  
- Nonlinearity  
- Strict Avalanche Criterion (SAC)  
- Bit Independence Criterion (BIC)  
- Linear Approximation Probability (LAP)  
- Differential Uniformity  
- Algebraic Resistance  

Results show that the proposed dynamic S-Box consistently preserves bijectivity, achieves competitive nonlinearity, satisfies SAC, improves BIC, and significantly enhances resistance compared to the original UL–AES design.

## Features

- Implementation of UL–AES with a dynamic S-Box.  
- SPTP-based S-Box generation (polynomial transformation, modular inversion, affine transformation, and permutation).  
- Key-dependent parameters for deterministic reconstruction.  
- Security evaluation functions (bijectivity, nonlinearity, SAC, BIC, LAP).  
- Performance analysis including execution time, throughput, and memory usage.

## Requirements

- Python 3.8+  
- NumPy  
- (Optional) Matplotlib — for visualization of results  

You can install dependencies with:

bash
pip install -r requirements.txt


# Usage

Example of running the encryption:
from ulaes_sptp import ULAES

# Example 128-bit key (16 bytes)
key = [0x25, 0x46, 0x78, 0xe5, 0x28, 0xae, 0xd2, 0xa6,
       0xab, 0xf7, 0x97, 0x75, 0x55, 0x63, 0x8c, 0x7f]

# Example plaintext (16 bytes)
plaintext = [0x32, 0x88, 0x31, 0x34, 0x88, 0x31, 0x34, 0x32,
             0x32, 0x88, 0x31, 0x34, 0x88, 0x31, 0x34, 0x32]

cipher = ULAES(key)
ciphertext = cipher.encrypt(plaintext)

print("Ciphertext:", ciphertext)


[![DOI](https://zenodo.org/badge/1058383909.svg)](https://doi.org/10.5281/zenodo.17139050)
