# Final Project - Poverty Analysis
In this final project, we study classification in the context of the [Poverty dataset](https://wilds.stanford.edu/datasets/#povertymap), which is part of the [Wilds Project](https://wilds.stanford.edu/).

The goal of this project is to classify poor vs. wealthy regions in Africa based on satellite imagery. There are `~20,000` images covering `23` countries in Africa.

The satellite images are of the shape `224 X 224 X 8`. Each pixel corresponds to a `30m X 30m` area and each image corresponds to a `6.7km X 6.7km` square. To see some sample images, see [this notebook](<https://github.com/SateeshKumar21/PovertyAnalysis/tree/main/HW5/Pre-processing/2.browse images.ipynb>). 

This dataset comprises images from both urban and rural areas. In general, urban areas are significantly more wealthy than rural areas. See [this notebook](<https://github.com/SateeshKumar21/PovertyAnalysis/tree/main/HW5/Pre-processing/2.browse images.ipynb>) for details. To make the problem into a classification task, we define a threshold on the wealth that separates the poor from wealthy. As there is a large difference between rural and urban, we use a different threshold for each subset. Rural images with wealth less than -0.5 are labeled as poor and greater than -0.5 as wealthy. Similarly, we pick a threshold of 1.3 for urban images.

## Dataset 
You can find the image files at the following location:
- `/home/username/public/cs255-sp22-a00-public/poverty`

All files (train and test) are stored inside this folder in npz format. We divided this dataset into one train and 2 test sets. We separated out ~25% of the data to build a countries test set (`Country_test_reduct.csv`) s.t. the test countries that are not present in the training set. In the random test set, we separated 25% of the instances at random from the remaining 75% of data to generate a random test set (`Random_test_reduct.csv`).

So, there are 3 csv files:
1. `train.csv`: Ground truth for the training dataset. Use the column `label` to train your models.
2. `Country_test_reduct.csv`: Country test set. You have all the same columns as `train.csv` except for `label` and `wealthpooled`.
3. `Random_test_reduct.csv`: Random test set. You have all the same columns as `train.csv` except for `label` and `wealthpooled`.

Note, random test set is an easier one and follows the same distribution as the train set. Country test set is harder as it consists of countries that you will not encounter in the train set. 


There are four files to submit:
1. `results.csv` — your predictions on the random test set 
2. `results_country.csv` — your predictions on the country test set 
3. `code.zip` or `code.tgz` — your code in a zip file, max size of zip file is 10MB.
4. `explanation.md` - your explanation for your implementation

Each csv file should have the following columns:

- `filename` — e.g. `image13724.npz`
- `urban` — `1` when urban, `0` when not urban
- `pred_with_abstention`  — predictions of `-1`, `1`, and `0` when I don’t know
- `pred_wo_abstention` - predictions of `-1`, `1` 


## Number of Submissions Per Day
Each group can make at most one submission per group member per 24 hour period.

