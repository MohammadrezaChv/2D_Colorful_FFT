
# 2D Fast Fourier Transform (FFT) and Inverse Fast Fourier Transform (IFFT)

This repository provides an implementation of the 2D FFT and IFFT algorithms for image processing. The code is implemented in Python and utilizes the NumPy library for efficient numerical computations.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The 2D FFT and IFFT algorithms are fundamental tools in signal processing and are widely used in various applications, including image processing, audio processing, and data compression. This code provides an implementation of these algorithms specifically for image processing tasks.

## Prerequisites

Before using this code, ensure that you have the following dependencies installed:

- Python 3.x
- NumPy

## Installation

To use this code, follow these steps:

1. Clone the repository to your local machine:

   ```
   git clone https://github.com/your-username/2d-fft-implementation.git
   ```

2. Navigate to the project directory:

   ```
   cd 2d-fft-implementation
   ```

3. Install the required dependencies using pip:

   ```
   pip install -r requirements.txt
   ```

## Usage

To use the 2D FFT and IFFT code, follow these steps:

1. Import the required modules:

   ```python
   import numpy as np
   import cv2
   ```

2. Define the functions `fft2D`, `fft2D_single_channel`, `ifft2D`, `ifft2D_single_channel`, `fft`, and `ifft` in your script. These functions are provided in the code snippet you shared.

3. Load the input image using `cv2.imread()`:

   ```python
   image = cv2.imread('input.jpg')
   ```

4. Perform the 2D FFT on the image using the `fft2D` function:

   ```python
   fft_result = fft2D(image)
   ```

5. Perform the 2D IFFT on the FFT result using the `ifft2D` function:

   ```python
   reconstructed_image = ifft2D(fft_result)
   reconstructed_image = np.real(reconstructed_image)
   ```

6. Scale the pixel values of the reconstructed image to the range of 0-255:

   ```python
   reconstructed_image = (reconstructed_image - np.min(reconstructed_image)) * (255 / np.max(reconstructed_image))
   reconstructed_image = reconstructed_image.astype(np.uint8)
   ```

7. Save or display the input and reconstructed images using `cv2.imwrite()` or `cv2.imshow()`.

For more advanced usage and customization, you can explore additional image processing operations using the FFT and IFFT results.

## Example

For a detailed example of using the 2D FFT and IFFT code, refer to the provided example script [example.py](example.py). The script demonstrates the step-by-step process of performing the 2D FFT and IFFT on an image, along with additional image processing operations.

## Contributing

Contributions to this project are welcome! If you find any issues or have suggestions for improvement, please open an issue or submit a pull request. Let's make this code better together!

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute this code for personal or commercial purposes.

```
