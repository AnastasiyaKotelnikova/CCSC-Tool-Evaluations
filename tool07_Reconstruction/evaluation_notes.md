# Evaluation Notes for Tool 07 - Reconstruction of Total Solar Irradiance by Deep Learning

1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7516668#.Y7xGBBXMLrk) into the designated folder:
   C:/Users/anast/Documents/GitHub/CCSC-Tool-Evaluations/tool07_Reconstruction_of_Total_Solar_Irradiance  
   
2. **Verified contents** - Jupyter notebooks:  
   - `YA_01_ReconstructionOfTSIbyDeepLearning.ipynb`
   - Multiple Python scripts: `tsinet_reconstructor.py`, `tsinet_train.py`, `tsinet_utils.py`
   - Supporting Folders: `default_model/`, `default_results/`, `figures/`, `results/`, `train_data/`
   - Metadata and setup: `README.md`, `evaluation_notes.md`, 'requirements.txt', 'environment.yml'

3. **Created the environment** using the original unmodified environment.yml:
    export SKLEARN_ALLOW_DEPRECATED_SKLEARN_PACKAGE_INSTALL=True
    conda env create -f environment.yml
    conda activate binder_env

4. Installed and launched Jupyter Notebook from within the binder_env environment:
    conda install jupyter
    jupyter notebook

5. Verified correct kernel using: !which python
   Output confirmed: /c/Users/anast/miniconda3/envs/binder_env/python

6. **Attempted to launch Jupyter Notebook**:
   jupyter notebook

### Problem Identified: 
The notebook opened and executed up to cell [3].
Library imports were successful despite a minor warning:
RuntimeError: module compiled against API version 0xe but this version of numpy is 0xd
This did not interrupt execution, but indicates a NumPy version mismatch: TypeError in reconstruct_tsinet()
This occurred inside: from tsinet_reconstructor import *
                      reconstruct_tsinet()
The error points to tsinet_utils.py during an internal call to TensorFlow: 
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '3'
import tensorflow as tf
This suggests a version or compatibility issue with TensorFlow or its submodules, but no syntax error or missing file was found in your installation or import logic.v

### Suggested Action: 
Downgrade or reinstall a compatible NumPy version: pip install numpy==1.19.5
Run with arguments explicitly: reconstruct_tsinet(dataset_name='TCTE', model_dir='default_model')
If needed, use from tensorflow import keras instead of standalone keras to avoid TF/Keras version mismatches.
Review process_args() logic in tsinet_reconstructor.py for argument expectations or required paths.
