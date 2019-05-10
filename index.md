---
layout: default
---

```python
"""
#
#
# Attention: This page is under construction!
#
#
"""
```


# [](#overview)The Software Network Data Zoo

dassd 
dsadsa
dadsdasd
asdda

# [](#cite)Cite

# [](#data)Data sets
# [](#doc)Documentation
# [](#contribute)How to contribute?
# [](#contact)Contact

## Acknowledgments
This work has received funding from the European Union's Horizon 2020 research and innovation program under grant agreement No. H2020-ICT-2016-2 761493 ([5GTANGO](https://5gtango.eu)), and the German Research Foundation (DFG) within the Collaborative Research Centre ["On-The-Fly Computing" (SFB 901)](https://sfb901.uni-paderborn.de/).

## License
(c) 2019 by Manuel Peuster (Paderborn University)<br /><br />
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.


<!--


```sh
$ git clone git@github.com:sndzoo/ds_nfv_sec01.git
Cloning into 'ds_nfv_sec01'...
remote: Enumerating objects: 32, done.
remote: Counting objects: 100% (32/32), done.
remote: Compressing objects: 100% (28/28), done.
remote: Total 32 (delta 2), reused 29 (delta 2), pack-reused 0
Receiving objects: 100% (32/32), 45.70 KiB | 0 bytes/s, done.
Resolving deltas: 100% (2/2), done.
Checking connectivity... done.
$ cd ds_nfv_sec01
$ dvc pull
Preparing to download data from 'https://sndzoo.s3.amazonaws.com/ds_nfv_sec01'
Preparing to collect status from https://sndzoo.s3.amazonaws.com/ds_nfv_sec01
[##############################] 100% Collecting information
[##############################] 100% Analysing status.
(1/4): [##############################] 100% data/csv_experiments.csv
(2/4): [##############################] 100% data/raw_records.tar.gz
(3/4): [##############################] 100% data/csv_timeseries.tar.gz
(4/4): [##############################] 100% data/raw_prometheus_data.tar.gz
[##############################] 100% Checkout finished!
$ tree -h
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


<img align="left" width="200" height="200" style="margin-right: 30px" src="https://raw.githubusercontent.com/containernet/logo/master/containernet_logo_v1.png">

Containernet is a fork of the famous [Mininet](http://mininet.org) network emulator and allows to use [Docker](https://www.docker.com) containers as hosts in emulated network topologies. This enables interesting functionalities to build networking/cloud emulators and testbeds. One example for this is the [NFV multi-PoP infrastructure emulator](https://github.com/sonata-nfv/son-emu) which was created by the [SONATA-NFV](http://sonata-nfv.eu) project and is now part of the [OpenSource MANO (OSM)](https://osm.etsi.org) project. Besides this, Containernet is actively used by the research community, focussing on experiments in the field of cloud computing, fog computing, network function virtualization (NFV), and mobile edge computing (MEC).
<br><br><br>



