---
title: Azure 逻辑应用的连接器 | Microsoft Docs
description: 从所有可用的 Microsoft 连接器中进行选择，以生成并创建逻辑应用
services: logic-apps
documentationcenter: ''
author: ecfan
manager: jeconnoc
editor: ''
tags: connectors
ms.assetid: f1f1fd50-b7f9-4d13-824a-39678619aa7a
ms.service: logic-apps
ms.workload: integration
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: get-started-article
ms.date: 06/21/2017
ms.author: estfan; ladocs
ms.openlocfilehash: caeb3bbf6e3106aff498b12906b730191e56a3d5
ms.sourcegitcommit: 6f6d073930203ec977f5c283358a19a2f39872af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35294820"
---
# <a name="connectors-list"></a>连接器列表
若要查找每个连接器的 Swagger 说明和连接器限制所定义的触发器和操作，请参阅[连接器详细信息](/connectors/)。

在创建逻辑应用时，连接器是不可或缺的一部分。 使用这些连接器可以扩展本地应用程序和云应用程序，对所创建的数据以及已经拥有的数据执行不同的操作。 连接器以内置操作或托管连接器的形式提供。

**内置操作**：逻辑应用引擎本身提供内置操作，用于与终结点通信以及执行任务。 例如，可以使用这些操作来调用 HTTP 终结点、Azure Functions 和 Azure API 管理操作，以及使用数据操作和变量来操作消息。

**托管连接器**：通过创建逻辑应用服务托管和管理的 API 连接，为各种服务提供 API 访问权限。 托管连接器分为以下类别：

* **标准连接器**：在使用逻辑应用时自动提供。 示例包括服务总线、Power BI、OneDrive 等。

* **本地连接器**：使用[本地数据网关][gatewaydoc]连接到本地服务器应用程序。 本地连接器包括到各种服务器应用程序（例如 SharePoint Server、SQL Server、Oracle DB、文件共享等）的连接。

