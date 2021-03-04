|<a href="https://www.ebc.eonerc.rwth-aachen.de/"> <img alt="EBC" src="https://www.ebc.eonerc.rwth-aachen.de/global/show_picture.asp?id=aaaaaaaaaakevlz" height="100"> </a>|<a href="https://n5geh.de/"> <img alt="N5GEH" src="https://avatars.githubusercontent.com/u/43948851?s=200&v=4" height="100"> </a>|
|---|---|

# FiLiP 

[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)


FiLiP (Fiware Library for Python) is a python software development kit for 
accelerate the development of web services that use Fiware's Generic 
Enablers (GEs) as backend.

## General Motivation

Why implementing a client library in times when clients can be autogenerated 
from openapi documentation? 
However, a general prerequisite to do so is that the documentation is of 
good quality in whole depth. 
FIWARE generally provides [openapi documentation](https://github.com/FIWARE/specifications/tree/master/OpenAPI/ngsiv2)
But here are some general thoughts on auto generation of client code from 
these documents:

- Auto generated code tends to become rather bulky and its quality strongly
  depends on the provides input data.
- Manipulating generated code can result in a big hassle for maintenance if 
  additional features will be integrated.
- The underlying NGSI (New Generation Service Interface) for FIWARE is a
  rather generic specification.
  Hence, generated models may be also generic types as lists
  and dicts in Python. Hence, there is no real benefit.
  Furthermore, there is no chance for reasonable validation and error handling  

## FIWARE

The following section introduces FIWARE. If you are already familiar with 
FIWARE you can skip this section.

### What is FIWARE?

FIWARE, which is a framework of open-source cloud platform components created 
to facilitate the development of smart solutions within various application 
domain. 
At the moment, the FIWARE 
[catalogue](https://www.fiware.org/developers/catalogue/) contains over 30 
interoperable software modules, so-called Generic Enablers 
(GE)for developing and providing customized IoT platform solutions.

To get familiar with the APIs of the different modules we highly recommend 
to check the 
[step-by-step tutorial](https://fiware-tutorials.readthedocs.io/en/latest/). 
It provides a good overview of the most important concepts, but not all of 
it may be relevant to your use cases.
Usually, one only requires a small set of components. 
Nevertheless, the tutorial helps to understand the general concepts.

### How to setup a FIWARE platform?

The easiest way to setup a FIWARE platform is by using docker as all GEs are 
developed open-source and distributed as docker containers on dockerhub.

However, as mentioned, for most use cases only a subset of GEs is required.
Hence, we wrote a small [tutorial](https://github.com/N5GEH/n5geh.platform) 
explaining how to setup a platform suited for most use cases within the energy 
domain. 

### FIWARE GEs covered by FiLIP

FiLIP is library developed on the demand.
Hence, we do not aim to cover the APIs of all GEs included in the 
[catalogue](https://www.fiware.org/developers/catalogue/), which would mean an 
unnecessary development overhead. 
Therefore, currently covers the APIs of following GEs:

- NGSIv2 Context Broker for managing of context data. We use the its 
  reference implementation ORION.
    - [documention](https://fiware-orion.readthedocs.io/en/master/)
    - [github](https://github.com/telefonicaid/fiware-orion)
    - [swagger](https://swagger.lab.fiware.org/)
    - [NGSI v2 specifications](https://github.com/FIWARE/specifications/tree/master/OpenAPI/ngsiv2)
    
    
- IoT-Agents for managing IoT Devices. IoT agents are implemented using 
  the FIWARE IoT Agent Node Lib as a common framework:
    - [documention](https://iotagent-node-lib.readthedocs.io/en/latest/)
    - [github](https://github.com/telefonicaid/iotagent-node-lib)
    
- IoT-Agent-JSON for managing devices using a JSON message payload protocol 
  format.
  
    - [documentation](https://fiware-iotagent-json.readthedocs.io/en/latest/)
    - [github](https://github.com/telefonicaid/iotagent-json)
    - [apiary](https://telefonicaiotiotagents.docs.apiary.io/) 
    (*partly deprecated*)

  Example payload:
  
        {
            "humidity": "45%",
            "temperature": "23",
            "luminocity": "1570"
        }  

- IoT-Agent-Ultralight for managing devices using a Ultralight 2.0 message 
  payload protocol.
  
    - [documentation](https://fiware-iotagent-ul.readthedocs.io/en/latest/)
    - [github](https://github.com/telefonicaid/iotagent-ul)
    - [apiary](https://telefonicaiotiotagents.docs.apiary.io/) 
      (*partly deprecated*)
    
    Example payload:
  
        humidity|45%|temperature|23|luminocity|1570
        
- QuantumLeap for the management of time series data
  
    - [documentation](https://quantumleap.readthedocs.io/en/latest/)
    - [github](https://github.com/FIWARE-GEs/quantum-leap)
    - [swagger](https://app.swaggerhub.com/apis/smartsdk/ngsi-tsdb/0.7) (*not 
      up to date*, newest API version is 8.0)

## Getting started

### Installation

The easiest way to install the library is via pip:

```
pip install git+git://github.com/n5geh/n5geh.tools.filip

```

### Running examples or tests

Explain how to run the automated tests for this system or any beginner-friendly examples of how to use it.

## Documentation

In-depth documentation can be found in the project [wiki].

## Authors

* [Thomas Storek](https://www.ebc.eonerc.rwth-aachen.de/cms/E-ON-ERC-EBC/Das-Institut/Mitarbeiter/N5GEH-National-5G-Energy-Hub/~lhda/Thomas-Storek/?allou=1) (corresponding)
* **Felix Rehmann**

## References

We presented the library in the following publications:

- Baranski, M., Storek, T. P. B., Kümpel, A., Blechmann, S., Streblow, R., 
Müller, D. et al.,
(2020). National 5G Energy Hub : Application of the Open-Source Cloud Platform 
FIWARE for Future Energy Management Systems. 
https://doi.org/10.18154/RWTH-2020-07876

- T. Storek, J. Lohmöller, A. Kümpel, M. Baranski & D. Müller (2019). 
Application of the open-source cloud platform FIWARE for future building 
energy management systems. 
Journal of Physics: 
Conference Series, 1343, 12063. https://doi.org/10.1088/1742-6596/1343/1/012063

## License

This project is licensed under the BSD License - see the [LICENSE](LICENSE) file for details

## Copyright

2021, RWTH Aachen University, E.ON Energy Research Center, Institute for Energy 
Efficient Buildings and Indoor Climate

[Institute for Energy Efficient Buildings and Indoor Climate (EBC)](http://www.ebc.eonerc.rwth-aachen.de)  
[EON Energy Research Center (EONERC)](http://www.eonerc.rwth-aachen.de)  
[RWTH University Aachen, Germany](http://www.rwth-aachen.de)

## Acknowledgments

We gratefully acknowledge the financial support by Federal Ministry \\ for Economic Affairs and Energy (BMWi), promotional reference XXX.

|<a href="https://www.bmwi.de/Navigation/EN/Home/home.html"> <img alt="BMWE" src="https://www.bmwi.de/SiteGlobals/BMWI/StyleBundles/Bilder/bmwi_logo_en.svgz?__blob=normal&v=10" height="100"> </a>|
|---|