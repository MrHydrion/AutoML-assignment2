# Neural Architecture Search 

This codebase compares five Neural Architecture Search (NAS) methods using the NATS-Bench benchmark

The algorithms that were compared were:

* Random Search
* Random Sampling
* Bayesian Optimisation
* Succesive Halving
* An Iteration-based learning curve method called Pow3

## Setting up the project

To run the notebook, we first needd to setup a virtual environment. That can be done with the following command in the terminal:

```bash
python -m venv .venv
```

To activate the environment you can use the following command on windows:
```bash
.venv\Scripts\Activate.ps1
```

And on Mac/Linux:

```bash
source .venv/bin/activate
```

To download the necesary requirements, use the following commands:
```bash
python -m pip install -r requirements.txt
```

## Dataset
The dataset we used was the NATS-Bench Topology Search Space benchmark file from the official NATS-Bench repisotory.
You can downlaod the .tar file with the following link:

 `NATS-tss-v1_0-3ffb9-simple.tar` | [Google Drive](https://drive.google.com/file/d/17_saCsj_krKjlCBLOJEpNtzPXArMCqxU/view?usp=sharing) |

After downloading, extract the .tar archive into a folder named data in the project directory.

The notebook expect the extracted benchmark to be at:

```
data/NATS-tss-v1_0-3ffb9-simple
```

You can however change this value in the first section of the notebook from the BENCH_PATH variable

## Running the notebook

Open the Jupyter notebook in VS Code or a different program that can run Jupyter Notebook and select the Python environment that was just created. You can run the cells from top of Bottom.


The experiment itself uses three datasets: CIFAR-10 (validation version), CIFAR-100 and ImageNet16-120. Each algorithm is evaluated using 10 random seeds, considering 128 architectures per run. More information about the experiment can be found in the report.

## NoteBook structure

The notebook is organized in the following structure

1. Setup: Imports, loading the api and benchmark. Loading experiment parameters
2. NAS Algorithm: Implementations of the 5 NAS algorithms
3. Experiments run: Code for running the experiments on the three datasets and 10 different randomization seeds
4. Results: Code for creating tables and figures that can be used the analyze