# Transfer (Pull & Push) docker images

自 2024 年的某月末日起，DockerHub 加速服务器无法拉取镜像。
该项目利用 Github Actions 将 DockerHub 的镜像自动迁移到自定义的仓库(Registry)。

## 使用方法

在项目的配置 `Settings > Security > Secrets and variables > Repository secrets` 中添加一下变量：

- DOCKER_USERNAME: 用户名
- DOCKER_PASSWORD: 密码
- DOCKER_REGISTRY: 仓库地址
- DOCKER_NAMESPACE: 命名空间

将 dockerhub 的镜像名称填入 `images.txt` 文件，例如：非官方镜像`gvenzl/oracle-xe:18-slim-faststart`，推送自定义 registry 时候会自动去除`gvenzl/`，目标为`${DOCKER_REGISTRY}/${DOCKER_NAMESPACE}/oracle-xe:18-slim-faststart`
