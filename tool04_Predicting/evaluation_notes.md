## Evaluation Notes for Tool 04 - Predicting Coronal Mass Ejections Using SDO/HMI Vector Magnetic Data Products and Recurrent Neural Networks

### What Was Done
1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7415731#.Y5IkXXbMJD8) into the designated folder:  
   ~/Documents/GitHub/CCSC-Tool-Evaluations/tool04_Predicting_Coronal_Mass_Ejections_with_RNN/.

2. **Verified contents** of the extracted folder:
   - Jupyter notebooks:  
   - `YA_01_Predicting_CME_with_RNN.ipynb`  
   - 'environment.yml' file
   - Supporting documentation: `README.md`, `LICENSE`, '.gitignore'
   - No additional subfolders
3. **Environment Setup**:
   - Created Conda environment using: conda env create -f environment.yml
   - Installation took ~10–15 minutes due to resolution of older tensorflow-gpu, keras==2.8.0, and associated package downgrades.
   - Activated environment: conda activate binder_env
   - Launched Jupyter Notebook: jupyter notebook
     
### Problem Identified: Jupyter Notebook File Tree Does Not Render
Although Jupyter successfully launched and opened at http://localhost:8892/tree, the file browser view failed to load.
Only the orange Jupyter logo appeared — no files or folders were listed.

### Troubleshooting Steps Taken
Waited several minutes for the interface to load — no change
Refreshed browser and used hard reload (Ctrl+F5) — issue persisted
Re-ran jupyter notebook multiple times — same result
Confirmed active directory was correct before launching
Verified conda environment activation (binder_env)
No visible error messages in terminal after launch

### Possible Causes
Incompatibility between Jupyter Notebook and older Python or frontend versions
Chrome rendering/cache issue
Broken or outdated notebook package used in the environment
Port conflict or stale browser session
Jupyter kernel misconfiguration or missing dependency

### Outcome
Environment was created and activated successfully
All dependencies were installed
Jupyter interface failed to load the file browser
Unable to proceed with tool evaluation due to inaccessible notebook


### Deliverables Verified
Files extracted and organized properly
Environment successfully created: binder_env
No installation errors
Jupyter frontend failed to render, blocking further progress

### Suggested Action
Try launching in Firefox, Edge, or Chrome Incognito
Clear browser cache
Launch notebook using a new port: jupyter notebook --no-browser --port=8893
Try launching with JupyterLab instead: conda install jupyterlab
                                       jupyter lab
                                       
Open notebook in VS Code as a workaround
Consider updating the environment.yml to support Python 3.8+ and modern Jupyter
                                 





