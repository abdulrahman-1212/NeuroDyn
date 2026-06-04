<p align="center">
  <img src="assets/neurodyn_logo.png" width="300">
</p>


# NeuroDyn

**High-Performance Neural Dynamics for Scientific Machine Learning**

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/yourusername/neurodyn.svg)](https://github.com/yourusername/neurodyn)
[![CUDA](https://img.shields.io/badge/CUDA-Accelerated-76B900.svg)](https://pytorch.org/cppdocs/)
[![C++20](https://img.shields.io/badge/C++-20-blue.svg)]()

NeuroDyn is a **high-performance library** for Scientific Machine Learning with a strong focus on **dynamical systems**, physics-informed modeling, and reliability.

### Current MVP (v0.1)
- **CUDA-accelerated C++ core** powered by **LibTorch**
- High-performance tensor operations and automatic differentiation
- Core utilities for scientific ML (collocation, residuals, metrics)
- Scientific visualization tools
- Python bindings via pybind11

---

## ✨ MVP Features

- **CUDA-Accelerated Core** using LibTorch (C++ backend)
- High-order automatic differentiation for PINN-style residuals
- Efficient collocation point sampling and grid generation
- Physics-aware tensor utilities and loss computation
- Scientific visualization module (field plots, phase space, residuals)
- Clean Python API with zero-copy tensor conversion
- Modular architecture designed for performance and extensibility

---

## Installation

### Prerequisites
- CUDA Toolkit (12.6 or 13.x recommended)
- CMake ≥ 3.20
- Python ≥ 3.10

### Build from Source

```bash
git clone https://github.com/yourusername/neurodyn.git
cd neurodyn

# Download LibTorch CUDA into externals/
mkdir -p externals
cd externals
wget https://download.pytorch.org/libtorch/cu126/libtorch-shared-with-deps-latest.zip
unzip libtorch-shared-with-deps-latest.zip -d libtorch
cd ..

# Build the project
mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release \
         -DTORCH_DIR=../externals/libtorch \
         -DCMAKE_PREFIX_PATH=../externals/libtorch
make -j$(nproc)

# Install Python package
cd ..
pip install -e .
