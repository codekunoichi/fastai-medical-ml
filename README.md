# fastai-medical-ml

This repository contains hands-on machine learning exercises inspired by the fast.ai course, adapted and applied to real-world problems in ambulatory healthcare.

The goal of this project is not leaderboard performance, but deep understanding. Each notebook focuses on learning the full modeling lifecycle end to end, including problem framing, data exploration, feature engineering, model training, evaluation, error analysis, and clinical or operational caveats.

The work intentionally emphasizes practical healthcare scenarios such as risk prediction, operational efficiency, and decision support, while being mindful of data leakage, bias, and misuse in clinical contexts. Where public or synthetic datasets are used, their limitations are explicitly documented.

This repository serves as a learning gym for building intuition and technical skill in applied machine learning, with a long-term focus on ambulatory healthcare domains such as chronic disease management, patient access, and revenue cycle operations.

## Setup

This project uses Python 3.12 and a local virtual environment.
My Mac has multiple Python versions installed, so we explicitly pin and verify the interpreter.

1. Verify Python 3.12 is available
```
which python3.12
python3.12 --version
```


Expected:
```
Python 3.12.11
```

2. Create and activate a virtual environment

```
python3.12 -m venv myenv
source myenv/bin/activate
```


Verify the environment is active and using the correct Python:

```
(myenv) python --version
(myenv) which python
```


Example output on my machine:

`/Users/rumpagiri/Projects/fastai-medical-ml/myenv/bin/python`

3. Create requirements.txt

Start with a minimal dependency set:
```
fastai
jupyter
ipykernel
pandas
scikit-learn
```


Install dependencies:

`pip install -r requirements.txt`


Note: fastai will automatically install PyTorch.

4. Verify fastai installation (terminal check)

Launch the Python REPL:

`python`


Then run:
```
import fastai
print(fastai.__version__)
fastai.__file__
```


Expected:

`fastai version prints (e.g. 2.8.5)`

file path points inside `myenv/lib/python3.12/site-packages/`

Exit the REPL.

5. Register the virtual environment as a Jupyter kernel
```
python -m ipykernel install \
  --user \
  --name fastai-medical-ml \
  --display-name "fastai-medical-ml (py312)"
```


Verify the kernel exists:

`jupyter kernelspec list`


You should see:

`fastai-medical-ml`

6. Launch Jupyter Notebook
```
jupyter notebook
```


In the browser:

Navigate to the notebooks/ directory

Create a new notebook using kernel `fastai-medical-ml (py312)`

Name it `00_fastai_sanity_check.ipynb`

7. Sanity check (inside the notebook)

Run the following cell:
```
from fastai.vision.all import *
import sys

print(fastai.__version__)
print(sys.executable)
```

Expected:
```
fastai version prints

Python executable path points to myenv/bin/python
```

If both are correct, the environment is ready.