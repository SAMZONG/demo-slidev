---
title: MCP
theme: apple-basic
colorSchema: light
---

# 什么是 MCP ?

多云容器平台（Multi-Cloud Container Platform，MCP）是华为云基于多年容器云领域实践经验和社区先进的集群联邦技术（Karmada），提供的容器多云和混合云的解决方案。

<p align="center">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0295712308.png"    class="rounded shadow" width="600" />
</p>

多云管理旨在将企业多个容器平台进行统一管理，提供应用的跨云部署(k8s)，用于实现应用多活、异地负载均衡、灾备等等功能。

---

# 功能介绍

<br>

## 统一集群管理

多云容器平台通过集群联邦实现对多个云运营商的集群进行统一管理，支持动态集群接入和全局集群监控仪表盘。通过多云容器平台的多集群统一管理入口可以实现统一部署、统一发布及统一运维。

<p align="center">
<img src="http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/jwByyB.png?x-oss-process=image/resize,w_960,m_lfit" class="rounded shadow" width="560" />
</p>

目前支持的集群，基本覆盖主流的。 **公有云、私有云**，通过添加上传 .kubeconfig 的方式 连接

---

## 统一集群管理

为增加的集群配置对应的 `区域`  `集群名称`  `连接方式` ，添加完成后会进入到自动检测的过程。

<br>

<p align="center">
<img src="http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/wVAMZ1.png?x-oss-process=image/resize,w_960,m_lfit" class="rounded shadow" width="540" />
</p>

- 连接方式支持公网链接，和专线网络连接（与使用华为云专线服务打通网络）

---

## 全局应用管理

基于多集群与Federation联邦技术，多云容器平台可以实现多个不同区域、不同云的Kubernetes管理，支持统一的全局应用管理，支持基于Kubernetes社区集群联邦标准化接口的跨集群应用的部署、删除、升级等全生命周期管理。

<p align="center">
<img src="http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/5d6t0u.png?x-oss-process=image/resize,w_960,m_lfit" class="rounded shadow" width="540" />
</p>

- **目前仅支持 Deployment** 无状态负载

---

## 跨集群的弹性伸缩能力

多云容器平台支持跨集群的应用弹性伸缩策略，用以均衡各集群的应用实例分布，实现全局负载均衡。您无需再担心集群节点的水平扩展，多云容器平台将根据应用的负载情况，轻松灵活的自动扩缩容应用所需的资源。

## 标准兼容

多云容器平台兼容Kubernetes社区最新Federation架构，提供原生Kubernetes API及Karmada API。您可使用熟悉的Kubernetes命令行和API来部署容器应用，无需修改任何服务代码即可支持Kubernetes典型应用场景。

## 跨集群的服务发现能力

多云容器平台支持创建联邦服务，支持跨集群的服务发现机制，能够基于服务就近访问原则实现业务的区域亲和，从而在业务进行多区域部署时，实现访问与服务的同地域优先，降低用户访问时的网络延迟。

---

# 集群控制台

<br>

## 单集群应用多云化

多云容器平台支持将单集群应用一键式转换为多云应用，将应用实例部署到多云多集群，方便快捷的完成业务多云容灾、多云业务流量分担等多云价值场景。

## 跨集群应用克隆和迁移能力

多云容器平台支持将某个集群的应用克隆或者迁移到其他集群，可以使用该能力完成跨云跨集群的应用主动迁移，或者跨云跨region的镜像环境复制等场景应用。

---

# 组网方案

## 混合云的组网方案

是指混合华为云的CCE集群和自建数据中心的Kubernetes集群的场景，该方案具有如下特点：

- 云上统一管理：在公有云上实现资源、应用、网络等多云统一管理。
- 云上数据无关：**核心数据放在线下，公有云上运行与核心数据无关的应用。**
- 业务迁移过渡：合理利用原有的物理计算资源，将业务逐步平稳切换到公有云上，实现资源的最大化利用。

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166121931.png" class="rounded shadow" width="500" />
</p>

---

## 多云方案

是指混合华为云的CCE集群与其它云运营商（如阿里云、腾讯云）的Kubernetes集群，该方案具有如下特点：

- 统一管理：实现资源、应用、网络等多云统一管理。
- 多云容灾：**相同业务部署到不同云运营商的集群，实现多云容灾。**

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166121933.png" class="rounded shadow" width="500" />
</p>

---

## 多区域方案

混合在华为云相同或不同的虚拟私有云、区域下的CCE集群，该方案具有如下特点：

- 统一管理：实现资源、应用、网络等多云统一管理。
- 智能路由：**多集群分布在不同区域，实现地域亲和的请求转发，降低用户因跨区域访问造成的网络延迟**。
- 多区域容灾：相同业务部署到华为云不同区域的集群，实现多云容灾。

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166121934.png" class="rounded shadow" width="500" />
</p>

---

# 应用场景

<br>

## 业务流量分担

