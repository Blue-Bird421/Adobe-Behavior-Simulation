# Regression Task Approach 

## Overview
This repository contains a sequence of Jupyter notebooks designed to perform a regression task on a set of data with the goal of predicting 'likes' on media based on captions generated from the media content. The process involves generating captions using the Blip2 model, creating instructional data from these captions, classifying the data into buckets, and then performing regression on each classified bucket.

### Workflow:
1. **Caption Generation**: Use the `blip2-caption-generation.ipynb` notebook to generate captions for input media data.
2. **Instruction Data Creation**: Utilize the `making-instruction-data-for-task1.ipynb` notebook to create prompts corresponding to the input, incorporating various metadata.
3. **Bucket Classification**: Implement the `training-and-inference-distilbert.ipynb` notebook to classify the data into 7 distinct buckets based on the number of likes.
4. **Regression Analysis**: Employ the `regression_on_buckets.ipynb` notebook to perform regression on each bucket using various regressor models.

## Notebooks Description

### 1. Blip2 Caption Generation (`blip2-caption-generation.ipynb`)
- **Purpose**: Generates captions for input media data using the Blip 2 model.
- **Outputs**: Captions and associated IDs for each media item.

### 2. Making Instruction Data for Task 1 (`making-instruction-data-for-task1.ipynb`)
- **Purpose**: Creates a detailed prompt for each input item, combining the generated captions with additional information like username, inferred company, date, and time.
- **Outputs**: Instructional data prompts ready for further processing.

### 3. Training and Inference with DistilBERT (`training-and-inference-distilbert.ipynb`)
- **Purpose**: Divides the data into 5 buckets based on the number of log_likes using the distil-BERT model.
- **Buckets**:
  - Bucket 1: 0->2
  - Bucket 2: 2->3.75
  - Bucket 3: 3.75->6.25
  - Bucket 4: 6.25->11
  - Bucket 5: 11+ (Outliers)
-11+: Outliers
- **Outputs**: Classified data into respective buckets.

### 4. Regression on Buckets (`regression_on_buckets.ipynb`)
- **Purpose**: Performs regression for each bucket to predict the number of likes.
- **Regressors**:
  - Regressor 1: XGBoost 
  - Regressor 2: XGBoost 
  - Regressor 3: CatBoost
  - Regressor 4: CatBoost
  - Regressor 5: CatBoost
    
- **Outputs**: Predictive models capable of estimating the number of likes for new, unseen data based on the bucket classification followed by regression.
