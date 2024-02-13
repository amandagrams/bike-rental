# Automated Machine Learning in Azure Machine Learning

Welcome to the guide on exploring Automated Machine Learning (AutoML) in Azure Machine Learning! In this exercise, you will utilize the AutoML feature to train, evaluate, deploy, and test a machine learning model. This guide will walk you through the process step by step.

## Overview

AutoML allows you to efficiently experiment with multiple algorithms and parameters to find the best model for your data. This guide focuses on training a model to predict the number of bicycle rentals based on historical data from Capital Bikeshare.

## Prerequisites

Before getting started, ensure you have the following:
- Azure subscription
- Microsoft account credentials

## Time Required

Approximately 30 minutes

## Steps

1. **Create an Azure Machine Learning workspace**
   - Provision an Azure Machine Learning workspace in your Azure subscription.
   - Sign in to the Azure portal and follow the instructions to create the workspace.

2. **Use Automated Machine Learning to train a model**
   - Access Azure Machine Learning studio.
   - Create a new Automated ML job with specified settings.
     - Navigate to Azure Machine Learning studio.
     - Go to the Automated ML page under Authoring.
     - Create a new Automated ML job with the following settings:
       - **Basic settings**:
         - Job name: mslearn-bike-automl
         - New experiment name: mslearn-bike-rental
         - Description: Automated machine learning for bike rental prediction
         - Tags: none
       - **Task type & data**:
         - Select task type: Regression
         - Select dataset: Create a new dataset with specified settings.
       - **Task settings**:
         - Specify task type, dataset, target column, and additional configuration settings.
       - **Compute**:
         - Select compute type, virtual machine type, tier, size, and number of instances.
       - Submit the training job.

3. **Review the best model**
   - Review the trained model's performance and metrics.
     - On the Overview tab of the automated machine learning job, note the best model summary.
     - Select the best model to view its details, including metrics.

4. **Deploy and test the model**
   - Deploy the best model as a web service.
     - On the Model tab for the best model trained by your automated machine learning job, select Deploy and use the Web service option with specified settings.
   - Test the deployed service with sample input data.
     - Access the deployed web service.
     - Input sample data and observe the predicted results.

5. **Clean-up**
   - Delete the deployed web service and associated resources to avoid unnecessary charges.
     - In Azure Machine Learning studio, delete the deployed endpoint.
   - Optionally, delete the Azure Machine Learning workspace and associated resources to avoid further charges.

## Test It

### Input

```Json
 {
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }
```

### Output
```Json
  {
   "Results": [
     444.27799000000000
   ]
 }
```

## Examples

- **Predicting Bicycle Rentals**: The trained model can predict the number of bicycle rentals based on factors like season, weather, and day type. For example, it might predict that on a sunny weekday in summer, there will be a high demand for bicycle rentals, while on a rainy weekend in winter, the demand might be lower.

- **Automating Business Decisions**: In retail, the AutoML feature can predict sales based on historical data, helping businesses make decisions about inventory management, marketing strategies, and staffing levels. For instance, it can forecast increased demand for certain products during holiday seasons or promotional events.

- **Healthcare Applications**: AutoML can also be used in healthcare to predict patient outcomes or diagnose diseases based on medical records and diagnostic tests. For example, it can assist in predicting the risk of complications for patients with chronic conditions, enabling healthcare providers to intervene early and improve patient care.

## Conclusion

Congratulations on exploring Automated Machine Learning in Azure Machine Learning! You've learned how to train, evaluate, deploy, and test machine learning models efficiently. Experiment further with different datasets and model configurations to deepen your understanding and unlock insights in various domains.

Happy modeling! 🚀




