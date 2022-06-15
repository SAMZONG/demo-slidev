---
title: MCP
theme: seriph
colorSchema: light
highlighter: shiki
download: true
background: https://sli.dev/demo-cover.png
selectable: true
---

# 华为云 MCP 调研资料分享


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

### 基础信息

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

### 添加存储的参数


| 参数           | 参数说明                                                     |
| :--------------: | ------------------------------------------------------------ |
| 存储来源       | 当“部署集群”为华为云集群时：EVS：块存储。MCP支持将EVS创建的云硬盘挂载到容器的某一路径下。当容器迁移时，挂载的云硬盘将一同迁移。这种存储方式适用于需要永久化保存的数据。OBS：对象存储。MCP支持创建OBS对象存储卷并挂载到容器的某一路径下，对象存储适用于云工作负载、数据分析、内容分析和热点对象等场景。SFS：文件存储。MCP支持创建SFS存储卷并挂载到容器的某一路径下，也可以使用底层SFS服务创建的文件存储卷，SFS存储卷适用于多读多写的持久化存储，适用于多种工作负载场景，包括媒体处理、内容管理、大数据分析和分析工作负载程序等场景。当“部署集群”为第三方集群时：仅支持“第三方存储”。 |
| 存储类型       | 当“存储来源”为“第三方存储”时生效，并且集群支持的存储类型取决于注册集群的实际环境。 |
| 存储容量（GB） | 新建存储的容量。                                             |
| 访问模式       | 文件存储来源为EVS时，访问模式为ReadWriteOnce (RWO)，即文件存储卷只能以读写模式被单个节点同时加载。文件存储来源为OBS或SFS时，访问模式为ReadWriteMany (RWX)，即文件存储卷能够以读写模式被多个节点同时加载。当部署集群为第三方集群时，访问模式支持ReadWriteOnce (RWO)和ReadWriteMany (RWX)两种模式。 |
| 注释           | 注释以Key/value键值对的形式附加到存储声明对象上。单击“新增一条注释” 。输入键、值。 |


---

## 设置访问方式 Service

若工作负载需要和其它服务互访，或需要被公网访问，您需要添加服务，设置访问方式。工作负载访问的方式决定了这个工作负载的网络属性，不同访问方式的工作负载可以提供不同网络能力，操作详情请参见网络管理。

- ClusterIP：只能集群内访问服务，详细信息见ClusterIP访问。
- NodePort：可以通过集群内任意节点访问到服务，详细信息见NodePort访问。

对无状态的工作负载创建成功后，每个集群的服务都会有一个开放到公网的 Ingress 链接；

通过 华为云的云 DNS解析来实现 灾备、多活、地区亲和性配置。


---

### MCP的网关管理

在MCP控制台上创建Service、Ingress后，会在所有部署的集群中创建一个同名的Service、Ingress和NetworkPolicy。

- ClusterIP访问
  
表示工作负载暴露给同一集群内其他工作负载访问的方式，可以通过“集群内部域名”访问。集群内部域名格式为“<自定义的访问方式名称>.<工作负载所在命名空间>.svc.cluster.local”，例如“nginx.default.svc.cluster.local”。

- NodePort访问
  
表示工作负载可以让同一虚拟私有云内其他工作负载访问，通过“集群节点的IP”访问，主要场景：云上同一虚拟私有云内其他工作负载需要访问Kubernetes集群内部的工作负载。

- LoadBalancer访问
  
通过弹性负载均衡从公网访问工作负载，一般用于系统中需要暴露到公网的服务。访问方式由公网弹性负载均衡ELB服务地址以及设置的访问端口组成，例如“10.117.117.117:80”。

- Ingress访问
  
采用了增强型弹性负载均衡，在四层负载均衡访问方式的基础上支持了URI配置，通过对应的URI将访问流量分发到对应的服务。同时，服务根据不同URI实现不同的功能。该访问方式由公网弹性负载均衡ELB服务地址、设置的访问端口组成、定义的URI组成，例如：10.117.117.117:80/helloworld。


---

## MCP 多命名空间

命名空间（Namespace）是一种在多个用户（通过资源配额）之间划分集群资源的方法。适用于用户中存在多个团队或项目的环境中。而MCP控制台创建的是多集群命名空间，会在加入MCP实例的所有集群下创建一个同名的命名空间。

