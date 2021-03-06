[Rules of Machine Learning](https://developers.google.com/machine-learning/guides/rules-of-ml) by Martin Zinkevich  

ML Pipeline  
[AWS ML Pipeline](https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works-mlconcepts.html)  
[GCP ML Pipeline](https://cloud.google.com/ai-platform/docs/ml-solutions-overview)  
[MS Azure ML Pipeline](https://docs.microsoft.com/en-us/azure/machine-learning/overview-what-is-azure-ml)  

What is Cloud Computing  
[AWS Cloud Computing](https://aws.amazon.com/what-is-cloud-computing/)  
[GCP Cloud Computing](https://cloud.google.com/what-is-cloud-computing/)  
[MS Azure Cloud Computing](https://azure.microsoft.com/en-us/overview/what-is-cloud-computing/)  

An example of a [dockerfile](https://github.com/pytorch/pytorch/blob/master/docker/pytorch/Dockerfile) that creates a docker container with Python 3.6 and PyTorch installed.  

Updating a deployed model: [Data Stream Generation with Concept Drift](https://edouardfouche.com/Data-Stream-Generation-with-Concept-Drift/)  

SageMaker does automated hyperparameter tuning using Bayesian Optimization. Also, CloudWatch for logs generated during training.  

Creating an **endpoint that sends data to more than one model** (Ex: XGBoost and Linear models) and **how to update an existing endpoint** without any downtime for the user.  

Features offered by Amazon's SageMaker service:  
1. **Notebook Instances** provide a convenient place to process and explore data in addition to making it very easy to interact with the rest of SageMaker's features.
2. **Training Jobs** allow us to create model artifacts by fitting various machine learning models to data.
3. **Hyperparameter Tuning** allow us to create multiple training jobs each with different hyperparameters in order to find the hyperparameters that work best for a given problem.
4. **Models** are essentially a combination of model artifacts formed during a training job and an associated docker container (code) that is used to perform inference.
5. **Endpoint Configurations** act as blueprints for endpoints. They describe what sort of resources should be used when an endpoint is constructed along with which models should be used and, if multiple models are to be used, how the incoming data should be split up among the various models.
6. **Endpoints** are the actual HTTP URLs that are created by SageMaker and which have properties specified by their associated endpoint configurations. Have you shut down your endpoints?
7. **Batch Transform** is the method by which you can perform inference on a whole bunch of data at once. In contrast, setting up an endpoint allows you to perform inference on small amounts of data by sending it do the endpoint bit by bit.
Amazon Services:
**S3** is a central repository which is used to store our data. This included test / training / validation data as well as model artifacts that we created during training.
**Lambda** and **API Gateway** We also looked at how we could combine a deployed SageMaker endpoint with **Lambda** and **API Gateway** to create our own simple web app.  

SageMaker Case Studies:  
1. Population Segmentation
2. Credit Card Payment Fraud
3. Non-linear Classification
4. Time-Series Forecasting
5. Plagiarism Detection  


Population Segmentation (Unsupervised):  
- Used to create localized Marketing Campaigns that want to target a variety of regions based on demographic similarities  
- [K-means Constructor](https://sagemaker.readthedocs.io/en/stable/algorithms/kmeans.html) - apply this to the transformed data (dimensionality reduction) that is obtained after PCA  
- [Estimators](https://sagemaker.readthedocs.io/en/stable/api/training/estimators.html#sagemaker.estimator.EstimatorBase) - a high level interface for SageMaker training  

Payment Fraud Detection (Supervised):  
- Identify atypical patterns in tansactions and flag them. ML algorithms help find patterns by looking at users' historical spending data (valid vs fraudulent)  
- Use LinearLearner's Binary Classification algorithm to classify the data into 'valid' (0) and 'fraudulent' (1) labels. [Note: LinearLearner has a. LinearRegression b. BinaryClassification]  

Plagiarism Detector (Binary Classification):  
- Find the text similarity features using 'Containment'  
- Calculate the Longest Common Subsequence (LCS) between the answer text and source text. Compute Normalized LCS value  

Time-Series Forecasting:  
- Household Energy Consumption - Train a DeepAR model defined context and prediction data points  
- Forecasting vs Classification: For Forecasting, it's important to do the train-test split in 'time' unlike the Classification where the train-test split could be done randomly  
- Accepted data format: JSON
- Create a function (`create_training_series`) which takes in a list of complete time series and creates a different list of training time series that have n prediction length points left off  
- DeepAR being an RNN, setting the hyperparameters plays a key role in training. More cells, more layers = captures more complex relationships in the data; batch size, learning rate = how the model rains and improves  
- The `request data` will be a dictionary of `instances` and `configuration`  

ML Capstone:  
- Refer to "Possible Pojects" section under "ML Engineer Capstone" chapter  
- Capstone Report Examples: [Project 1](https://github.com/udacity/machine-learning/blob/master/projects/capstone/report-example-1.pdf), [Project 2](https://github.com/udacity/machine-learning/blob/master/projects/capstone/report-example-3.pdf)
- Project Ideas: [Kaggle Competitions](https://www.kaggle.com/competitions), [Devpost](https://devpost.com/)
- Bertelsmann Arvato Project



