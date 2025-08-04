# Evaluation Notes for Tool 09 - Predicting CME Arrival Time Through Data Integration And Ensemble Learning

1. **Downloaded and extracted** the ZIP archive from (https://zenodo.org/records/7516684#.Y7xI1hXMLrk) into the designated folder:  
   tool09_Predicting_CME_Arrival_with_Ensemble_Learning

2. **Verified contents** - Jupyter notebooks:  
- KA_01_PredictingCMEArrivalTimeThroughDataIntegrationAndEnsembleLearning.ipynb
- environment.yml file
- ZIP archive: CMETNet-v1.1.zip
- Supporting folders: CMETNet_Package/, figures/
- Supporting documentation: README.md, LICENSE, evaluation_notes.md

3. **Created the environment** from environment.yml:
   conda env create -f environment.yml
   conda activate CMETNet
   Encountered and resolved a charset_normalizer error by allowing package updates when prompted.

4. **Launched the Jupyter Notebook in the activated environment successfully**: jupyter notebook
   
5. **Ran the notebook without modification:**:
- All cells executed successfully.
- Pretrained model results were plotted.
- CNN model trained and displayed output layer structure.
- COMB models (SVR, RF, GP, XGB) trained.
- Final ensemble prediction results were generated.
- No runtime errors or missing package issues occurred.
