# Question 1 
Supervised and unsupervised learning are two primary types of machine learning algorithms used in data analysis. Here's a basic overview of each:

### Supervised Learning

#### Definition:
Supervised learning involves training a model on a labeled dataset, meaning that each training example is paired with an output label. The model learns to predict the output from the input data.

#### Key Characteristics:
- **Labeled Data**: Requires a dataset with input-output pairs.
- **Training Objective**: The objective is to learn a mapping from inputs to outputs.
- **Feedback**: Direct feedback is available in the form of the correct labels.

#### Common Algorithms:
- **Linear Regression**: Predicts a continuous output based on the linear relationship between input features.
- **Logistic Regression**: Used for binary classification problems, predicting the probability of a binary outcome.
- **Decision Trees**: A tree-like model of decisions used for classification and regression.
- **Random Forest**: An ensemble method using multiple decision trees to improve performance and control overfitting.
- **Support Vector Machines (SVM)**: Finds the hyperplane that best separates different classes in the feature space.
- **Neural Networks**: Composed of interconnected layers of nodes, suitable for complex pattern recognition tasks.
- **K-Nearest Neighbors (KNN)**: Classifies a data point based on the majority class among its k-nearest neighbors.

#### Applications:
- Email spam detection
- Image and speech recognition
- Predictive maintenance
- Medical diagnosis

### Unsupervised Learning

#### Definition:
Unsupervised learning involves training a model on data that does not have labeled responses. The goal is to identify underlying patterns or structures within the data.

#### Key Characteristics:
- **Unlabeled Data**: Uses datasets without predefined labels or outputs.
- **Training Objective**: The objective is to infer the natural structure within a dataset.
- **Feedback**: No direct feedback is available.

#### Common Algorithms:
- **Clustering**: Groups similar data points together. Common clustering algorithms include:
  - **K-Means Clustering**: Partitions data into k clusters, with each data point belonging to the cluster with the nearest mean.
  - **Hierarchical Clustering**: Builds a tree of clusters by either merging or splitting them successively.
  - **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**: Forms clusters based on dense regions of data points.
- **Dimensionality Reduction**: Reduces the number of features in a dataset while retaining important information. Common techniques include:
  - **Principal Component Analysis (PCA)**: Transforms data to a new coordinate system, reducing dimensionality while preserving variance.
  - **t-Distributed Stochastic Neighbor Embedding (t-SNE)**: Reduces dimensionality for visualization, maintaining local similarities.
- **Association Rule Learning**: Identifies interesting relations between variables in large datasets. Common algorithms include:
  - **Apriori Algorithm**: Finds frequent itemsets and derives association rules.

#### Applications:
- Market basket analysis
- Customer segmentation
- Anomaly detection
- Data compression

# Q Decision Problem

A decision tree is a graphical representation of all the possible solution to a decision. These days tree based algorithm are the most commonly used algorithm in the case of supervised learning scenarios. They are easier to interpret and visualize with great adapatability. 

## Regression tree
A regression tree is a type of decision tree specifically designed for predicting **continuous** numerical values rather than categorical labels. It is used in regression tasks, where the goal is to predict a continuous output based on input features. A regression tree follows a top-down greedy approach.

## Classification tree
A classification tree is a type of decision tree used for predicting categorical labels. It is used in classification tasks, where the goal is to assign input data to one of several predefined categories. It follows a top-down greedy approach.
