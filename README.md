# ML Monitor
This codebase builds on the original ML_monitor as presented in https://github.com/wiatrak2/ml_monitor
This repository work on local installation of Python only and DOES NOT Support Colab at the moment.
### Requirements:
* python >= 3.6
* [docker](https://www.docker.com)
## Installation
1. Clone and enter the repository
```bash
git clone https://github.com/sohiniroych/ML-Monitoring-with-Grafana.git
cd ML-Monitoring-with-Grafana
```
2. Install package using `pip`
```bash
pip install .
```
3. Install and Setup docker
```bash
sudo snap install docker
sudo apt install docker-compose
```
This process will set up the docker image that houses the Grafana Dashboad!

## Processing (shown in the video)

1. Enable docker using the command
```bash
cd docker
sudo docker-compose up
```
* `docker` directory contains an easy setup of tools used for metrics visualization and analysis. These are [Prometheus](https://prometheus.io) and [Grafana](https://grafana.com). You should firstly start these programs, with `docker-compose up` command. Now you should be able to reach the Grafana admin panel on http://localhost:3000. 
* Logging in for the first time use username: admin, password: ml_monitor

2. To set up the ml_monitor sensing through post 9090, open a separate terminal and enter the following:
```
python
import ml_monitor
ml_monitor.control.start()
```
You will get a message that a Prometheus UI should be reachable on http://localhost:9090. 

3. Setup Jupyter notebook and open the file "ML_minitoring_Grafana.ipynb"
Run this file. The first part will train the model and in the end random test samples will be generated to mimic a production setup. Increase the number of "epochs" to run for a longer Production-like setup

4. Open the Grafana dashboard at http://localhost:3000 and monitor the "n_rmse" metric.

# Congratulations, now you know how to monitor metrics at production time!
