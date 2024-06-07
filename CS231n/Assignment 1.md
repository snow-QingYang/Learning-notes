# K Nearest Neighbour
## Introduction
The K-Nearest Neighbors (KNN) algorithm is a fundamental and widely used classification and regression method. It operates on the premise that similar data points are likely to be close to one another.
## Work Flow
### Workflow

1. **Choosing the K value**: K represents the number of nearest neighbors to consider. In classification or regression, the algorithm looks at the closest K neighbors to the data point in question.
    
2. **Distance Measurement**: You need to select a method to measure distance between data points. Common choices include Euclidean distance and Manhattan distance. This measurement helps in identifying the nearest neighbors in the feature space.
    
3. **Classification or Regression Decision**:
    
    - **Classification**: Among the K nearest neighbors, count the frequency of each category. The category that appears most frequently is used as the prediction outcome.
    - **Regression**: Typically, the outcome is determined by calculating the average or median of the target values among the K nearest neighbors.
## Some questions in the assignment:
### Inline Question 1
Notice the structured patterns in the distance matrix, where some rows or columns are visibly brighter. (Note that with the default color scheme black indicates low distances while white indicates high distances.)

- What in the data is the cause behind the distinctly bright rows?
- What causes the columns?
Because the data is an outlier to the row of training data or to the column of test data

## Cross Validation


# Support Vector Machine
