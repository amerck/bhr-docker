# Installing Docker

These installation instructions relies heavily on both Docker and Docker-compose.  Some introductory guides
to get you familiar with these technologies are linked below:

[Docker Getting Started](https://docs.docker.com/get-started/)

[Docker Compose Overview](https://docs.docker.com/compose/overview/)

[Docker Compose Overview](https://docs.docker.com/compose/overview/)

The default deployment model uses Docker and Docker Compose to deploy
containers for the project's tools, and so, require the following:

* Docker >= 1.13.1
* Docker Compose >= 1.15.0

Please note that you will have a more stable experience by installing docker-compose and docker from your 
distributions repos, rather than downloading docker directly from Docker. Direct downloads from Docker *do* tend to 
have more features, but those features often come at the price of unresolved bugs. 

__Note:__ On Linux, you will need some escalated privileges to run docker.
This may include having rights to run `$ sudo docker-compose`, or your user being a part of the
`docker` group.

### Ubuntu Installation

```
$ sudo apt install docker docker-compose python3 python3-pip
$ sudo systemctl enable docker
$ sudo systemctl start docker
```


### RHEL/CentOS Installation

Ensure that you have the EPEL repository available.  Instructions on how to
enable this can be found [here](https://fedoraproject.org/wiki/EPEL)
You may need to specify whether you want python3.4 or python3.6. Where possible, use python3.6 or newer.
```
$ sudo yum install docker docker-compose python3 python3-pip
$ sudo systemctl enable docker
$ sudo systemctl start docker
```


### OSX Installation

Ensure that Homebrew is installed.  Homebrew installation information can be
found [here](https://brew.sh/)

```
$ brew install docker docker-compose
```