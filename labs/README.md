# Data Science Lab

### Run locally with Jupyter Notebook
Make sure you have python3, pip and Jupiter installed. Then run the following commands:

```bash
python3 -m venv venv
source venv/bin/activate
ipython kernel install --user --name=venv  # To enable the venv kernel on jupyter
pip install -r requirements.txt
jupyter notebook  # Select the venv kernel
```