- **命名空间可以在集群控制台中修改资源配额，并且修改的配额只作用于当前集群** ，其他集群中的这个命名空间配额不会改变。
- **当命名空间在某个集群的集群控制台中被删除后会被重新创建**


### 创建命名空间

登录MCP控制台，单击左侧导航栏的“资源管理”列表，选择“命名空间”。单击“创建命名空间”。


| 参数     | 参数说明                                                     |
| -------- | ------------------------------------------------------------ |
| 命名空间 | 新建命名空间的名称，命名必须唯一。                           |
| 标签     | key/value对格式。给命名空间添加标签，定义不同属性，通过这些标签了解各个命名空间的特点 |
| 注释     | key/value对格式。给命名空间添加注释。                        |
| 描述     | 输入对命名空间的描述信息。                                   |


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


---

### 差异化策略

创建对应了 K8s 资源后，会自动生成对应的差异化策略，由 Karmada 提供独立的差异化策略API，用来配置与集群相关的差异化配置，目前仅支持通过 `Yaml` 的方式创建。

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/60V00v.png?x-oss-process=image/resize,w_600,m_lfit' alt='resize,w_960,m_lfit'/>


```yaml
apiVersion: policy.karmada.io/v1alpha1
kind: OverridePolicy
metadata:
  name: nginx-ccecluster-deployment
  namespace: default
spec:
  overriders:
    plaintext:
      - operator: replace
        path: /spec/replicas
        value: 2
      - operator: add
        path: /spec/template/spec/containers
        value:
          - image: 'nginx:perl'
            imagePullPolicy: IfNotPresent
            name: container-0
            resources:
              limits:
                cpu: 250m
                memory: 512Mi
              requests:
                cpu: 250m
                memory: 512Mi
  resourceSelectors:
    - apiVersion: apps/v1
      kind: Deployment
      name: nginx
      namespace: default
  targetCluster:
    clusterNames:
      - ccecluster

```


---

### 差异化策略参数说明

