# %W% %G% %U%
#		Dockerfile  0.03.17  2018-05-17_17:45:36_CDT  https://github.com/BradleyA/Search-docker-registry-v2-script.2.0.git  uthree  three.cptx86.com 0.02  
#		   continue testing #23 
#		Dockerfile  0.02.16  2018-05-17_17:39:45_CDT  https://github.com/BradleyA/Search-docker-registry-v2-script.2.0.git  uthree  three.cptx86.com No-parent-git-tag-found-in-repository  
#		   initial commit test 3 
#
FROM registry:latest
# Dockerfile maintainer
MAINTAINER Bradley Allen, allen.bradley@ymail.com
#
#	
#	docker run -d -p 5000:5000 -v /mnt/three/docker-registry/registry-data:/tmp --restart=always 192.168.1.102:5000/registry:1508191703
#	docker run -d -p 5000:5000 -v /mnt/three/docker-registry/registry-data:/tmp --restart=always registry
#	docker run -d -p 5000:5000 -v /mnt/three/docker-registry/registry-data:/var/lib/registry --restart=always 192.168.1.102:5000/registry:1508191526
#	docker run -d -p 5000:5000 -e REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY=/var/lib/registry --restart=always registry
#	docker run -d -p 5000:5000 -e REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY=/var/lib/registry -v /mnt/three/docker-registry/registry-data:/var/lib/registry --restart=always -it registry
#	docker run -d -v /mnt/three/docker-registry/registry-data:/var/lib/registry --restart=on-failure:5 --name registry registry/private:1.0
#
#	docker run -d -p 5000:5000 -e 
#		REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY=/var/lib/registry \
#		-v /mnt/three/docker-registry/registry-data:/var/lib/registry \
#		--restart=always --name registry registry
#
RUN apt-get -y update

ENV REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY=/var/lib/registry

EXPOSE 5000

LABEL Description="This image is used to start a private registry three"

# CMD "-d --port 5000 -v /mnt/three/docker-registry/registry-data:/var/lib/registry --restart=on-failure:5 --name registry"
