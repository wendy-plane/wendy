<div align="center">
    <img src="https://raw.githubusercontent.com/ylei2024/wendy/main/docs/wendy.png" style="width:150px; height:200px; border-radius:50%;"/>
</div>

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/ylei2024/wendy/main.yml)

# wendy
这是基于容器化部署、管理饥荒游戏的项目、基于docker+fastapi+tortoise-orm开发

## 环境
- linux
- docker

## 功能
- 一键开服
- 上传存档开服
- 支持配置DOCKER-API
- 自动更新游戏版本
- 饥荒服务的启停
- 存档下载
- 远程执行控制台指令
- 日志查看
- 模组下载

## 快速部署
- 拉取项目

      git clone https://github.com/ylei2024/wendy.git
- 运行

      cd wendy && docker compose up -d
- 国内运行

      cd wendy && export IMAGE_TAG=$(date +'%Y%m%d%H%M%S') && export DST_IMAGE=swr.cn-north-4.myhuaweicloud.com/ylei/dontstarvetogether && docker compose up -d

- 快速开服

      curl -X 'POST' \
        'http://127.0.0.1:8000/deploy' \
        -H 'accept: application/json' \
        -H 'Content-Type: application/json' \
        -d '{
            "cluster_token": "你的科雷令牌",
            "ini": {
                        "cluster_name": "Wendy Cute"
                  }
            }'
    
    注意第一次部署可能很慢需要拉取镜像

- [接口文档](http://127.0.0.1:8000/docs)
      
      http://127.0.0.1:8000/docs

## 镜像
- 默认
  
      docker pull ylei2023/dontstarvetogether:饥荒版本号
- 国内

      docker pull swr.cn-north-4.myhuaweicloud.com/ylei/dontstarvetogether:饥荒版本号

- [构建](https://github.com/ylei2024/dontstarve-server-docker)
  
      https://github.com/ylei2024/dontstarve-server-docker

## 其他
- 查询饥荒版本号接口

      https://api.steamcmd.net/v1/info/343050


## 感谢
- 感谢superjump22提供的镜像构建参考, 项目地址：https://github.com/superjump22/dontstarve-server-docker
