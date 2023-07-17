# Poverty Analysis - Final Project

**Note: This project is based on a variant of the poverty mapping dataset collected by Yeh et al. (2020). Due to copyright and licensing restrictions, I cannot upload the associated dataset of images. Therefore, the image files required for this project are not included in the repository.**

In this final project, we aim to perform classification on the Poverty dataset, which is part of the Wilds Project. The objective is to classify regions in Africa as either poor or wealthy based on satellite imagery. The dataset consists of approximately 20,000 images covering 23 countries in Africa.

### Project Objectives

Our project aims to address two main challenges:

1. Domain Generalization: We aim to solve a domain generalization problem across country borders. The training and test distributions comprise disjoint sets of domains, and the goal is to generalize to domains unseen during training. For example, we want our models to perform well on countries or regions that were not part of the training data.

2. Subpopulation Shift: We also focus on improving subpopulation performance across urban and rural areas. The training and test domains overlap, but their relative proportions differ. Our goal is to develop models that perform well in both urban and rural regions, taking into account the varying distributions in wealth values.

### Dataset Information

The satellite images are of the shape 224 X 224 X 8, where each pixel corresponds to a 30m X 30m area, and each image represents a 6.7km X 6.7km square region. The dataset comprises images from both urban and rural areas, where urban regions tend to be wealthier than rural ones.

### Dataset Files

As mentioned, the image files required for this project are not provided due to copyright restrictions. However, we have included the following CSV files that contain the necessary ground truth and test sets:

1. `train.csv`: Ground truth for the training dataset. It includes columns such as "label" which you will use to train your models.

2. `Country_test_reduct.csv`: Country test set. This test set contains data from countries that are not present in the training set. The columns are the same as in `train.csv`, except for "label" and "wealthpooled".

3. `Random_test_reduct.csv`: Random test set. This test set is easier and follows the same distribution as the training set. The columns are the same as in `train.csv`, except for "label" and "wealthpooled".

### Files Structure

For the final project submission, you need to provide the following four files:

1. `results.csv`: Your predictions on the random test set. This file should contain the columns "filename," "urban," "pred_with_abstention," and "pred_wo_abstention."

2. `results_country.csv`: Your predictions on the country test set. This file should also contain the columns "filename," "urban," "pred_with_abstention," and "pred_wo_abstention."

3. `code`: A folder containing your code.

4. `explanation.md`: A markdown file containing an explanation of your implementation.
