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