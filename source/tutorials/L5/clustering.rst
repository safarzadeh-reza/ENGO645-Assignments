
Clustering in Machine Learning: An Introduction
===================================================

In this tutorial, we'll dive into the fundamental concept of clustering and explore its applications across various domains.



These materials have been adapted from:

- `Clustering in Machine Learning <https://www.datacamp.com/blog/clustering-in-machine-learning-5-essential-clustering-algorithms>`__
- `Clustering in Python with Scikit-Learn <https://scikit-learn.org/stable/modules/clustering.html>`__


In this clustering tutorial, you will learn:

- What is clustering?
- 3 essential clustering algorithms:
  - K-Means
  - DBSCAN
  - Hierarchical clustering


What is clustering in Machine Learning?
-------------------------------------------
Clustering is an unsupervised machine learning technique with a lot of applications in the areas of pattern recognition, image analysis, customer analytics, market segmentation, social network analysis, and more. 
A broad range of industries use clustering, from airlines to healthcare and beyond. 

It is a type of unsupervised learning, meaning that we do not need labeled data for clustering algorithms; this is one of the biggest advantages of clustering over other supervised learning like Classification. 



Let’s say we have a huge collection of image dataset containing three fruits (i) strawberries, (ii) pears, and (iii) apples. 

In the dataset all the images are mixed up and your use-case is to group similar fruits together i.e. create three groups with each one of them containing one type of fruit. This is exactly what a clustering algorithm will do. 


.. figure:: img/clustering.png
    
    Unsupervised Learning clustering

Key Success Criteria for Clustering Analysis
----------------------------------------------

Clustering, unlike supervised learning use-cases such as classification, cannot be completely automated end-to-end. Instead, it is an iterative process of information discovery that requires domain expertise and human judgment used frequently to make adjustments to the data and the model parameters to achieve the desired result. 

Most importantly, because clustering is unsupervised learning and doesn’t use labeled data, we cannot calculate performance metrics like accuracy, AUC, RMSE, etc., to compare different algorithms or data preprocessing techniques. As a result, this makes it really challenging and subjective to assess the performance of clustering models. 

The key success criteria in clustering models revolve around:

- Is it interpretable?
- Is the output of clustering useful for business?
- Have you learned new information or discovered new patterns in the data that you weren’t aware of before clustering?


Comparison of Different Clustering Algorithms
----------------------------------------------

There are totally 10 unsupervised clustering algorithms implemented in scikit-learn - a popular machine learning library in Python. 
There are fundamental underlying differences in how each algorithm determines and assigns clusters in the dataset. 

The underlying differences in the mathematical modality of these algorithms boil down to four aspects on which we can compare and contrast these algorithms:

- Parameters required for the model 
- Scalability 
- Use-cases, 
- Geometry, i.e., metric used for calculation of distances. 
Let’s focus on the output of these algorithms. In the diagram 
below, each column represents an output from a different clustering algorithm such as KMeans, Affinity Propagation, MeanShift, etc. 
There are a total of 10 algorithms that are trained on the same dataset.

Some algorithms have yielded the same output. 
Notice Agglomerative Clustering, DBSCAN, OPTICS, and Spectral Clustering have resulted in the same clusters. 

However, if you notice and compare the output of KMeans with the output of MeanShift algorithm, you will notice both the algorithms yielded different results. 
In the case of KMeans, there are only two groups (clusters: blue and orange), whereas, in the case of MeanShift, there are three i.e., blue, green, and orange. 

.. figure:: img/Comparison_of_different_cluster.png
    
    Image Source: https://scikit-learn.org/stable/_images/sphx_glr_plot_cluster_comparison_001.png

  
Unfortunately (or fortunately), there is no right or wrong answer in Clustering. 
It would have been so simple to determine and make a statement like “X Algorithm is performing best here.” 

This is not possible and it is because of this reason clustering is a very challenging task. 

Ultimately, which algorithm works better doesn’t depend on any metric that is easily measurable but rather on the interpretation and how useful the output is for the use-case in hand.



3 Essential Clustering Algorithms
--------------------------------

In this section, we will explore three essential clustering algorithms:

- K-Means
- DBSCAN
- Hierarchical clustering

K-Means Clustering
~~~~~~~~~~~~~~~~~~

K-Means clustering algorithm is easily the most popular and widely used algorithm for clustering tasks. 
It is primarily because of the intuition and the ease of implementation. 
It is a centroid-based algorithm where the user must define the required number of clusters it wants to create. 

This normally comes from business use-case or by trying different values for the number of clusters and then evaluating the output. 

K-Means clustering is an iterative algorithm that creates non-overlapping clusters meaning each instance in your dataset can only belong to one cluster exclusively. 
The easiest way to get the intuition of the K-Means algorithm is to understand the steps along with the example diagram below. 

