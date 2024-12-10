# Face-Detection-Using-Haar-Cascade

1. Create virtual environment with all the dependencies
conda env create -f Virtual_Env.yml
2. Activate environment
conda activate env
3. Open Jupyter notebook
jupyter notebook
4. Open Face Detection with Haar Cascade Features.ipynb file in Jupyter notebook

And the file should run. Tada!!
# Prometheus Python Client with Pushgateway
This repository demonstrates how to use the Prometheus Python client library to push metrics to a Prometheus Pushgateway and set up alerting rules in Prometheus.

## Table of Contents
[Introduction](#about-the-job-and-instance-labels)
[Setup Instruction](#about-the-job-and-instance-labels)


## Introduction
Prometheus Pushgateway is used for pushing metrics from short-lived batch jobs. This repository focuses on:
	Using the Prometheus Python client library for defining and pushing metrics.
	Configuring Prometheus to alert based on the pushed metrics.


## Setup Instructions
* Clone this repository
```bash
	git clone https://github.com/your-username/prometheus-pushgateway-python.git  
	cd prometheus-pushgateway-python  

* Install Dependencies
	Make sure you have Python 3.6 or later installed.
	Install the premetheus-client Python library using pip:

		pip install prometheus-client  

* Getting Started
	Set up Prometheus Pushgateway
		Download and run Pushgateway

			wget https://github.com/prometheus/pushgateway/releases/download/v1.4.3/pushgateway-1.4.3.linux-amd64.tar.gz  
			tar -xvf pushgateway-1.4.3.linux-amd64.tar.gz  
			./pushgateway --web.listen-address=":9091"  
````
		Ensure the Pushgateway is running at http://localhost:9091.

