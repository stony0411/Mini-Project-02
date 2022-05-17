# Mini-Project-02/03 for ECE 7123 DeepLearning
In this project, we are going to implement two Visual object Tracker using Transformer. 

**Stark** folder is the script from "https://github.com/researchmm/Stark". paper:[[Learning Spatio-Temporal Transformer for Visual Tracking]](https://openaccess.thecvf.com/content/ICCV2021/papers/Yan_Learning_Spatio-Temporal_Transformer_for_Visual_Tracking_ICCV_2021_paper.pdf)

**TransformerTrack** folder is the script from "https://github.com/594422814/TransformerTrack". paper:[[Transformer Meets Tracker:Exploiting Temporal Context for Robust Visual Tracking]](https://arxiv.org/pdf/2103.11681.pdf)

# Installation
>**note:** since environments implemented by these two models are different, we create two virtual environments respectively ***Stark*** and ***pytracking***

**Stark**: 

 - Use the Anaconda : 
```
conda create -n stark python=3.6
conda activate stark
bash install_pytorch17.sh
```
 - Data preparation : Put the tracking datasets in ./data. It should look like:
   ```
   ${STARK_ROOT}
    -- data
        -- lasot
            |-- airplane
            |-- basketball
            ...
        -- got10k
            |-- test
            |-- train
            |-- val
        -- trackingnet
            |-- TRAIN_0
            |-- TRAIN_1
            ...
            |-- TRAIN_11
            |-- TEST
   ```
**pytracking**: 
 - Use the bash : 
 
 ```bash install.sh conda_install_path pytracking```

# Preliminary results
Stark tracking result:

![](../main/stark.png)

transtrack tracking results:

![](../main/transtrack.png)

# Other scripts
Preprocess_Dataset.ipynb
Preprocess_Dataset_tcoco.ipynb
Those are the scripts to reform UAV123 dataset

Generate_Graph.ipynb is used to generate graphs.

