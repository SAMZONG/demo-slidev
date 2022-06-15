---
title: MCP
theme: apple-basic
colorSchema: light
highlighter: shiki
download: true
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

对于会造成特定时间范围的超高流量，为了应对流量的冲击，使用基于流量策略的跨云弹性伸缩能力，用来提升业务稳定性。在跨云部署应用时设置流量策略， **当流量高峰来临，私有云或某个公有云无法负担时，可以根据流量策略，弹性扩容到其它公有云集群上，分担流量负载，** 避免因流量冲击而造成系统瘫痪。


<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166193802.png" class="rounded shadow" width="500" />
</p>

---

## 多活容灾

为避免集群单点宕机故障，业务应用的实例可以多云多活的部署在不同云上的容器服务中， **当云单点宕机故障发生时，多云容器平台可以秒级自动完成应用实例的弹性迁移以及流量的切换** ，业务的可靠性大大提升。

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166193774.png" class="rounded shadow" width="500" />
</p>

---

## 数据与业务分离

对于金融、安全等行业的用户，业务数据的敏感性要求核心业务必须运行在自建的私有云集群中。通过华为云多云容器平台，您可以将 **敏感的数据业务保留在本地的私有云集群中，而将一般业务部署在公有云上** ，通过多云容器平台实现信息隔离和统一管理。

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166193807.png" class="rounded shadow" width="500" />
</p>

---

## 开发与生产分离

在CI/CD的场景中，希望开发环境和测试环境部署在本地的私有云集群，生产环境部署在公有云上。通过华为云多云容器平台可以将开发环境、测试环境和生产环境的集群统一管理，配合容器开发流水线，完成业务上线流水化作业，提高企业代码交付和部署的效率。

<p align="center">
<img src="https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0166193810.png" class="rounded shadow" width="500" />
</p>


---

# 使用限制

## Kubernetes版本约束

接入多云容器平台的Kubernetes集群版本必须为1.11及以上版本。

## 配额限制

多云容器平台最多可管理资源数：
- 专业版最多可管理5个集群，500个节点和1000个Pod。
- 企业版最多可管理10个集群，1000个节点和4000个Pod。
- 铂金版最多可管理20个集群，2000个节点和10000个Pod。

> 如果您需要管理更多集群、节点和Pod，请提交工单申请。配额的详细信息请参见关于配额。

## 其他限制

在多云容器平台中，通过多云容器平台创建联邦资源（如：federateddeployment、federatedservice，federatedpvc...），会在接入多云容器平台的集群中创建对应的Kubernetes资源（如：deployment、service、pvc...），请提供**接入集群的admin权限**认证凭证。

---

# 使用流程

在开通了华为云 MCP 后，本身不会自带集群服务，所以需要再创建对应的集群；可以采用华为的 CCE，也可以 直接纳管其他公有云或者自建 K8s 等。

<p align="center">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0166750723.png" class="rounded shadow" />
</p>

- 添加集群后，MCP 会自动在集群内创建对应的初始化资源
- **华为云支持在账号下购买多个 MCP 资源**，用于建立不同的集群纳管分组，互不影响。

MCP提供了两处资源负载的管理工作台：

- 多云应用需要在 MCP 工作台进行配置，目前仅支持 Deployment
- 同时支持更多其他的负载类型，可以进入对应的集群工作台操作

---

## 添加集群


登录MCP控制台，在左侧导航栏单击“资源管理”列表，选择“集群管理”，单击“添加集群”。
进入添加集群页面，在“选择云服务商”步骤中，单击选择对应的云服务商。

**选择网络连接方式**

- 公网： 需要被加入的集群能够提供公网的访问方式
- **枢纽私有云： MCP通过云专线物理网络打通与枢纽VPC的之间的网络，实现MCP与集群的互相访问。您需要购买物理专线**

<p align="center">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0172495322.png" class="rounded shadow" width="480" />
</p>

---

## 支持 kubectl 管理 MCP

MCP 同样提供了 kubectl 的管理方式，这对工程师是非常友好的，可以通过 终端完成集群的添加维护和资源管理

<p align="left">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0167702919.png" class="rounded shadow" width="460" />
</p>


---

## 创建无状态工作负载（Deployment）

- 登录MCP控制台，在左侧导航栏中单击“工作负载 > 无状态Deployment”，在右侧页面中单击“创建无状态工作负载”。
- 设置工作负载基本信息：
   - 工作负载名称：新增工作负载的名称，命名必须唯一。
   - 命名空间：选择工作负载所在命名空间。
   - 部署集群：选择需要部署工作负载的集群，集群个数请您根据自身业务进行选择。
   - 实例部署方式：支持“普通模式”和“权重模式”两种实例部署方式。
   - 实例数量：当“实例部署方式”选择为“普通模式”时生效。设置多集群的工作负载中各集群的实例数。用户可以设置具体实例个数，默认为2。每个工作负载实例都由相同的容器部署而成。在MCP中可以通过设置弹性扩缩容策略，根据工作负载资源使用情况，动态调整工作负载实例数。
   - 权重比例：当“实例部署方式”选择为“权重模式”时生效。设置多集群的工作负载的总实例数以及各集群的权重、实例范围。

---

## 添加存储

**在MCP控制台创建的是存储声明，创建完成后，会在所有部署的集群中创建一个同名的存储声明。** 在集群控制台中对多集群创建的存储声明执行修改或删除操作时，操作提示成功，但最终创建的存储声明会被重建。

<p align="left">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0157074435.png" class="rounded shadow"  width="440" />
</p>

配置参数:

- 名称：新建存储声明名称，命名必须唯一。
- 命名空间：新建存储声明所属的命名空间。若不选择，默认配置为default。
- 部署集群：选择存储要部署的集群。


---

### 图片介绍

<p align="center">
<img src="http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/H5KCDK.png?x-oss-process=image/resize,w_600,m_lfit" class="rounded shadow" />
</p>

---

### 选取镜像

- 添加容器”选择需要部署的镜像”
  - 支持选择 华为云内的镜像，开源镜像，第三方自建镜像
  - **支持镜像仓库是否需要认证的选择，对需要认证的镜像仓库，提供了维护秘钥的功能**

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/j4W3uk.png?x-oss-process=image/resize,w_560,m_lfit' alt='resize,w_960,m_lfit'/>

---

## 容器的差异化配置

MCP 利用了 Karmada 的差异化配置能力，以界面化的形式呈现；让用户方便 **对同一个应用部署在不同集群时，可以做差异化配置**

<p align="center">
<img src="https://support.huaweicloud.com/usermanual-mcp/zh-cn_image_0180779587.png" class="rounded shadow"  width="300" />
</p>

通用配置参数。
- 名称：新建存储声明名称，命名必须唯一。
- 命名空间：新建存储声明所属的命名空间。若不选择，默认配置为default。
- 部署集群：选择存储要部署的集群。
