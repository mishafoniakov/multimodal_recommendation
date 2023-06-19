# Application of multimodal models for the image recommendation systems

With the development of Internet technologies new sources of information have become available. Social networks play an important role in our life. Users started to upload images of everything they preferred. There was a need to systematize these images. The special algorithm was required and it was called recommendation (or recommender) system. However, it is not perfect. Different tasks require different data to make recommendations. Examples of such data can be descriptive text of the goods or some metrics, which we can obtain. These properties/characteristics are called multimodal information. And the models that use this information, are called multimodal.
In this thesis I present the multimodal recommendation model, which consists of two parts. The first part is the image itself. We vectorise it, and obtain different metrics. The second part is the test description of the image. We also vectorise it and add necessary metrics. Then we concatenate these data sets into one and train the model with all the data. Finally for one random image we obtain a certain amount of recommendation images.

Welcome to the GitHub page of my project 'Application of multimodal models for the image recommendation systems'

This repository consists of two parts. Part 1 contains only results of my project. Part 2 contains all steps of my project.

## 1. Results

### Step 1. Download image dataset and text dataset
+ [Yandex Image Dataset](https://disk.yandex.ru/d/3owCpPC5nd3BAQ)
+ [Yandex Text Dataset](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_1/01_image_text_dataset.json)

### Step 2. Run the notebok
+ [Results notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_5/05_results.ipynb)

## 2. All steps

### Step 0. Download image dataset and text dataset
+ [Yandex Image Dataset](https://disk.yandex.ru/d/3owCpPC5nd3BAQ)

### Step 1. Building CLIP&BERT vectors

Run these notebooks contineously
+ [CLIP Preparing notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_1/01_img_dataset.ipynb)
+ [BERT Preparing notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_1/01_txt_dataset.ipynb)

As a result, you should have this file
[CLIP&BERT Dataset](https://disk.yandex.ru/d/zBu38Dzt0c1_HA)

### Step 2. Creating clusters for CLIP&BERT embeddings. Run this notebook
+ [Creating clusters notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_2/02_clusters_pipeline.ipynb)

As a result, you should have this dataframe with images and it's candidates according to three nearest clusters
[Images candidates dataframe](https://disk.yandex.ru/d/kJpqsozauypL-g)

### Step 3. Learn CatBoost model
+ Download this learning dataset
[Learning pipeline](https://disk.yandex.ru/d/j-shokV1xPW1-w)
+ Run this notebook [Learning model notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_3/03_model_learning.ipynb)

As a result, you should have file with catboost model
[Catboost model](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_3/03_catboost_model.bin)

### Step 4. Predict targets for paired images
+ You should use this dataframe, which you have obtained at step 2
[Nearest clusters](https://disk.yandex.ru/d/kJpqsozauypL-g)

+ Run this notebook
[Target predicting notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_4/04_image_candidates.ipynb)

As a result, you should have files with candidates for 3 different models: (1) CatBoostModel (2) using only CLIP (3) using only BERT

+ [Catboost model](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_4/04_image_model_candidates_5.json)

+ [CLIP model](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_4/04_image_candidates_5_clip_cossim.json)

+ [BERT model](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_4/04_image_candidates_5_bert_cossim.json)

### Step 5. Results

[Results notebook](https://github.com/mishafoniakov/multimodal_recommendation/blob/main/step_5/05_results.ipynb)