* 集成帐户连接器：在购买集成帐户时提供。 使用这些连接器可以转换和验证 XML、处理 AS2/X12/EDIFACT 格式的企业到企业消息，以及对平面文件进行编码和解码。 如果使用 BizTalk Server，则可选择这些连接器将 BizTalk 工作流扩展到 Azure 中。  

    BizTalk Server 还有一个[逻辑应用适配器](https://msdn.microsoft.com/library/mt787163.aspx)，既可从逻辑应用接收数据，也可向逻辑应用发送数据。

* **企业连接器**：包括 MQ 和 SAP。 需支付额外费用。 

有关费用的详细信息，请参阅逻辑应用的[定价详细信息](https://azure.microsoft.com/pricing/details/logic-apps/)和[定价模型](../logic-apps/logic-apps-pricing.md)。 

## <a name="popular-connectors"></a>常用连接器
成千上万的应用程序和执行操作成功使用这些连接器处理数据和信息。 

### <a name="built-in-actions"></a>内置操作
逻辑应用引擎提供的操作可以用来操作数据、通过 HTTP 进行通信，以及控制逻辑应用定义的流。 部分此类操作包括：

| |  |  |  |
| --- | --- | --- | --- |
| [![API 图标][HTTPicon]<br/>**HTTP**][httpdoc] | 使用逻辑应用与任何基于 HTTP 的终结点通信。| [![API 图标][Azure-Functionsicon]<br/>**Azure Functions**][azure-functionsdoc] | 创建运行 C# 或 node.js 自定义代码片段的函数，并在逻辑应用中使用这些函数。  |
| [![API 图标][HTTP-Requesticon]<br/>**请求**][HTTP-Requestdoc] | 提供一个可调用的 HTTPS URL，在其他应用程序中通常用作 webhook。 当逻辑应用收到向此 URL 发出的请求时，逻辑应用就会启动。 | [![API 图标][Recurrenceicon]<br/>**计划**][recurrencedoc] | 根据简单或复杂的循环计划启动逻辑应用。 例如，在创建计划时，可以创建简单的计划，每天循环一次，也可以创建复杂的计划，在每月最后一个星期五的早晨 9:00 到下午 5:00 之间每小时循环一次。 |
| [![API 图标][CallLogicApp-icon]<br/>**调用<br/>逻辑应用**][nested-logic-appdoc] | 调用嵌套的逻辑应用。 任何具有请求触发器的逻辑应用都可以作为嵌套的逻辑应用来调用。| [![API 图标][API/Web-Appicon]<br/>**API 应用**][api/web-appdoc] | 调用应用服务 API 应用。 具有 swagger 的 API 应用在呈现时，与其他一类操作一样。|

### <a name="standard-connectors"></a>标准连接器
下表列出了用户最常用和最喜欢的一些连接器：

| |  |  |  |
| --- | --- | --- | --- |
| [![API 图标][AzureBlobStorageicon]<br/>**Azure Blob<br/>存储**][AzureBlobStoragedoc] | 如果需要自动完成存储帐户的任务，则应使用此连接器。 支持 CRUD（创建、读取、更新、删除）操作。 | [![API 图标][Dynamics-365icon]<br/>**Dynamics 365<br/>CRM Online**][Dynamics-365doc] | 最受欢迎的连接器之一。 它包含触发器和操作、有助于自动完成潜在客户的工作流，等等。 |
| [![API 图标][Event-Hubs-icon]<br/>**事件中心**][event-hubs-doc] | 在事件中心使用和发布事件。 例如，可以通过事件中心获取逻辑应用的输出，然后将输出发送到实时分析提供程序。 | [![API 图标][FTPicon]<br/>**FTP**][FTPdoc] | 如果可以从 Internet 访问 FTP 服务器，则可自动完成用于处理文件和文件夹的工作流。 <br/><br/>也可通过 SFTP 连接器来使用 SFTP。 |
| [![API 图标][Office-365-Outlookicon]<br/>**Office 365<br/>Outlook**][office365-outlookdoc] | 大量的触发器，以及数量更多的操作，便于在工作流中使用 Office 365 电子邮件和事件。 <br/><br/>此连接器包括“审批电子邮件”操作，用于审批休假请求、费用报表等。 <br/><br/>也可通过 Office 365 用户连接器使用 Office 365 用户。| [![API 图标][Salesforceicon]<br/>**Salesforce**][salesforcedoc] | 轻松使用 Salesforce 帐户登录，以便访问各种对象，例如潜在客户等。 | 
| [![API 图标][Service-Busicon]<br/>**服务总线**][Service-Busdoc] | 逻辑应用中最常用的连接器，其包括的触发器和操作适用于异步消息传送，以及队列、订阅和主题的发布/订阅。 |  [![API 图标][SharePointicon]<br/>**SharePoint<br/>Online**][SharePointdoc] | 如果通过 SharePoint 进行操作，并且可以利用自动化，则建议使用此连接器。 可以与本地 SharePoint 以及 SharePoint Online 配合使用。 |
| [![API 图标][SQL-Servericon]<br/>**SQL Server**][SQL-Serverdoc] | 使用次数最多的连接器之一，可以连接到本地 SQL Server 以及 Azure SQL 数据库。 | [![API 图标][Twittericon]<br/>**Twitter**][Twitterdoc] | 轻松使用 Twitter 帐户登录，并在有新推文发布时启动工作流。 然后，将这些推文保存到 SQL 数据库或 SharePoint 列表。 | 

### <a name="on-premises-connectors"></a>本地连接器 

本地连接器用于访问本地服务器中的数据。  创建到本地服务器的连接时，需要[本地数据网关][gatewaydoc]，该网关的作用是提供安全的通信通道，不需配置网络基础结构。  某些连接器包括：

|  |  |  |  |
| --- | --- | --- | --- |
| [![API 图标][db2icon]<br/>**DB2**][db2doc] | [![API 图标][oracle-DB-icon]<br/>**Oracle DB**][oracle-db-doc] | [![API 图标][sharepointicon]<br/>**SharePoint</br> Server**][sharepointserver] | [![API 图标][filesystem-icon]<br/>**文件</br>系统**][filesystemdoc] |
[![API 图标][sql-servericon]<br/>**SQL</br> Server**][sql-serverdoc] | ![API 图标][Biztalk-Servericon]<br/>**BizTalk</br> 服务器**| |

### <a name="integration-account-connectors"></a>集成帐户连接器 

Enterprise Integration Pack (EIP) 包括 BizTalk Server 社区众所周知的连接器。 购买[集成帐户](../logic-apps/logic-apps-enterprise-integration-create-integration-account.md)时，还会获得以下连接器： 

|  |  |  |  |
| --- | --- | --- | --- |
| [![API 图标][as2icon]<br/>**AS2</br> 解码**][as2decode] | [![API 图标][as2icon]<br/>**AS2</br> 编码**][as2encode] | [![API 图标][x12icon]<br/>**EDIFACT</br> 解码**][EDIFACTdecode] | [![API 图标][x12icon]<br/>**EDIFACT</br> 编码**][EDIFACTencode] |
[![API 图标][flatfileicon]<br/>**平面文件</br>编码**][flatfiledoc] | [![API 图标][flatfiledecodeicon]<br/>**平面文件</br>解码**][flatfiledecodedoc] | [![API 图标][integrationaccounticon]<br/>**集成<br/>帐户**][integrationaccountdoc] | [![API 图标][xmltransformicon]<br/>**转换<br/>XML**][xmltransformdoc] |
| [![API 图标][x12icon]<br/>**X12</br> 解码**][x12decode] | [![API 图标][x12icon]<br/>**X12</br> 编码**][x12encode] | [![API 图标][xmlvalidateicon]<br/>**XML <br/>验证**][xmlvalidatedoc] | [![API 图标][liquidicon]<br/>**转换 <br/>JSON**][JSONliquidtransformdoc] |

### <a name="enterprise-connectors"></a>企业连接器

连接到逻辑应用中的企业应用程序。

|  |  |
| --- | --- |
|[![API 图标][MQicon]<br/>**MQ**][mqdoc]|[![API 图标][SAPicon]<br/>**SAP**][sapconnector]|

> [!TIP]
> 若要在注册 Azure 帐户之前开始使用 Azure 逻辑应用，请转到[试用逻辑应用](https://tryappservice.azure.com/?appservice=logic)。 可立即创建短期的初学者逻辑应用。 不需要使用信用卡，也不需要做出承诺。

## <a name="connectors-as-triggers-and-actions"></a>用作触发器和操作的连接器

**触发器**可启动或运行逻辑应用的实例。 某些连接器提供触发器，在发生特定事件时通知应用。 例如，FTP 连接器提供 `OnUpdatedFile` 触发器，在更新文件时启动逻辑应用。 

逻辑应用包括以下类型的触发器：  

* *轮询触发器*：这些触发器以指定的频率轮询服务，检查是否有新数据。 

    有新数据可用时，将运行逻辑应用的新实例并以该数据作为输入。 

* *推送触发器*：这些触发器侦听终结点上的数据或要发生的事件，并触发逻辑应用的新实例。

* *定期触发器*：此触发器按规定的计划实例化逻辑应用。

连接器还提供可在工作流中使用的**操作**。 例如，可以通过逻辑应用查找数据，再在逻辑应用中使用该数据。 更具体地说，可以在 SQL 数据库中查找客户数据，并使用该客户数据生成工作流。 

> [!TIP]
> [连接器概述](connectors-overview.md)提供了有关触发器和操作的更多详细信息。 


## <a name="message-manipulation-actions"></a>消息操纵操作

逻辑应用包括内置的操作，可以用来更改或操纵有效负载数据。 内置的“数据操作”连接器包括以下操作： 

| | |
|---|---|
| **编制** | 生成以后使用或在生成工作流时使用的值或对象。 例如，可以创作一个其值来自多个步骤的 JSON 对象，也可以计算一个在以后的逻辑应用运行中引用的常量。 |
| **创建 CSV 表**<br/>**创建 HTML 表** | 将数组结果集转换为 CSV 或 HTML 表。 例如，添加 CRM“列出记录”操作，以及为今天添加的记录添加筛选器。 然后，将结果作为电子邮件中的 HTML 表发送。 |
| **筛选数组**（查询） | 从结果集中筛选出感兴趣的条目。 例如，使用 `#Azure` 搜索所有推文，并对返回的推文进行“筛选”，仅返回 `Tweeted_by_followers > 50` 的结果。 |
| **Join** | 通过某个分隔符来联接数组。 例如，“检测关键短语”操作返回包含关键短语的数组。 可以使用 `,` 或类似的符号来“联接”它们。 因此，请采用 `"Some, Phrase"` 格式，而不是 `["Some", "Phrase"]` 格式。 |
| **分析 JSON** | 分析并访问设计器中的 JSON 对象提供的值。 例如，如果 Azure Function 返回 JSON 有效负载，则可对其进行分析，以便以后在另一步骤中访问 JSON 属性。 该操作还验证 JSON 是否与运行时的指定架构匹配。 | 
| **Select** | 选择某个数组的特定属性进行进一步的处理。 如果从 SQL“列出记录”时返回了 15 个列，则只选择其中一部分进行进一步的处理。 输出是只包含所选属性的数组。 |

## <a name="custom-connectors-and-azure-certification"></a>自定义连接器和 Azure 认证 

若要调用的 API 运行自定义代码，或者无法作为连接器使用，可以[创建基于 REST 的 API 应用](../logic-apps/logic-apps-create-api-app.md)，以便扩展逻辑应用平台。 也可创建自己的[自定义连接器](../logic-apps/custom-connector-overview.md)，将其提供给订阅中的任何逻辑应用使用。

若要将自定义 API 应用公开并使其可以在 Azure 中使用，则可[提交进行 Microsoft 认证的连接器](../logic-apps/custom-connector-submit-certification.md)。

## <a name="get-help"></a>获取帮助

若要提问、解答问题以及了解其他 Azure 逻辑应用用户的活动，请访问 [Azure 逻辑应用论坛](https://social.msdn.microsoft.com/Forums/en-US/home?forum=azurelogicapps)。

为了帮助我们改进 Azure 逻辑应用和连接器，敬请在[逻辑应用用户反馈站点](http://aka.ms/logicapps-wish)上投票或发表看法。

我们是否缺少连接器主题，或者你认为哪些细节很重要？ 如果是，请帮帮忙，为我们的现有主题添加相关内容，或者写下你自己的主题。 我们的文档是开源的，托管在 GitHub 上。 [GitHub 存储库](https://github.com/Microsoft/azure-docs)入门。 

## <a name="next-steps"></a>后续步骤
* [创建第一个逻辑应用](../logic-apps/quickstart-create-first-logic-app-workflow.md)
* [为逻辑应用创建自定义 API](../logic-apps/logic-apps-create-api-app.md)
* [监视逻辑应用](../logic-apps/logic-apps-monitor-your-logic-apps.md)

<!--Connectors Documentation-->

[gatewaydoc]: ../logic-apps/logic-apps-gateway-connection.md "通过本地数据网关，从逻辑应用连接到本地数据源"
[api/web-appdoc]: ../logic-apps/logic-apps-custom-hosted-api.md "将逻辑应用与应用服务 API 应用集成"
[azureblobstoragedoc]: ./connectors-create-api-azureblobstorage.md "使用 Azure Blob 存储连接器管理 Blob 容器中的文件"
[azure-functionsdoc]: ../logic-apps/logic-apps-azure-functions.md "将逻辑应用与 Azure Functions 集成"
[db2doc]: ./connectors-create-api-db2.md "连接到云中或本地的 IBM DB2。更新行、获取表，等等"
[Dynamics-365doc]: ./connectors-create-api-crmonline.md "连接到 Dynamics CRM Online，以便使用 CRM Online 数据"
[event-hubs-doc]: ./connectors-create-api-azure-event-hubs.md "连接到 Azure 事件中心。在逻辑应用与事件中心之间接收和发送事件"
[filesystemdoc]: ../logic-apps/logic-apps-using-file-connector.md "连接到本地文件系统"
[ftpdoc]: ./connectors-create-api-ftp.md "连接到 FTP/FTPS 服务器以执行 FTP 任务，例如上传、获取、删除文件，等等"
[httpdoc]: ./connectors-native-http.md "通过 HTTP 连接器进行 HTTP 调用"
[http-requestdoc]: ./connectors-native-reqres.md "向逻辑应用添加 HTTP 请求和响应的操作"
[http-swaggerdoc]: ./connectors-native-http-swagger.md "通过 HTTP + Swagger 连接器进行 HTTP 调用"
[informixdoc]: ./connectors-create-api-informix.md "连接到云中或本地的 Informix。读取行、列出表，等等"
[nested-logic-appdoc]: ../logic-apps/logic-apps-http-endpoint.md "将逻辑应用与嵌套工作流集成"
[office365-outlookdoc]: ./connectors-create-api-office365-outlook.md "连接到 Office 365 帐户。发送和接收电子邮件、管理日历和联系人，等等"
[oracle-db-doc]: ./connectors-create-api-oracledatabase.md "连接到 Oracle 数据库以添加、插入和删除行以及执行其他操作"
[mqdoc]: ./connectors-create-api-mq.md "连接到 MQ 本地或 Azure，并发送和接收消息"
[recurrencedoc]:  ./connectors-native-recurrence.md "针对逻辑应用触发重复执行的操作"
[salesforcedoc]: ./connectors-create-api-salesforce.md "连接到 Salesforce 帐户。管理帐户、潜在客户、商机等"
[sapconnector]: ../logic-apps/logic-apps-using-sap-connector.md "连接到本地 SAP 系统"
[service-busdoc]: ./connectors-create-api-servicebus.md "从服务总线队列和主题发送消息，并从服务总线队列和订阅接收消息"
[sharepointdoc]: ./connectors-create-api-sharepointonline.md "连接到 SharePoint Online。管理文档、列出项，等等"
[sharepointserver]: ./connectors-create-api-sharepointserver.md "连接到 SharePoint 本地服务器。管理文档、列出项，等等"
[sql-serverdoc]: ./connectors-create-api-sqlazure.md "连接到 Azure SQL 数据库或 SQL Server。在 SQL 数据库表中创建、更新、获取和删除条目。"
[twitterdoc]: ./connectors-create-api-twitter.md "连接到 Twitter。获取时间线、发布推文，等等"
[webhookdoc]: ./connectors-native-webhook.md "向逻辑应用添加 Webhook 操作和触发器"

[as2doc]: ../logic-apps/logic-apps-enterprise-integration-as2.md "了解企业集成 AS2。"
[x12doc]: ../logic-apps/logic-apps-enterprise-integration-x12.md "了解企业集成 X12"
[flatfiledoc]:../logic-apps/logic-apps-enterprise-integration-flatfile.md "了解企业集成平面文件。"
[flatfiledecodedoc]:../logic-apps/logic-apps-enterprise-integration-flatfile.md "了解企业集成平面文件。"
[xmlvalidatedoc]: ../logic-apps/logic-apps-enterprise-integration-xml-validation.md "了解企业集成 XML 验证。"
[xmltransformdoc]: ../logic-apps/logic-apps-enterprise-integration-transform.md "了解企业集成转换。"
[as2decode]: ../logic-apps/logic-apps-enterprise-integration-as2-decode.md "了解企业集成 AS2 解码"
[as2encode]:../logic-apps/logic-apps-enterprise-integration-as2-encode.md "了解企业集成 AS2 编码"
[X12decode]: ../logic-apps/logic-apps-enterprise-integration-X12-decode.md "了解企业集成 X12 解码"
[X12encode]: ../logic-apps/logic-apps-enterprise-integration-X12-encode.md "了解企业集成 X12 编码"
[EDIFACTdecode]: ../logic-apps/logic-apps-enterprise-integration-EDIFACT-decode.md "了解企业集成 EDIFACT 解码"
[EDIFACTencode]: ../logic-apps/logic-apps-enterprise-integration-EDIFACT-encode.md "了解企业集成 EDIFACT 编码"
[integrationaccountdoc]: ../logic-apps/logic-apps-enterprise-integration-metadata.md "在集成帐户中查找架构、映射、合作伙伴等内容"
[JSONliquidtransformdoc]: ../logic-apps/logic-apps-enterprise-integration-liquid-transform.md "了解使用 Liquid 进行的 JSON 转换"


[boxDoc]: ./connectors-create-api-box.md "连接到 Box。上传、获取、删除、列出文件，等等"
[delaydoc]: ./connectors-native-delay.md "执行延迟的操作"
[dropboxdoc]: ./connectors-create-api-dropbox.md "连接到 Dropbox。上传、获取、删除、列出文件，等等"
[facebookdoc]: ./connectors-create-api-facebook.md "连接到 Facebook。发布到时间线、获取页面源，等等"
[githubdoc]: ./connectors-create-api-github.md "连接到 GitHub，对问题进行跟踪"
[google-drivedoc]: ./connectors-create-api-googledrive.md "连接到 GoogleDrive，以便使用数据"
[google-sheetsdoc]: ./connectors-create-api-googlesheet.md "连接到 Google Sheets，以便修改表"
[google-tasksdoc]: ./connectors-create-api-googletasks.md "连接到 Google Tasks，以便管理任务"
[google-calendardoc]: ./connectors-create-api-googlecalendar.md "连接到 Google Calendar 即可管理日历。"
[http-responsedoc]: ./connectors-native-reqres.md "向逻辑应用添加 HTTP 请求和响应的操作"
[instagramdoc]: ./connectors-create-api-instagram.md "连接到 Instagram。触发事件或针对事件进行操作"
[mailchimpdoc]: ./connectors-create-api-mailchimp.md "连接到 MailChimp 帐户。管理邮件和自动执行邮件操作"
[mandrilldoc]: ./connectors-create-api-mandrill.md "连接到 Mandrill 进行通信"
[microsoft-translatordoc]: ./connectors-create-api-microsofttranslator.md "连接到 Microsoft Translator。翻译文字、检测语言，等等" 
[office365-usersdoc]: ./connectors-create-api-office365-users.md 
[office365-videodoc]: ./connectors-create-api-office365-video.md "获取视频信息、视频列表和频道，以及 Office 365 视频的播放 URL"
[onedrivedoc]: ./connectors-create-api-onedrive.md "连接到个人 Microsoft OneDrive。上传、删除、列出文件，等等"
[onedrive-for-businessdoc]: ./connectors-create-api-onedriveforbusiness.md "连接到企业 Microsoft OneDrive。上传、删除、列出文件，等等"
[outlook.comdoc]: ./connectors-create-api-outlook.md "连接到 Outlook 邮箱。管理电子邮件、日历、联系人等"
[project-onlinedoc]: ./connectors-create-api-projectonline.md "连接到 Microsoft Project Online。管理项目、任务、资源等"
[querydoc]: ./connectors-native-query.md "通过查询操作选择和筛选数组"
[rssdoc]: ./connectors-create-api-rss.md "发布和检索源项，在新项发布到 RSS 源时触发操作。"
[sendgriddoc]: ./connectors-create-api-sendgrid.md "连接到 SendGrid。发送电子邮件和管理收件人列表"
[sftpdoc]: ./connectors-create-api-sftp.md "连接到 SFTP 帐户。上传、获取、删除文件，等等"
[slackdoc]: ./connectors-create-api-slack.md "连接到 Slack，并将消息发布到 Slack 通道"
[smtpdoc]: ./connectors-create-api-smtp.md "连接到 SMTP 服务器，发送带附件的电子邮件"
[sparkpostdoc]: ./connectors-create-api-sparkpost.md "连接到 SparkPost 进行通信"
[trellodoc]: ./connectors-create-api-trello.md "连接到 Trello。管理项目，与任何人一起组织任何事情"
[twiliodoc]: ./connectors-create-api-twilio.md "连接到 Twilio。发送和获取消息、获取可用号码，管理来电号码，等等"
[wunderlistdoc]: ./connectors-create-api-wunderlist.md "连接到 Wunderlist。管理任务和待办事项列表，让生活有条不紊，等等"
[yammerdoc]: ./connectors-create-api-yammer.md "连接到 Yammer。发布消息、获取新消息，等等"
[youtubedoc]: ./connectors-create-api-youtube.md "连接到 YouTube。管理视频和频道"


<!--Icon references-->
[appFiguresicon]: ./media/apis-list/appfigures.png
[AppServices-icon]: ./media/apis-list/AppServices.png
[Asanaicon]: ./media/apis-list/asana.png
[Azure-Automation-icon]: ./media/apis-list/azure-automation.png
[AzureBlobStorageicon]: ./media/apis-list/azureblob.png
[Azure-Data-Lake-icon]: ./media/apis-list/azure-data-lake.png
[Azure-MLicon]: ./media/apis-list/azureml.png
[Azure-Resource-Manager-icon]: ./media/apis-list/azure-resource-manager.png
[Azure-Queues-icon]: ./media/apis-list/azure-queues.png
[Basecamp-3icon]: ./media/apis-list/basecamp.png
[Bitbucket-icon]: ./media/apis-list/bitbucket.png
[Bitlyicon]: ./media/apis-list/bitly.png
[BizTalk-Servericon]: ./media/apis-list/biztalk.png
[Bloggericon]: ./media/apis-list/blogger.png
[Boxicon]: ./media/apis-list/box.png
[Campfireicon]: ./media/apis-list/campfire.png
[Cognitive-Services-Text-Analyticsicon]: ./media/apis-list/cognitiveservicestextanalytics.png
[DB2icon]: ./media/apis-list/db2.png
[Dropboxicon]: ./media/apis-list/dropbox.png
[Dynamics-365icon]: ./media/apis-list/dynamicscrmonline.png
[Dynamics-365-for-Financialsicon]: ./media/apis-list/madeira.png
[Dynamics-365-for-Operationsicon]: ./media/apis-list/dynamicsax.png
[Easy-Redmineicon]: ./media/apis-list/easyredmine.png
[Event-Hubs-icon]: ./media/apis-list/eventhubs.png
[Facebookicon]: ./media/apis-list/facebook.png
[FileSystem-icon]: ./media/apis-list/filesystem.png
[FileSystemIcon]: ./media/apis-list/filesystem.png
[FTPicon]: ./media/apis-list/ftp.png
[GitHubicon]: ./media/apis-list/github.png
[Google-Calendaricon]: ./media/apis-list/googlecalendar.png
[Google-Driveicon]: ./media/apis-list/googledrive.png
[Google-Sheetsicon]: ./media/apis-list/googlesheet.png
[Google-Tasksicon]: ./media/apis-list/googletasks.png
[HideKeyicon]: ./media/apis-list/hidekey.png
[HipChaticon]: ./media/apis-list/hipchat.png
[Informixicon]: ./media/apis-list/informix.png
[Insightlyicon]: ./media/apis-list/insightly.png
[Instagramicon]: ./media/apis-list/instagram.png
[Instapapericon]: ./media/apis-list/instapaper.png
[JIRAicon]: ./media/apis-list/jira.png
[MailChimpicon]: ./media/apis-list/mailchimp.png
[Mandrillicon]: ./media/apis-list/mandrill.png
[Microsoft-Translatoricon]: ./media/apis-list/microsofttranslator.png
[MQicon]: ./media/apis-list/mq.png
[Office-365-Outlookicon]: ./media/apis-list/office365.png
[Office-365-Usersicon]: ./media/apis-list/office365users.png
[Office-365-Videoicon]: ./media/apis-list/office365video.png
[OneDriveicon]: ./media/apis-list/onedrive.png
[OneDrive-for-Businessicon]: ./media/apis-list/onedriveforbusiness.png
[Oracle-DB-icon]: ./media/apis-list/oracle-db.png
[Outlook.comicon]: ./media/apis-list/outlook.png
[PagerDutyicon]: ./media/apis-list/pagerduty.png
[Pinteresticon]: ./media/apis-list/pinterest.png
[Project-Onlineicon]: ./media/apis-list/projectonline.png
[Redmineicon]: ./media/apis-list/redmine.png
[RSSicon]: ./media/apis-list/rss.png
[Common-Data-Serviceicon]: ./media/apis-list/runtimeservice.png
[Salesforceicon]: ./media/apis-list/salesforce.png
[SAPicon]: ./media/apis-list/sap.png
[SendGridicon]: ./media/apis-list/sendgrid.png
[Service-Busicon]: ./media/apis-list/servicebus.png
[SFTPicon]: ./media/apis-list/sftp.png
[SharePointicon]: ./media/apis-list/sharepointonline.png
[Slackicon]: ./media/apis-list/slack.png
[Smartsheeticon]: ./media/apis-list/smartsheet.png
[SMTPicon]: ./media/apis-list/smtp.png
[SparkPosticon]: ./media/apis-list/sparkpost.png
[SQL-Servericon]: ./media/apis-list/sql.png
[Todoisticon]: ./media/apis-list/todoist.png
[Trelloicon]: ./media/apis-list/trello.png
[Twilioicon]: ./media/apis-list/twilio.png
[Twittericon]: ./media/apis-list/twitter.png
[Vimeoicon]: ./media/apis-list/vimeo.png
[Visual-Studio-Team-Servicesicon]: ./media/apis-list/visualstudioteamservices.png
[WordPressicon]: ./media/apis-list/wordpress.png
[Wunderlisticon]: ./media/apis-list/wunderlist.png
[Yammericon]: ./media/apis-list/yammer.png
[YouTubeicon]: ./media/apis-list/youtube.png

<!-- Primitive Icons -->
[API/Web-Appicon]: ./media/apis-list/appservices.png
[Azure-Functionsicon]: ./media/apis-list/function.png
[CallLogicApp-icon]: ./media/apis-list/calllogicapp.png
[Delayicon]: ./media/apis-list/delay.png
[HTTPicon]: ./media/apis-list/http.png
[HTTP-Requesticon]: ./media/apis-list/request.png
[HTTP-Responseicon]: ./media/apis-list/response.png
[HTTP-Swaggericon]: ./media/apis-list/http_swagger.png
[Nested-Logic-Appicon]: ./media/apis-list/workflow.png
[Recurrenceicon]: ./media/apis-list/recurrence.png
[Queryicon]: ./media/apis-list/query.png
[Webhookicon]: ./media/apis-list/webhook.png

<!-- EIP Icons -->
[as2icon]: ./media/apis-list/as2.png
[x12icon]: ./media/apis-list/x12new.png
[flatfileicon]: ./media/apis-list/flatfileencoding.png
[flatfiledecodeicon]: ./media/apis-list/flatfiledecoding.png
[xmlvalidateicon]: ./media/apis-list/xmlvalidation.png
[xmltransformicon]: ./media/apis-list/xsltransform.png
[integrationaccounticon]: ./media/apis-list/integrationaccount.png
[liquidicon]: ./media/apis-list/liquidtransform.png
