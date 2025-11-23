# SPATIAL STATISTICS FOR REMOTELY SENSED IMAGES
## UNIT 3: IMAGE TRANSFORMATION AND SEGMENTATION
### Comprehensive Classroom Notes

---

## 3.1 IMAGE TRANSFORMATION

### 3.1.1 Definition and Concept

**Image Transformation** refers to a process in which we manipulate various bands of image data. The data is manipulated from one or more than one multi-spectral images. These images may consist of the same area that is captured at different times. 

In basic image transformation, we apply arithmetic operations to our image data. It is the ability to convert an image from one domain to another.

---

## 3.2 SPECTRAL INDICES (SI)

### 3.2.1 Definition

**Spectral Indices (SI)** characterize the specific features of interest of a target by identifying its biophysical and chemical properties. These features of interest enable us to identify plant, water, soil, and various forms of built-up regions such as roads, houses, and other regions.

### 3.2.2 Concept and Formulation

Generally, spectral indices are the combination of pixel values from two or more spectral bands in a multispectral image, designed to highlight pixels showing the relative abundance or lack of a land cover type of interest in an image.

Each pixel is described by **m** values, where **m** is the number of spectral bands.

A SI is calculated using some of these values (depends on specific index) in a mathematical form. In its most general form, it is the difference between two selected bands normalized by their sum.

### 3.2.3 Common Formulas for Spectral Indices

**General Formula 1:**
$$SI = \frac{b_x - b_y}{b_x + b_y}$$

where:
- $b_x$ and $b_y$ are the reflectance values of a pixel in bands x and y

**General Formula 2:**
$$SI = \frac{b_x}{b_y}$$

---

## 3.3 TYPES OF SPECTRAL INDICES

Several spectral indices are commonly used in remote sensing:

1. **Normalized Difference Vegetation Index (NDVI)**
2. **Normalized Difference Water Index (NDWI)**
3. **Normalized Difference Building Index (NDBI)**
4. **Normalized Difference Moisture Index (NDMI)** [Note: Some sources refer to this as NDII]
5. **Soil-Adjusted Vegetation Index (SAVI)**
6. **Enhanced Vegetation Index (EVI)**

---

## 3.4 NORMALIZED DIFFERENCE VEGETATION INDEX (NDVI)

### 3.4.1 Definition and Formula

**NDVI** quantifies vegetation by measuring the difference between near infrared light (which vegetation strongly reflects) and red light (which vegetation absorbs).

$$NDVI = \frac{NIR - RED}{NIR + RED}$$

where:
- **NIR** → Light reflected in the near infrared spectrum
- **RED** → Light reflected in the red range of the spectrum

### 3.4.2 Range and Interpretation

The NDVI value varies from **-1 to +1**. 

- **Higher value of NDVI** reflects high near infrared reflectance, which means dense greenery (forests)

**Value Ranges and Interpretation:**
- NDVI defines values from **-1 to +1**, where **negative values** are primarily formed from clouds, water, smoke, and rocks and bare soil
- **Values close to zero** are from rocks and bare soil
- **Very small values (0.1 or less)** correspond to empty areas of rocks, sand, or snow
- **Moderate values (0.2 to 0.3)** represent shrubs
- **Large values (0.6 to 0.8)** indicate tropical forest and dense greenery

### 3.4.3 NDVI Saturation

#### Definition and Problem

**NDVI Saturation** is a well-known phenomenon and limitation in the use of normalized difference vegetation index that should not be ignored. Saturation occurs when the amount of leaf pigmentation reaches a critical point, thus decreasing NDVI sensitivity.

#### Cause

As the reflectance in the near infrared bands keeps increasing at the final stage of crop development, the red light remains absorbed. In other words:
- NIR value keeps growing
- RED value stays the same

As a result, the **NDVI values become less reliable indicators of crop prediction**.

[**Important Conceptual Note:** NDVI saturation is particularly problematic in high-biomass regions where vegetation is very dense. This is precisely why Enhanced Vegetation Index (EVI) was developed to overcome this limitation.]

