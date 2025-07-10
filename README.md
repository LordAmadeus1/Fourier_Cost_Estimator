# Fourier Cost Estimator

This project aims to estimate the production cost of physical pieces from images by applying a Fourier Transform-based pipeline and AI-based length estimation. It reconstructs the primary shape from an image, measures its total length, and calculates an approximate cost based on user-defined parameters such as material price and line thickness.

## Proyect Overview

- Apply image preprocessing techniques to isolate the primary figure.
- Use 2D Fourier Transform (FFT) to analyze and filter image frequencies
- Reconstruct the figure by applying inverse FFT and binarizing the result.
- Detect contours and compute the total length assuming a fixed line thickness.
- Calculate estimated material cost based on predefined unit prices.
- Visualize intermediate steps: original image, frequency spectrum, reconstruction, and final shape.
