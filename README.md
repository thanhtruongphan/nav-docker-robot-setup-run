# nav-docker-robot-setup-run

in Jetson nano
clone **linorobot2** and **linorobot2_hardware** repositories

then 
```
cd linorobot2/docker
docker compose build
docker compose up -d webtop
export DISPLAY=:200; docker compose up rviz
```
NOTE: Edit .env, add your a1m8 to "LASER_SENSOR=a1".
RViz works now.

if doesn't work, pls try:
```
git clone -b pr-lidar https://github.com/hippo5329/linorobot2.git
cd linorobot2/docker
sudo docker compose build
sudo docker compose up bringup
```
on another Tab, run it
```
cd linorobot2/docker
sudo docker compose up -d webtop bringup debug navigate rviz-nav slam
```
... navigate in rviz
```
sudo docker compose up save-map
```

down docker 
```
sudo docker compose down # will down all service containers
```
