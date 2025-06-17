# Data Description:
- This dataset is about classifying healthy vs early stage cancer samples
- around 850 training samples and around 400 test samples
- first 350 columns (length_51, length_52, ..., length_400) are features: "length_51" denotes the max normalized frequency of DNA fragment length 51
- last column (class_label) is the sample class: healthy/cancer
- It's a class imbalanced dataset

# Task:
- need to classify cancer vs healthy
- need to use appropriate metrics to account for positive class accuracy and negative class accuracy

# Expectations:
- perform appropriate normalization and feature extraction through data visualization
    - compare healthy vs cancer sample profiles (feature index in X-axis and feature value in Y-axis)
- perform feature selection/feature grouping/smoothing
- design appropriate architecture and loss function for your model