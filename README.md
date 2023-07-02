# 2D FFT and IFFT for Image Processing

This Jupyter Notebook provides an implementation of the Fast Fourier Transform (FFT) and Inverse Fast Fourier Transform (IFFT) for 2D image processing. The code utilizes the `numpy` and `cv2` libraries for numerical computations and image handling.

## Prerequisites

To run this code, you need the following libraries installed in your Python environment:
- `numpy`
- `opencv-python` (cv2)

You can install these libraries using the following command:

pip install numpy opencv-python


## Code Description

The code consists of the following functions:

### 1. `fft2D(image)`

This function performs a 2D FFT on an input image. It takes an image as input and returns the FFT result as an array of complex numbers.

### 2. `fft2D_single_channel(channel)`

This function performs a 2D FFT on a single color channel of an image. It takes a single-channel image (e.g., grayscale) as input and returns the FFT result for that channel as an array of complex numbers.

### 3. `ifft2D(image_fft)`

This function performs a 2D Inverse FFT (IFFT) on an input image in the frequency domain (FFT representation). It takes an image in the frequency domain as input and returns the reconstructed image as an array of complex numbers.

### 4. `ifft2D_single_channel(channel_fft)`

This function performs a 2D IFFT on a single color channel of an image in the frequency domain. It takes a single-channel image in the frequency domain as input and returns the reconstructed channel as an array of complex numbers.

### 5. `fft(x)`

This function implements the 1D FFT using the Cooley-Tukey algorithm. It performs a 1D FFT on an input array `x` and returns the FFT result as an array of complex numbers.

### 6. `ifft(x)`

This function implements the 1D IFFT using the Cooley-Tukey algorithm. It performs a 1D IFFT on an input array `x` and returns the IFFT result as an array of complex numbers.

## Example Usage

Here's an example of how to use the provided functions to perform 2D FFT and IFFT on an image:

```python
import numpy as np
import cv2

# Load the image
image = cv2.imread('input.jpg')

# Perform 2D FFT
fft_result = fft2D(image)

# Perform 2D IFFT
reconstructed_image = ifft2D(fft_result)
reconstructed_image = np.real(reconstructed_image)

# Scale the pixel values to the range of 0-255
reconstructed_image = (reconstructed_image - np.min(reconstructed_image)) * (255 / np.max(reconstructed_image))
reconstructed_image = reconstructed_image.astype(np.uint8)

# Display the images
cv2.imshow("Original Image", image)
cv2.imshow("Reconstructed Image", reconstructed_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

In this example, we first load an input image using cv2.imread(). Then, we apply the fft2D() function to perform a 2D FFT on the image. Afterward, the ifft2D() function is used to perform a 2D IFFT to reconstruct the image. Finally, we scale the pixel values and display both the original and reconstructed images using cv2.imshow().

Further Customization
Feel free to modify the example code to suit your specific needs. You can change the input image file, adjust the scaling or normalization techniques, and explore other image processing operations using the FFT and IFFT results.

References
If you would like to learn more about the Fast Fourier Transform and its applications in image processing, consider exploring the following resources:

numpy.fft documentation
OpenCV documentation
License
This code is provided under the MIT License. Feel free to use and modify it for your own purposes.
