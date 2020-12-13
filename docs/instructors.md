## ML Case Studies  
Cezanne Camacho, Udacity  
[Dan Mbanga](https://www.linkedin.com/in/dan-romuald-mbanga-62850a22/), Head of Amazon AI Business Development efforts for ML services.   

## SageMaker Fridays  
### Season 1:  
[Session Videos](https://www.twitch.tv/aws/videos)  
Email: sagemaker-fridays@amazon.com  

**Instructors**  
[Emily Webber](https://www.linkedin.com/in/emily-webber-921b4969/)  
[Alex McClure](https://www.linkedin.com/in/alexjmcclure/)  
[Tianqi Chen](https://tqchen.com/) (Guest Session on XGBoost) - S1E4  
[Shelbee Eigenbrode](https://www.linkedin.com/in/shelbee-eigenbrode-5b632414/) (Guest Session on MLOps) - S1E6  

### [Season 2](https://amazonsagemakerfridays.splashthat.com/):  
[Julien SIMON](https://www.linkedin.com/in/juliensimon/)  
[Dr. Ségolène Dessertine-Panhard](https://www.linkedin.com/in/dr-s%C3%A9gol%C3%A8ne-dessertine-panhard-41416010/)  

S2E1: [Aircraft Predictive Maintenance](https://github.com/awslabs/predictive-maintenance-using-machine-learning/tree/master/source/notebooks)  
S2E2: [Deep Demand Forecasting with SageMaker](https://github.com/awslabs/sagemaker-deep-demand-forecast)  
S2E3: [Fraud Detection using Machine Learning](https://github.com/awslabs/fraud-detection-using-machine-learning/blob/master/source/notebooks/sagemaker_fraud_detection.ipynb)  
*Note: How to detect concept drift and/or data drift using [SageMaker Model Monitor](https://github.com/aws/amazon-sagemaker-examples/tree/master/sagemaker_model_monitor)*  
S2E6: [Computer Vision and Large Scale Training](https://github.com/PacktPublishing/Learn-Amazon-SageMaker/blob/master/sdkv2/ch10/spot/Image%20Classification%20on%20Imagenet%20-%20Managed%20Spot%20Training.ipynb) - Image Classification on ImageNet.  
*Motive: How do you scale your training jobs when you're dealing with very large datasets?*  
Notes:  
- What makes ResNet unique? - Error reduced to 3.6%, Addition of (a) skip connections (b) deep residual layer [Deep Residual Learning for Image Recognition](https://arxiv.org/pdf/1512.03385.pdf)  
- Pipe mode: Useful for large datasets (petabyte-scaled distributed datasets). Inpute datatset is fed/streamed directly into your trainig instance instead of downloading. Short training time. Less disk space. High throughput.  
- ml.p3dn.24xlarge: largest instance_type available on SageMaker today (64 NVIDIA V100 GPUs).  
- CloudWatch: GPU Utilization graph has lots of highs and lows. This is because of the cost of synchronization. Again, it's a tradeoff between GPU Utilization and Model Convergence.  

## AWS Power Hour: Cloud Practitioner  
[AWS Certified Cloud Practitioner, Global Challenge](https://pages.awscloud.com/awspowerhour-CP.html)  

## AWS re:Invent 2020:  
ML Keynote by [Swami Sivasubramanian](https://www.linkedin.com/in/swaminathansivasubramanian/)  
#### Customers and Use cases  
- Domino's Pizza (predictive ordering and delivering in <10 min), Roche (uses SageMaker to accelerate the delivery of treatments and tailor medical experiences), Kabbage (ML in loan application process and surpassed major US Banks to become 2nd largest Business Payment Protection Program lender in the US, preserving an estimated 945k jobs), BMW (uses SageMkaer to process, analyze and enrich more tham 7petabytes of data inorder to froecast the demand both model mix and individual equipment on a worldwide scale), Nike (built a product recommender for online shopping experience towards wholesale customers), F1 (ML in car design process, giving them new insights into more than 550M data points collected through mor ethan 5000 single single and multi car simulations).  

#### Overview of ML stack  
- ML farmeworks & infrastructure - Amazon SageMaker - AI Services)  
- Launched AI Services (Polly, Lex, Rekognition) in 2016. 11 new AI Services till date and 250+ features in the last year.  
- Amazon S3, RDS, Dynamo - how it transitioned many industries leveraging the AWS Cloud  

#### Freedom to Invent  
1. Tenet 1: Provide firm foundations - optimizing frameworks and infrastructure to enable more builders to build and deploy ML models  
TensorFlow, PyTorch, mxnet (Ex: TorchServe, the default model serving library on PyTorch was built and is maintained by AWS in partnership with FB)  
P4d instances: provides the highest performance of ML training in the cloud, NVIDIA A100 GPUs, 400 Gigabit per second networking  
(a) AWS Inferentia: EC2 based instances that provides upto 45% lower cost or 30% higher throughput than comparable GPU based instances (Amazon Alexa achieved 25% lower end-to-end latency for text to speech workloads)  
Customers: Snap, Finra, Autodesk, Conde Nast use Inf1 instances  
Habana gaudi-based Amazon EC2 instances  
(b) AWS Trainium: a ML training chip custom designed by AWS for the most cost effective training in the cloud.  
SageMaker applies Distributed Training automatically: used by Mask-RCNN (SOTA CV model used by autonomous vehicles) for Data Parallelism, T5-3B (SOTA NLP model) for Model Parallelism to speed up the training process  

2. Tenet 2: Create the shortest path to success  
Speeding up innovation with SageMaker. Customers: Lyft, T-Mobile, Vanguard, ifood, ADP, NFL (Health, Safety, Predict and Prevent Injury), Intuit (Tax Deduction, Fraud Detection, Customer Services, Personalization, Development of new features),  
- Amazon SageMaker Data Wrangler: the fastest way to prepare data for ML; 300+ pre-configured data transformations (with no code required); see data spot inconsistencies, diagnose and fix; export data with a single click  
- Amazon SageMaker Featre Store: securely store, discover and share features, so you don't need to recreate teh same features for different ML applications; single digit ms latency for inference; keep features consistent and in sync; search your features easily with visualizations.  
- Amazon SageMaker Clarify: detecting potential bias across ML workflows. Dr. Nashlie Sephus (Applied Scientist). Bias may be due to inconsistent data, model drift (Ex: a substantial change in mortgage rates could cause a home loan model to become bias), Use dashboards and reports (Ex: BA wants to understand what is driving a demand forecast prediction),  
- Deep Profiling for SageMaker Debugger: to help identify bottlenecks and maximize resource utilization (CPU, GPU, Network, I/O Memory) for training.  
Amazon SageMaker Pipelines: the first purpose built easy to use ML CI/CD service. Create an automated ML workflow with just a few clicks. Dr. Matt Wood  
- Amazon SageMaker Edge Manager: Deploying models at the Edge: Industrial robots, Autonomous vehicles, Automated checkouts require ML models that run on robots, smart cameras, equipment, etc. Challenges of ML at Edge: limited compute memory, connectivity, months of hand tuning each model to optimize, the need for multiple ML models to run ona  single device. Amazon SageMaker Neo did a decent job. As ML Edge adoption grew, SageMaker Edge Manager was created. It provides model management to edge devices so you can prepare, run, monitor, update ML models across fleets of edge devices. Easily integrate Edge Manager to your Edge Apps through APIs and common programming languages. Continuosly monitors each instance across your device fleet to detect when the model quality declines. All these encompasses the **SageMaker Studio** with End-to-End services for ML.  

3. Expand ML to more builders  
- SageMaker Autopilot: AutoML-created models (as opposed to Manually-built models) for beginners or non-ML practitioners. Raw data -> Automati model creation -> Model leaderboard -> Deploy and monitor the model.  
- Amazon Aurora ML: make it easier for customers to integrate ML into Aurora-powered apps, apply ML to apps right from the database just by using a SQL query. (Ex: Sentiment Analysis of customer product reviews to identify negative feedback). Run a SQL query to invoke the ML service -> Aurora passes relevant data to Amazon Comprehend -> Results returned to Aurora that are ready to use. Aurora ML makes it easy for Relational DB Developers to apply ML.  
- Amazon Athena ML: Customers can easily add ML-based predictions to their queries on S3. Run inferences to forecast sales, detect suspicious logins, sort users into customer cohorts by invoking pretrained ML models.  
- Amazon Redshift ML: use SQL to make ML predictions from your data warehouse. Create model using SQL -> Selected data is securely exported from Redshift to S3 -> SageMaker Autopilot applies the best algo for the data -> Interactions between Redshift, S3, SageMaker and ML are abstracted away -> Avalilable as a SQL function to use in data queries, reports, dashboards. (Ex: Run the Customer Churn SQL function on new customer data in the data warehouse to identify the customers at risk and feed thsi to the Sales/Marketing teams). Redshift ML mostly useful fro DAs.  
- Amazon Neptune ML: Predictions on connected datasets with graph neural networks. Fast, reliable, fully managed graph DB service that makes it easy to build and run applications that work with these kind of graphs. Graph DBs ar sue to store complex relationships between data and a graph model. Ex: Knowledge Graph, Life sciences, Fraud Detection, Recommendation Engines. SOTA ML with Deep Graph Library and SgaeMaker.  
Integration SageMaker into other products and BI tools: Domo, Sisense, Qlik, Tableau, Snowflake, Databricks, etc. starting 2021.  
- Amazon QuickSight ML Insights: scalable, embeddable BI service for the cloud. It integrates with SageMkaer Autopilot to enable BAs for tasks like anomaly detection, forecasting. Customers: Expedia, TCS, Ricoh Company. Autonarratives: a feature that uses ML insights to tell customers the story of their dashboard using plain language narratives. Business questions in plain written language is a big plus. Dorothy Li on QuickSight Q: deep learning capability that empowers business users to ask questions in NLP. (Type your question directly in the Q search bar: "Show me last year's weekly sales in California versus New York").  

4. Solve real business problems, end-to-end  
What are some good ML models: Are rich in data + Impact the business + Haven't been solved well to date (Example areas: Product recommendations, Improving code reviews, Bringing more efficiency to manual processes, faster and more accurate forecasting and fraud detection)  
- Amazon Connect (Contact Center): a contact center in the cloud where we provide automatic voice transcription, sentimental analysis and analytics using ML through Contact Lens.  
- Amazon Kendra (Intelligent Search): end-to-end intelliget search solution which can connect to multiple internal data silos and uses ML to create an accurate index which can be searched with simple NLP queries.    
- Amazon CodeGuru + DevOps Guru (Code + DevOps): provide automated code reviews, guidance and recommendations on how to fix some truly hard to find bugs and locate some expensive lines of code, reduce latency, reduce CPU contention. DevOps Guru is used to improve application's operational performnace and availability.  
Challenges of Anomaly Detection in etrics: High latency of detection, Failed detection, Too many false detections, Lack of actionable results, Adaptability to changes in data streams. Example: when a retailer prices a product incorrectly on e-commerce site, that product could be sold out before someone even realizes that there is a certain spike in sales.  
- Amazon Lookout for Metrics: uses ML to detect anomalies in virtually any timeseries-driven business and operational metrics (revenue performance, purchase transactions, customer acquisitions, retention rates). Ex: Category-level Revenue in Retail, Ad Tech company can optimize ad spend by detecting spikes/dips in metrics like reach, impressions, views, ad clicks.  