The K-Means algorithm works as follows:

1. User specifies the number of clusters.
2. Initialize centroids randomly based on the number of clusters. In the diagram below in Iteration 1, notice three centroids are initialized randomly in blue, red, and green colors.
3. Calculate the distance between data points and each centroid and assign each data point to the nearest centroids.
4. Recalculate the mean of the centroid based on all the assigned data points, and this will change the position of the centroid, as you can see in Iteration 2 - 9, until it finally converges.
5. Iteration keeps on going until there is no change to the centroid's mean or a parameter max_iter is reached, which is the maximum number of the iterations as defined by the user during training. In scikit-learn, max_iter by default is set to 300.



.. figure:: img/K_means.png
    
    Image Source: https://www.learnbymarketing.com/wp-content/uploads/2015/01/method-k-means-steps-example.png





DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

DBSCAN or Density-Based Spatial Clustering of Applications with Noise is an unsupervised clustering algorithm that works on the premise that clusters are dense spaces in the region separated by lower-density regions. 

The biggest advantage of this algorithm over K-Means and MeanShift is that it is robust to outliers meaning it will not include outliers data points in any cluster. 

DBSCAN algorithms require only two parameters from the user: 

- The radius of the circle to be created around each data point, also known as ``epsilon``
- ``minPoints`` which defines the minimum number of data points required inside that circle for that data point to be classified as a Core point.

Every data point is surrounded by a circle with a radius of epsilon, and DBSCAN identifies them as being either a Core point, Border point, or Noise point. 
A data point is considered to be a Core point if the circle that surrounds it has a minimum number of points specified by minPoints parameter. 

It is considered a Border Point if the number of points is lower than the minimum required, and it is considered Noise if there are no additional data points located within an epsilon radius of any data point. Noise data points are not categorized in any cluster (basically, they are outliers).

Some of the common use-cases for DBSCAN clustering algorithm are:

- It performs great at separating clusters of high density versus low density;
- It works great on non-linear datasets; and
- It can be used for anomaly detection as it separates out the noise points and do not assign them to any cluster.


.. note::

    Comparing DBSCAN with K-Means algorithms, the most common differences are: 

    - K-Means algorithm cluster all the instances in the datasets whereas DBSCAN doesn’t assign noise points (outliers) to a valid cluster
    - K-Means has difficulty with non-global clusters whereas DBSCAN can handle that smoothly
    - K-Means algorithm makes assumptions that all data points in the dataset come from a gaussian distribution whereas DBSCAN makes no assumption about the data.


.. figure:: img/DBSCAN.gif
    
    Image Souce: https://miro.medium.com/proxy/1*tc8UF-h0nQqUfLC8-0uInQ.gif





Hierarchical Clustering
~~~~~~~~~~~~~~~~~~~~~~~~


Hierarchical clustering is a method of clustering that builds a hierarchy of clusters. There are two types of this method. 

- **Agglomerative**: This is a bottom-up approach where each observation is treated as its own cluster in the beginning and as we move from bottom to top, each observation is merged into pairs, and pairs are merged into clusters. 
- **Divisive**: This is a "top-down" approach: all observations start in one cluster, and splits are performed recursively as we move from top to bottom.
When it comes to analyzing data from social networks, hierarchical clustering is by far the most common and popular method of clustering. The nodes (branches) in the graph are compared to each other depending on the degree of similarity that exists between them. By linking together smaller groups of nodes that are related to one another, larger groupings may be created.

The biggest advantage of hierarchical clustering is that it is easy to understand and implement. Usually, the output of this clustering method is analyzed in an image such as below. It is called a Dendrogram.


.. figure:: img/hierarchical_clustering7.png

  Image Source: https://www.researchgate.net/profile/Rahmat-Widia-Sembiring/publication/48194320/figure/fig1/AS:307395533262848@1450300214331/Example-of-a-dendrogram-from-hierarchical-clustering.png









Examples of Machine Learning Classification in Real Life
--------------------------------------------------------
Supervised Machine Learning Classification has different applications in multiple domains of our day-to-day life. 
Below are some examples. 



Transportation
~~~~~~~~~~~~~~

- **Traffic Flow Prediction**:
  Supervised learning algorithms can be used to predict traffic flow patterns on roads and highways. 
  For example, historical traffic data, weather conditions, and time of day can be used to classify traffic congestion levels as light, moderate, or heavy. 
  This information can help optimize route planning and traffic management systems.

- **Vehicle Classification**:
  Machine learning models can classify vehicles based on their size, type, and purpose. 
  This classification is useful for toll collection systems, parking management, and traffic enforcement. 
  For instance, image classification algorithms can distinguish between cars, trucks, buses, and motorcycles in surveillance footage or traffic camera feeds.

