# Image-encryption

Chaos-Based Image Encryption
🔒 Overview

This project implements an image encryption algorithm using chaotic maps. It reshapes and shuffles image pixel values, applies confusion and diffusion processes using secret keys, and produces a highly secure encrypted image.

The method ensures:

Confusion: Pixel values are permuted using chaotic sequences.

Diffusion: Pixel bits are XORed with keys to spread plaintext influence across ciphertext.

Security: Sensitive dependence on initial conditions (chaos property) makes decryption without the correct keys computationally infeasible.

⚙️ Features

Uses 2D Logistic-Sine Map for generating chaotic sequences.

Supports additional maps like Tent Map and Bernoulli Map.

Bit-level reshaping: Each channel is decomposed into 8 sub-matrices of size 256×256.

Double confusion process using Key 1 and Key 2.

Final encrypted image is noise-like and resistant to common cryptographic attacks.

Tested with standard Lena image and other sample images.

🖼️ Workflow

Input: Original RGB image (e.g., Lena, 256×256).

Shuffling: Pixels of each channel are shuffled using chaotic sequences.

Bit-Plane Decomposition: Each channel is split into 8 sub-matrices (bit planes).

Confusion 1: XOR with Key 1 (bit-by-bit).

Reshape Again: Reconstruct into 8×256×256 format.

Confusion 2: XOR with Key 2.

Output: Encrypted image.

🔑 Chaotic Maps Used

2D Logistic-Sine Map – ensures complex chaotic behavior.

Tent Map – piecewise linear chaotic function for additional randomness.

Bernoulli Map – binary chaos for pseudo-random sequences.

📊 Performance Metrics

The encryption performance is validated using:

NPCR (Number of Pixels Change Rate)

UACI (Unified Average Changing Intensity)

Histogram Analysis

Correlation Coefficient Analysis

Key Sensitivity Tests
