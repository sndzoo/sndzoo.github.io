---
layout: default
---


# [](#overview)Overview

<!--
<img align="left" width="200" height="200" style="margin-right: 30px" src="https://raw.githubusercontent.com/containernet/logo/master/containernet_logo_v1.png">

Containernet is a fork of the famous [Mininet](http://mininet.org) network emulator and allows to use [Docker](https://www.docker.com) containers as hosts in emulated network topologies. This enables interesting functionalities to build networking/cloud emulators and testbeds. One example for this is the [NFV multi-PoP infrastructure emulator](https://github.com/sonata-nfv/son-emu) which was created by the [SONATA-NFV](http://sonata-nfv.eu) project and is now part of the [OpenSource MANO (OSM)](https://osm.etsi.org) project. Besides this, Containernet is actively used by the research community, focussing on experiments in the field of cloud computing, fog computing, network function virtualization (NFV), and mobile edge computing (MEC).
<br><br><br>



## News and Releases

* 2018-04-03: [Release: Containernet 2.0](https://github.com/containernet/containernet/releases/tag/v2.0)
* 2017-09-04: [Release: Containernet 1.0](https://github.com/containernet/containernet/releases/tag/v1.0)

## Cite this work

If you use [Containernet](containernet.github.io) for your work, please cite the following publication:

M. Peuster, H. Karl, and S. v. Rossem: [**MeDICINE: Rapid Prototyping of Production-Ready Network Services in Multi-PoP Environments**](http://ieeexplore.ieee.org/document/7919490/). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Palo Alto, CA, USA, pp. 148-153. doi: 10.1109/NFV-SDN.2016.7919490. (2016)

Bibtex:

```bibtex
@inproceedings{peuster2016medicine, 
    author={M. Peuster and H. Karl and S. van Rossem}, 
    booktitle={2016 IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN)}, 
    title={MeDICINE: Rapid prototyping of production-ready network services in multi-PoP environments}, 
    year={2016}, 
    volume={}, 
    number={}, 
    pages={148-153}, 
    doi={10.1109/NFV-SDN.2016.7919490},
    month={Nov}
}
```


# [](#get-started)Get started

Using Containernet is very similar to using Mininet with [custom topologies](http://mininet.org/walkthrough/#custom-topologies).

## Create a custom topology

To start, a Python-based network topology description has to be created as shown in the following example:

```python
"""
Example topology with two containers (d1, d2),
two switches, and one controller:

          - (c)-
         |      |
(d1) - (s1) - (s2) - (d2)
"""
from mininet.net import Containernet
from mininet.node import Controller
from mininet.cli import CLI
from mininet.link import TCLink
from mininet.log import info, setLogLevel
setLogLevel('info')

net = Containernet(controller=Controller)
info('*** Adding controller\n')
net.addController('c0')
info('*** Adding docker containers using ubuntu:trusty images\n')
d1 = net.addDocker('d1', ip='10.0.0.251', dimage="ubuntu:trusty")
d2 = net.addDocker('d2', ip='10.0.0.252', dimage="ubuntu:trusty")
info('*** Adding switches\n')
s1 = net.addSwitch('s1')
s2 = net.addSwitch('s2')
info('*** Creating links\n')
net.addLink(d1, s1)
net.addLink(s1, s2, cls=TCLink, delay='100ms', bw=1)
net.addLink(s2, d2)
info('*** Starting network\n')
net.start()
info('*** Testing connectivity\n')
net.ping([d1, d2])
info('*** Running CLI\n')
CLI(net)
info('*** Stopping network')
net.stop()
```

You can find this topology in [`containernet/examples/containernet_example.py`](https://github.com/containernet/containernet/tree/master/examples/containernet_example.py).

## Run emulation and interact with containers

Containernet requires root access to configure the emulated network described by the topology script:

```bash
sudo python containernet_example.py
```

After launching the emulated network, you can interact with the involved containers through Mininet's interactive CLI as shown with the `ping` command in the following example:

```bash
containernet> d1 ping -c3 d2
PING 10.0.0.252 (10.0.0.252) 56(84) bytes of data.
64 bytes from 10.0.0.252: icmp_seq=1 ttl=64 time=200 ms
64 bytes from 10.0.0.252: icmp_seq=2 ttl=64 time=200 ms
64 bytes from 10.0.0.252: icmp_seq=3 ttl=64 time=200 ms

--- 10.0.0.252 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2002ms
rtt min/avg/max/mdev = 200.162/200.316/200.621/0.424 ms
containernet>
```

To stop the emulation, do:

```
containernet> exit
```

# [](#installation)Installation
Containernet comes with three installation and deployment options.

## Option 1: Bare-metal installation
Automatic installation is provided through an Ansible playbook. Requires: Ubuntu **16.04 LTS**.

```bash
sudo apt-get install ansible git aptitude
git clone https://github.com/containernet/containernet.git
cd containernet/ansible
sudo ansible-playbook -i "localhost," -c local install.yml
```

## Option 2: Nested Docker deployment
Containernet can be executed within a privileged Docker container (nested container deployment). There is also a pre-build Docker image available on [DockerHub](https://hub.docker.com/r/containernet/containernet/).

```bash
# build the container locally
docker build -t containernet .
```

```bash
# or pull the latest pre-build container
docker pull containernet/containernet
```

```bash
# run the container
docker run --name containernet -it --rm --privileged --pid='host' -v /var/run/docker.sock:/var/run/docker.sock containernet /bin/bash
```

## Option 3: Vagrant-based VM creation
Using the provided Vagrantfile is the another way to run and test Containernet:

```bash
vagrant up
vagrant ssh
```

# [](#libvirt)Libvirt Extension

Containernet 2.0 comes with an extended version that adds [libvirt](https://libvirt.org) support which allows to connect and run arbitrary, fully-featured virtual machines (Qemu/KVM) as emulated hosts inside Containernet networks. You can find this extension in a dedicated [branch on GitHub](https://github.com/containernet/containernet/tree/libvirt_support). More documentation about the libvirt integration is available on this [wiki page](https://github.com/containernet/containernet/wiki/Libvirt-Support). *Note: The libvirt integration is still in an early stage and should be considered as experimental code!*

# [](#references)References

Containernet has been used for a variety of research tasks and networking projects. If you use Containernet, let us know!

## Publications

* M. Peuster, H. Karl, and S. v. Rossem: [MeDICINE: Rapid Prototyping of Production-Ready Network Services in Multi-PoP Environments](http://ieeexplore.ieee.org/document/7919490/). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Palo Alto, CA, USA, pp. 148-153. doi: 10.1109/NFV-SDN.2016.7919490. IEEE. (2016)

* S. v. Rossem, W. Tavernier, M. Peuster, D. Colle, M. Pickavet and P. Demeester: [Monitoring and debugging using an SDK for NFV-powered telecom applications](https://biblio.ugent.be/publication/8521281/file/8521284.pdf). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Palo Alto, CA, USA, Demo Session. IEEE. (2016)

* Qiao, Yuansong, et al. [Doopnet: An emulator for network performance analysis of Hadoop clusters using Docker and Mininet.](http://ieeexplore.ieee.org/document/7543832/) Computers and Communication (ISCC), 2016 IEEE Symposium on. IEEE. (2016)

* M. Peuster, S. Dräxler, H. Razzaghi, S. v. Rossem, W. Tavernier and H. Karl: [A Flexible Multi-PoP Infrastructure Emulator for Carrier-grade MANO Systems](https://cs.uni-paderborn.de/fileadmin/informatik/fg/cn/Publications_Conference_Paper/Publications_Conference_Paper_2017/peuster_netsoft_demo_paper_2017.pdf). In IEEE 3rd Conference on Network Softwarization (NetSoft) Demo Track . (2017) **Best demo award!**

* M. Peuster and H. Karl: [Profile Your Chains, Not Functions: Automated Network Service Profiling in DevOps Environments](http://ieeexplore.ieee.org/document/8169826/). IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN), Berlin, Germany. IEEE. (2017)

* M. Peuster, H. Küttner and H. Karl: [Let the state follow its flows: An SDN-based flow handover protocol to support state migration](https://ris.uni-paderborn.de/publication/3345). In IEEE 4th Conference on Network Softwarization (NetSoft). IEEE. (2018) **Best student paper award!**

* M. Peuster, J. Kampmeyer and H. Karl: [Containernet 2.0: A Rapid Prototyping Platform for Hybrid Service Function Chains](https://ris.uni-paderborn.de/publication/3346). In IEEE 4th Conference on Network Softwarization (NetSoft) Demo, Montreal, Canada. (2018)

* M. Peuster, M. Marchetti, G. García de Blas, H. Karl: [Emulation-based Smoke Testing of NFV Orchestrators in Large Multi-PoP Environments](https://ris.uni-paderborn.de/publication/3347). In IEEE European Conference on Networks and Communications (EuCNC), Lubljana, Slovenia. (2018)

* S. Schneider, M. Peuster,Wouter Tvernier and H. Karl: A Fully Integrated Multi-Platform NFV SDK. In IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN) Demo, Verona, Italy. (2018)

* M. Peuster, S. Schneider, Frederic Christ and H. Karl: [A Prototyping Platform to Validate and Verify Network Service Header-based Service Chains](https://ris.uni-paderborn.de/record/6483). In IEEE Conference on Network Function Virtualization and Software Defined Networks (NFV-SDN) 5GNetApp, Verona, Italy. (2018)

## Containernet is part of the OpenSource MANO research ecosystem

<center>
<a href="https://osm.etsi.org/wikipub/index.php/Research" target="_blank">
<img align="center" width="300" style="margin-right: 30px" src="https://github.com/containernet/containernet.github.io/raw/master/osm_ecosystem_research.png"></a>
</center>

## Links

* [Mininet website](http://mininet.org)
* [Maxinet website](http://maxinet.github.io)
* [Docker](https://www.docker.com)

# [](#contact)Contact

## Support
If you have any questions, please use GitHub's [issue system](https://github.com/containernet/containernet/issues) or Containernet's [Gitter channel](https://gitter.im/containernet/) to get in touch.

## Contribute
Your contributions are very welcome! Please fork the GitHub repository and create a pull request. We use [Travis-CI](https://travis-ci.org/containernet/containernet) to automatically test new commits. 

## Lead developer

Manuel Peuster
* Mail: <manuel (dot) peuster (at) upb (dot) de>
* GitHub: [@mpeuster](https://github.com/mpeuster)
* Website: [Paderborn University](https://cs.uni-paderborn.de/cn/person/?tx_upbperson_personsite%5BpersonId%5D=13271&tx_upbperson_personsite%5Bcontroller%5D=Person&cHash=bafec92c0ada0bdfe8af6e2ed99efb4e)
-->
