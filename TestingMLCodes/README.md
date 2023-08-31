# How to Test Machine Learning Code and Systems

ML tests can be further split into testing and evaluation. We’re familiar with ML evaluation where we train a model and evaluate its performance on an unseen validation set; this is done via metrics (e.g., accuracy, Area under Curve of Receiver Operating Characteristic (AUC ROC)) and visuals (e.g., precision-recall curve).

On the other hand, ML testing involves checks on model behaviour. Pre-train tests—which can be run without trained parameters—check if our written logic is correct. For example, is classification probability between 0 to 1? Post-train tests check if the learned logic is expected. For example, on the Titanic dataset, we should expect females to have a higher survival probability (relative to males).
![Workflow for testing machine learning models Image](https://eugeneyan.com/assets/testing-ml-flow.jpg)
Taken together, here’s how the workflow might look like. To complement this, we’ll implement a machine learning model and run the following tests on it:
[Pre-train tests to ensure correct implementation](https://eugeneyan.com/writing/testing-ml/#pre-train-tests-to-ensure-correct-implementation1)

[Post-train test to ensure expected learn behaviour](https://eugeneyan.com/writing/testing-ml/#post-train-tests-to-ensure-expected-learned-behaviour)

[Evaluation to ensure satisfactory model performance](https://eugeneyan.com/writing/testing-ml/#model-evaluation-to-ensure-satisfactory-performance)

## Setting up the context (algorithm and data)

Before we can do ML testing, we’ll need an algorithm and some data. Our algorithm will be a numpy implementation of DecisionTree which predicts a probability for binary classification. (Extensions to make it support regression welcome!).

To run our tests, we’ll use the Titanic dataset. This tiny data set (~900 rows, 10 features) makes for fast testing (when model training is involved) and allows us to iterate quickly. (As part of performance evaluation, we run fit() and predict() hundreds of times to get the 99th percentile timing.) The simplicity and familiarity of the data also makes it easier to discuss the post-train (i.e., learned logic) tests.

![Screenshot](![image](https://github.com/B3rnoulli-jnr/How-to-Test-Machine-Learning-Codes--and-Systems/assets/88025774/cb17bbe8-1f83-4e3e-968c-f67b15172122)
)


Resource: ![How to Test Machine Learning Code and Systems](https://eugeneyan.com/writing/testing-ml/01)
