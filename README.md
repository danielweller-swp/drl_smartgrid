# Reinforcement Learning Demo

From a joint effort of Sina Henning, Felix Krause und Johannes Spieß 

Mandatory assignment 1 for Artificial Intelligence for Energy Informatics at UiO Autumn 2023.


## Setup
### Environment setup

Create new environment "venv"
```shell
python -m venv venv
```

Activate env in bash:
```bash
source venv/bin/activate
```

Install packages in venv
```bash
pip install -r requirements.txt
```

Add virtual environment to kernel
```bash
python -m ipykernel install --user --name=venv
```

### Provide Datasets
There is already all data needed in the data/directory. 

For full replication (and more freedom regarding the energy demand), put the following datasets into a folder "/data" in this repo
* [SolarIrradiance.csv](https://drive.google.com/file/d/1SUjtybPtUzwSEDQoqXbMNijEeDi8QF8m/view)
* [rate_consumption_charge.csv/electricity price](https://drive.google.com/file/d/1uxM9TC401TBwjcdxe3i7TAxSo9tPNWi1/view)
* [WindSpeed.csv](https://drive.google.com/file/d/1X87VRm88-Tp2cs9zjmOB0R6wTxJl8QBf/view)

And put the "BASE" profiles in a folder "/data/residential_load_data_base"
* **[Residential load profiles](https://data.openei.org/files/153/RESIDENTIAL_LOAD_DATA_E_PLUS_OUTPUT.zip)**: Check out data source [here](https://data.openei.org/submissions/153)

## Run training
Open the notebook ["notebooks/1_training.ipynb"](notebooks/1_training.ipynb) and follow instructions.

## Analysis of results
Open the notebook ["notebooks/2_result_viz.ipynb"](notebooks/2_result_viz.ipynb).


## Conventions
* The main unit used for energy is kWh
* The used time frame is an hour


## RL software

* **[pymgrid](https://github.com/Total-RD/pymgrid)** is discontinued, we looked at its successor python-microgrid
* **[python-microgrid](https://github.com/ahalev/python-microgrid/tree/master)** can be used "to generate and simulate a large number of microgrids"; according to their [data section](https://github.com/ahalev/python-microgrid/tree/master#data), they als use OpenEI load data and PV datasets ("Data in pymgrid are based on TMY3 (data based on representative weather)", this might be EnergyPlus)
* **[easygrid:](https://github.com/YannBerthelot/easygrid/tree/main)** a simple version based on [OpenAI gym](https://github.com/openai/gym), maybe we should use this to get started
* **[example tutorial](https://github.com/Wenuka/RL_for_energy_tutorial)** an example project that is very similar to ours
* **[gym environments](https://www.gymlibrary.dev//content/environment_creation/#)** tutorial on how to create a RL environment
* **[stable baselines3](https://stable-baselines3.readthedocs.io/en/master/modules/ppo.html)** documentary of stable baselines3