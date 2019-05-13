---
layout: default
---

```python

"""
This page is under construction.
"""

```

# [](#overview)The Softwarised Network Data Zoo

<img align="left" width="200" height="200" style="margin-right: 30px" src="https://github.com/sndzoo/logo/raw/master/sndzoo_logo_small_trans.png">

The *softwarised network data zoo (SNDZoo)* is an open collection of software networking data sets aiming to streamline and ease machine learning research in the software networking domain. Most of the published datasets focus on, but are not limited to, the performance of virtualised network functions (VNFs). The data is collected using fully automated NFV benchmarking frameworks, such as [tng-bench](https://github.com/sonata-nfv/tng-sdk-benchmark) [[1], [2]](#references).

All data sets are archived in their own GitHub repository using [data version control (DVC)](https://dvc.org) as technology to manage and version the contained table- and time series-based data. If you are working in the network softwarisation domain, you are welcome to [contribute](#contribute) your own data sets to this project.


# [](#cite)Cite

To cite this work or one of the data sets, please use:

```bibtex
@inproceedings{peuster2019sndzoo,
	Author = {Peuster, Manuel and Schneider, Stefan and Karl, Holger},
	Booktitle = {TODO)},
	Keywords = {Measurement;Network function virtualization;Machine learning; Open data sets},
	Month = {TODO},
	Pages = {TODO},
	Title = {{The Softwarised Network Data Zoo}},
	Year = {2019}
}
```

# [](#data)Available data sets

Overview of data sets available in the SNDZoo:

| Data set name | Class | SUT | Configs | Exp. metrics | TS metrics | Total data points | Data |
|---------------|---------------|---------------|-----------------------|--------------------|---------------------|-------------------|-----------|
| [SEC01](https://github.com/sndzoo/ds_nfv_sec01) | IDS System | [Suricata VNF](https://cloud.docker.com/repository/docker/mpeuster/vnf-ids-suricata) | [1600](https://github.com/sndzoo/ds_nfv_sec01/blob/master/meta/ped.yml) | 280 | 157 | 7.9M | [Repo](https://github.com/sndzoo/ds_nfv_sec01), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [SEC02](https://github.com/sndzoo/ds_nfv_sec02) | IDS System | [Snort 2.9 VNF](https://cloud.docker.com/repository/docker/mpeuster/vnf-ids-snort2) | [1600](https://github.com/sndzoo/ds_nfv_sec02/blob/master/meta/ped.yml) | 280 | 169 | 8.6M | [Repo](https://github.com/sndzoo/ds_nfv_sec02), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [SEC03](https://github.com/sndzoo/ds_nfv_sec03) | IDS System | [Snort 3.0 VNF](https://cloud.docker.com/repository/docker/mpeuster/vnf-ids-snort3) | [800](https://github.com/sndzoo/ds_nfv_sec03/blob/master/meta/ped.yml) | 281 | 593 | 14.5M | [Repo](https://github.com/sndzoo/ds_nfv_sec03), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [WEB01](https://github.com/sndzoo/ds_nfv_web01) | Load balancer | [Nginx VNF](https://cloud.docker.com/u/mpeuster/repository/docker/mpeuster/vnf-lb-nginx) | [1600](https://github.com/sndzoo/ds_nfv_web01/blob/master/meta/ped.yml) | 268 | 43 | 2.5M | [Repo](https://github.com/sndzoo/ds_nfv_web01), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [WEB02](https://github.com/sndzoo/ds_nfv_web02) | Load balancer | [HAProxy VNF](https://cloud.docker.com/u/mpeuster/repository/docker/mpeuster/vnf-lb-haproxy) | [1600](https://github.com/sndzoo/ds_nfv_web02/blob/master/meta/ped.yml) | 268 | 43 | 2.5M | [Repo](https://github.com/sndzoo/ds_nfv_web02), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [WEB03](https://github.com/sndzoo/ds_nfv_web03) | Proxy | [Squid VNF](https://cloud.docker.com/u/mpeuster/repository/docker/mpeuster/vnf-px-squid) | [1600](https://github.com/sndzoo/ds_nfv_web03/blob/master/meta/ped.yml) | 268 | 43 | 2.5M | [Repo](https://github.com/sndzoo/ds_nfv_web03), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [IOT01](https://github.com/sndzoo/ds_nfv_iot01) | MQTT Broker | [Mosquitto VNF](https://cloud.docker.com/u/mpeuster/repository/docker/mpeuster/vnf-broker-mosquitto) | [1600](https://github.com/sndzoo/ds_nfv_iot01/blob/master/meta/ped.yml) | 275 | 90 | 4.7M | [Repo](https://github.com/sndzoo/ds_nfv_iot01), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |
| [IOT02](https://github.com/sndzoo/ds_nfv_iot02) | MQTT Broker | [Emqx VNF](https://cloud.docker.com/u/mpeuster/repository/docker/mpeuster/vnf-broker-emqx) | [1600](https://github.com/sndzoo/ds_nfv_iot02/blob/master/meta/ped.yml) | 275 | 90 | 4.7M | [Repo](https://github.com/sndzoo/ds_nfv_iot02), [ZIP](https://www.amazon.de/clouddrive/share/uhWZecRzEhosckpO7ri4bQIW06rYykBBfsPugZbVICp) |

# [](#doc)Documentation

The following sections describe and use the data sets.

## How to download the data sets?

Each data set is stored in its own GitHub repository from which the data files are linked using [DVC](https://dvc.org). To download and use the data sets, you should use Git and DVC to ensure that you can always access the latest version of the data set. As a fallback, we also linked ZIP versions of each data set. However, the ZIP versions might be slightly outdated and not as well maintained as the Git/DVC versions are.

To get the data set (using [SEC01](https://github.com/sndzoo/ds_nfv_sec01) as example) do:

1. Install Git/DVC: [https://dvc.org/](https://dvc.org/)
2. Clone the data set repository: `git clone https://github.com/sndzoo/ds_nfv_sec01.git`
3. Switch to the cloned repository: `cd ds_nfv_sec01`
4. Pull the data using DVC: `dvc pull`

Full example:

```sh
# 1. install DVC
$ pip install dvc

# 2. clone data set git repository
$ git clone https://github.com/sndzoo/ds_nfv_sec01.git

# 3. switch folder
$ cd ds_nfv_sec01

# 4. pull the data files
$ dvc pull
```

DVC will start to download the data files belonging to the data set. This process might take some minutes (depending on your Internet connection):

```
Preparing to download data from 'https://sndzoo.s3.amazonaws.com/ds_nfv_sec01'
Preparing to collect status from https://sndzoo.s3.amazonaws.com/ds_nfv_sec01
[##############################] 100% Collecting information
[##############################] 100% Analysing status.
(1/4): [##############################] 100% data/csv_experiments.csv
(2/4): [##############################] 100% data/raw_records.tar.gz
(3/4): [##############################] 100% data/csv_timeseries.tar.gz
(4/4): [##############################] 100% data/raw_prometheus_data.tar.gz
[##############################] 100% Checkout finished!
```

## Structure of the data sets

All data sets follow a similar file/folder structure (using [SEC01](https://github.com/sndzoo/ds_nfv_sec01) as example):

```
$ tree -h ds_nfv_sec01
├── [4.0K]  meta
│   ├── [2.9K]  ped.yml
│   ├── [108K]  platform_hw_info.xml
│   ├── [ 298]  platform_sw_info_os.txt
│   ├── [113K]  platform_sw_info_pkg.txt
│   └── [ 14K]  ts_metrics.yml
├── [4.0K]  data
│   ├── [2.5M]  csv_experiments.csv
│   ├── [ 173]  csv_experiments.csv.dvc
│   ├── [ 67M]  csv_timeseries.tar.gz
│   ├── [ 175]  csv_timeseries.tar.gz.dvc
│   ├── [307M]  raw_prometheus_data.tar.gz
│   ├── [ 180]  raw_prometheus_data.tar.gz.dvc
│   ├── [ 33M]  raw_records.tar.gz
│   └── [ 172]  raw_records.tar.gz.dvc
├── [ 20K]  LICENSE
└── [2.0K]  README.md
```

* `meta/` Folder containing configurations and further information about the data collection process and platform.
* `ped.yml`
* `platform_hw_info.xml`
* `platform_sw_info_os.txt`
* `platform_sw_info_pkg.txt`
* `ts_metrics.yml`

* `data/` Folder containing the actual measurement data.
* `*.dvc` Reference file used by DVC. Not of interest for the user.
* `csv_experiments.csv` Table that contains the experiment metrics and configurations. Each column contains one experiment parameter or metric. Each row represents one execution of the experiment and contains the measured data. Default CSV file format that can be imported with, e.g., [Pandas](https://pandas.pydata.org/).
* `csv_timeseries.tar.gz` Archive containing the time series data collect during each experiment in CSV format. Each file contains one time series metric for one experiment execution. Each row contains one data record. The archive can contain hundreds of thousands of small CSV files.
* `raw_prometheus_data.tar.gz` RAW Prometheus data recorded during experiment. The `csv_timeseries.tar.gz` data is exported from this raw data  (for reference, only for advanced users).
* `raw_records.tar.gz` Raw outputs and measurements produced by [tng-bench](https://github.com/sonata-nfv/tng-sdk-benchmark). The  `csv_experiments.csv` file is exported from this raw data (for reference, only for advanced users).

## How to reproduce the experiments?



# [](#contribute)How to contribute?

```sh
# TODO #
```

# [](#references)References

* [1] M. Peuster and H. Karl: [Profile Your Chains, Not Functions: Automated Network Service Profiling in DevOps Environments](http://ieeexplore.ieee.org/document/8169826/). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Berlin, Germany. (2017)

* [2] M. Peuster, H. Karl, and S. v. Rossem: [MeDICINE: Rapid Prototyping of Production-Ready Network Services in Multi-PoP Environments](http://ieeexplore.ieee.org/document/7919490/). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Palo Alto, CA, USA, pp. 148-153. doi: 10.1109/NFV-SDN.2016.7919490. (2016)


# [](#contact)Contact

Manuel Peuster<br>
Computer Networks Group<br>
Paderborn University, Germany<br>
Mail: manuel (at) peuster (dot) de

## Acknowledgments
This work has received funding from the European Union's Horizon 2020 research and innovation program under grant agreement No. H2020-ICT-2016-2 761493 ([5GTANGO](https://5gtango.eu)), and the German Research Foundation (DFG) within the Collaborative Research Centre ["On-The-Fly Computing" (SFB 901)](https://sfb901.uni-paderborn.de/).

## License
(c) 2019 by Manuel Peuster (Paderborn University)<br /><br />
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

