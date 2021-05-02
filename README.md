# Filenet Workload Creater

![](https://img.shields.io/github/stars/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/forks/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/tag/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/release/gokcenkarasu/FilenetWorkload.svg) 
![](https://img.shields.io/github/issues/gokcenkarasu/eFilenetWorkload.svg) 
![](https://img.shields.io/bower/v/FilenetWorkload.svg)

The repository aim is to create workload for Filenet on Kubernetes platform and traditional systems. 

> **Disclaimer:** If you are planning to use this standalone jar version please check your java version in your environment and please check the pre-requirments for your system. 

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

##  1. <a name='Summary'></a>Summary

This asset is created to show how to auto scale IBM Filenet pods and network performans on Kubernetes (Openshift) platform or you can run it to created workload on traditional Filenet deployment.

There are two different options you can select: 
Runnable container version or standalone jar version.

When you would like to see how to run auto scale Filenet pods in Openshift, you need to create manuel upload,read,review transactions at the same time, so it is hard to make it at the same time.
This program support to you to create diffrent files to upload your system at the same time by multi-thread features. 

The program able to select how many files do you upload and which size files. 

If you prefer to select using container version, you can enter the parameters when docker starting like enviortment or after  the startting container , program asks you these parameters. 

There are 2 different options to use this program:
	
> * Fist one is contianer base system. 
> * Second one is Jar base system. 
	
Both of them are using the same java codes of which you can find the details below. 


![Alt text](images/screenShotTerminal.png "filenetworkload")


##  2. <a name='JavaCode'></a>Java Code

*  I developed Javacode with 1.8 JDK in Eclipse development environment. 
 	
	There are 3 Classes to run this jar program. 
	
	** 1- ConnectionInfo = This is static abstraction class to use collecting data from getting user. 
	
	** 2- MultiThreadUpload = This includes runnable method and is using to get some information from user also extends ConnectionInfo class. First it checks system enviorment to get parameters then it wants parameters from operators.
	It has time units sleep method to wait thread until wait to runnig containers. 
	`TimeUnit.SECONDS.sleep(6);`
	
	** 3- AddDocument = This is main method which implements Runnable class and include uploading and creating files methods.
	

		Please enter thread size :

		File Sizes : xs = 1K
		File Sizes : s  = 10K
		File Sizes : m  = 100K
		File Sizes : l  = 1000K
		File Sizes : xl = 10000K
		Please enter sample file sizes (xs/s/m/l/xl) :

		Please enter Username :

		Please enter Password :

		Please enter Object Store Name :

		Please enter Folder Name :

		Please enter Server Url :

		Please enter Port :


If you select one of those options, the program executes only the selected one, if you enter "ALL" keyword, the program executes all of them to test it. 

 
##  3. <a name='ProductVersions'></a>Product Versions
	
This is 1.4 version of the program. 
	
I used Java 1.8 so If you are planning to use this standalone jar version please check your java version in your environment. Also if you want to use container version of the program, you need to have to at least one of these platforms: Docker, Podman, Kubernetes or Openshift.  Please check kubernetes client version , it must be min 1.10 version to run correctly kubectl codes below.


##  5. <a name='RunContainer'></a>How to run container version?

I used IBM JAVA container as a base of this program.

[Filenet Workload Connection Docker Hub](https://hub.docker.com/repository/docker/gokcenk/filenetworkload)

> `docker pull gokcenk/filenetworkload`

###  5.1. <a name='InDocker'></a>In Docker

>  `docker run -it --rm filenetworkload`

###  5.2. <a name='InKubernetes'></a>In Kubernetes

> `kubectl run flntwrkld --image=gokcenk/filenetworkload -it --rm`    

###  5.2. <a name='InOpenshift'></a>In Openshift

> `kubectl run flntwrkld --image=gokcenk/filenetworkload -it --rm`    

##  6. <a name='RunJarVerison'></a>How to run container version?

 > `java -jar FilenetWorkload.jar`