---

## 3.5 MULTISPECTRAL AND HYPERSPECTRAL IMAGING

### 3.5.1 Multispectral Imaging

**Multispectral Imaging** is a technique that involves capturing and analyzing images at multiple discrete spectral bands within the electromagnetic spectrum.

Multispectral imaging is characterized by capturing information at several combinations of predefined bands. This allows for extraction of spectral signatures and information from different parts of the spectrum.

### 3.5.2 Hyperspectral Imaging

**Hyperspectral Imaging** acquires data across a continuous range of wavelengths (rather than discrete bands).

---

## 3.6 ENHANCED VEGETATION INDEX (EVI)

### 3.6.1 Definition and Purpose

**Enhanced Vegetation Index (EVI)** is an advanced vegetation index developed to improve upon NDVI in situations where NDVI's saturation condition exists. 

It is generally useful in areas with dense vegetation like tropical forests and reduces atmospheric and soil background effects that often limit NDVI.

### 3.6.2 Formula

$$EVI = G \times \frac{NIR - RED}{NIR + G \times RED - B \times BLUE + L}$$

where:
- **NIR** = Near infrared band reflectance
- **RED** = Red band reflectance
- **BLUE** = Blue band reflectance
- **G** = Gain factor (usually 2.5)
- **L** = Canopy background adjustment factor (usually 1)
- **B** = Coefficient of atmospheric resistance (usually 6 and 7.5)

### 3.6.3 MODIS Standard EVI Formula

The standard MODIS (NASA) version of EVI is:

$$EVI = 2.5 \times \frac{NIR - RED}{NIR + 6 \times RED - 7.5 \times BLUE + 1}$$

### 3.6.4 Properties of EVI

1. **Range:** -1 to +1 (similar to NDVI)
2. **Healthy vegetation:** Gives higher values in the range 0.3–0.9
3. **Improves sensitivity:** In high biomass regions
4. **Atmospheric correction:** Uses the BLUE band to correct for atmospheric scattering
5. **Minimizes effects:** Reduces soil reflectance effects

### 3.6.5 MODIS Instrument Information

**Note:** MODIS is a key instrument on NASA satellites:
- **Terra** (Launched in 1999)
- **Aqua** (Launched in 2002)

MODIS captures data in **36 spectral bands**.

---

## 3.7 FOURIER TRANSFORMATION

### 3.7.1 Definition and Purpose

**Fourier Transformation** is an important image processing tool which is used to decompose an image into its sine and cosine components. The output of the transformation represents the image in the Fourier or **frequency domain**, while the input image is in the **spatial domain**.

In the Fourier domain image, each point represents a particular frequency contained in the spatial image.

### 3.7.2 Applications

Fourier transformation is used in a wide range of applications such as:
- Image analysis
- Image filtering
- Image reconstruction
- Image compression
- Medical fields like Digital Imaging

### 3.7.3 Fourier Transformation in Spatial Statistics

Fourier transformation in spatial statistics is mainly about moving from spatial patterns to frequency representation, helping to analyze scale, periodicity, and structure of spatial processes.

---

## 3.8 DISCRETE FOURIER TRANSFORM (DFT)

### 3.8.1 Definition

The **Discrete Fourier Transform (DFT)** is the sampled Fourier transform and therefore does not contain all frequencies forming an image, but only a set of samples which is large enough to fully describe the spatial domain image.

The number of frequencies corresponds to the number of pixels in the spatial domain image, i.e., the image in the spatial and Fourier domains are of the same size.

### 3.8.2 2D Discrete Fourier Transformation Formula

For a square image of size **N×N**, the two-dimensional discrete Fourier transformation is given by:

$$F(k,\ell) = \sum_{i=0}^{N-1} \sum_{j=0}^{N-1} f(i,j) \cdot e^{-j2\pi(\frac{ik}{N} + \frac{j\ell}{N})}$$

