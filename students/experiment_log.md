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

Experiment Log Anish - 01_baseline_random_forest_gradio

Run 1:
Date: 09/15/2025
Goal / Question:
Turning out previous random forest which predicts if a user income is over or under 50k into a gradio app

Setup:
Created a random forest algorithm in the previous notebook, from there we integrted into gradio by first locking in the feature order, then installing gradio, then writing a method to preprocess (inputing, concatenation, and filling with 0), and then writing the predict function, which outputs the over or under 50k based off age, hours worked per week, education, sex, and workclass. Finally, we built the UI for the app incoorperating sliders and such. 

Results:
The app looked fine but the output didn't work due to the feature names not being in the same order as they were fit. 

Reflection:
To fix this I made my preprocess_input function more robust because it carefully mirrors the training-time pipeline and enforces consistency at every step. I started by initializing a full one-row DataFrame with all expected columns, so missing inputs don’t cause errors. Numeric features are imputed and scaled using the same fitted transformers, while categorical features are imputed, label-encoded for one special column, and one-hot encoded for the rest with handle_unknown="ignore", ensuring unseen categories don’t break inference. Finally, by reindexing with feature_order, you guarantee the output has the exact same columns and order as the model expects, filling in any missing one-hot categories with zeros. Together, these steps make the function resilient to incomplete or slightly messy user inputs while ensuring perfect alignment with the trained model’s feature space. Although this should have worked, it didn't fix the issue.

