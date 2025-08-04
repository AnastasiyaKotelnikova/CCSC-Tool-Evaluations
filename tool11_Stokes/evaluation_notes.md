# Evaluation Notes for Tool 11 - Stokes Inversion for GST/NIRIS Using Stacked Deep Neural Networks

1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7521580#.Y72WVBXMLrk) into the designated folder:  
   C:/Users/anast/Documents/GitHub/CCSC-Tool-Evaluations/tool11_Stokes_Inversion_for_GST_with_Stacked_DNN

2. **Verified contents**
- Jupyter notebook: run_SDNN.ipynb
- Environment setup files:
    environment.yml
    requirements.txt
- Python source files:: `SDNN.py', 'SDNN_test.py', 'utils.py'
   - Folders: `data/`, `models/`, `logs/`, `results/`, `custom_models/`
   - Supporting documentation: `README.md`, `LICENSE`
- Archive and documentation: 'SDNN-v1.3.zip', 'README.md', 'evaluation_notes.md', 'readme.txt'
- Folders: 'inputs/', 'outputs/'
  
3. Set up a virtual environment with Python 3.8 and dependencies listed in environment.yml. All packages were installed successfully without errors.

4. Ran the notebook run_SDNN.ipynb from top to bottom without making any code changes:
- The pretrained model and FITS files were downloaded successfully via utils.download_model() and download_fits().
- The model was loaded using load_model() from the SDNN module.
- Input and output directories were correctly set.
- The prediction code block ran as expected, producing LOS velocities, Doppler widths, and magnetic field vector outputs.
- No execution errors or tracebacks were encountered.
