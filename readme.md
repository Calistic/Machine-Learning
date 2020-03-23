# Oversample
## - Random Oversampler
Note: I normalized the dataset

Balanced Accuracy Score: 0.774

Confusion Matrix:
![Random Oversampler](https://github.com/Calistic/Machine-Learning/blob/master/pics/ROS-cm.PNG)

Classification Report:
![Random Oversampler](https://github.com/Calistic/Machine-Learning/blob/master/pics/ROS-cr.PNG)

## - SMOTE
Note: I normalized the dataset

Balanced Accuracy Score: 0.772

Confusion Matrix:
![SMOTE](https://github.com/Calistic/Machine-Learning/blob/master/pics/SMOTE-cm.PNG)

Classification Report:
![SMOTE](https://github.com/Calistic/Machine-Learning/blob/master/pics/SMOTE-cr.PNG)

# Undersample
## - Undersampling
Note: I normalized the dataset

Balanced Accuracy Score: 0.754

Confusion Matrix:
![Undersample](https://github.com/Calistic/Machine-Learning/blob/master/pics/Under-cm.PNG)

Classification Report:
![Undersample](https://github.com/Calistic/Machine-Learning/blob/master/pics/Under-cr.PNG)

# Combination
## - SMOTEENN
Balanced Accuracy Score: 0.654

Confusion Matrix:
![Combination](https://github.com/Calistic/Machine-Learning/blob/master/pics/SMOTTEEN-cm.PNG)

Classification Report:
![Combination](https://github.com/Calistic/Machine-Learning/blob/master/pics/SMOTTEEN-cr.PNG)

# Final Recommendation
Ideally our algorithm is 100% accurate, but we aren't going to achieve this today. The next best result we can hope for is to minimize the number of false negatives (incorrectly classifying loans as low risk loans).

Achieving this would enable the company to fast track Low Risk loans. All High-Risk positives (True and False) could then be manually screened by a human.

The method with the lowest proportion of True Positive to False Negatives was the Random Oversampler. However, the number of False Negatives is very high, 3,507 of 3,583 low_risk entries. If we tried to fast track loan approval by approving all negatives (low_risk), we would unintentionally approve 97.9% (3507/3583) of the High-Risk loans. Not good!

Alternatively, we could try to fast track loan rejections by rejecting every positive (high_risk). However, this also provides little benefit as the percent of positives (high_risk) is low, 101 of 17,104 (0.6%). We just wouldn't save many manhours.

I recommend not using any of these tools at least until the number of False Negatives is significantly reduced.
