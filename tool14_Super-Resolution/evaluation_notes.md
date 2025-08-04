# Evaluation Notes for Tool 14 - Super-Resolution of SOHO/MDI Magnetograms of Solar Active Regions Using SDO/HMI Data and an Attention-Aided Convolutional Neural Network

## What Was Done
1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/15250172) into the designated folder:  
   C:/Users/anast/Documents/GitHub/CCSC-Tool-Evaluations/tool14_YA_01_ReconstructionOfTSIbyDeepLearning


2. **Verified contents** 
Jupyter Notebook: prediction_workflow.ipynb
Python Scripts: model/model_solarcnn
Supporting folders: data/, model/, result/
No requirements.txt or environment.yml provided


3. **Set up environment**
Manually activated pre-configured conda environment base
Verified Python installation: python 3.8.6
Attempted installation of missing dependencies via pip


4. **Issues Encountered**
Missing or Unlisted Dependencies
tensorflow-addons was not installed and not listed in the archive
Manual installation attempt via: pip install tensorflow-addons
failed with: ERROR: Could not find a version that satisfies the requirement tensorflow-addons
astropy module was not installed and not listed
Missing astropy caused data loading to fail: ModuleNotFoundError: No module named 'astropy'
Model Dependency Warning: Model loading required custom objects (mix_loss, ssim_metric) and worked correctly assuming those were defined in model.py
TensorFlow executed successfully, but emitted compatibility warnings: UserWarning: Protobuf gencode version 5.28.3 is exactly one major version older than the runtime version 6.31.1...


5. **Undefined Variable**:
The notebook attempted to iterate over test_input before successful loading: NameError: name 'test_input' is not defined
This was due to the previous failure in loading data from FITS files (missing astropy).


6. **Recommendations**
- Add requirements.txt or environment.yml with: 
tensorflow==2.11.0
tensorflow-addons
astropy
h5py
numpy
matplotlib
- Specify compatible Python version (e.g., python=3.8.6) in documentation.
- Include data samples or paths for reproducibility, or adjust notebook to handle missing files gracefully.



