# PNNL_Wildfire
Scripts from my work as a research associate working on developing models to update the fuels attributes and 40 Scott and Burgan Fire Behavior Fuel Models (F40) using updated disturbance data. 

The term "fuels attributes" collectively refers to the LANDFIRE Fuel Vegetation Type (FVT), Fuel Vegetation Cover (FVC), and Fuel Vegetation Height (FVH) raster datasets. 

__Background__: Up-to-date fuels data representing current vegetation conditions across the landscape are critical inputs for wildfire behavior models. While LANDFIRE (LF) offers annual releases of fuels data products, they are based on disturbance data through the end of the previous calendar year (as of LF 2022) and therefore do not reflect the impact of the most recent disturbances, which could lead to incorrect wildfire behavior modeling results. This necessitates a method to update the fuels products using updated disturbance information.

In previous years PNNL used a data-engineering approach to identify a set of rules that describe how Fuel Vegetation Type (FVT), Cover (FVC), and Height (FVH) change in response to disturbance and succession. These updated products, along with the LANDFIRE Zone and updated disturbance data, were then used in conjunction with the LANDFIRE Fuel Rules Database to develop an updated fuel models (F40) product. While the final F40 classification accuracy of these methods was generally high, with the misclassified areas being similar enough to have little impact on the modeled fire behavior, the method is labor and time intensive and tended to yield “many-to-one” rules. The aim of this work is to streamline the process of updating these products by developing machine learning models to learn the associations and apply the associations between the fuels products and disturbance data.  

# __Scripts__

-----

__F40_sampling__: Script to generate sample point layer to be used to train F40 model. Utilizes Arcpy and therefore requires an ArcGIS license with Spatial Analyst to run. NOTE: This is neither up-to-date nor functional at the time. 

__fuels_attributes_raster_eval__: Script to evaluate raster results. Explores accuracy metrics as well as misclassification distributions.

__fuels_modeling_wrapper__: Script to ultimately be used to update fuels data using most recent disturbance data. Running the script will both train FVT/FVC/FVH/F40 models givens sample points and generate predicted rasters for each target given paths to input rasters. Predicted FVT is used as an input to predicting FVC/FVH, and predicted FVT/FVC/FVH are used as inputs to predicted F40. Alternatively, the user can specify trained models to be used to generate predicted rasters. 

__train_models__: The model training component of fuels_modeling_wrapper. Given paths to sample point shapefiles, trains and saves sklearn Histogram-based Gradient Boosting Classifier models for each FVT/FVC/FVH/F40. Includes functions to evalute model results by performing a train/test split on the sample points data.  

__NOTE__: Most of the code in train_models is redundant to fuels_modeling_wrapper. It additionally has code to quickly evaluate model performance by performing a train/test split on the sample points. 





