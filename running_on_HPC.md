---
layout: page
title: Running on HPC
---


PEMA has been developed in a High Performance Computing (HPC) - oriented way. 

That is because it is rather usual to have large datasets of dozins, maybe hundreds of samples to analyze.

Many of the tools and the algorithms encapsulated on PEMA require for either essential computational power or memory (RAM) or sometimes both. Thus, PEMA was developed fon HPC systems originally. 


>The best way to run PEMA is at an HPC system using the Singularity container. 


Let us now run an example case for running PEMA on a HPC system.


## Dependencies

Assuming you have access at an HPC system, you need to check whether that supports [Singularity](https://sylabs.io/docs/) in a version later than `v3.0`. 

To do so, you may run 

```
singularity --version
```


If Singularity is not available, you need to ask your sys-admin to add it. Singularity is also HPC-oriented so there are no problems for the HPC coming with that. 

Singularity has some dependencies on its own but that is beyond the scope of this *how to*.


## Get PEMA Singularity container

Once Singularity is on, you need to run the following command to get the PEMA container on your account

```
singularity pull shub://hariszaf/pema:<tag>
```

This will take a few moments as the container is 3Gb approximately. 

If you leave the `:<tag>` part empty, then you will get the latest PEMA version. 

The latest version is changing from time to time and it is the most recent version of PEMA with the newest feature included. 

You may have a look on the [PEMA versioning](https://hariszaf.github.io/pema_documentation/versioning/) section for more details on that. 


Once the container has been downloaded completed, you are ready to go! 


## Prepare your `analysis_directory`




