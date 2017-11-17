---
title: "Azure SQL 数据仓库性能层 | Microsoft Docs"
description: "Azure SQL 数据仓库的“弹性优化”和“计算优化”性能层简介。"
services: sql-data-warehouse
documentationcenter: NA
author: jrowlandjones
manager: jhubbard
editor: 
ms.service: sql-data-warehouse
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: data-services
ms.custom: performance
ms.date: 11/10/2017
ms.author: jrj;barbkess
ms.openlocfilehash: c403a73d03fd5152e2c0617b3e3784926c28f5c3
ms.sourcegitcommit: 659cc0ace5d3b996e7e8608cfa4991dcac3ea129
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2017
---
# <a name="azure-sql-data-warehouse-performance-tiers-preview"></a>Azure SQL 数据仓库性能层（预览）
SQL 数据仓库提供两个已针对分析工作负荷进行优化的性能层。 本文介绍性能层的概念，以帮助选择最适合工作负荷的性能层。 


## <a name="what-is-a-performance-tier"></a>什么是性能层？
性能层是确定数据仓库配置的选项。 此选项是创建数据仓库时所要做出的首要选择之一。  

- **“弹性优化”性能层**在体系结构中将计算层和存储层分开。 此选项非常适合可以根据短期的高峰活动频繁进行缩放，从而充分利用独立的计算层和存储层的工作负荷。 此计算层的价格门槛最低，可以根据大多数客户工作负荷的需求进行缩放。

- **“计算优化”性能层**使用最新的 Azure 硬件，引入了新的 NVMe 固态磁盘缓存，让访问频率最高的数据靠近 CPU，这正是你所需要的。 此性能层可以对存储自动分层，尤其适合复杂的查询，因为所有 IO 对计算层来说都是本地的。 另外，列存储进行了增强，以便在 SQL 数据仓库中存储无限数量的数据。 计算优化性能层提供最高级别的可伸缩性，允许扩展到 30,000 个计算数据仓库单位 (cDWU)。 对于需要进行持续且速度极快的操作的工作负荷，请选择此层。

## <a name="service-levels"></a>服务级别
服务级别目标 (SLO) 是确定数据仓库的成本和性能级别的可伸缩性设置。 “计算优化”性能层规模的服务级别以计算数据仓库单位 (cDWU) 计量，例如 DW2000c。 “弹性优化”服务级别以 DWU 计量，例如 DW2000。 有关详细信息，请参阅[什么是数据仓库单位？](what-is-a-data-warehouse-unit-dwu-cdwu.md)

在 T-SQL 中，SERVICE_OBJECTIVE 设置确定了数据仓库的服务级别和性能层。

```sql
--Optimized for Elasticity
CREATE DATABASE myElasticSQLDW
WITH
(    SERVICE_OBJECTIVE = 'DW1000'
)
;

--Optimized for Compute
CREATE DATABASE myComputeSQLDW
WITH
(    SERVICE_OBJECTIVE = 'DW1000c'
)
;
```

## <a name="memory-maximums"></a>内存最大值
性能层具有不同的内存配置文件，这些配置文件可解释成每个查询可用的不同内存量。 “计算优化”性能层提供的每个查询内存量是“弹性优化”性能层的 2.5 倍。 这些额外的内存有助于“计算优化”性能层提供飞快的性能。 更多的每个查询内存量还可让我们并行运行更多的查询，因为查询可以使用更低的[资源类](resource-classes-for-workload-management.md)。 

### <a name="optimized-for-elasticity"></a>弹性优化

“弹性优化”性能层的服务级别范围为 DW100 到 DW6000。 

| 服务级别 | 并发查询数上限 | 计算节点 | 每个计算节点的分布区数 | 每个分布区的最大内存 (MB) | 每个数据仓库的最大内存 (GB) |
|:-------------:|:----------------------:|:-------------:|:------------------------------:|:--------------------------------:|:----------------------------------:|
| DW100         | 4                      | 1             | 60                             | 400                              |  24                                |
| DW200         | 8                      | #N/A             | 30                             | 800                              |  48                                |
| DW300         | 12                     | 3             | 20                             | 1,200                            |  72                                |
| DW400         | 16                     | 4             | 15                             | 1,600                            |  96                                |
| DW500         | 20                     | 5             | 12                             | 2,000                            | 120                                |
| DW600         | 24                     | 6             | 10                             | 2,400                            | 144                                |
| DW1000        | 32                     | 10            | 6                              | 4,000                            | 240                                |
| DW1200        | 32                     | 12            | 5                              | 4,800                            | 288                                |
| DW1500        | 32                     | 15            | 4                              | 6,000                            | 360                                |
| DW2000        | 32                     | 20            | 3                              | 8,000                            | 480                                |
| DW3000        | 32                     | 30            | #N/A                              | 12,000                           | 720                                |
| DW6000        | 32                     | 60            | 1                              | 24,000                           | 1440                               |

