# Exam project

The goal of this project is to build a data science pipeline that predicts for each event, given as inputs the characteristics of the signals measured by each pad, the target (x,y) coordinates where the particle of interest passed.

Read the [assignment](Assignment_Winter_2024.pdf) for more details.

### Run locally with Jupyter Notebook
Make sure you have python3 and pip installed. Then run the following commands:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
ipython kernel install --user --name=venv  # To enable the venv kernel on jupyter
jupyter notebook  # Select the venv kernel
```


## Algorithm scores

Machine used for the tests: MacBook Pro M1 PRO 10 cores 16GB RAM.

Avarege CPU temperature during training: 95°C.

R2 score is a metric for regression problems. Closer to 1 is better.

Euclidean score is the metric that will be used to evaluate the submission. 
This function is defined in the assignment. Closer to 0 is better.

R2 score and Euclidean score are calculated on the test set. The test set is 25% of the training set.

Submission score is the score obtained by submitting the predictions to the PoliTO server.

### Random Forest with MultiOutputRegressor
|    Time | n_estimators | criterion     | max_features | R2 score   | Euclidean score | Submission score |
|--------:|--------------|---------------|--------------|------------|-----------------|------------------|
| 52s     | 100          | squared_error | log2         | 0.99848024 | 5.369           | 5.577            |
| 2m 49s  | 300          | squared_error | log2         | 0.99855958 | 5.220           | 5.730            |
| 1m 10s  | 100          | squared_error | sqrt         | 0.99877615 | 4.842 [4.703]** | 5.243 [5.157]**  |
| 2m 20s  | 200          | squared_error | sqrt         | 0.99882048 | 4.753           | 5.153            |
| 4m 53s  | 400          | squared_error | sqrt         | 0.99884119 | 4.708           | 5.104            |
| 2m 20s  | 200          | friedman_mse  | sqrt         | 0.99882251 | 4.746           | skip             |
| 8m 22s  | 600          | friedman_mse  | sqrt         | 0.99884875 | 4.690           | 5.089            |
| 2m 38s  | 200          | poisson       | sqrt         | 0.99881351 | 4.759           | skip             |
| 4m 48s  | 100          | squared_error | 0.35         | 0.99904227 | 4.255**         | skip             |
| 6m 02s  | 100          | squared_error | 0.45         | 0.99904534 | 4.251**         | 4.851**          |
| 4m 50s  | 100+variance | squared_error | 0.45         | 0.99905931 | 4.222**         | 4.810**          |
| 18m 24s | 400+variance | squared_error | 0.45         | 0.99908886 | **4.160****     | **4.757****      |
| 7m 19s  | 100          | squared_error | 0.55         | 0.99903096 | 4.271**         | 4.879**          |
| 8m 16s  | 100          | squared_error | 0.63         | 0.99902100 | 4.286**         | skip             |
| 7m 10s  | 100          | friedman_mse  | 0.7          | 0.99894805 | 4.425           | 5.009            |
| 11m 24s | 100          | squared_error | 1.0          | 0.99875576 | 4.689           | 5.361            |

** Performed with test_size=0.05

Variance = Removes all low-variance features.

Also tested with criterion "absolute_error" but it was stopped after 20 minutes of training.

Also tested with the regressor GradientBoostingRegressor with n_estimators=60 but the euclidean score was 14.671

Also tested with the regressor 

Also tested with classifier DecisionTreeClassifier.
Transforming the regression problem into a classification problem focused on predicting ranges, since x&y are multiple of 5. 
Hopping to get a better score with a classification algorithm but the euclidean score was 8.120.

Got better results with the regressor RandomForestClassifier, but still worse than the RandomForestRegressor. (euclidean score around 5.039 -> submission score 7.599)

Chosing the right estimator: https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html

For easy table generation:
https://www.tablesgenerator.com/markdown_tables
