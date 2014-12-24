W00t? 
==================

This repository contains description of the third Cloudopoly challenge. Cloudopoly is a set of challenges targeted towards raising awareness of AWS stack. Winners will get prizes from AWS! The first Cloudopoly will have 3 challenges, one per month. By getting 3 times in top 3 you will win a special prize from LatCraft.

Information about the first challenge can be found [here](https://github.com/latcraft/cloudopoly-search). Second challenge is described [here](https://github.com/latcraft/cloudopoly-pics)

Problem definition
==================
Create deployment service for Docker containers on top of AWS infrastructure. 

Service must expose the following endpoints:

### /api/apps


```POST``` spins up new app instance in a region with fewest deployed app instances. JSON body contains publicly accessible Docker image id  ``` { "imageId": "<imageId>" }``` with the app to be ran.


```GET``` lists all deployed app in the following format:

```
[
	{ "id": "<appId>", "region": "<region>"  },
	{ "id": "<appId>", "region": "<region>"  }
	...
]
```
... where ```<appId>``` uniquely identifies app instance and ```<region>``` is, well, region.

### /api/apps?region=&lt;region&gt;

```POST``` spins up new app instance in a given ```<region>```.

```GET``` lists deployed app in a given ```<region>```.


### /api/apps/{appId}

```DELETE``` undeploys app instance by ```<appId>```

### /api/regions
```GET``` lists all regions available for deployment in the following format:

```
[
	{ "region": "<region>" }
	{ "region": "<region>" }
	...
]
```


# Requirements

- Any programming language, any operating system
- Deploy your service to *AWS* *EC2* 
- Use whatever instances you want
- Send IP address of your service before `02.02.2015 18:00` to contest@latcraft.lv
- On `02.02.2015 20:00` we start the test! 
- Keep EC2 instances running in at least 2 regions during testing time
 
# Winner election

???

### Good luck!
