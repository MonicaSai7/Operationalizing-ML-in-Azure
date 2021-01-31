# Operationalizing Machine Learning in Azure

This project uses Bank Marketing dataset that is related with direct marketing campaigns of a Portugese banking institution. The classification goal is to predict if the client will subscribe a term deposit. Microsoft Azure is used to configure a cloud-based machine learning production model, deploy the best model and consume the model endpoints. Apart from using Azure ML Studio, Azure Python SDK is used to create, publish and consume a pipeline.

The projects is structured with the folowwing steps:<br>
1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline
8. Documentation

## Architectural Diagram
<img src="/Resources/ArchitectureDiagram.png"><br>
In this project both Python SDK and Azure Machine Learning Studio are used to perform the tasks. The architecture starts with authenticating to Azure Machine Learning Services, then create an AutoML experiment and deploy the best model. Next, logging is enabled so that important log information can be reviewed. After that, the model endpoints are consumed. Then a Azure pipeline is created, published and consumed. The final and important stage is the documentation which acts as a project report.

## Key Steps
### Step 1: Automated ML Experiment
At this point, security is enabled an authentication is completed. In this step, an experiment is created using Azure Automated ML. In order to run the experiment, a compute cluster must also be configured.

The following screenshot shows the datasets registered for the experiment:<br>
<img src="/Resources/Step1-1.png"><br><br>
The following screenshot shows the experiment status completed:<br>
<img src="/Resources/Step1-2.png"><br><br>
The following screenshot shows the list of different models used throughout the experiment:<br>
<img src="/Resources/Step1-3.png"><br><br>
The following screenshot shows the best model after the experiment is completed:<br>
<img src="/Resources/Step1-4.png"><br><br>

### Step 2: Deploy the Best Model
The best model is set for deployment in the best model's *Details* tab. Deploying the Best Model will allow to interact with the HTTP API servie and interact with the model by sending data over POST requests.

The following screenshot shows the real-time endpoint created after the best model is deployed:<br>
<img src="/Resources/Step2.png"><br><br>

### Step 3: Enable Logging
After the *Best Model* is deployed, *Application Insights* must be enabled to retrieve logs.

The following screenshot shows the *Application Insights* enabled in the Details tab of the endpoint:<br>
<img src="/Resources/Step3-1.png"><br><br>
The following screenshot shows the logs produced by running the provided logs.py scripts:<br>
<img src="/Resources/Step3-2.png"><br><br>

### Step 4: Swagger Documentation
In this step, the deployed model is consumed using Swagger. Azure provided a Swagger JSON file for deployed models in the *Endpoints* section.

The following screenshots shows that swagger runs on localhost with the HTTP API methods and responses for the model:
<img src="/Resources/Step4-1.png"><br>
<img src="/Resources/Step4-2.png"><br>
<img src="/Resources/Step4-3.png"><br><br>

### Step 5: Consume Model Endpoints
Once the model is deployed, endpoint.py script is used to interact with the trained model with appropriate JSON payload.

The following screenshot shows the endpoint.py script running against the API producing the JSON output from the model:<br>
<img src="/Resources/Step5.png"><br><br>

### Step 6: Create, Publish and Consume Pipeline
For this step, the Jupyter Notebook providede is used with appropriate keys, URI, dataset, cluster and model names created previously.

The following screenshot shows the pipeline created:<br>
<img src="/Resources/Step6-1.png"><br><br>
The following screenshot shows the Pipeline Endpoint:<br>
<img src="/Resources/Step6-2.png"><br><br>
The following screenshot shows the *Published Pipeline Overview* with a REST Endpoint and status of ACTIVE:<br>
<img src="/Resources/Step6-3.png"><br><br>
The following screenshot shows the *Run Details* of the published pipeline:<br>
<img src="/Resources/Step6-4.png"><br><br>

## Screen Recording
The screencast of the project demo can be viewed [here](https://youtu.be/SZE16-p13uo).

## Standout Suggestions
1. Perform hyperparameter tuning by training a model with HyperDrive.
2. Enabel *Deep Learning* in Classification while creating the AutoML experiment.
3. Perform data preprocessing such as feature selection by observing the influence of features on different models.

