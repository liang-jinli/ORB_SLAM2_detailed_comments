<!--
 * @Author: LiuJialin
 * @Date: 2022-10-30 23:13:19
 * @LastEditors: LiuJialin
 * @LastEditTime: 2022-10-30 23:37:43
-->
# ORB-SLAM Docker

ubuntu下运行可以利用GPU在宿主机进行Pangolin可视化

## docker镜像构建说明

```bash
sudo docker build -f Dockerfile.txt -t orbslam2gl  --network=host . 
```

## 进入docker的指令

```bash
docker run --gpus all -it --rm\
    -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
    -e DISPLAY=$DISPLAY \
    -v ${PWD}:${PWD} \
    -v ${HOME}/dataset:${HOME}/dataset \
    -w ${PWD} \
    --name orbslam2 \
    orbslam2gl
```

## 镜像拉取

```bash
docker pull liangjinli/orbslam2-docker:orbslam2gl
```

### 拉取的镜像使用方式

```bash
docker run --gpus all -it --rm -v /tmp/.X11-unix:/tmp/.X11-unix:rw -e DISPLAY=$DISPLAY -v ${PWD}:${PWD} -v /media/liangjinli/HDD:${HOME}/dataset -w ${PWD} --name orbslam2 liangjinli/orbslam2-docker:orbslam2gl
```