Sustainable Development
~~~~~~~~~~~~~~~~~~~~~~~

- **Land Cover Classification**:
  Remote sensing data combined with supervised classification algorithms can be used to classify land cover types such as forests, water bodies, agricultural land, and urban areas. 
  This information is crucial for monitoring changes in land use, assessing environmental impact, and planning sustainable development initiatives.

- **Species Identification**:
  Classification algorithms can aid in species identification and biodiversity monitoring. 
  By analyzing ecological data such as species distributions, habitat characteristics, and environmental variables, machine learning models can classify species presence or absence in specific regions, helping conservation efforts and ecosystem management.

Education
~~~~~~~~~

- **Student Performance Prediction**:
  Supervised learning techniques can predict student academic performance based on various factors such as attendance, previous grades, study habits, and socio-economic background. 
  These predictions can help educators identify at-risk students early on and provide targeted interventions to improve learning outcomes.

- **Educational Content Recommendation**:
  Classification algorithms can personalize educational content recommendations for students based on their learning preferences, interests, and proficiency levels. 
  For example, a recommender system powered by machine learning can suggest relevant textbooks, online courses, or learning resources tailored to individual student needs.

Healthcare
~~~~~~~~~

- **Disease Diagnosis**:
  Supervised learning models can assist in medical diagnosis by classifying patients into different disease categories based on symptoms, medical history, diagnostic tests, and imaging data. 
  For instance, machine learning algorithms can analyze medical images such as X-rays, MRIs, or CT scans to detect abnormalities and classify them as indicative of specific diseases or conditions.

- **Drug Response Prediction**:
  Classification algorithms can predict patient responses to different medications and treatment regimens based on genetic markers, demographic information, and clinical variables. 
  This personalized medicine approach helps healthcare providers prescribe the most effective treatments while minimizing adverse effects and optimizing patient outcomes.




Different Types of Classification Tasks in Machine Learning
----------------------------------------------------------

Classification is a supervised learning task in machine learning where the goal is to predict the categorical class labels of new instances based on past observations. 
There are several types of classification tasks, including binary classification, multi-class classification, multi-label classification, and imbalanced classification.


Binary Classification
~~~~~~~~~~~~~~~~~~~~~

Binary classification is a type of classification task where the goal is to classify instances into one of two classes or categories. 
The classes are typically represented as "positive" and "negative" or "1" and "0". 
Examples of binary classification tasks include email spam detection (spam or not spam), medical diagnosis (disease present or absent), fraud detection (fraudulent or non-fraudulent transactions), or classification of students can enter a university or not based on their grades and other factors (will be accepted or not accepted).


**Example: Email Spam Detection**

In email spam detection, the goal is to classify emails as either spam or not spam. The features used for classification may include the presence of certain keywords, email sender information, and email content characteristics. A binary classifier trained on labeled email datasets can predict whether incoming emails are spam or legitimate.


