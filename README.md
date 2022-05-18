# Mini-Project-02/03 for ECE 7123 DeepLearning
In this project, we are going to implement Visual object Tracker using Transformer. 

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

# Train

## 1. set project path
Run the following command to set paths for this project

 ```python tracking/create_default_local_file.py --workspace_dir . --data_dir ./data --save_dir .```

Then we can modify the paths of datasets by these two files.

```lib/train/admin/local.py  # paths about training ; ```
```lib/test/evaluation/local.py  # paths about testing```

## 2. Change the baseline

[baseline](https://github.com/stony0411/Mini-Project-02/tree/main/Stark/experiments/stark_s)

MAX_SAMPLE_INTERVAL: 200;

TRAIN:
    DATASETS_NAME:
    DATASETS_RATIO: ;

BATCH_SIZE: 16;

EPOCH: 50;

OPTIMIZER: ADAMW;

SCHEDULER:  TYPE: step ; DECAY_RATE: 0.1;

NUM_WORKER: 8;

## 3. Train command 

```!python /content/gdrive/MyDrive/Stark/tracking/train.py --script stark_st --config baseline --save_dir . --mode single```

## 4. Test command

```python /content/gdrive/MyDrive/Stark/tracking/test.py stark_st baseline --dataset data --threads 32```

# Results and evaluation

![](../main/plot.png)
![](../main/Success.png)
![](../main/Precision.png)
![](../main/class.png)




# Other scripts
Those are the scripts to reform UAV123 dataset

[Dataset_process](https://github.com/stony0411/Mini-Project-02/blob/main/Preprocess_Dataset.ipynb)

[tococo](https://github.com/stony0411/Mini-Project-02/blob/main/Preprocess_Dataset_tcoco.ipynb)

[Annotation tool](https://github.com/stony0411/Mini-Project-02/tree/main/DarkLabel2.4)


