# ML Flow, DVC, and Other Tools

In the realm of machine learning, it may be difficult to keep track of multiple different versions of models, datasets, and experiments.
To address these challenges, various tools have been developed to facilitate model, data, and experiment versioning.
Some of the most popular tools in this space include MLflow and DVC (Data Version Control), Weights & Biases, Comet ML, and others.

In this section, we describe the challenges these tools aim to solve, and provide an overview of how these tools try to address them. Several sections come with code examples and illustrations to help you get started with these tools.

## Challenge: Data Versioning

Datasets are very rarely static. They evolve over time as new data is collected and annotated, errors are corrected, and new features are added. Retraining models on updated datasets is a common practice in machine learning, and it is often crucial to keep track on which version of the dataset was used to train a particular model.

**Example:** Consider a scenario where a machine learning model is trained on a dataset of customer reviews with the goal of predicting customer retention. The current model was reported as having a 95% accuracy on the test set. However, after retraining the model on an updated dataset with new customer reviews, the accuracy drops to 85%. Without proper data versioning, it would be difficult to identify why the performance of the model has degraded. It could be due to changes in the data distribution, errors in the new data, or other factors. Data versioning allows us to track changes in the dataset over time and identify which version of the dataset was used to train each model.

### DVC (Data Version Control)

DVC is an open-source tool that provides data versioning capabilities for machine learning projects. It allows users to track the changes in datasets similar to how Git tracks changes in code.
DVC integrates with Git and provides a command-line interface for managing data files, models, and experiments. 

We outline more details about DVC in the [Code Examples](./1-1-MLFlowDvcAndOthers.md#code-examples) section.

**Pros:**
- Simple integration with Git
- Low learning curve
- Supports large files and datasets
- Provides experiment tracking capabilities

**Cons:**
- Limited ability to handle conflicts in data files
- Requires additional storage for data files
- May not be suitable for very large datasets or complex data pipelines

### LakeFS

LakeFS is an open-source data versioning tool that provides Git-like capabilities for data lakes. It allows users to create branches, commit changes, and merge datasets in a similar way to how Git works with code repositories. LakeFS is designed to work with large datasets and provides features such as data lineage tracking, access control, and data validation.

For more details about LakeFS, refer to the [official documentation](https://lakefs.io/docs/).

**Pros:**
- Git-like interface for data lakes
- Supports large datasets
- Provides data lineage tracking and access control

**Cons:**
- Requires integration with existing data lakes
- May have a steeper learning curve compared to other tools

## Challenge: Model Versioning

As machine learning models are trained and retrained over time, it is important to keep track of different versions of the models.
Model versioning allows data scientists and engineers to manage the lifecycle of machine learning models and compare the performance for different experiments. Additionall, these tools typically are key components in the MLOps toolchain enabling CI/CD for machine learning systems.

### MLflow

MLflow is an open-source platform for managing the end-to-end machine learning lifecycle. It provides tools for experiment tracking, model versioning, and deployment. MLflow allows users to log parameters, metrics, and artifacts associated with machine learning experiments, making it easier to compare different runs and track model performance over time.

We outline more details about MLflow in the [Code Examples](./1-1-MLFlowDvcAndOthers.md#code-examples) section.

**Pros:**
- Comprehensive platform for managing the machine learning lifecycle
- Easy to use and integrate with existing workflows
- Supports multiple programming languages and frameworks

**Cons:**
- May require additional infrastructure for deployment
- Limited support for complex model versioning scenarios

### Weights & Biases

Weights & Biases (W&B) is a popular tool for experiment tracking and model versioning. It provides a web-based interface for visualizing and comparing machine learning experiments, making it easier to track model performance over time. W&B allows users to log parameters, metrics, and artifacts associated with machine learning experiments, and provides features such as hyperparameter tuning and collaboration tools.

For more details about Weights & Biases, refer to the [official documentation](https://docs.wandb.ai/).

**Pros:**
- User-friendly web interface for experiment tracking
- Supports collaboration and sharing of experiments
- Provides hyperparameter tuning capabilities

**Cons:**
- Commercial tool with pricing plans
- May require internet access for full functionality

