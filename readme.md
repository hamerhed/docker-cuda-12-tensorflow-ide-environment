In order to run gui application from withhin docker container
you need to enable xhost server running belowed command:
#run xserver
xhost +local:docker

#XSOCK=/tmp/.X11-unix
#XAUTH=/tmp/.docker.xauth
#xauth nlist $DISPLAY | sed -e 's/^..../ffff/' | xauth -f $XAUTH nmerge -

next run docker compose file running command:

docker-compose -f docker-compose-code.yml up

after finished work disable xhost server by running command:
 
#stop xserver
xhost -local:docker


Troubleshooting

In case or running application error described below:
Execution error
Could not find compiler for platform CUDA: NOT_FOUND: could not find registered compiler for platform CUDA -- was support for that platform linked in?

You need to install tensorflow with flag `ENV TF_ENABLE_XLA` enabled. To do that change or add variable set to 1:

`ENV TF_ENABLE_XLA 1`

