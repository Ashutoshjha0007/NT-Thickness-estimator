# NT-Thickness-estimator
Used Deep-learning to estimate Nuchal Translucency Thickness and Performed image processing on Ultrasound Images, Compared the NT thickness to Normal range and calculated the risk of Down Syndrome.


### Project Description: Nuchal Translucency Measurement and Classification

**Objective**:
The project aims to develop a system for measuring nuchal translucency (NT) thickness in fetal ultrasound images and classify the measurements as either "Normal" or "Increased". NT thickness is a key marker for assessing the risk of chromosomal abnormalities such as Down syndrome in early pregnancy.

**Components**:

1. **Image Preprocessing**:
    - The system begins by processing input ultrasound images to create binary masks. These masks highlight the regions of interest (i.e., the nuchal area) for further analysis.

2. **Binary Mask Generation**:
    - Example predictions of binary masks are generated using a thresholding method where pixel values above a certain threshold are set to 1 (indicating the nuchal region), and the rest are set to 0.

3. **NT Thickness Calculation**:
    - The primary function, `calculate_thickness`, processes each binary mask to determine the NT thickness. Key steps include:
        1. **Labeling Connected Components**: Identify all connected regions in the binary mask.
        2. **Selecting the Largest Component**: Determine which connected component corresponds to the nuchal region by size.
        3. **Area Calculation**: Compute the area of the largest connected component.
        4. **Thickness Measurement**: Calculate the thickness in millimeters using a given scale factor, which converts pixel dimensions to real-world measurements.

4. **Classification**:
    - The calculated NT thickness is then classified into "Normal" or "Increased" based on a predefined cutoff value (e.g., 3.5 millimeters). Measurements equal to or above the cutoff are classified as "Increased".

5. **Example Usage**:
    - The provided code includes an example usage scenario where random binary masks are generated, processed, and classified. The results are printed with the thickness and classification for each mask.

**Code Structure**:

- **Libraries and Dependencies**: The project uses standard libraries such as NumPy and OpenCV for numerical and image processing tasks.
- **Function Definitions**:
    - `calculate_thickness(binary_mask, scale_factor)`: Calculates NT thickness from a binary mask.
- **Main Execution**:
    - A loop processes multiple binary masks, calculates their NT thickness, classifies them, and prints the results.


**Outcome**:
The system outputs the NT thickness measurements and classifications for each processed ultrasound image, which can be used by medical professionals for early diagnosis and intervention planning.
