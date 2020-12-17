## Search-docker-registry-v2-script.2.0

### STOP:  This is NOT ready for development or production ... it is in design, prototyping the design, and hopfully development and test

#### WARNING: These instructions are incomplete. Consider them as notes quickly drafted on a napkin rather than proper documentation!

#### Support more than one private registry:v2 on the same host

#### Support different namespace(s)

#### Support encripted registry

#### Test Docker fixes this problem by providing an underlying framework called Docker Content Trust which verified images before running the container. Not just that, it constantly polls the Docker registry for any updates in the image and if there is, it is fetched before launching the container. The engine behind enforcing and managing this trust is Docker Notary, a Docker service which is implemented based on The Update Framework (TUF).

#### TUF is a specification for secure software distribution. It establishes trust using a hierarchy of roles represented by asymmetric keys and metadata signed using these asymmetric keys. A key hierarchy of root key, snapshot key, timestamp key and target keys together provide several security guarantees like freshness guarantees, survivable key compromise, etc. The root key is the root of all trust that signs the root metadata. The snapshot metadata is a collection of hashes of all the files for a given snapshot of the image.   https://medium.com/walmartlabs/docker-notary-very-tuf-but-devil-is-in-the-detail-5e643ea0aa16

docker-search is a bash script for listing images in a private registry v2.  It does not require registry v2 to be running on the system, only the filesystem where the images are stored.  Docker search registry v2 functionality is currently not supported at the time of this writing. See discussion since Feb 2015: "propose registry search functionality #206" https://github.com/docker/distribution/issues/206
## Install
To install, change directory to the location you want to download the script.  Use git to pull or clone this script into your directory.  If you do not have git installed then enter; "sudo apt-get install git" if using Ubuntu.  On the github page of this script use the "HTTPS clone URL" with the 'git clone' command. 

    git clone https://github.com/BradleyA/Search-docker-registry-v2-script.2.0.git

    cd Search-docker-registry-v2-script

Edit docker-search script, change PERSISTENT_REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY to the path to your registry storage filesystem root directry.  It is the volume you used when you started registry v2 container (/var/lib/registry).

     PERSISTENT_REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY="<your registry storage filesystem root directry>"

Move the script or create a symbolic link to a location in your working path; example /usr/local/bin. To find directories in your working path use; "echo $PATH".

    cp docker-search ..
    cd ..
    sudo ln -s $PWD/docker-search /usr/local/bin/docker-search

## Usage
    docker-search [OPTIONS] [IMAGE]

## Output example:

    $ docker-search
    busybox:latest
    gcr.io/google_containers/etcd:2.0.9
    gcr.io/google_containers/hyperkube:v0.21.2
    gcr.io/google_containers/pause:0.8.0
    google/cadvisor:latest
    jenkins:latest
    logstash:latest
    mongo:latest
    nginx:latest
    python:2.7
    redis:latest
    registry:2.1.1
    stackengine/controller:latest
    tomcat:7
    tomcat:latest
    ubuntu:14.04.2
    Number of images:   16
    Disk space used:    1.7G    /mnt/three/docker-registry/registry-data

#### Version of registry v2 using
 * registry github.com/docker/distribution v2.1.1

#### ARCHITECTURE TREE

#### Traffic
  * <img alt="Clones" src="https://img.shields.io/static/v1?label=Clones&message=61&color=blue">  [Clones Table](images/clone.table.md)
  * <img alt="Views" src="https://img.shields.io/static/v1?label=Views&message=51&color=blue">  [Views Table](images/view.table.md)

#### Author
[<img id="github" src="images/github.png" width="50" a="https://github.com/BradleyA/">](https://github.com/BradleyA/)    [<img src="images/linkedin.png" style="max-width:100%;" >](https://www.linkedin.com/in/bradleyhallen) [<img id="twitter" src="images/twitter.png" width="50" a="twitter.com/bradleyaustintx/">](https://twitter.com/bradleyaustintx/)       <a href="https://twitter.com/intent/follow?screen_name=bradleyaustintx"> <img src="https://img.shields.io/twitter/follow/bradleyaustintx.svg?label=Follow%20@bradleyaustintx" alt="Follow @bradleyaustintx" />    </a>

#### System OS script tested
 * Ubuntu 14.04.3 LTS
 * CoreOS 723.3.0

#### Design Principles
 * Have a simple setup process and a minimal learning curve
 * Be usable as non-root
 * Be easy to install and configure

#### License
MIT License

Copyright (c) 2020  [Bradley Allen](https://www.linkedin.com/in/bradleyhallen)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

