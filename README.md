Plant Detection and Counting Using Computer Vision Techniques
Author: Azad Rasul (azad.rasul@soran.edu.iq)
Attribution: The code was inspired by the DroneMapper CropAnalysis project: DroneMapper CropAnalysis

Introduction
This project explores the use of computer vision techniques to detect and count plants using raster data. By leveraging tools like OpenCV, rasterio, and EarthPy, the tutorial processes raster datasets to identify and visualize plant locations. The method employs blob detection to count plants within a specified plot area accurately, providing valuable insights for applications in agriculture and environmental monitoring.

Data Download
Download the data from: DroneMapper Crop Analysis Data and extract it into the data/ directory of your notebook.

Dependencies
The following Python libraries are required to run the code in this repository:

GeoPandas
NumPy
Rasterio
Matplotlib
EarthPy
OpenCV
Pandas
You can install them using pip:

bash
Copy code
pip install geopandas numpy rasterio matplotlib earthpy opencv-python pandas
Code Overview
1. Import Libraries
The project starts by importing essential libraries for geospatial data handling, raster data processing, computer vision, and data visualization.

2. Reading and Processing Data
read_plot_data(file_path): Reads the plot data from a shapefile using GeoPandas.
load_raster(file_path): Loads raster data from a file using Rasterio.
mask_raster_with_plot(raster, plot): Masks the raster data with the plot extent, cropping and filtering the data.
generate_plant_model(dem_clip, dtm_clip): Generates a plant model by calculating the difference between the DEM (Digital Elevation Model) and the DTM (Digital Terrain Model).
3. Visualization
plot_plant_model_and_binary(plant_model, binary_image, plot_extent): Plots the plant model and binary image using EarthPy and Matplotlib.
4. Plant Detection
setup_blob_detector(): Configures the SimpleBlobDetector with parameters to detect blobs (plants) in an image.
detect_plants(binary_image_int, rgb): Detects plant keypoints in the binary image.
plot_plant_count(rgb, keypoints): Visualizes the detected plants with blue circles on the RGB image.
5. Image Normalization and Building True Color Image
normalize_rgb(image): Normalizes RGB image data to the range [0, 255].
build_true_color_image(rgb_clip): Ensures RGB values are correctly scaled for true color representation.
Usage
After setting up the environment and downloading the necessary data, run the Python scripts or Jupyter notebooks provided in this repository. Follow the instructions within the code to process the data, detect plants, and visualize the results.

License
This project is licensed under the MIT License.

Acknowledgements
This project is heavily inspired by the DroneMapper CropAnalysis project. Special thanks to the original authors for providing the data and initial code structure.