.. figure:: img/binary_classificaiton.png
    
    Binary Classification (source: https://www.datacamp.com/blog/classification-machine-learning)




Multi-Class Classification
~~~~~~~~~~~~~~~~~~~~~~~~~~

Multi-class classification is a type of classification task where the goal is to classify instances into one of three or more classes or categories. 
Each instance can belong to only one class, and the classes are mutually exclusive. 
Examples of multi-class classification tasks include hand-written digit recognition (digits 0-9), sentiment analysis (positive, negative, neutral), and image classification (various object categories).

**Example: **Example: Fruit Classification**

Let's say you have a bunch of fruits, like apples, oranges, and bananas. 
You want a computer to tell you which fruit is which just by looking at them. 
You take pictures of each fruit and feed them into a computer program. 
The program learns to recognize different fruits based on their features like color, shape, and size. 
So when you show it a new picture of a fruit, it can tell you if it's an apple, orange, banana, or any other fruit it's been trained on.

.. figure:: img/supervised_learning.jpg
    
    Multi-Class Classification



Other Types of Classification Tasks
------------------------------------

- **Multi-Label Classification**: In multi-label classification, each instance can belong to multiple classes simultaneously. 
- For example, a news article may belong to multiple categories such as "politics," "sports," and "technology" simultaneously.

- **Imbalanced Classification**: In imbalanced classification, the distribution of classes in the dataset is skewed, with one class significantly outnumbering the others. 
- This imbalance can lead to biased models and inaccurate predictions, requiring special techniques to handle class imbalance effectively.


.. note::
    
        Understanding the differences between these classification tasks is crucial for selecting appropriate algorithms and evaluation metrics. 
        Binary and multi-class classification are among the most common types of classification tasks encountered in real-world machine learning applications, and mastering them is essential for building accurate and robust classification models.



Different Types of Classification Algorithms
-------------------------------------------

Classification algorithms are methods used to classify data into different categories or classes. 
There are several types of classification algorithms, each with its strengths and weaknesses. 
Some common classification algorithms include:

1. Logistic Regression:
   - Logistic regression is a simple yet powerful algorithm used for binary classification tasks. It models the probability of an instance belonging to a particular class using a logistic function.

2. Decision Trees:
   - Decision trees are tree-like structures where each internal node represents a "decision" based on a feature, and each leaf node represents a class label. There are different types of decision trees, including:
     - CART (Classification and Regression Trees): CART is a type of decision tree algorithm that can be used for both classification and regression tasks.
     - C4.5: C4.5 is an algorithm used to generate decision trees from a dataset. It employs a divide-and-conquer strategy to recursively split the dataset into subsets based on the most informative features.
   
3. Random Forests:
   - Random forests are ensembles of decision trees where each tree is trained on a random subset of the training data and features. They improve upon the performance of single decision trees by reducing overfitting and increasing robustness.

4. Support Vector Machines (SVM):
   - SVM is a powerful algorithm used for binary and multi-class classification tasks. It finds the optimal hyperplane that separates data points into different classes while maximizing the margin between classes.

5. K-Nearest Neighbors (KNN):
   - KNN is a simple and intuitive algorithm that classifies instances based on the majority class of their nearest neighbors. It does not require training and can be used for both binary and multi-class classification tasks.

6. Naive Bayes:
   - Naive Bayes is a probabilistic algorithm based on Bayes' theorem with the "naive" assumption of feature independence. It is particularly effective for text classification tasks such as spam detection and sentiment analysis.

7. Adaptive Boosting (AdaBoost):
   - AdaBoost is an ensemble learning technique that combines multiple weak learners (e.g., decision trees) to create a strong classifier. It iteratively trains classifiers on subsets of the data, focusing on instances that are misclassified by previous classifiers, to improve overall performance.


.. Note:: 
    For more detailed information on classification algorithms and their implementation in Python, I recommend referring to the `scikit-learn documentation <https://scikit-learn.org/stable/user_guide.html>`__. Scikit-learn provides a comprehensive library of machine learning algorithms and tools for building classification models.




How do measure the efficiency of a Classification model?
-------------------------------------------------------

After we build a classification model, we need to evaluate its performance to ensure that it is accurate and reliable.
We can evaluate the performance of a classification model in different ways, including:

- **Holdout Method**: The holdout method involves splitting the dataset into a training set and a test set, training the model on the training set, and evaluating it on the test set.


.. figure:: img/holdout.jpg
    
    Holdout Method

- **Cross-Validation**: Cross-validation is a technique used to assess the generalization performance of a model by splitting the dataset into multiple subsets, training the model on a subset, and evaluating it on the remaining subsets. With this technique, the data set is randomly divided into k equal-sized, mutually exclusive subsets. One is retained for testing, while the others are utilized for training the model. For each of the k folds, the same procedure is followed.


.. figure:: img/cross_validation.jpg
    
    Cross-Validation


Evaluation Metrics for Classification Models:
--------------------------------------------
There are several evaluation metrics used to measure the performance of classification models, including:

- **Accuracy**: Accuracy is the proportion of correctly classified instances out of the total instances. It is a simple and intuitive metric but may not be suitable for imbalanced datasets.
- **Precision**: Precision is the proportion of true positive predictions out of all positive predictions. It measures the accuracy of positive predictions and is useful when the cost of false positives is high.
- **Recall**: Recall is the proportion of true positive predictions out of all actual positive instances. It measures the ability of the model to identify positive instances and is useful when the cost of false negatives is high.
- **F1 Score**: The F1 score is the harmonic mean of precision and recall. It provides a balance between precision and recall and is useful when the class distribution is imbalanced.
- **Log Loss or Cross-Entropy Loss**: Log loss is a measure of uncertainty in the predictions of a classification model. It is commonly used for binary and multi-class classification tasks and penalizes incorrect predictions based on the confidence of the model.
- **Confusion Matrix**: A confusion matrix is a table that summarizes the performance of a classification model by comparing actual and predicted class labels. It provides insights into the true positive, true negative, false positive, and false negative predictions.
- **AUC-ROC Curve**: The area under the receiver operating characteristic (ROC) curve is a measure of the trade-off between true positive rate and false positive rate across different threshold values. It provides a comprehensive view of the model's performance across different classification thresholds.


.. note::
    Understanding these evaluation metrics is essential for interpreting the performance of classification models and selecting appropriate metrics based on the specific requirements of the task.
    To learn more about these evaluation metrics and their implementation in Python, I recommend referring to the `scikit-learn documentation <https://scikit-learn.org/stable/modules/model_evaluation.html>`__.



