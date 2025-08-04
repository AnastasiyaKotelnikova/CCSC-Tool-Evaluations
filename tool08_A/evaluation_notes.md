# Evaluation Notes for Tool 08 - A Transformer-Based Framework for Geomagnetic Activity Prediction


1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7514451#.Y7uEWhXMLrc) into the designated folder:
   CCSC-Tool-Evaluations/tool08_Transformer_Based_Geomagnetic_Activity_Prediction
   
2. **Verified contents**
   - Jupyter notebooks: `YA_01_ATransformerBasedFrameworkForGeomagneticActivity.ipynb`  
   - Multiple Python scripts: `KpNet_test.py', 'plot_figures.py, README.md`
   - Folders: `default_models/', 'default_results/', 'figures/`
 
3. **Created the environment** using the environment.yml file:
 conda env create -f environment.yml
 conda activate binder_env

4. Verified core packages:
  Python 3.8.20 
  TensorFlow 2.8.0 
  Keras 2.8.0 
  NumPy 1.22.4 
  Others matched the expected versions listed in the notebook

5. Launched Jupyter Notebook successfully: jupyter notebook
  Opened YA_01_ATransformerBasedFrameworkForGeomagneticActivity.ipynb
  Kernel initialized properly (Python 3, binder_env)

### Problem Identified: 
1. NumPy ABI mismatch:
   Error: RuntimeError: module compiled against API version 0xe but this version of numpy is 0xd
   This suggests that one or more packages (likely tensorflow-probability) were compiled against a different NumPy version.

2. TypeError in KpNet_test.py:
   Error: TypeError: 'ABCMeta' object is not subscriptable
   Location: PIL._typing.py
   Cause: Likely due to a conflict or incompatibility in the Pillow version or with Python typing extensions.

### Notebook Execution Summary
Cells Executed:
   Library imports (with warnings)
   Pretrained model test → failed due to ABCMeta issue
   TensorFlow-probability runtime warning due to NumPy mismatch

Result:
   Notebook did not fully execute due to critical runtime errors.
   Functional model evaluation and plots were not generated due to above issues.
