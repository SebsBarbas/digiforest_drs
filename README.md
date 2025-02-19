# DigiForest DRS

DRS tooling developed for the DigiForest project

Authors: Benoit Casseau, Matias Mattamala, Nived Chebrolu, Maurice Fallon

## Package descriptions

- `digiforest_analysis`: Python modules to extract tree data
- `digiforest_analysis_ros`: ROS wrappers
- `digiforest_slam_logger`: Tool to export a state estimate solution in the SLAM format

## Setup

Use a virtual environment (`env` in the example), isolated from the system dependencies:

```sh
python3 -m venv env
source env/bin/activate
```

Install the dependencies:

```sh
pip install -r requirements.txt
```

Install `python-pcl` (custom DRS build for PCL 1.10, not available on pypi):

```sh
gdown https://drive.google.com/uc?id=1zv2OO3tSRGvyNLqUt-R-gJYHAwodA3wW
pip install python_pcl-0.3.0rc1-cp38-cp38-linux_x86_64.whl && rm python_pcl-0.3.0rc1-cp38-cp38-linux_x86_64.whl
```

Install the automatic formatting pre-commit hooks (black and flake8), which will check the code before each commit:

```sh
pre-commit install
```

Install `digiforest_analysis`:

```sh
cd ~/git/digiforest_drs/digiforest_analysis
pip install -e .
```

## Execution

To run the offline pipeline:

```sh
cd ~/git/digiforest_drs/digiforest_analysis
python scripts/offline_pipeline.py <input_pcd_file> --out <output_directory>
```

This will export a series of PCD files:

```sh
ground_cloud.pcd
forest_cloud.pcd
tree_<ID>.pcd
...
```
