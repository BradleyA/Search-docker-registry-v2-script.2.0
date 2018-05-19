# Search-docker-registry-v2-script
//--	README.md  0.08.23  2018-05-19_09:45:23_CDT  https://github.com/BradleyA/Search-docker-registry-v2-script.2.0.git  uthree  three.cptx86.com 0.07-1-g5685e54  
//--	   initital commit 
Displays a live stream of one or more running containers’ resource usage statistics by container name.
## Install
To install, change directory to the location you want to download the script directory.  Use git to pull or clone this script into directory.  If you do not have git then enter; "sudo apt-get install git".  On the github page of this script use the "HTTPS clone URL" with the 'git clone' command. 

    git clone https://github.com/BradleyA/dmonitor.git
    cd dmonitor

Edit view-private-registry script, change PERSISTENT_REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY to the path to your registry storage filesystem root directry.  It is the volume you used when start the registry for /var/lib/registry.

     PERSISTENT_REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY="<your registry storage filesystem root directry>"

Move the script or create a symbolic link to a location in your working path; example /usr/local/bin. To find directories in your working path use; "echo $PATH".

    cp view-private-registry ..
    cd ..
    sudo ln -s $PWD/view-private-registry /usr/local/bin/view-private-registry

## Usage
    view-private-registry

## Output

    $ view-private-registry`
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

#### System OS script tested
 * Ubuntu 14.04.3 LTS
 * CoreOS 723.3.0

#### Design Principles
 * Have a simple setup process and a minimal learning curve
 * Be usable as non-root
 * Be easy to install and configure

## License
view-private-registry is free software/open source.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

