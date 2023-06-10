# Helm

## Helm
Helm is a package manager for Kubernetes that allows you to define, install, and manage applications and services on a Kubernetes cluster. It provides a way to package all the necessary resources and configurations for your application into a single deployable unit called a Helm chart.

## Installation
  Download the latest version of Helm commandline tool
```h
wget https://get.helm.sh/helm-v3.12.0-linux-amd64.tar.gz
```
Extract the tar file using 
```sh
tar -xvzf helm-v3.12.0-linux-amd64.tar.gz
```
Move the binary file to /usr/local/bin/helm
```sh
sudo mv linux-amd64/helm /usr/local/bin/helm 
```
check version
```sh
helm version
```

## To get started with Helm, follow these steps:

Step 1: Create a Helm Chart
```sh
helm create mychart
```
Step 2: check the syntax and validity of a Helm chart
```sh
helm lint <chart-directory>
```
Step 3: Customize the Chart
Inside the mychart directory, you'll find several files. The most important ones are:

Chart.yaml: This file contains metadata about the chart, such as its name, version, and description.

values.yaml: This file contains the default configuration values for your application.

templates/: This directory contains the template files for the Kubernetes resources that will be deployed.

You can modify these files according to your application's requirements.

Step 4: Package and Install the Chart
```sh
helm package mychart
```
This command will create a .tgz file in the current directory containing your chart.

Step 5: To install the chart on your Kubernetes cluster, you can use the following command:
```sh
helm install myrelease mychart-0.1.0.tgz
```
Step 6: Upgrade the Chart
```sh
helm upgrade myrelease mychart-0.2.0.tgz
```
Step 7: list of releases deployed
```sh
helm list
```
step 8: list of all releases, including deleted ones. 
```sh
helm list -a
```
Step 9:Uninstall the Chart
```sh
helm uninstall myrelease
```
## Example
```sh
git clon https://github.com/TECDevOps/web-app.git
or
helm create web-app 
helm lint web-app
helm package web-app web-app-0.1.0.tgz
helm install web-app-1 web-app-0.1.0.tgz
helm package web-app web-app-0.2.0.tgz
helm upgrade web-app-2 web-app-0.2.0.tgz
helm list -a
helm uninstall web-app-2
```

 









