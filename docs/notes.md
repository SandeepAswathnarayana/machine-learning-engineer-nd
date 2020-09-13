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
In addition to the features provided by SageMaker we used three other Amazon services. In particular, we used **S3** as a central repository in which to store our data. This included test / training / validation data as well as model artifacts that we created during training.
We also looked at how we could combine a deployed SageMaker endpoint with **Lambda** and **API Gateway** to create our own simple web app.


