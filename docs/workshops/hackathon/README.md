# IDCF DevOps 黑马马拉松操作手册

## 1. 环境概述

为了能让团队更好的进行开发调试包括对整个DevOps工具链进行搭建以及测试，我们为每个团队提供了以下配套环境

![Boathouse Environment](images/boathouse-env-architecture.png)

环境配置如下：

- 2台 Linux 虚拟机（团队自行分配2台VM的用途）
  - VM#1: VM-Tools（用于搭建工具链） （CPU: 2 Core MEM: 8G）
  - VM#2: VM-Dev（用于搭建测试环境） （CPU: 2 Core MEM: 4G）
- 1个 容器镜像仓库 （使用微软Azure云的Azure Container Registry)
- 1个 k8s 集群（使用微软Azure云的Azure Kubernetes Services）
  - k8s 总会通过 命名空间（NS）划分成 Test/Prod 两个环境

### 获取团队云资源

黑客马拉松的环境通过 [DevOps实验室](https://labs.devcloudx.com) 提供，讲师会在现场发放环境激活码给各团队的负责人。

**注意：每一个团队只有一套环境! 大家注意做好分工。**

## 2. 基础流水线搭建和dev环境部署

### 2.2 团队环境配置

- [示例代码导入](version-control-config.md): 按照此文档完成Gitee上面的代码库复制（Fork）。

- [Jenkins服务器搭建](team-env-config.md)：按照此文档完成Jenkins服务器搭建，添加节点并安装插件。

### 2.3 使用Jenkins完成到dev环境的自动化部署

- [流水线配置](team-pipeline-config.md)：按照此文档完成Jenkins中各种环境变量和密钥的配置，并从代码库中导入Jenkinsfile

### 2.4 团队开发环境部署

- [使用流水线完成Dev环境的自动化部署](team-dev-env-deploy.md)：使用流水线完成Dev环境的自动化部署

### 2.5 团队快速开发指南

- [快速开发指南](dev-guide.md)：搭建本地开发环境，完成Boathouse前后端代码的联调。

## 3. 完整流水线搭建和测试/生产环境部署

### 3.1 加分项 - 团队 K8s 环境（Test & Prod）部署

- [使用流水线完成Test/Prod环境的自动化部署](team-k8s-env-config.md)：按照此文档完成K8s环境中的 Test 和 Prod 两个环境的部署。

### 3.2 加分项 - 高级流水线组件

- 完成本链接中（工具指导文档）中的任意配置，团队可以获得额外加分 [Boathouse工具链指导文档列表](../../../README.md?id=工具指导文档)

## 小结

本文档描述了IDCF DevOps 黑客马拉松的流水线搭建过程。
