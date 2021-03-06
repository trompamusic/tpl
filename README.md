# TROMPA Processing Library

Aggelos Gkiokas (aggelos.gkiokas@upf.edu)

## Overview

This repo contains two main programs:
- The TROMPA Processing Library (TPL) which a software that automatically triggers the algorithms and handles all the communication with the CE. Currently, for each algorithm an instance of the TPL must be invoked.
- The client library: it is a helper program provides an interface to create and (or) execute queries.


## Installation

    pip install git+https://github.com/trompamusic/trompa-ce-client.git

    git clone https://github.com/trompamusic/tpl

    cd tpl

    pip install -r requirements.txt


## Processing Library 

To invoke one the TPL for a specific algorithm/software one has to run the following:

    python -m tpl.application --connection ce_config_file --app app_config_file --client client_config_file [--force] [--execute]


`--connection`: configuration file for trompace-client containing information about CE connection

`--app`: configuration file containing information about the program

`--client`: a client configuration file created by the TPL of the client software. It describes the input/output/parameter of a specific algorithm

`--force`: a flag inficating that the app will be registered to the CE even if it has been done before (creates a new application/entry point/control action nodes)

`--execute`: a flag indicating if the algorithm will be executed or not (display only the command)

Examples of the configuration files can be found in the ./config/ folder

###Note:
In order to run the docker commands (algorithms) the TPL should be run as root, or
your user should have permission to run `docker`


## Processing Library Client

To invoke one the TPL for a specific algorithm/software one has to run the following:

    --client_ini client.ini --inputs {a list of inputs} --params {a list of params}

e.g.

    python client.py --client_ini client.ini --inputs 5ea78f18-8f12-46e0-ba38-582e254d4de7 5d6fadc9-0a32-4692-af44-afc0b692bafd -params 1 28 0.460487499990472 Soprano

