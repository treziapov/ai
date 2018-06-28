Thesholding
- because logistic regression returns probabilities we need a classification (aka decision) threshold

Accuracy
- one metric for evaluating classification models
- informal definition: fraction of predictions our model got right
- formal definition: accuracy = (# correct predictions) / (# total predictions)
- another definition for binary classification: accuracy = (TP + TN) / (TP + TN + FP + FN)
- CON: not sufficient for *class-imbalanced data set*

Precision and recall
Precision
- informal definition: what proportion of positive identifications was actually correct?
- formal definition: precision = TP / (TP + FP)

Recall
- informal definition: what proportion of actual positives was identified correctly?
- formal definition: recall = TP / (TP + FN)

- Precision and recall should be evaluted together
- Metric relying on both: F1 score

ROC and AUC
ROC
- receiver operating characteristc curve
- graph showing performance of a classification model at all decision thresholds
- plots True Positive Rate (TPR/recall = TP / (TP + FN)) and False Positive Rate (FPR = FP / (FP + TN))
- to compute the curve use AUC algorithm

AUC
- area under the ROC curve
- interpretation: the probability that the model ranks a random positive example more highly than a random negative example
- Desirable for two reasons:
    1) scale-invariant - measures how well predictions are ranked, rather than their absolute values
    2) classification-threshold-invariant - measures the quality of the model's predictions irrespective of what the threshold is chosen to be
- Caveats:
    1) scale invariance is not always desirable i.e. when you want well calibrated probability outputs
    2) classification-threshold invariance is not always desirable i.e. when you want to miniimize one type of classification error

Predition bias
- logistic regression predictions should be unbiased i.e. "prediction avg. ~= observation avg."
- prediction bias is a quantity that measures how far apart those two averages are
- prediction bias = avg. of predictions - avg. of labels in data set
- possible root causes:
    1) incomplete feature set
    2) noisy data set
    3) buggy pipeline
    4) biased training sample
    5) overly strong regularization
- adding a calibration layer to fix bias is generally a bad idea:
    1) fixing symptom rather than the cause
    2) must maintain a more brittle system

Bucketing and prediction bias
- need buckets of examples (0/1s) to accurately determine prediction bias
- two ways to form buckets:
    1) linearly break up the target predictions
    2) form quantiles

