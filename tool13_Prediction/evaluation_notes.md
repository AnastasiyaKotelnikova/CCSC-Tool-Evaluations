# Evaluation Notes for Tool 13 - Prediction of the SYM-H Index Using a Bayesian Deep Learning Method with Uncertainty Quantification

## What Was Done
1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/10602518) into the designated folder:  
   C:/Users/anast/CCSCTools/Tool13_SYMHnet/

2. **Set up a virtual environment** using the provided environment.yml file:
   conda env create -f environment.yml
   conda activate symhnet_env
   
   All dependencies were installed, including tensorflow, protobuf, matplotlib, numpy, and others required by the tool.

4. **Launched the notebook** run_SYMHnet.ipynb using the symhnet_env conda environment.

5. **Verified directory contents** included:
   run_SYMHnet.ipynb
   SYMHnet_test.py
   Supporting folders and model data files

6. **Observations During Execution**:
  Environment was correctly configured, and the Jupyter kernel was running under symhnet_env.
  Notebook execution began successfully, but Section 2.2.1 Predicting Storms #36 and #37 raised the following error:
  TypeError: Descriptors cannot be created directly.
  If this call came from a _pb2.py file, your generated code is out of date and must be regenerated with protoc >= 3.19.0.
  This error comes from tensorflow/core/framework/tensor_shape_pb2.py and points to a known version conflict between protobuf and tensorflow.

  **Outcome**
  Environment setup and launch were successful.
  Notebook execution failed due to a protobuf compatibility issue.
  No modifications were made to the codebase, as per evaluation policy.

  **Notes**
  To make the notebook functional in a future pass, either of the following actions could help:
  Downgrade protobuf to <=3.20.3
  Or update tool code to work with current protobuf versions
  Let me know if you'd like the report saved or exported. Ready to begin Tool14 when you are.
