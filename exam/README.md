# Exam project

### Run locally with Jupyter Notebook
Make sure you have python3 and pip installed. Then run the following commands:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
ipython kernel install --user --name=venv  # To enable the venv kernel on jupyter
jupyter notebook  # Select the venv kernel
```
