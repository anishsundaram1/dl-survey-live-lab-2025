Experiment Log (Your Name)
For each experiment you run this semester:

Copy the template block below.
Fill it in.
Add it to the bottom of this file.
Experiment Template
Run #:
Date:
Goal / Question:
(What are you testing or curious about?)

Setup:
(What data, model, hyperparameters, preprocessing did you use?)

Results:
(Key metrics: accuracy, precision/recall, confusion matrix, etc.)

Reflection:
(What worked? What didn’t? What would you try next?)

Example Experiment Log — Taiwo
Run 1 — 2025-09-04
Goal / Question: What happens if I change n_estimators from 100 to 200?
Setup: Baseline Random Forest, train/test split = 80/20
Results: Accuracy = 0.84, Precision = 0.72, Recall = 0.66
Reflection: Increasing estimators gave a small accuracy bump. Took longer to train. Worth it? Maybe.

Run 2 — 2025-09-06
Goal / Question: Compare Random Forest vs Logistic Regression
Setup: Same preprocessing as before
Results: RF Acc = 0.85, LogReg Acc = 0.79
Reflection: LogReg underfit the data. Nice reminder that not all models capture interactions.

Which method finished faster? Why? Grid search is slower than randomized search becasue it tries EVERY possible combination of the given hyperparameters.
Did they find similar or different best parameters? Yes similar best parameters: max_depth and n_estimators were around or the same.
When would you choose GridSearchCV vs RandomizedSearchCV in practice? Gridsearch is more accurate but the tradeoff is the energy and computationaly heavy cost. Randomized search finds "good enough" parameters.