### <a name="optimized-for-compute"></a>计算优化

“计算优化”性能层的服务级别范围为 DW1000c 到 DW30000c。 

| 服务级别 | 并发查询数上限 | 计算节点 | 每个计算节点的分布区数 | 每个分布区的最大内存 (GB) | 每个数据仓库的最大内存 (GB) |
|:-------------:|:----------------------:|:-------------:|:------------------------------:|:--------------------------------:|:----------------------------------:|
| DW1000c       | 32                     | #N/A             | 30                             |  10                              |   600                              |
| DW1500c       | 32                     | 3             | 20                             |  15                              |   900                              |
| DW2000c       | 32                     | 4             | 15                             |  20                              |  1200                              |
| DW2500c       | 32                     | 5             | 12                             |  25                              |  1500                              |
| DW3000c       | 32                     | 6             | 10                             |  30                              |  1800                              |
| DW5000c       | 32                     | 10            | 6                              |  50                              |  3000                              |
| DW6000c       | 32                     | 12            | 5                              |  60                              |  3600                              |
| DW7500c       | 32                     | 15            | 4                              |  75                              |  4500                              |
| DW10000c      | 32                     | 20            | 3                              | 100                              |  6000                              |
| DW15000c      | 32                     | 30            | #N/A                              | 150                              |  9000                              |
| DW30000c      | 32                     | 60            | 1                              | 300                              | 18000                              |

最大 cDWU 为 DW30000c，包括 60 个计算节点，每个计算节点有一个分布区。 例如，DW30000c 级别的 600 TB 数据仓库的每个计算节点可以处理大约 10 TB 数据。

## <a name="concurrency-maximums"></a>并发性最大值
SQL 数据仓库在单个数据仓库中提供行业领先的并发性。 为了确保每个查询具有足够的资源来有效执行，系统会通过向每个查询分配并发槽位，跟踪计算资源利用率。 系统将查询放入某个队列，然后，查询在队列中等待有足够的并发槽位可用。 

并发槽位还确定 CPU 优先级。 有关详细信息，请参阅[分析工作负荷](analyze-your-workload.md)。

### <a name="concurrency-slots"></a>并发槽位
使用并发槽位可以方便地跟踪可用于执行查询的资源。 这些槽位就像是演唱会的门票，因为席位有限，必须预订。 同样，SQL 数据仓库的计算资源量也是有限的。 查询需要通过获取并发槽位来预留计算资源。 在查询可以开始执行之前，必须预留足够的并发槽位。 查询完成后，会释放其并发槽位。 

* “弹性优化”性能层可扩展到 240 个并发槽位。
* “计算优化”性能层可扩展到 1200 个并发槽位。

每个查询消耗零个、一个或多个并发槽位。 系统查询和一些不重要的查询不消耗任何槽位。 默认情况下，由资源类控制的查询需要一个并发槽位。 较复杂的查询可能需要更多并发槽位。  

- 使用 10 个并发槽位运行的查询可以访问的计算资源，是使用 2 个并发槽位运行的查询的 5 倍。
- 如果每个查询需要 10 个并发槽位并且有 40 个并发槽位，则只有 4 个查询可以并发运行。
 
只有受资源控制的查询消耗并发槽位。 消耗的确切并发槽位数由查询的[资源类](resource-classes-for-workload-management.md)决定。

### <a name="optimized-for-compute"></a>计算优化
下表显示了每个[动态资源类](resource-classes-for-workload-management.md)的最大并发查询数和并发槽位数。  这些数字适用于“计算优化”性能层。

**动态资源类**
| 服务级别 | 并发查询数上限 | 可用的并发槽位数 | smallrc 使用的槽数 | mediumrc 使用的槽数 | largerc 使用的槽数 | xlargerc 使用的槽数 |
|:-------------:|:--------------------------:|:---------------------------:|:---------------------:|:----------------------:|:---------------------:|:----------------------:|
| DW1000c       | 32                         |   40                        | 1                     |  8                     |  16                   |  32                    |
| DW1500c       | 32                         |   60                        | 1                     |  8                     |  16                   |  32                    |
| DW2000c       | 32                         |   80                        | 1                     | 16                     |  32                   |  64                    |
| DW2500c       | 32                         |  100                        | 1                     | 16                     |  32                   |  64                    |
| DW3000c       | 32                         |  120                        | 1                     | 16                     |  32                   |  64                    |
| DW5000c       | 32                         |  200                        | 1                     | 32                     |  64                   | 128                    |
| DW6000c       | 32                         |  240                        | 1                     | 32                     |  64                   | 128                    |
| DW7500c       | 32                         |  300                        | 1                     | 64                     | 128                   | 128                    |
| DW10000c      | 32                         |  400                        | 1                     | 64                     | 128                   | 256                    |
| DW15000c      | 32                         |  600                        | 1                     | 64                     | 128                   | 256                    |
| DW30000c      | 32                         | 1200                        | 1                     | 64                     | 128                   | 256                    |

