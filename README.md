# Classification: When 90% Accurate Is Worthless

## Objective

I examined how the decision threshold affects loan default predictions and the lender's cost.

## Methodology

- I fitted a logistic regression using 6,000 simulated loan applications.
- I interpreted the coefficients as changes in log-odds and as odds ratios.
- I compared precision and recall across six thresholds.
- I chose the lowest-cost threshold using the training data and evaluated it on the test data.
- I wrote `precision_recall_at()` to calculate precision and recall at any threshold.

## Key Findings

The default rate was 9.6%. At the 0.5 threshold, the model predicted zero defaults and had 90.4% accuracy. A rule that approved every applicant had the same accuracy.

One more prior default multiplied the odds of default by 1.63. The change in predicted probability depended on the starting probability.

The lowest-cost threshold on the training data was 0.121, compared with the closed-form threshold of 0.118. On the test data, the cost was $944 per applicant at 0.121 and $1,147 at 0.5. At the closed-form threshold, precision was 0.181 and recall was 0.477.
