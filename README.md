# Face-Detection-Using-Haar-Cascade

1. Create virtual environment with all the dependencies
conda env create -f Virtual_Env.yml
2. Activate environment
conda activate env
3. Open Jupyter notebook
jupyter notebook
4. Open Face Detection with Haar Cascade Features.ipynb file in Jupyter notebook

And the file should run. Tada!!


## Push Swift-Recon Data from Prometheus Python Client with Pushgateway
This repository demonstrates how to use the Prometheus Python client library to push swift-recon metrics to a Prometheus Pushgateway and set up alerting rules in Prometheus.

### Introduction
Prometheus Pushgateway is used for pushing metrics from short-lived batch jobs. This repository focuses on:\
	1. Using the Prometheus Python client library for defining and pushing metrics.\
	2. Configuring Prometheus to alert based on the pushed metrics.

### Prerequisites
Python 3.6 or later installed.\
SAIO : [Configure Swift](https://docs.openstack.org/swift/latest/development_saio.html)

### Quick Start Guide
* Set up Promethueus\
	Download the latest release from [Prometheus Github](https://github.com/prometheus/prometheus/releases)
````bash
	tar -xvzf prometheus-*.tar.gz
	cd prometheus-*
	./prometheus --config.file=prometheus.yml --web.enable-lifecycle
````
Ensure Prometheus UI is running at http://localhost:9090

* Install the prometheus-client Python library using pip:
````bash
	pip install prometheus-client
````

* Set up Prometheus Pushgateway\
	Download the latest release from [Pushgateway](https://prometheus.io/download/)
````bash
	tar -xvf pushgateway-1.4.3.linux-amd64.tar.gz
	./pushgateway --web.listen-address=":9091"
````
Ensure Pushgateway is running at ````http://localhost:9091````

* Clone this repository
````bash
	git clone https://github.com/username/prometheus-pushgateway-python.git
	cd prometheus-pushgateway-python
	cp prometheus.yml <your-prometheus-path>/prometheus.yml
	cp alerts.yml <your-prometheus-path>/alerts.yml
````
* Reload Prometheus Configuration

After copying the configuration, reload Prometheus:
````bash
	curl -X POST http://localhost:9090/-/reload
`````

### Execute Script

* Run prometheus_recon.py with required options

Usage: prometheus_recon.py [options]

Options:\
-h, --help show this help message and exit\
-v, --verbose Print verbose info\
--suppress Suppress most connection related errors\
--swiftdir=SWIFTDIR Default = /etc/swift

````bash
	python3 prometheus_recon.py --swiftdir /etc/swift --verbose
````
Currently, the script pushes details for async, quarantined replication/object from swift-recon.

With this repository, you can easily push metrics from Python applications to Prometheus Pushgateway and set up alerts in Prometheus. For issues or contributions, feel free to create a pull request or raise an issue.\
Happy Monitoring! 🎉
