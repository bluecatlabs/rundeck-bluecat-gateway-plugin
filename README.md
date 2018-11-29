# Rundeck BlueCat Gateway Plugin

This is a Plugin for [Rundeck](https://www.rundeck.com/open-source) 3.0.8 that provides the ability to call BlueCat Gateway endpoints from the Rundeck UI. This Plugin is built to utilize the [rest_api](https://github.com/bluecatlabs/gateway-workflows/tree/master/Community/rest_api) workflow on Gateway Verions [18.10.2](https://quay.io/repository/bluecat/gateway?tag=latest&tab=tags) or greater 

## Prerequisites

* BlueCat Address Manager 3000 appliance or greater running software version 8.1.1 or greater
* BlueCat Gateway [v18.10.2](https://quay.io/repository/bluecat/gateway?tag=latest&tab=tags) or greater Instance Running
* BlueCat Gateway has [rest_api](https://github.com/bluecatlabs/gateway-workflows/tree/master/Community/rest_api) workflow installed and permissioned properly
* Rundeck Instance Running


## Installation
  1. Download and start [Rundeck](http://rundeck.org/downloads.html), or install the docker [version](https://hub.docker.com/r/rundeck/rundeck/) <br /> <br />
  2. Download this repository as a .zip file <br /> <br />
  3. Drop it in your libext folder <br /> <br />
  4. restart rundeck <br /> <br />

### Docker Installation
  1. if you are using Rundeck-docker you will need to mount a data volume to libext with: <br />
  ```
  docker run --name rundeck -v data:/home/rundeck/server/data -v plugins:/home/rundeck/libext -p 4440:4440 -e RUNDECK_GRAILS_SERVER=http://<ip address of your host machine>:4440 rundeck/rundeck
  ```
  2. put the .zip file into /home/rundeck/libext with: <br />
  ```
  docker cp bluecat-gateway-rundeck-plugin.zip rundeck:/home/rundeck/libext/
  ```
  3. then restart the docker container with : <br />
  ```
  docker stop rundeck <br />
  docker rm rundeck <br />
  docker run --name rundeck -v data:/home/rundeck/server/data -v plugins:/home/rundeck/libext -p 4440:4440 -e RUNDECK_GRAILS_SERVER=http://<ip address of your host machine>:4440 rundeck/rundeck
  ```

## Usage

* Select the gateway-workflow in the workflow tab when creating a job and fill in the boxes below

![Alt Screenshot](resources/First_page.PNG)

* NOTE: the additional data should always be in JSON format

![Screenshot2](resources/expected_result.PNG)

* For complete information on Rundeck refer to https://rundeck.org/docs/