**静态资源类**

下表显示了每个[静态资源类](resource-classes-for-workload-management.md)的最大并发查询数和并发槽位数。  

| 服务级别 | 并发查询数上限 | 可用的并发槽位数 |staticrc10 | staticrc20 | staticrc30 | staticrc40 | staticrc50 | staticrc60 | staticrc70 | staticrc80 |
|:-------------:|:--------------------------:|:---------------------------:|:---------:|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|
| DW1000c       | 32                         |   40                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 32         |  32        |
| DW1500c       | 32                         |   60                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         |  64        |
| DW2000c       | 32                         |   80                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         |  64        |
| DW2500c       | 32                         |  100                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         |  64        |
| DW3000c       | 32                         |  120                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW5000c       | 32                         |  200                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW6000c       | 32                         |  240                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW7500c       | 32                         |  300                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW10000c      | 32                         |  400                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW15000c      | 32                         |  600                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |
| DW30000c      | 32                         | 1200                        | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |

### <a name="optimized-for-elasticity"></a>弹性优化
下表显示了每个[动态资源类](resource-classes-for-workload-management.md)的最大并发查询数和并发槽位数。  这些数字适用于“弹性优化”性能层。

**动态资源类**

| 服务级别 | 并发查询数上限 | 可用的并发槽位数 | smallrc | mediumrc | largerc | xlargerc |
|:-------------:|:--------------------------:|:---------------------------:|:-------:|:--------:|:-------:|:--------:|
| DW100         |  4                         |   4                         | 1       |  1       |  #N/A      |   4      |
| DW200         |  8                         |   8                         | 1       |  #N/A       |  4      |   8      |
| DW300         | 12                         |  12                         | 1       |  #N/A       |  4      |   8      |
| DW400         | 16                         |  16                         | 1       |  4       |  8      |  16      |
| DW500         | 20                         |  20                         | 1       |  4       |  8      |  16      |
| DW600         | 24                         |  24                         | 1       |  4       |  8      |  16      |
| DW1000        | 32                         |  32                         | 1       |  8       | 16      |  32      |
| DW1200        | 32                         |  32                         | 1       |  8       | 16      |  32      |
| DW1500        | 32                         |  32                         | 1       |  8       | 16      |  32      |
| DW2000        | 32                         |  48                         | 1       | 16       | 32      |  64      |
| DW3000        | 32                         |  64                         | 1       | 16       | 32      |  64      |
| DW6000        | 32                         | 128                         | 1       | 32       | 64      | 128      |

**静态资源类**下表显示了每个[静态资源类](resource-classes-for-workload-management.md)的最大并发查询数和并发槽位数。  这些数字适用于“弹性优化”性能层。

| 服务级别 | 并发查询数上限 | 最大并发槽位数 |staticrc10 | staticrc20 | staticrc30 | staticrc40 | staticrc50 | staticrc60 | staticrc70 | staticrc80 |
|:-------------:|:--------------------------:|:-------------------------:|:---------:|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|
| DW100         | 4                          |   4                       | 1         | #N/A          | 4          | 4          |  4         |  4         |  4         |   4        |
| DW200         | 8                          |   8                       | 1         | #N/A          | 4          | 8          |  8         |  8         |  8         |   8        |
| DW300         | 12                         |  12                       | 1         | #N/A          | 4          | 8          |  8         |  8         |  8         |   8        |
| DW400         | 16                         |  16                       | 1         | #N/A          | 4          | 8          | 16         | 16         | 16         |  16        |
| DW500         | 20                         |  20                       | 1         | #N/A          | 4          | 8          | 16         | 16         | 16         |  16        |
| DW600         | 24                         |  24                       | 1         | #N/A          | 4          | 8          | 16         | 16         | 16         |  16        |
| DW1000        | 32                         |  40                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 32         |  32        |
| DW1200        | 32                         |  48                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 32         |  32        |
| DW1500        | 32                         |  60                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 32         |  32        |
| DW2000        | 32                         |  80                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         |  64        |
| DW3000        | 32                         | 120                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         |  64        |
| DW6000        | 32                         | 240                       | 1         | #N/A          | 4          | 8          | 16         | 32         | 64         | 128        |

满足其中一个阈值时，就会按“先进先出”原则排队执行新查询。  如果查询已完成并且查询数和槽位数低于限制，则 Azure SQL 数据仓库会释放排队的查询。 

## <a name="next-steps"></a>后续步骤

若要详细了解如何利用资源类来进一步优化工作负荷，请查看以下文章：
* [用于工作负荷管理的资源类](resource-classes-for-workload-management.md)
* [分析工作负荷](analyze-your-workload.md)
