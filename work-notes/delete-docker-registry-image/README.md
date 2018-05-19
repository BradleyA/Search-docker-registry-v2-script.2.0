# delete-docker-registry-image
#	README.md  0.06.20  2018-05-19_09:30:38_CDT  https://github.com/BradleyA/Search-docker-registry-v2-script.2.0.git  uthree  three.cptx86.com 0.05  
#	   inital commit 

## Install

    curl https://raw.githubusercontent.com/burnettk/delete-docker-registry-image/master/delete_docker_registry_image | sudo tee /usr/local/bin/delete_docker_registry_image >/dev/null
    sudo chmod a+x /usr/local/bin/delete_docker_registry_image

## Run

Set up your data directory via an environment variable:

    export REGISTRY_DATA_DIR=/opt/registry_data/docker/registry/v2

You can also just edit the script where this variable is set to make it work for your setup.

Almost delete a repo:

    delete_docker_registry_image --image testrepo/awesomeimage --dry-run

Actually delete a repo (remember to shut down your registry first):

    delete_docker_registry_image --image testrepo/awesomeimage

Delete one tag from a repo:

    delete_docker_registry_image --image testrepo/awesomeimage:supertag