| 参数       | 参数类型                                                     | 描述                                                         |
| ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apiVersion | String                                                       | API版本，固定值“policy.karmada.io/v1alpha1”，该值不可修改。  |
| kind       | String                                                       | API类型，固定值“OverridePolicy”，该值不可修改。              |
| metadata   | [OverridePolicy.metadata](https://support.huaweicloud.com/usermanual-mcp/mcp_01_0063.html#mcp_01_0063__table1929971023815) object | 差异化策略的基本信息，为集合类的元素类型，包含一组由不同名称定义的属性。 |
| spec       | [OverridePolicy.spec](https://support.huaweicloud.com/usermanual-mcp/mcp_01_0063.html#mcp_01_0063__table174471622103919) object | 差异化策略相关属性详细信息，通过spec的描述来创建或更新对象。 |


---

# 通过域名访问实现流量分发

MCP 要求企业将一个主域名托管到华为云的域名服务，从而提供统一的域名访问服务，MCP服务会以此域名作为根域名生成一个完整的应用外部访问域名。

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/qmF1nj.png?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_lfit'/>


---

## 创建域名访问

根据创建无状态工作负载完成的提示页面，您可以单击“添加服务”，添加LoadBalancer类型的服务，使应用工作负载可以对外提供服务。在LoadBalancer类型的服务创建完成的提示页面中单击“创建域名访问”。

- 登录MCP控制台，在左侧导航栏选择“域名访问”，单击“创建域名访问”。
- 设置“关联服务”参数。
  - 命名空间：选择命名空间。
  - 目标服务：选择目标服务，若您还没有可以关联的LoadBalancer类型的服务，请先创建服务。详细创建服务步骤见LoadBalancer访问。
- 单击“下一步”，配置访问模式。
  - 主备模式：流量只会解析到您所选择的主集群中，可以通过修改流量配比功能，修改主备集群。若开启域名流量解析自动切换，主集群发生故障时，DNS流量解析会随机自动切换至备集群。
  - 自适应模式：流量解析根据各集群后端实例数量自动分配权重。并且可以配置地域亲和，设置特定区域的用户流量访问特定的集群。
  - 自定义模式：您可以自定义配置域名解析到每个集群的权重。并且可以配置地域亲和，设置特定区域的用户流量访问特定的集群。

单击“创建”完成域名访问 创建。


---

## 修改别名

- 登录MCP控制台，选择“域名访问”，单击访问名称，进入域名访问详情界面。
- 单击填写别名，填写完成后单击

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/2z0q4J.jpg?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_lfit'/>


---

## 修改流量比例

- 登录MCP控制台，选择“域名访问”，单击访问名称，进入域名访问详情界面。
- 在“拓扑图”页签下，单击“修改流量配比”。
- 修改完成后，单击“确定”

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/YCunzu.jpg?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_l' />


---

# 单集群工作台

MCP 提供了一个统一的集群工作台，在这里可以进行每个集群的资源管理

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/QUTNKE.png?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_lfit'/>

- 仅提供了最基础的通用能力，这样可以保证在多个云的视频
- 这部分的能力提升空间会很多


---

## 迁移

多云容器平台支持将某个集群的应用迁移到其他集群。当 MCP 拥有 2 个集群时，就具备了迁移的能力。

操作步骤：
- 登录集群控制台，在左侧导航栏中单击“工作负载 > 无状态（Deployment）”。
- 选择需要进行迁移的工作负载名称，单击对应操作列的“更多 > 迁移”。
- 在“基本信息”页签，配置相关信息。
  - 现部署集群：当前部署集群。
  - 迁入集群：选择需要迁入的集群。
  - 实例数量：设置迁入集群的实例数量，用户可以设置具体实例个数。
- 单击“下一步”，在“集群差异配置”页签，对迁入的集群进行差异化配置，详细介绍请参见4。
- 单击“确定”完成集群迁移配置。


---

## 克隆

多云容器平台支持将某个集群的应用克隆到其他集群。

操作步骤： 
- 登录集群控制台，在左侧导航栏中单击“工作负载 > 无状态（Deployment）”。
- 选择需要进行克隆的工作负载名称，单击对应操作列的“更多 > 克隆”。
- 在“基本信息”页签，配置相关信息。
  - 工作负载名称：工作负载的名称，命名必须唯一。
  - 命名空间：选择工作负载所在的命令空间，若不选择，默认配置为default。
  - 克隆负载部署集群：选择需要克隆工作负载的集群。
  - 实例数量：设置克隆集群的实例数量，用户可以设置具体实例个数。
- 单击“下一步”，在“集群差异配置”页签，对克隆的集群进行差异化配置，详细介绍请参见4。
- 单击“确定”完成集群克隆配置。


---

## 多云化

多云容器平台支持将单集群应用一键式转换为多云应用，将应用实例部署到多云多集群。

操作过程，与创建多云 Deployment 一致，目前仅支持 Deployment


---

# 监控功能

在MCP上您可以监控添加的Kubernetes集群，查看节点、负载和实例三个维度的监控信息，方便您统一运维。

您需要在Kubernetes集群安装Metric Server和Prometheus，这样才能将监控数据上报到MCP。

## Metric Server

跨集群HPA基于社区Metric API，获取集群中资源使用情况。使用跨集群HPA前提是集群安装了Metrics Server，Metrics Server通过kubelet summary API获取数据，实现Metrics API。 Metrics API只可以查询当前数据，不提供历史数据。

## Prometheus

MCP支持使用Prometheus上报Kubernetes集群的监控数据到监控中心，使用此功能您需要在Kubernetes集群中安装Prometheus。


---

## 监控接入管理

登录MCP控制台，单击左侧导航栏的“监控中心 > 接入管理”，在“操作”一列单击“接入Prometheus插件”。

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/a8IsKi.jpg?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_lfit'/>

<img src='http://ipic-typora-samzong.oss-cn-qingdao.aliyuncs.com//uPic/umK3e3.jpg?x-oss-process=image/resize,w_960,m_lfit' alt='resize,w_960,m_lfit'/>


---

# 录屏和文档资料

- 录屏： https://yongyu2000hotmailcom.sharepoint.cn/:f:/s/ndx/Em2DInt59tVDgV8dUXuLjWkBHYmlWyoG8XAn9-dQZrzgTA?e=Uv7Hzu

- 华为云文档： https://support.huaweicloud.com/productdesc-mcp/mcp_productdesc_0001.html
