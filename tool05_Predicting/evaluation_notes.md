# Evaluation Notes for Tool 05 - Predicting Solar Energetic Particles Using SDO/HMI Vector Magnetic Data Products and a Bidirectional LSTM Network

1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7516609#.Y7xChBXMLrk) into the designated folder: ~/Documents/GitHub/CCSC-Tool-Evaluations/tool05_Predicting_Solar_Energetic_Particles_with_BiLSTM/
   
2. **Verified contents** - Jupyter notebooks:  
     - `BiLSTM_SEP.ipynb`  
   - Multiple Python scripts: 'train.py', 'test.py', 'utils.py'
   - Folders: `data/`, `model/`, `results/`
   - Supporting documentation: `README.md`, `LICENSE`

3. **Created the environment** using:
conda create -n binder_env python=3.8
conda activate binder_env
pip install -r requirements.txt

5. **Activated environment**:
conda activate binder_env

7. **Attempted to launch Jupyter Notebook**:
   jupyter notebook

### Problem Identified: 
Pip installation failed with: pip._vendor.pyproject_hooks._impl.BackendUnavailable: Cannot import 'setuptools'
TensorFlow could not be imported due to protobuf-related error: TypeError: Descriptors cannot be created directly.
Importing tensorflow and numpy failed even after installation.
Manually installed tensorflow later gave: ImportError: cannot import name 'NDArray' from 'numpy.typing'

### Troubleshooting Steps Taken:
Attempted to verify TensorFlow and NumPy versions manually with:
import tensorflow as tf
import numpy as np
print(tf.__version__)
print(np.__version__)
→ Resulted in ModuleNotFoundError.
Tried reinstalling packages and fixing protobuf issues.
Switched Python environments and shells (base vs binder_env).
Verified that numpy 2.0.2 was incompatible with required numpy <= 1.19.2.

### Possible Causes:
The protobuf version installed is incompatible with the TensorFlow version used in the tool.
numpy 2.0.2 is incompatible with tensorflow-gpu==2.6.0.
Broken pip environment due to missing or corrupted setuptools.
Environment might have corrupted system paths during failed builds.

### Outcome:
Tool environment was partially created but ultimately non-functional.
Could not successfully import or run core dependencies like TensorFlow or NumPy.
Jupyter Notebook was not evaluated because its contents depend on TensorFlow code execution.
This error prevents any meaningful use or evaluation of the tool without resolution.

### Deliverables Verified:
All tool files were successfully extracted and accounted for.
Environment creation attempted with correct commands.
README and notebooks present.
requirements.txt file exists but causes critical install issues.

### Suggested Action: 
Downgrade protobuf to 3.20.0 or lower: pip install protobuf==3.20.0
Downgrade numpy to a compatible version: pip install numpy==1.19.2
Consider using Python 3.7 and older TensorFlow (e.g., 2.6.0 or 2.7.0) if compatibility persists.
Clean and recreate the environment from scratch using a modified requirements.txt.
Report this dependency break as a critical error for tool usage in the evaluation log.

