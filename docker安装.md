## 卸载老版本
  yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
## 安装基础包
  yum install -y yum-utils \
  yum install -y device-mapper-persistent-data \
  yum install -y lvm2\
## 设置稳定仓库
  yum-config-manager \
    --add-repo \
    https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
## 更新最新社区版
  1.安装最新版
    yum install docker-ce docker-ce-cli containerd.io
  2.安装指定版本
    yum list docker-ce --showduplicates | sort -r  #查看版本
    sudo yum install docker-ce-<VERSION_STRING> docker-ce-cli-<VERSION_STRING> containerd.io #安装指定版本
## 启动与测试
    sudo systemctl start docker  # 启动docker
    docker run hello-world  #测试