where:
- **f(i,j)** is the image in the spatial domain (input image)
- **F(k,ℓ)** is the transformed image in the frequency domain (output image)
- The exponential term is the basis function corresponding to each point in the frequency domain

### 3.8.3 Basis Functions in Fourier Space

In Fourier space, the basis functions are sine and cosine waves with increasing frequencies:
- **F(0,0)** corresponds to the lowest brightness
- **F(N-1, N-1)** corresponds to the highest frequency

### 3.8.4 Inverse Fourier Transform

When the Fourier image is transformed back to the spatial domain, the inverse Fourier transform is given by:

$$f(i,j) = \frac{1}{N^2} \sum_{k=0}^{N-1} \sum_{\ell=0}^{N-1} F(k,\ell) \cdot e^{j2\pi(\frac{ik}{N} + \frac{j\ell}{N})}$$

---

## 3.9 CONTINUOUS FOURIER TRANSFORMATION

### 3.9.1 Fourier Series

**Fourier Series** simply states that a periodic signal can be represented as the sum of sine and cosine waves, each multiplied with a certain weight.

### 3.9.2 Continuous Fourier Transform Formula

The continuous Fourier series can be represented by the following transformation formula:

$$F(k,\ell) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(a,b) \cdot e^{-j2\pi(ka + b\ell)} \, da \, db$$

### 3.9.3 Inverse Continuous Fourier Transform

The inverse can be calculated by:

$$f(a,b) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} F(k,\ell) \cdot e^{j2\pi(ka + b\ell)} \, dk \, d\ell$$

---

## 3.10 DIFFERENCE BETWEEN FOURIER SERIES AND FOURIER TRANSFORMATION

Although both Fourier series and Fourier transformation are given by Fourier, the key difference between them is:

- **Fourier Series:** Applied on **periodic signals**
- **Fourier Transformation:** Applied on **non-periodic signals**

Since images are **non-periodic in nature**, Fourier transformation is used to convert them into the frequency domain.

### 3.10.1 Key Distinction: Periodic vs. Non-Periodic Signals

**Remark:** The main difference between periodic and non-periodic signals is that periodic signals repeat after a specific time period, while non-periodic signals do not repeat. That is why non-periodic signals are sometimes random signals.

---

## 3.11 BASIS FUNCTIONS

**Basis Functions** are mathematical functions used in statistical modeling and machine learning to represent complex relationships between variables.

---

## 3.12 WAVELET TRANSFORMATION

### 3.12.1 Definition and Concept

A **Wavelet** is a wave-like oscillation with an amplitude that begins at zero, increases, and then decreases back to zero. It can be visualized as an oscillation like one recorded by a seismograph.

Therefore, wavelets are functions that are concentrated in time and frequency around a certain point. This transformation technique is used to overcome the drawbacks of Fourier transformations.

### 3.12.2 Motivation: Why Wavelets Over Fourier?

Although Fourier transformation deals with frequencies, **it does not provide temporal details**. 

**Wavelet Transformation** finds its most appropriate use in **non-stationary signals**. This transformation:
- Achieves good frequency resolution for low-frequency components
- Achieves good temporal resolution for high-frequency components

### 3.12.3 Basic Properties of Wavelets

Wavelets have two basic properties:

#### 1. Scale Parameter
- **Defines how stretched a wavelength is**
- **Related to frequency** (how "zoomed out" or "zoomed in" we are)
- Related to: Shape, Skewness, Kurtosis

#### 2. Location Parameter
- **Defines where the wavelet is positioned in time or space**
- Related to: Mean

### 3.12.4 Mathematical Definition

Mathematically, a wavelet is a function used to divide a time component signal into different scale components. Given function:

$$\psi_{a,b}(t) = \frac{1}{\sqrt{a}} \psi\left(\frac{t-b}{a}\right)$$

where:
- **ψ** is the wavelet function
- **a** is the scaling parameter which measures the degree of compression or scale
- **b** is the translation parameter which determines the time location of the wavelet

### 3.12.5 Comparison: Wavelet vs. Fourier Transformation

**Key Difference:**

