---
title: include 文件
description: include 文件
services: cosmos-db
author: SnehaGunda
ms.service: cosmos-db
ms.topic: include
ms.date: 04/13/2018
ms.author: sngun
ms.custom: include file
ms.openlocfilehash: 0a9f2aaa4bc6422d4e8a86373b5e578c5bd65b4c
ms.sourcegitcommit: 0a84b090d4c2fb57af3876c26a1f97aac12015c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38726093"
---
1. 在新浏览器窗口中，登录到 [Azure 门户](https://portal.azure.com/)。
2. 在左菜单中，依次单击“创建资源”、“数据库”，然后在“Azure Cosmos DB”下单击“创建”。 
   
   ![Azure 门户的屏幕截图，突出显示“更多服务”和“Azure Cosmos DB”](./media/cosmos-db-create-dbaccount-table/create-nosql-db-databases-json-tutorial-1.png)

3. 在“新建帐户”页上，输入新 Azure Cosmos DB 帐户的设置。 
 
    设置|建议的值|说明
    ---|---|---
    ID|*输入唯一名称*|输入标识此 Azure Cosmos DB 帐户的唯一名称。 由于 documents.azure.com 将追加到用户提供的 ID 用于创建 URI，因此，请使用唯一但可识别的 ID。<br><br>ID 只能包含小写字母、数字和连字符 (-) 字符，并且必须包含 3 到 50 个字符。
    API|Azure 表|API 确定要创建的帐户的类型。 Azure Cosmos DB 提供了五种 API，用以满足应用程序的需求：SQL（文档数据库）、Gremlin（图形数据库）、MongoDB（文档数据库）、Azure 表和 Cassandra，每个目前都需要单独的帐户。<br><br>选择“Azure 表”，因为在本快速入门中，将创建一个使用表 API 的表。<br><br>[详细了解表 API](../articles/cosmos-db/table-introduction.md) |
    订阅|*输入上面在 ID 中提供的同一唯一名称*|选择要用于此 Azure Cosmos DB 帐户的 Azure 订阅。 
    资源组|新建<br><br>然后输入上面在 ID 中提供的同一唯一名称|选择“新建”，然后输入帐户的新资源组名称。 为简单起见，可以使用与 ID 相同的名称。
    位置|*选择离用户最近的区域*|选择要在其中托管 Azure Cosmos DB 帐户的地理位置。 使用离用户最近的位置，使他们能够以最快的速度访问数据。
    启用异地冗余| 留空 | 这将在第二个（配对）区域中创建数据库的复制版本。 将此项留空。  
    固定到仪表板 | Select | 选中此框，以便将新的数据库帐户添加到门户仪表板以便于访问。

    然后单击“创建”。

    ![Azure Cosmos DB 的“新建帐户”页](./media/cosmos-db-create-dbaccount-table/azure-cosmos-db-create-new-account.png)

4. 创建帐户需要几分钟时间。 等待门户中显示“祝贺你!已创建 Azure Cosmos DB 帐户”页。

    ![Azure 门户“通知”窗格](./media/cosmos-db-create-dbaccount-table/azure-cosmos-db-account-created.png)
