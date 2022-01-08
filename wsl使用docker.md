https://stackoverflow.com/questions/61592709/docker-not-running-on-ubuntu-wsl-cannot-connect-to-the-docker-daemon-at-unix

1、wsl升级为wsl2
https://docs.microsoft.com/zh-cn/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package

2、安装docker，将镜像换成aliyun
https://docs.docker.com/engine/install/ubuntu/
https://developer.aliyun.com/mirror/docker-ce?spm=a2c6h.13651102.0.0.6a891b1140OQ4c
sudo apt-get update
sudo apt-get -y install apt-transport-https ca-certificates curl software-properties-common
# step 2: 安装GPG证书
curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
# Step 3: 写入软件源信息
sudo add-apt-repository "deb [arch=amd64] https://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
# Step 4: 更新并安装Docker-CE
sudo apt-get -y update
sudo apt-get install docker-ce docker-ce-cli containerd.io

3、启动docker daemon
sudo dockerd &

然后
sudo docker run hello-world

4、postinstall
https://docs.docker.com/engine/install/linux-postinstall/

5、以普通用户运行
docker run -u $(id -u):$(id -g) args...

6、tensorflow
Run a Jupyter notebook server with your own notebook directory (assumed here to be ~/notebooks). To use it, navigate to localhost:8888 in your browser:
docker run -it --rm -v $(realpath ~/notebooks):/tf/notebooks -p 8888:8888 tensorflow/tensorflow:latest-jupyter

Start a CPU-only container:
docker run -it --rm tensorflow/tensorflow bash

Start a GPU container, using the Python interpreter:
docker run -it --rm --runtime=nvidia tensorflow/tensorflow:latest-gpu python

