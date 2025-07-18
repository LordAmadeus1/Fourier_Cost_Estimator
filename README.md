# Fourier Cost Estimator

This project aims to estimate the production cost of physical pieces from images by applying a Fourier Transform-based pipeline and AI-based length estimation. It reconstructs the primary shape from an image, measures its total length, and calculates an approximate cost based on user-defined parameters such as material price and line thickness.

## Proyect Overview

- Apply image preprocessing techniques to isolate the primary figure.
- Use 2D Fourier Transform (FFT) to analyze and filter image frequencies
- Reconstruct the figure by applying inverse FFT and binarizing the result.
- Detect contours and compute the total length assuming a fixed line thickness.
- Calculate estimated material cost based on predefined unit prices.
- Visualize intermediate steps: original image, frequency spectrum, reconstruction, and final shape.

## Project Structure

Fourier_Cost_Estimator/

┣ notebooks/

┣  └── preprocessing_01.ipynb

┣  └── fft_analysis_02.ipynb

┣  └── skeleton_analysis_03.ipynb

┣  └── cost_calculation_04.ipynb

┣ outputs/

┣  └── outputs_preprocessing/ #results of preprocessing progess

┣  └── outputs_fft_analysis/ #reconstructed images

┣ src/

┣  └── preprocessing.py

┣  data/

┣  └── materials_price.csv

┣  scripts/

┣ README.md

└── requirements.txt

## Preprocessing 

The `preprocessing.ipynb` notebook focuses on preparing input images for the Fourier-based cost estimation pipeline. It applies a series of computer vision techniques such as grayscale conversion, adaptive thresholding, and morphological operations to isolate the primary figure from background noise.

The result is a clean, binarized image that highlights the main shape to be processed in the following Fourier Transform step.

**Example Output:**

<img width="645" height="707" alt="character_result" src="https://github.com/user-attachments/assets/8656ac83-8e6b-41ec-bc53-bb2fea88d8a0" />

This step is essential to improve the accuracy of contour detection, shape reconstruction, and cost estimation in the later stages of the project.

## FFT Analysis Notebook

The fft_analysis.ipynb notebook performs the core frequency-based analysis within the cost estimation pipeline. It applies a 2D Fast Fourier Transform (FFT) to the preprocessed image in order to convert the spatial domain into the frequency domain.

Key processes include:

Computing the Fourier Transform of the binary image to obtain its frequency spectrum.

Visualizing the magnitude spectrum to identify high and low frequency components.

Applying frequency filtering to isolate relevant components, removing noise or insignificant frequencies.

Performing an inverse FFT (iFFT) to reconstruct the image based on the filtered spectrum.

Preparing the reconstructed image for contour detection in the subsequent steps.

This notebook is essential to enhance the accuracy of shape reconstruction and optimize cost estimation by reducing background noise and isolating the figure’s structural frequencies.

<img width="1000" height="400" alt="results_fft_analysis" src="https://github.com/user-attachments/assets/739d022f-86d1-4f92-8acc-b3e13ca03803" />


## Skeleton Analysis

The 03_skeleton_analysis.ipynb notebook performs structural simplification of the preprocessed shape using morphological skeletonization. This step aims to reduce the shape to its essential linear structure while preserving topology.

Key processes included:

- Applying binary skeletonization to extract the central "spine" of the figure.
- Visualizing both the original and skeletonized versions to validate correctness
- Saving the resulting skeleton image for later use in length estimation and cost calculation

This process is crucial for simplifying the geometry before estimating material usage based on shape length and complexity.

<img width="1000" height="500" alt="ske_compare_final" src="https://github.com/user-attachments/assets/af97cc33-b99e-4a2a-992e-535a40f92b8a" />



