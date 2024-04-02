# Diffusion Model

## Introduction

### Diffusion Process

- A predefined Markov process to gradually add Gaussian noise to the input until the input becomes a pure noise.

### Reverse Process

- A neural network that learns to de-noise the pure noise to the original input.

## Latent Diffusion

- Features
  - Compress the input into a latent space (low-dimensional space).
- Benefits
  - The latent space attends more to the global information of the input.
  - Latent Diffusion model is more computationally efficient than the Direct Diffusion model.
