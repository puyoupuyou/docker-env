# docker-env
docker environment for development

# How to use

On your host Os, run following  commands:

```
#xxx means what ubuntu version you will use
cd ubuntu-xxx 
sudo docker build -t "mh1905-sdk/ubuntu18-full:v1" .
```

Have a rest, this will take some times.

You will see some logs if successful to create images named "mh1905-sdk/ubuntu18-full".

```
Sending build context to Docker daemon  815.5MB
Step 1/17 : FROM ubuntu:18.04
 ---> e28a50f651f9
Step 2/17 : LABEL mantainer="ding_zhao@megahuntmicro.com"       vendor="Megahunt"       description="Container with everything needed to run MH1905 SDK"
 ---> Using cache
 ---> 31535408c961
Step 3/17 : ARG DEBIAN_FRONTEND=noninteractive
 ---> Using cache
 ---> f868f99664bd
 
...

Step 17/17 : CMD [ "systemd" ]
 ---> Running in 5494169965f6
Removing intermediate container 5494169965f6
 ---> b3d97e800b14
Successfully built b3d97e800b14
Successfully tagged mh1905-sdk/ub18-full:v1
```

images can be find using:

```
sudo docker images
```

Finially, you can use this images to create container to get starting of development.
