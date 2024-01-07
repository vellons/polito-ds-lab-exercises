# Exam project

The goal of this project is to build a data science pipeline that predicts for each event, given as inputs the characteristics of the signals measured by each pad, the target (x,y) coordinates where the particle of interest passed.

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

Machine: Macbook Pro M1 PRO 10 cores 16GB RAM

Avarege CPU temperature during training: 95°C

RAM used by the python kernel: 2.7GB

R2 score is a metric for regression problems. Closer to 1 is better.

Euclidean score is the metric that will be used to evaluate the submission. (This function is defined by the assignment)


### Random Forest with MultiOutputRegressor
|    time | n_estimators | criterion     | max_features | R2 score   | Euclidean score | submission score |
|--------:|--------------|---------------|--------------|------------|-----------------|------------------|
| 52s     | 100          | squared_error | log2         | 0.99848024 | 5.369           | 5.577            |
| 2m 49s  | 300          | squared_error | log2         | 0.99855958 | 5.220           | 5.730            |
| 1m 10s  | 100          | squared_error | sqrt         | 0.99877615 | 4.842           | 5.243            |
| 2m 20s  | 200          | squared_error | sqrt         | 0.99882048 | 4.753           | **5.153**        |
| 11m 24s | 100          | squared_error | 1.0          | 0.99875576 | 4.689           | 5.361            |

For easy table generation:
https://www.tablesgenerator.com/markdown_tables
