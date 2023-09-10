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