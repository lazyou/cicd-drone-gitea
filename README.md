### 参考
* https://www.cnblogs.com/yan7/p/15881087.html

###
sqlite3
admin01
admin112233
admin01@qq.com



### 扩展

### 什么是 CI/CD
* CICD 是持续集成(Continuous Integration) 和 持续部署(Continuous Deployment)简称

#### CI : 持续集成
* 通俗一点说，就是把代码提交到代码托管平台

#### CD : 持续交付 + 持续部署
* 简单的说，就是自动化轻松的部署到生产坏境，且全程自动更新代码


### drone （参考: https://www.cnblogs.com/yan7/p/15881087.html）
* https://www.drone.io/

* Drone 也是一个优秀、开源的持续部署工具

* Drone 应用由 Server（服务器） 和 Runner（执行器） 两种服务构成。

* Server（服务器） 主要负责管理和展示， Runner（执行器） 主要负责执行操作。
	* Server 服务可以与一个或多个 Runner 连接通信进行管理。
	* Runner（执行器） 是真正执行持续部署操作服务。Runner 执行时会轮询 Server 来确定执行的操作。
	* Drone 官方提供了多种类型的 Runner（执行器），用于适配不同的运行环境(Docker Runner、 SSH Runner、 Kubernetes Runner)。


* Drone 可以无缝集成多种主流代码仓库: GitHub， Gogs， Gitea， Gitee， GitLab，。



### Gitea
sqlite3
admin01
admin112233
admin01@qq.com



### 持续部署概述 (https://www.cnblogs.com/yan7/p/15881087.html)
* 持续部署是能以自动化方式，频繁而且持续性的，将软件部署到生产环境。使软件产品能够快速迭代。

* 在之前部署 web 项目时，都是手动进行部署
	* 拉取代码 ---> 编译项目 ---> 打包镜像 ---> 推送镜像仓库 ---> 服务器拉取新镜像 ---> 停止和移除旧容器 ---> 启动新容器

	* 这一整套部署步骤枯燥又费时。

* 持续部署就是使用工具自动处理整套步骤。代码在提交之后自动执行整套流程将项目部署到生产环境，省去繁琐的人工操作。

* 持续部署整套流程本质上是一个极其简单的东西。可以拆解为两个阶段
	* 打包阶段： 拉取代码 ---> 编译项目 ---> 镜像打包 ---> 推送镜像仓库
	* 部署阶段： SSH 连接服务器 ---> 拉取新镜像 ---> 停止和移除旧容器 ---> 启动新容器

* 未使用自动化部署工具时，整套套也可以使用 .sh 脚本实现半自动化。甚至可以编写一个小程序，自动连接服务器实现全自动化。
