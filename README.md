# PNNL_Wildfire
Scripts from my work as a research associate working on developing models to update the fuels attributes and 40 Scott and Burgan Fire Behavior Fuel Models (F40) using updated disturbance data. 

The term "fuels attributes" collectively refers to the LANDFIRE Fuel Vegetation Type (FVT), Fuel Vegetation Cover (FVC), and Fuel Vegetation Height (FVH) raster datasets. 

__F40_model_development__ - Script where I did initial testing and development of models to predict the LANDFIRE F40 raster. 

__F40_model_eval__ - Script to evaluate the results of the F40 model, both on the sample point test set and raster data. The raster evaluation section is currently a work in progress. 

__F40_raster_predict__ - Script that ingests the source datasets and applies the F40 model to generate a predicted F40 raster. 

__F40_train_model__ - Script to train the F40 model. Based off of resulst from F40_model_development.

__FVC/FVH/FVT_raster_predict__ - Scripts that ingest the source data and apply the FVC/FVH/FVT model to generate respective predicted rasters.

__FVC/FVH/FVT_train_model__ - Scripts to train FVC/FVH/FVT models. 

__fuels_attributes_model_development__ - Script used to develop and test models for FVC/FVH/FVT.

__fuels_attributes_model_eval__ - Script used to evaluate model performance on the sample points test set. 

__fuels_attributes_model_eval__ - Script used to evaluate FVC/FVH/FVT model performance on the raster data. 

__LF22-23_F40_GROUP_eda__ - Script to explore whether and to what degree there were transitions between FBFM40 "parent classes". The purpose of this is to determine whether LANDFIRE was treating these classes as structural and static in order to decide whether it makes sense to include F40_GROUP as a predictor. 
