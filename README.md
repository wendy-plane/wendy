<div align="center">
<img src="https://raw.githubusercontent.com/leiyi2000/wendy/main/docs/resources/logo.webp" style="width:200px; height:200px; border-radius:50%;"/>
</div>

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/leiyi2000/wendy/main.yml)

# wendy
这是基于容器化部署、管理饥荒游戏的项目、基于docker+fastapi+tortoise-orm开发

## 环境
- linux
- docker

## 功能
- 容器化部署饥荒
- 监听饥荒版本更新自动更新容器
- 饥荒服务的启停

## TODO
- 存档备份
- 存档下载
- 饥荒容器交互(支持饥荒指令)

## 镜像
- [构建](https://github.com/leiyi2000/dontstarve-server-docker)
  
      https://github.com/leiyi2000/dontstarve-server-docker
- 拉取

      docker pull ylei2023/dontstarvetogether:饥荒版本号

## 部署
- 拉取项目

      git clone https://github.com/leiyi2000/wendy.git
- 启动

      docker compose up -d

- 快速部署

      curl -X 'POST' \
        'http://127.0.0.1:8000/deploy' \
        -H 'accept: application/json' \
        -H 'Content-Type: application/json' \
        -d '{
        "cluster_token": "科雷令牌",
        "cluster_name": "Wendy Cute",
        "cluster_description": "Wendy is cute."
        }'
    
    注意第一次部署可能很慢需要拉取镜像: ylei2023/dontstarvetogether:饥荒版本号

- [接口文档](http://127.0.0.1:8000/docs)
      
      http://127.0.0.1:8000/docs


## 其他
- 查询饥荒版本号接口

      https://api.steamcmd.net/v1/info/343050


## 感谢
- 感谢superjump22提供的镜像构建参考, 项目地址：https://github.com/superjump22/dontstarve-server-docker
