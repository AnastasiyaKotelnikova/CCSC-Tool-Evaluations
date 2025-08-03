## Evaluation Summary for Tool 01: Predicting Solar Flares Using a Long Short-Term Memory Network

###  Project Name
**cscc_FlarePredict**

### Location
`tool01_Predicting/`

---

### Setup Steps Completed

1. **Downloaded and Extracted Files**
   - Obtained the ZIP archive from the tool list (https://zenodo.org/records/5739321#.YaWNcNDMKUk).
   - Extracted it into the `tool01_Predicting` directory.

2. **Verified Project Contents**
   - Confirmed presence of the following key files:
     - `cscc_FlarePredict.ipynb`
     - `environment.yml`
     - Relevant `.py`, `.csv`, and `README.md` files.

3. **Created a Conda Environment**
   - Used Python 3.6 and the provided environment file:
     ```bash
     conda env create -f environment.yml
     ```

4. **Activated the Environment**
   ```bash
   conda activate cscc_flarepredict

## Issue Encountered: Missing Kernel
Opened the notebook cscc_FlarePredict.ipynb successfully.

However, the kernel list did not include the cscc_flarepredict environment.

## Troubleshooting Performed
1. Attempted Kernel Registration
   python -m ipykernel install --user --name=cscc_flarepredict

2. Checked Kernel Registration
   jupyter kernelspec list
   
3. Other Actions
  Restarted the Jupyter Notebook server.
  Refreshed browser and interface.
  Confirmed that the cscc_flarepredict environment was active in Git Bash.
  Despite these steps, the kernel still did not appear as a selectable option within Jupyter. 

##  Potential Cause
  The tool appears to have been built for older versions of Python (e.g., 3.5–3.6).
  Compatibility or linking issues may exist with modern Jupyter installs.
  The notebook might reference a kernel name that no longer exists or was not properly registered.

## Outcome
   Environment successfully created: cscc_flarepredict (Python 3.6)
   Notebook file accessible: cscc_FlarePredict.ipynb
   Code execution blocked due to missing kernel in Jupyter
