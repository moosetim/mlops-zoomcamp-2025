# MLOps Zoomcamp 2025

# 1. Introduction
## 1.1 Introduction
**MLOps** - set of best practices of and tools for putting machine learning models to production.

ML problem in the course: predicting the duration of a taxi ride (how many minutes will the taxi ride take).

3 stages of an ML project:
1. **Design**
   1. Is ML the appropriate/best tool to use? Are there simpler methods that we can use?
2. **Train**
   1. Find and train the best ML model for the problem
3. **Operate**
   1. Deploy the model
   2. Maintain the deployed model

## 1.2 Environment preparation
### 1.2.1 GitHub Codespaces
Some advantages of using Codespaces: 
1. It comes with some pre-installed tools (e.g., Docker is already installed)

1. Install the GitHub Codespaces extension in VS Code
2. On GitHub: `Code` $\rightarrow$ `Codespaces` 
3. Switch to the desktop version of VS Code: `top left corner menu` $\rightarrow$ `Open in VS Code Desktop`
4. Check the version of Python installed in Codespaces: 
   1. `python --version` - check the version of Python
   2. `which python` - check the path to the Python executable

### 1.2.2 VM in AWS
Skipped for now. Potentially revisit later.

## 1.3 Training a ride duration prediction model
See the Jupyter notebooks.

## 1.4 Course overview
### MLflow
MLflow:
   - Model Registry
   - Experiment Tracker

### ML Pipelines
ML Pipelines:
   - Load and prepare data
   - Vectorise the dataframe
   - Train the model

We can parametrise the pipeline:
   - `train_data` = January 2021
   - `val_data` = February 2021
   - `model` = linear regression

Once a pipeline is created and parametrised, we can run it with different parameters:
   - `python pipeline.py --train_data=2021-01 --val_data=2021-02 --model=linear_regression`

Tools:
   - Prefect
   - Kubeflow Pipelines

### Serving the model 
Once the pipeline has run, we get a model. We now deploy the model to production so that it can serve the predictions to the users. 

### Monitoring the performance of the model

## 1.5 MLOps Maturity Model
Reference article can be accessed [here](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/mlops-maturity-model).
- **Level 0: No MLOps.** No automation. All code in sloppy Jupyter notebooks. Might be suitable for exploratory work (experimenation with a number of ML models) and POC but not for production or more mature projects.
- **Level 1: DevOps but no MLOps.** Best engineering practices (releases are automated, CI/CD, unit tests, integration test, some operational metrics monitoring - number of requests per second, network saturation) exist but they are not ML aware. We follow best software engineering practices but we do not have any ML specific practices. No experiment tracking, no model registry, no model monitoring, no data versioning. No reproducibility. 
- **Level 2: Automated training.** Training pipeline is automated. Experiment tracking. You know which models are in production (model registry). Model deployment is low friction (might or might not be automated). DS work with engineers.
- **Level 3: Automated deployment.** Easy to deploy models. Usually, there is a place where you store ML models (ML Platform). You make an API call to the ML Platform and it deploys the model for you. Often, at this stage you can also run A/B tests on the versions of the model (e.g., comparing v1 and v2 of the model). Models are monitored. 
- **Level 4: Full MLOps automation.** Automatic training, retraining, deployment altogether in one place.