# Project 4: Predict and Manage West Nile Virus


## Introduction

**West Nile Virus still plagues citizens in Chicago, Illinois, today.**

To make Chicago homes safer for all, our team of Data Scientists have 

- analyzed available data to predict likelihood of incidence of the disease, and 

- will present a preliminary cost-benefit analysis to inform health authorities on Zenivex spray-based interventions. (see slides)
---

#### Data
The Authorities have provided us with 4 datasets:
1. [Weather]('../datasets/weather.csv'),
2. [Spray]('../datasets/spray.csv'),
3. [Training]('../datasets/train.csv'),
4. [Test]('../datasets/test.csv'), and
5. Mapping resources.
---

## Methodology

1. Examine data
1. Clean data.
3. Visualize data using plots and maps.
4. Iteratively select features, engineer new features, and model data.
5. Finalize model for evaluation.

**Metrics**: We take the AUROC score (also the Kaggle default) as the primary metric, and also examine recall.

- AUROC provides some balance between costs and benefits
- Precision: Choose to avoid false positives (spray costs priority)
- Recall: Avoid false negatives (save the people priority)

---

### Organization

**Folder Organization**
```
|__ code
|   |__ 01_cleaning_eda.ipynb
|   |__ 02_maps.ipynb  
|   |__ 03_models.ipynb
|__ datasets
|   |__ train.csv
|   |__ test.csv   
|   |__ weather.csv
|   |__ spray.csv
|   |__ mapdata_copyright_openstreetmap_contributors.txt
|__ images
|   |__ x.png
|   |__ x.png
|   |__ x.png
|   |__ x.png
|__ P04_group_presentation.pdf
|__ README.md
```

**Across the Project**
1. [Cleaning, Exploratory Visualizations, and Export](./code/01_cleaning_eda.ipynb)
2. [Visualizations via maps](./code/02_maps.ipynb)
3. [Models and Conclusions](./code/03_models.ipynb)