The main difference between wavelet transformation and Fourier transformation is that **wavelet transformation can analyze a signal by both time and frequency simultaneously**. Therefore, it can easily recover localized signal information.

Fourier transformation provides only frequency information without temporal localization.

---

## 3.13 TEMPORAL AND SPATIAL RESOLUTION

### 3.13.1 Spatial Resolution

**Spatial Resolution** refers to the ability to distinguish between different locations in an image.

### 3.13.2 Temporal Resolution

**Temporal Resolution** refers to the ability to measure different locations in an image over a period of time interval.

---

## 3.14 IMAGE SEGMENTATION

### 3.14.1 Definition

**Image Segmentation** is a method in which a digital image is broken into various subgroups called image segments, which help us in reducing complexity of the image to make processing or analyzing the image easier.

In other words, segmentation involves assigning labels to the pixels. All picture elements or pixels that belong to the same category have a common blend and common label assigned to them.

### 3.14.2 Practical Application

Consider a scenario where a picture has to be provided as input for object detection. Rather than processing the entire image, a region selected by a segmentation algorithm can be input to the detector. This will prevent the detector from processing the whole image and hence reducing inference time.

### 3.14.3 Note on Classification

When image data follows multivariate normal distribution, it can be classified on the principle of confusion matrix.

---

## 3.15 APPROACHES TO IMAGE SEGMENTATION

There are two common approaches to image segmentation:

### 3.15.1 Similarity Approach

This approach involves detecting similarity between image pixels to form a segment based on a given threshold. Machine learning algorithms like clustering are used with this type of approach to segment an image based on similarity of pixels.

### 3.15.2 Discontinuity Approach

This approach depends on discontinuity of the pixel intensity values of the image. Line, point, and edge detection techniques use this type of approach for obtaining intermediate segmentation results that can be further processed to obtain the final segmented image.

---

## 3.16 IMAGE SEGMENTATION TECHNIQUES

There are five common image segmentation techniques:

1. **Threshold-based image segmentation**
2. **Edge-based image segmentation**
3. **Region-based image segmentation**
4. **Clustering-based image segmentation**
5. **Artificial Neural Network (ANN) based image segmentation**

---

## 3.17 THRESHOLD-BASED IMAGE SEGMENTATION

### 3.17.1 Definition and Concept

**Threshold-based segmentation** is a simple form of image segmentation. It is a way of creating a binary or multi-color image based on fixing a threshold value on the pixel intensity of the original image.

In this thresholding process, we consider the intensity histogram of all the pixels in the image, and we set a threshold to divide the image into sections.

### 3.17.2 Example

Consider image pixels ranging from 0–255. Consider image pixels ranging from 0–60 by setting a threshold value of **T = 60**. So all the pixels with values less than or equal to 60 will be provided a value of **0 (black)**, and all the pixels with values greater than 60 will be provided with a value of **255 (white)**.

### 3.17.3 Mathematical Formulation

A single threshold **T** is applied to the image **f(x,y)**:

$$g(x,y) = \begin{cases}
1, & \text{if } f(x,y) > T \quad \text{(object)} \\
0, & \text{if } f(x,y) < T \quad \text{(background)}
\end{cases}$$

### 3.17.4 Spatial/Statistical Approaches to Thresholding

In spatial/statistical approaches, we use prior knowledge of pixel intensity distribution through:
- Gaussian modeling
- Mixture modeling
- Maximum likelihood estimation
- Bayesian decision rules

These can define the thresholds in spatial statistics based on probability bounds.

---

## 3.18 TYPES OF THRESHOLDING

### 3.18.1 Manual Thresholding

**Steps:**

1. Choose the initial threshold value $T_0$
2. Segment the image into two regions $G_1$ and $G_2$ using the threshold value
3. Find the mean of pixels of regions $G_1$ and $G_2$ as $M_1$ and $M_2$ respectively
4. Calculate new threshold: $T_{new} = \frac{M_1 + M_2}{2}$, and go back to step 2
5. Continue the process until $|T_{r} - T_{r-1}| \leq T'$, where $T'$ is some value defined by the user

