# Filenet Workload Creater

![](https://img.shields.io/github/stars/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/forks/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/tag/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/release/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/issues/gokcenkarasu/eFilenetWorkload.svg) 
![](https://img.shields.io/bower/v/FilenetWorkload.svg)

The repository aim is to create workload for Filenet on Kubernetes platform and traditional systems. 

<!-- vscode-markdown-toc -->

* 1.[Summary](#Summary)
* 2.[Java Code](#JavaCode)
* 3.[Product Versions](#ProductVersions)
* 4.[Pre-Requirements](#PreRequirements)
* 5.[How to run container version](#RunContainer)
	* 5.1. [In Docker](#InDocker)
	* 5.2. [In Kubernetes](#InKubernetes)
	* 5.3. [In Openshift](#InOpenshift)
* 6.[How to run jar version](#RunJarVerison)

<!-- vscode-markdown-toc-config numbering=true autoSave=true /vscode-markdown-toc-config -->

<!-- /vscode-markdown-toc -->

##  5. <a name='RunContainer'></a>How to run container version?

I used IBM JAVA container as a base of this program.

[Oracle Test Connection Docker Hub](https://hub.docker.com/repository/docker/gokcenk/filenetworkload)

> `docker pull gokcenk/filenetworkload`

###  5.1. <a name='InDocker'></a>In Docker

>  `docker run -it --rm filenetworkload`

###  5.2. <a name='InKubernetes'></a>In Kubernetes

> `kubectl run orcl --image=gokcenk/filenetworkload -it --rm`    

###  5.2. <a name='InOpenshift'></a>In Openshift

> `kubectl run orcl --image=gokcenk/filenetworkload -it --rm`    

##  6. <a name='RunJarVerison'></a>How to run container version?

 > `java -jar FilenetWorkload.jar`
