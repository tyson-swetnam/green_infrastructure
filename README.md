# Green Infrastructure

## Data

First, we needed to get the [PAG lidar data](http://www.library.arizona.edu/indexes/links/dbDetail.php?shortname=pag) 
onto a cloud machine where we could process it.

Ben Hickson from the [UA Library GIS](http://libguides.library.arizona.edu/GIS) 
moved the `*.las` data over to the CyVerse DataStore.

### Start Jetstream VMs 

We are using a Jetstream image with [Ubuntu 14 and Docker CE](https://use.jetstream-cloud.org/application/images/359) pre-installed to do the lidar analysis.

The second part of the project involves a Jetstream image with [Centos 6 and Matlab](https://use.jetstream-cloud.org/application/images/319).

### Process 2008 and 2015 lidar data

We are going to use [PDAL](www.pdal.io) to process the PAG 
lidar data into digital surface models (DSM), 
digital elevation models (DEM), and object / canopy height models (CHM), 
where *DSM - DEM = CHM*.

The nominal density of the PAG 2008 and 2015 data are ~ 4-8 points per meter quare (ppsm). 
We'll try a 0.5 m DSM/DEM size before moving to a 1 m DSM/DEM.

### Visualization of data

Data are visualized with [Plas.io]() and [Potree]() via [Greyhound]() 
on a `medium` Jetstream VM. The `tiny` and `small` VMs were found to be
too small to run the service.

### 
