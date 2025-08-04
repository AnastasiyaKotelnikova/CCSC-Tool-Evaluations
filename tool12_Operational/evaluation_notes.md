# Evaluation Notes for Tool 12 - Operational Prediction of Solar Flares Using a Transformer-Based Framework

## What Was Done
1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/10201356) into the designated folder:  
   ~/Documents/GitHub/CCSC-Tool-Evaluations/tool12_Operational_Solar_Flare_Prediction_with_Transformer/

2. Created and activated the virtual environment solarflare12 using Python 3.8.6, matching the project requirements.
   
3. Installed required packages listed in the documentation and observed in code:

tensorflow==2.8.0

keras==2.6.0

numpy==1.19.5

pandas==1.5.1

scikit-learn (latest compatible)

Other packages including: astropy, scipy, joblib, matplotlib, requests, oauthlib, google-auth, etc.

5. Verified contents of the extracted directory:

Jupyter notebook: ccsc_solarflare.ipynb

Scripts: SolarFlareNet_test.py, SolarFlareNet_train.py, SolarFlareNet_model.py

Folders: notebooks/, dataset/, models/, utils/, and supporting files like README.md and requirements.txt

6. Tested notebook execution:

Opened ccsc_solarflare.ipynb in Jupyter Lab

Attempted to run sections:

2.2 Predicting with Pretrained Models

2.2.1 SolarFlareNet Model Training

## Observations
Package installation succeeded, with some compatibility warnings related to legacy versions (e.g., tensorflow, keras, numpy).

Jupyter notebook launched correctly in the virtual environment.

Execution failed at model import due to a binary incompatibility in sklearn.utils.murmurhash:
ValueError: numpy.dtype size changed, may indicate binary incompatibility. Expected 96 from C header, got 88 from PyObject

Error occurs during import of class_weight from sklearn.utils

Likely caused by mismatch between installed numpy and prebuilt C-extensions in scikit-learn

## Summary
The tool was set up and run exactly as provided, using the required package versions. The notebook runs but fails during execution due to a known compatibility issue between numpy and compiled components within scikit-learn. No modifications were made, per the instructions to assess the original setup and behavior.
