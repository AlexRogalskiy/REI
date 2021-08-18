# RASA X Simple Installer (RSI) 

RSI will help you to get an easy way to run and test RASA X / RASA OSS on your local workstation with a breeze.

## How does RSI manage the installation

RSI installs KIND as Platform to run RASA X / OSS Helmchart on top.

RSI will check Requirments and install for the supported OS:

- Docker
- kubectl
- helm
- kind
- RASA X official Helmchart

### Requirements

Supported OS:

- MacOS Catalina+
- Ubuntu / Debian
- ArchLinux / Manjaro

to work with RSI in an optimal enviroment please use a  System with the following resources at hand

Minimum / (Recommended)

- Dual-Core CPU / Quad-Core CPU
- 8 GB RAM / 16 GB RAM
- 25 GB DISK / 50 DISK

## Quick Installation
TL:DR;

```bash
curl -O https://raw.githubusercontent.com/RasaHQ/RSI/main/rsi.sh && bash rsi.sh --yes
```

or

```bash
wget https://raw.githubusercontent.com/RasaHQ/RSI/main/rsi.sh && bash rsi.sh --yes
```

after installation you can access RASA X via -> http://localhost/ 
password: test


## Installation

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/RasaHQ/RSI/main/rsi.sh)"
```

Note - The defaults of the install script can be overridden see the built-in help.

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/RasaHQ/RSI/main/rsi.sh)" -- --help
```

## FAQ

### how do I see all logfiles ?

to get all logfiles from the RASA X / OSS Deployment just run in your terminal

```bash
kubectl -n rasa logs -l app.kubernetes.io/name=rasa-x
```

### how do i remove the RSI Cluster locally ?

excute the rsi.sh script with the -u flag

```bash
bash rsi.sh -u
```

### how do i see all running RASA containers ?

all running pods are inside the rasa namespace via kubectl

```bash
kubectl -n rasa get pods
```

### how do i access the KIND K8S Cluster via kubectl ?

```bash
kubectl cluster-info --context kind-rasa

```