**Remark:** The initial threshold value, which is selected by the user, depends on prior knowledge.

### 3.18.2 Optimal Thresholding

**Optimal Thresholding** technique can be used to minimize the misclassification of pixels performed by the segmentation.

---

## 3.19 HISTOGRAM-BASED METHOD FOR OPTIMAL THRESHOLDING

### 3.19.1 Principle

1. If the histogram of pixel intensity distribution is **bi-modal** (has two peaks), the value between peaks is the **optimal threshold**
2. This method **maximizes the variance between the classes**

### 3.19.2 Probability-Based Approach

The probability of a pixel is given by the following formula:

$$P(z) = P_1 p_1(z) + P_2 p_2(z)$$

where:
- $P_1(z)$ = PDF (Probability Density Function) of background pixels
- $P_2(z)$ = PDF of object pixels

### 3.19.3 Decision Rule

We consider a threshold value **T'** as the initial threshold. The value of the pixel to be determined:

$$f(x,y) > T' \Rightarrow (x,y) \text{ is object}$$
$$f(x,y) \leq T' \Rightarrow (x,y) \text{ is background}$$

### 3.19.4 Error Analysis

**Error Type 1:** Background pixel misclassified as object:
$$E_1(T') = \int_{T'}^{\infty} P_1(z) \, dz$$

**Error Type 2:** Object pixel misclassified as background:
$$E_2(T') = \int_{0}^{T'} P_2(z) \, dz$$

**Total Classification Error:**
$$E(T') = P_1 E_1(T') + P_2 E_2(T')$$

To minimize this error, we take the partial derivative:

$$\frac{\partial E(T')}{\partial T'} = 0$$

### 3.19.5 Gaussian Assumption

For Gaussian pixel density, the probability density function can be calculated as:

$$P(z) = P_1 \exp\left(-\frac{(z - M_1)^2}{2\sigma_1^2}\right) + P_2 \exp\left(-\frac{(z - M_2)^2}{2\sigma_2^2}\right)$$

where:
- $\sigma_1, \sigma_2$ are standard deviations of density regions
- $M_1, M_2$ are means of intensity of pixels in the regions

---

## 3.20 EDGE-BASED IMAGE SEGMENTATION

### 3.20.1 Definition and Concept

**Edge-based image segmentation** depends on edges found in an image by using various edge detection operators. These edges are image locations of discontinuity in gray levels, color, texture, etc.

When we move from one region to another, the gray level may change. If we can find discontinuity, we can identify that there is an edge.

### 3.20.2 Important Note

A variety of edge detector operators are available, but the resulting image is an **intermediate segmentation result** and should not be confused with the final segmentation image. We have to perform further processing on the image to obtain the final segmented image.

### 3.20.3 Edge Properties

Edges are usually associated with **magnitude** and **direction**. Some edge detectors give both direction and magnitude.

---

## 3.21 GRADIENT OPERATOR FOR EDGE DETECTION

### 3.21.1 Definition

Let **I(x,y)** be the pixel intensity at location (x,y). The gradient is:

$$\nabla I(x,y) = \left(\frac{\partial I}{\partial x}, \frac{\partial I}{\partial y}\right)$$

### 3.21.2 Gradient Magnitude (Edge Strength)

$$||\nabla I(x,y)|| = \sqrt{\left(\frac{\partial I}{\partial x}\right)^2 + \left(\frac{\partial I}{\partial y}\right)^2}$$

**Interpretation:** A large value of $||\nabla I||$ indicates that there is a potential edge or perfect edge.

[**Important Note:** Large values of semi-variance between adjacent pixels also indicate that there is an edge. This is the spatial statistics interpretation of edge strength using variance measures.]

---

## 3.22 REGION-BASED IMAGE SEGMENTATION

### 3.22.1 Definition

**Region-based Segmentation** is a method employed in computer vision and image analysis. It clusters or partitions an image int
