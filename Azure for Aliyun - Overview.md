# 关于Azure的账户、平台及服务的介绍——给阿里云的使用者

此篇文章旨在帮助阿里云的专家了解关于Azure的基础知识，包含账户、平台及服务。在文章中也将重点比较阿里云与Azure平台的主要异同之处。

你将学习到:

* Azure如何管理账户及资源
* Azure有哪些可用的解决方案
* Azure与阿里云提供的服务有哪些不同

 Azure与阿里云在设计云端平台与开发云服务各自独立，因此在各个主要的面向中都有一些差距。

## 概览

如同阿里云，Azure的服务建立在一系列的计算、存储、数据库以及网络服务。在许多面向中，两个平台提供基本相同的产品及服务。阿里云与Azure都能让你建立高可用的解决方案，不论是使用Windows或是Linux。因此，如果你是开源或是Linux的使用者，两个平台都能满足你的需求。

虽然两个平台都提供相似的功能，在资源的使用与管理上却有不同的设计。在部分的功能与解决方案设计中，无法有完全一对一的关系，有些服务也只在一个平台中提供。请参阅[Azure与阿里云的服务对照表](https://github.com/MS-HerbChung/AliCompetePreview/blob/master/Azure%20for%20Aliyun%20-%20Service%20Comparison.md)。

## 账户与订阅

Azure的服务可以透过多种选项购买，依据客户的大小或需求而有所差异。请参阅[Azure 定价](https://www.azure.cn/pricing/overview/)了解更多细节。

[Azure订阅](https://www.azure.cn/support/faq/)是一个资源的集合，同时能够指定管理员作账务及权限的管理。与阿里云不同的是，在阿里云账户下的资源是与该账户进行绑定，而Azure的订阅与账户是独立的，可以随时对资源进行移动及重新指定管理员。

![阿里云账号与Azure订阅管理架构对比](https://azureforaliyunexpert.blob.core.chinacloudapi.cn/images/AccountAndSubscriptionComparisonAzureAliyun.png "阿里云账号与Azure订阅管理架构对比")
<br/>*阿里云账号与Azure订阅管理架构对比*
<br/><br/>

在Azure中，订阅的管理员有三种类型：

-   **账户所有者** - 订阅及账单的管理员。账户所有者只能透过转换订阅拥有者进行改变。

-   **服务管理员** - 这个账号有权限创建与管理订阅里资源，但不包含账务信息。在默认中，账户所有者与服务管理员被分配到同一个账号中。账户所有者可以指派另一位使用者为服务管理员，作为技术及运营的负责人。一个订阅只能有一个服务管理员。

-   **协同管理员** - 一个订阅能有许多协同管理员。协同管理员没有权限改变服务管理员，但能够完全控制订阅下的资源。

在订阅的层级之下，使用者的角色和给别使用者的权限可以被分配到特定的资源，如同阿里云的访问控制。在Azure中，所有的使用者都将连结到一个Azure Active Directory的账号。

如同阿里云的账户，订阅有默认的配额及使用上限。请参阅[Azure 订阅和服务限制、配额和约束](https://docs.azure.cn/zh-cn/azure-subscription-service-limits)了解完整的清单。这些限制可根据需求增加到上限，可以透过[在线提交工单](https://www.azure.cn/support/support-ticket-form/?l=zh-cn)提交需求。 

### 了解更多

-   [Azure企业门户使用手册](https://docs.azure.cn/zh-cn/articles/azure-ea-portal-user-manual)

-   [Azure常见问题](https://www.azure.cn/support/faq/)

## 资源管理

在Azure中的“资源”与阿里云的代表意义基本相同，任何计算的实例、存储的物件、网络设备或其他类型的服务你可以透过平台创建、配置及管理。

Azure的资源能被创建及管理透过两种模式：Azure Resource Manger以及经典部署，可参阅[了解部署模型和资源状态](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-manager-deployment-model)了解两种模式的不同。新的资源将使用Azure Resource Manager的方式进行部署。

### 资源组

Azure有一个新的概念“资源组”，用于组织各式各样的资源如虚拟机、存储、虚拟网络等。因此，你可以发现[Azure资源组](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-group-overview#resource-groups)与阿里云的访问控制的概念并不相同。

在阿里云中，你需要在不同的授权策略中列出所有想包含的资源名称，而后决定在此授权策略中允许使用者作哪些操作。在Azure的资源组中，则是将资源预先分类到不同的资源组中，作为管理及授权的单位，而一个资源只能隶属于一个资源组。

Azure的资源同样可以用[标记](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-group-overview#tags)进行管理。标记同时包含键与值，允许你跨越资源组做管理与查询。

### 管理方式

Azure提供几种方式管理你的资源：

-   [Web 界面](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-group-portal)：如同阿里云的管理控制台，Azure门户提供一个网页版本的管理界面用以管理Azure的资源。

-   [REST API](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-manager-rest-api)：Azure Resource Manager REST API提供一个使用程式语言存取的接口，支持绝大多数Azure的服务。

-   [命令行](https://docs.azure.cn/zh-cn/azure-resource-manager/xplat-cli-azure-resource-manager)：Azure CLI提供命令行接口的工具，可用于创建及管理Azure的资源。Azure CLI同时是一个跨平台的工具，可选择适合的版本[下载](https://github.com/azure/azure-xplat-cli)。

-   [PowerShell](https://docs.azure.cn/zh-cn/azure-resource-manager/powershell-azure-resource-manager)：PowerShell中的Azure模组，允许你透过脚本执行自动化的管理任务。PowerShell可以在Windows, Linux及MAC上运行，可选择适合的版本[下载](https://github.com/PowerShell/PowerShell)。

-   [模板](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-manager-create-first-template)：Azure Resource Manager模板提供JSON文件为基础的操作方式，类似于阿里云的资源编排。

在每个操作方式中，资源组是最基础用来管理资源的创建及调整的概念，如同阿里云资源编排的stack概念。

这些管理方式及架构与阿里云略有不同，但是提供相似的作用。除此之外，你也可以发现许多第三方工具用来做阿里云及Azure的管理。

### 了解更多

-   [Azure Resource Manager 概述](https://docs.azure.cn/zh-cn/azure-resource-manager/resource-group-overview)

## 区域及可用区 (高可用设计)

在阿里云中，高可用的设计围绕着可用区的概念。而在Azure中,容错域及可用性集则扮演着设计高可用的解决方案的重要角色。成对的区域提供了额外的灾难备援，防止地区性的灾难发生。

### 可用区、容错域及可用性集

在阿里云中，根据区域的大小，一个区域将被分成多个可用区。一个可用区意味着在地理区域中一个物理隔离的数据中心。如果你将应用服务器部署到不同的可用区，单一可用区的硬件或是网络的故障将不会对另一个可用区的系统产生影响。

在Azure中，[容错域](https://docs.azure.cn/zh-cn/virtual-machines/windows/regions-and-availability)定义了一个虚拟机的集群，在这个集群中的机器共用一个物理的电源及网络交换机。可以透过配置[可用性集](https://docs.azure.cn/zh-cn/virtual-machines/windows/regions-and-availability#availability-sets)将虚拟机分配到不同的容错域。当实例被分配同一个可用性集，Azure将分配机器到不同的容错域。如果在一个容错域中发生电源错误或是网络故障，不会影响到在可用性集里的所有机器。

![阿里云可用区与Azure容错域及可用性集](https://azureforaliyunexpert.blob.core.chinacloudapi.cn/images/RegionAvailabilityAzureAliyun.png "阿里云可用区与Azure容错域及可用性集")
<br/>*阿里云可用区与Azure容错域及可用性集*
<br/><br/>

可用性集应该根据实例在应用中扮演的角色，去确保在每个角色中至少有一个实例能正确运行。举例而言，在一个标准的三层式架构中，你应该针对前端、应用服务器与数据库创建单独的可用性集。

![Azure针对不同角色的可用性集](https://azureforaliyunexpert.blob.core.chinacloudapi.cn/images/AvailabilitySetAzure.png "Azure针对不同角色的可用性集")
<br/>*Azure针对不同角色的可用性集*
<br/><br/>

当一个虚拟机实例被加到可用性集里，同时会被分配一个[更新域](https://docs.azure.cn/zh-cn/virtual-machines/windows/regions-and-availability)。一个更新域是一个虚拟机的群组，这个群组里的机器将会在同一个时段进行更新或维修。将虚拟集分配到多个更新域中可确保计划性的更新不会影响到所有的机器。

### 成对的区域

在Azure中，你可以利用[成对的区域](https://azure.microsoft.com/documentation/articles/best-practices-availability-paired-regions/)
来实现成对区域服务的可靠性，保证即使出现整个数据中心的故障，你的服务仍然可用。

跟阿里云的可用区不同的是，虽然可用区是物理隔离的数据中心，但在地理位置上仍然非常接近。相对而言，Azure的成对区域之间的距离至少是450公里，这样可用确保当大型的灾难发生时，两个数据中心不会同时损坏。成对数据中心内的数据能够进行同步，同时成对的数据中心不会同时进行维修或更新，确保数据中心的可用性。

Azure [异地冗余存储](https://docs.azure.cn/zh-cn/storage/common/storage-redundancy#geo-redundant-storage)是一个自动复写到成对区域的功能。对于所有其他资源，创建一个副本在成对区域能够保证你的解决方案的高可用性。

### 了解更多

-   [Azure 中虚拟机的区域和可用性](https://docs.azure.cn/zh-cn/virtual-machines/linux/regions-and-availability)

-   [设计高可用的Azure应用](https://docs.microsoft.com/en-us/azure/architecture/resiliency/high-availability-azure-applications)

-   [设计Azure应用的灾备方案](https://docs.microsoft.com/en-us/azure/architecture/resiliency/disaster-recovery-azure-applications)

-   [Azure虚拟机的计划内维护](https://docs.azure.cn/zh-cn/virtual-machines/windows/planned-maintenance)

## 服务

请参与[Azure与阿里云的服务对照表](https://github.com/MS-HerbChung/AliCompetePreview/blob/master/Azure%20for%20Aliyun%20-%20Service%20Comparison.md)，了解两个平台完整的服务对应关系。

并非所有的区域都有Azure所有的服务，请参考[Azur服务仪表盘](https://www.azure.cn/support/service-dashboard/)了解详细的区域信息。你也可以找到针对不同服务中，关于运行时间和连接性方面的承诺，请参阅[服务级别协议](https://www.azure.cn/support/legal/sla/).

下面的部分将提供简单的说明，比较阿里云和Azure在一些常用的功能与服务间的对照。

### 计算服务

#### 阿里云云服务器及Azure虚拟机

虽然阿里云实例类型与Azure的虚拟机都有大小不同的选择，在细部的规格上有所区别，如内存、处理器、存储的能力。.

-   [阿里云实例类型](https://cn.aliyun.com/product/ecs?spm=5176.8142029.388261.205.299601a8eEbuSQ)

-   [Azure虚拟机大小(Windows)](https://docs.azure.cn/zh-cn/virtual-machines/windows/sizes)

-   [Azure虚拟机大小(Linux)](https://docs.azure.cn/zh-cn/virtual-machines/linux/sizes)

跟阿里云以小时计费不同的是，Azure的虚拟机是以分钟计费的。

同时，如同阿里云的保留实例计价模式，Azure也提供了预付费实例的计价模式。

#### 阿里云块存储及Azure磁盘存储

用于Azure虚拟机的持久性数据存储，将利用[磁盘存储](https://docs.azure.cn/zh-cn/virtual-machines/linux/about-disks-and-vhds)来完成。这项功能与阿里云提供的块存储基本相同。另外，Azure的虚拟机还提供了一个额外的[临时存储磁盘](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/)，能够完成了低延迟的读写操作。

高性能的磁盘读写，可以透过[Azure高级存储](https://docs.azure.cn/zh-cn/storage/common/storage-premium-storage)来实现。这跟阿里云提供的SSD云盘大致相同。

#### 阿里云弹性伸缩及Azure自动扩展

在Azure中的自动扩展主要由两个功能来实现：

-   [VM规模集](https://docs.azure.cn/zh-cn/virtual-machine-scale-sets/virtual-machine-scale-sets-overview)：允许创建及管理特定的虚拟机集群，这些机器的数量可以根据性能的需求进行自动扩展。

-   [应用服务缩放](https://docs.azure.cn/zh-cn/app-service-web/web-sites-scale)：提供自动缩放Azure应用服务的能力。

#### 其他的计算服务 

Azure同时提供数个计算服务，作为HPC或是微服务的架构，功能近似于阿里云的批量计算及企业级分布式应用服务：

-   [Azure批处理](https://docs.azure.cn/zh-cn/batch/)：执行需要大量计算的工作，同时管理后端可扩充的虚拟机集群。

-   [Service Fabric](https://docs.azure.cn/zh-cn/service-fabric/)：作为开发及微服务的架构平台，同时提供扩展及高可靠性。 

#### 了解更多

-   [透过Azure门户创建Linux虚机](https://docs.azure.cn/zh-cn/virtual-machines/linux/quick-create-portal)

-   [Azure参考架构：在Azure上运行Linux虚拟机](https://azure.microsoft.com/documentation/articles/guidance-compute-single-vm-linux/)

-   [在Azure的应用服务中运行Node.js](https://docs.azure.cn/zh-cn/app-service-web/app-service-web-get-started-nodejs)

-   [Azure参考架构：基本的网页应用](https://azure.microsoft.com/documentation/articles/guidance-web-apps-basic/)


### 存储

#### 阿里云对象存储/块存储/文件存储及Azure存储

在阿里云的平台中，云端的存储基本上分为三大类型：

-   **对象存储**：基本的对象存储，让数据在公网上能被存取。

-   **块存储**：块层级的存储，目的是建立虚机的存储磁盘。

-   **文件存储**：给数个计算实例间共享的文件存储。

在Azure的存储中，可以在订阅中建立[存储账户](https://docs.azure.cn/zh-cn/storage/common/storage-create-storage-account)允许你创建及管理下列存储服务：

-   [Blob存储](https://docs.azure.cn/zh-cn/storage/blobs/storage-blobs-introduction)：存储任何类型的文本或是二进位数据，如文档、媒体文件、或是应用程序安装文件。你可以设计不同的Blob存储存取安全等级，决定是否让文件被公开的存取。Blob存储与阿里云的对象存储有类似的功能。

-   [队列存储](https://docs.azure.cn/zh-cn/storage/queues/storage-queues-introduction)：提供消息的传递给工作流或是应用间的通信。

-   [文件存储](https://docs.azure.cn/zh-cn/storage/files/storage-files-introduction)：提供基于标准接口(SMB)的共享存储。

#### 阿里云归档存储及Azure存储

Azure存储并未提供直接等同于阿里云归档存储的服务。针对长期且不常使用的数据，Azure提供[冷存储](https://docs.azure.cn/zh-cn/storage/blobs/storage-blob-storage-tiers)。冷存储提供更低成本的存储，类似于阿里云提供对象存储中的低频访问存储类型。

#### 了解更多

-   [Azure存储性能与扩充性确认清单](https://docs.azure.cn/zh-cn/storage/common/storage-performance-checklist)

-   [Azure存储安全性指南](https://docs.azure.cn/zh-cn/storage/common/storage-security-guide)


### 网络

#### 阿里云负载均衡及Azure负载均衡器、应用程序网关

在Azure中主要有两个服务作为负载均衡的作用：

-   [负载均衡器](https://docs.azure.cn/zh-cn/load-balancer/)：提供与阿里云负载均衡相似的功能，允许你分配网络流量到多台虚拟机。同时，负载均衡也能提供故障切换的功能。

-   [应用程序网关](https://docs.azure.cn/zh-cn/application-gateway/)：提供应用层级的路由分发，可根据需求定义规则。


#### 阿里云高速通道及Azure ExpressRoute

Azure提供站点到站点的专线连结，称为[ExpressRoute](https://docs.azure.cn/zh-cn/expressroute/)。ExpressRoute允许你通过一条专线连结你本地的网络直接到Azure的资源。Azure同时也提供了另一个方便且较低成本的作法，[站点到站点连结](https://docs.azure.cn/zh-cn/vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal)
。

#### 了解更多

-   [透过Azure门户创建虚拟网络](https://docs.azure.cn/zh-cn/virtual-network/virtual-network-get-started-vnet-subnet)

-   [计划及设计Azure虚拟网络](https://docs.azure.cn/zh-cn/virtual-network/virtual-network-vnet-plan-design-arm)

-   [Azure 网络安全最佳实践](https://docs.azure.cn/zh-cn/security/azure-security-network-security-best-practices)

### 数据库服务

#### 阿里云云数据库及Azure 数据库

阿里云和Azure提供的数据库类型略有不同，阿里云的云数据库提供多种版本，如MySQL、SQL、PostgreSQL等。

[SQL数据库](https://docs.azure.cn/zh-cn/sql-database/)是Azure主要的数据库服务，提供了高扩展性的关系型数据存储，SQL数据库是基于SQL进行开发，Azure同时也提供MySQL数据库的服务，用户可根据需求选择适合的版本。 

另外，针对非关系型数据库，Azure的[Cosmos DB](https://docs.azure.cn/zh-cn/cosmos-db/)，提供了与阿里云中的MongoDB及Oceanbase相似的功能。

#### 了解更多

-   [在Azure门户创建SQL数据库](https://docs.azure.cn/zh-cn/sql-database/sql-database-get-started-portal)

-   [配置SQL数据库的异地复制](https://docs.azure.cn/zh-cn/sql-database/sql-database-geo-replication-portal)

-   [使用表开发应用程序](https://docs.azure.cn/zh-cn/cosmos-db/create-table-dotnet)

### 安全及身份

#### 网页应用防火墙

在Azure中，你可以直接使用[Web 应用程序防火墙](https://docs.azure.cn/zh-cn/application-gateway/application-gateway-web-application-firewall-overview)，或是使用第三方在Azure市场所提供的解决方案。

#### 了解更多

-   [Azure安全概述](https://docs.azure.cn/zh-cn/security/security-get-started-overview)

-   [Azure身份管理及访问控制最佳实践](https://docs.microsoft.com/zh-cn/azure/security/azure-security-identity-management-best-practices)

### 应用及消息服务

#### 邮件及短信服务

阿里云提供邮件推送及短息服务作为通知或营销的沟通方式。在Azure上，必须使用第三方的服务，例如
[Sendgrid](https://sendgrid.com/partners/azure/)或是[SendCloud](http://www.sendcloud.net/)。

#### 阿里云消息队列、消息服务及Azure队列存储、服务总线

阿里云的消息队列及消息服务用来连结应用、服务及装置。Azure有两个服务提供相似的功能：

-   [队列存储](https://docs.azure.cn/zh-cn/storage/queues/storage-queues-introduction)：一个云端的消息服务允许在Azure应用元件中进行通信。

-   [服务总线](https://docs.azure.cn/zh-cn/service-bus/)：更加可靠的消息系统，用以连结应用、服务及装置。同时提供连结远端或本地服务的能力，请参阅[服务总线中继](https://docs.azure.cn/zh-cn/service-bus-relay/)。

#### 了解更多

-   [如何通过 Node.js 使用队列存储](https://docs.azure.cn/zh-cn/storage/queues/storage-nodejs-how-to-use-queues)

-   [使用服务总线进行开发](https://docs.azure.cn/zh-cn/service-bus-messaging/service-bus-queues-topics-subscriptions)

### 分析及大数据

Azure提供了许多产品及服务用来搜集、整理、分析及可视化大量的数据，其中包含：

-   [HDInsight](https://docs.azure.cn/zh-cn/hdinsight/)：管理Apache分布式的服务，包含Hadoop、Spark、Storm、及HBase。

-   [SQL 数据仓库](https://docs.azure.cn/zh-cn/sql-data-warehouse/)：大型的关系型数据库。

-   [流分析](https://docs.azure.cn/zh-cn/stream-analytics/)：实时的数据分析。

-   [PowerBI](https://www.microsoft.com/china/powerbi/)：用以做数据可视化。

#### 了解更多

-   [了解大数据解决方案](https://msdn.microsoft.com/library/dn749804.aspx)

## 后续步骤

-   [Azure与阿里云的服务对照表](https://aka.ms/azure4aws-services)

-   [互动式的Azure平台全览](http://azureplatform.azurewebsites.net/)

-   [Azure快速入门](https://school.azure.cn/category?filter=%7B%22curriculumCategoryId%22%3A%222%22%7D)

-   [Azure架构中心](https://azure.microsoft.com/solutions/architecture/)

-   [Azure参考架构](https://azure.microsoft.com/documentation/articles/guidance-architecture/)

-   [Azure模式与实践](https://azure.microsoft.com/documentation/articles/guidance/)
