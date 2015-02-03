W00t? 
==================

This repository contains description of the third Cloudopoly challenge. Cloudopoly is a set of challenges targeted towards raising awareness of AWS stack. Winners will get prizes from AWS! The first Cloudopoly will have 3 challenges, one per month. By getting 3 times in top 3 you will win a special prize from LatCraft.

Information about the first challenge can be found [here](https://github.com/latcraft/cloudopoly-search). Second challenge is described [here](https://github.com/latcraft/cloudopoly-pics).

Problem definition
==================

Create deployment service for Docker containers on top of AWS infrastructure. 

The service must expose the following endpoints:

### /containers

```POST``` spins up new container in a region with fewest deployed containers. JSON body contains publicly accessible Docker image id  ``` { "imageId": "<imageId>" }```. Image, when ran, starts web app that exposes ```/ping``` endpoint on port 8080.

```GET``` lists all deployed containers in the following format:

```
[
	{ "id": "<containerId>", "region": "<region>"  },
	{ "id": "<containerId>", "region": "<region>"  }
	...
]
```
... where ```<containerId>``` uniquely identifies container and ```<region>``` is, well, region (e.g. ```us-east-1```).

### /containers?region=&lt;region&gt;

```POST``` spins up new container in a given ```<region>```.

```GET``` lists deployed containers in a given ```<region>```.


### /containers/{containerId}

```DELETE``` undeploys container by ```<containerId>```

### /regions

```GET``` lists all regions available for deployment in the following format:

```
[
	{ "region": "<region>" }
	{ "region": "<region>" }
	...
]
```

### /app/{containerId}

```GET``` forwards request to the web application deployed under ```{containerId}```. That said, ```/app/{containerId}/ping``` must delegate to ```/ping``` mapped under port ```8080```.


# Requirements

- Any programming language, any operating system
- Deploy your service to *AWS* *EC2* 
- Use whatever instances you want
- Send IP address of your service before `02.03.2015 18:00` to contest@latcraft.lv
- On `02.03.2015 20:00` we start the test! 
- Keep EC2 instances running in at least 2 regions during testing time
 
# Winner election

Winners will be selected based on solution correctness and robustness.

### Good luck!
