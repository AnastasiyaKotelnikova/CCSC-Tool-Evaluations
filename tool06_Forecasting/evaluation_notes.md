# Evaluation Notes for Tool 06 - Forecasting the Disturbance Storm Time Index with Bayesian Deep Learning

1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7529705#.Y8ApDBXMJD8) into the designated folder: C:/Users/anast/Documents/GitHub/CCSC-Tool-Evaluations/tool06_Forecasting_Storm_Time_Index_with_Bayesian_DL

2. **Verified contents** - Jupyter notebooks:  
     - `YA_01_ForecastingDstIndexBayesianDeepLearning.ipynb`  
   - `environment.yml` file
   - Folders: `.ipynb_checkpoints/`, `DSTT_Package/`, `figures/`
   - Supporting documentation: `README.md`, `LICENSE`, 'evaluation_notes.md'

3. **Created the environment** using: conda env create -f environment.yml

4. **Activated environment**: conda activate binder_env

5. **Attempted to launch Jupyter Notebook**:
   jupyter notebook

### Problem Identified: 
Environment creation failed due to an error with the sklearn package. After manually activating the partially created environment, importing TensorFlow led to a TypeError related to incompatible protobuf.

### Troubleshooting Steps Taken:
Read full stack trace and pip error logs during environment creation.
Noted the use of deprecated sklearn (instead of scikit-learn).
Verified that TensorFlow errors stem from protobuf >= 3.20, which breaks TensorFlow < 2.10 compatibility.
Consulted the README and environment.yml to cross-check versions and dependencies.

### Possible Causes:
Incorrect dependency: sklearn listed instead of scikit-learn, which is deprecated on PyPI.
Incompatible protobuf version: protobuf==3.20.3 breaks compatibility with tensorflow==2.6.1.
Possible lack of version pinning or outdated compatibility in environment.yml.

### Outcome:
Environment was not fully created on first attempt.
Manual activation succeeded, but core imports such as tensorflow and keras failed due to version conflicts.
No notebooks or scripts were executed due to these blocking errors.

### Deliverables Verified:
All required files and folders were extracted successfully.
Jupyter Notebook is present and readable.
environment.yml matches those referenced in README.md.
README.md explains the tool's function and dependencies.

### Suggested Action: 
Suggested Action:
Update environment.yml:
- Replace sklearn with scikit-learn.
- Downgrade protobuf to <3.20, e.g. protobuf=3.19.6.
Recreate the environment after edits:
- conda env remove -n binder_env
- conda env create -f environment.yml
