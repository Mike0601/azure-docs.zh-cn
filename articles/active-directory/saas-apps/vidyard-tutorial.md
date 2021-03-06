---
title: 教程：Azure Active Directory 与 Vidyard 的集成 | Microsoft Docs
description: 了解如何在 Azure Active Directory 和 Vidyard 之间配置单一登录。
services: active-directory
documentationCenter: na
author: jeevansd
manager: femila
ms.reviewer: joflore
ms.assetid: bed7df23-6e13-4e7c-b4cc-53ed4804664d
ms.service: active-directory
ms.component: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 05/22/2018
ms.author: jeedes
ms.openlocfilehash: 0934ec2443d240234b2120056894921f2e30c81c
ms.sourcegitcommit: 16ddc345abd6e10a7a3714f12780958f60d339b6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36213159"
---
# <a name="tutorial-azure-active-directory-integration-with-vidyard"></a>教程：Azure Active Directory 与 Vidyard 的集成

本教程介绍了如何将 Vidyard 与 Azure Active Directory (Azure AD) 进行集成。

将 Vidyard 与 Azure AD 集成可提供以下优势：

- 可以在 Azure AD 中控制谁有权访问 Vidyard。
- 可以让用户使用其 Azure AD 帐户自动登录到 Vidyard（单一登录）。
- 可在中心位置（即 Azure 门户）管理帐户。

如需了解有关 SaaS 应用与 Azure AD 集成的详细信息，请参阅 [Azure Active Directory 的应用程序访问与单一登录是什么](../manage-apps/what-is-single-sign-on.md)。

## <a name="prerequisites"></a>先决条件

若要配置 Azure AD 与 Vidyard 的集成，需要准备好以下各项：

- Azure AD 订阅
- 启用了单一登录的 Vidyard 订阅

> [!NOTE]
> 为了测试本教程中的步骤，我们不建议使用生产环境。

测试本教程中的步骤应遵循以下建议：

- 除非必要，请勿使用生产环境。
- 如果没有 Azure AD 试用环境，可以[获取一个月的试用版](https://azure.microsoft.com/pricing/free-trial/)。

## <a name="scenario-description"></a>方案描述
在本教程中，将在测试环境中测试 Azure AD 单一登录。 本教程中概述的方案包括两个主要构建基块：

1. 从库中添加 Vidyard
2. 配置和测试 Azure AD 单一登录

## <a name="adding-vidyard-from-the-gallery"></a>从库中添加 Vidyard
若要配置 Vidyard 与 Azure AD 的集成，需要从库中将 Vidyard 添加到托管 SaaS 应用列表。

**若要从库中添加 Vidyard，请执行以下步骤：**

1. 在 **[Azure 门户](https://portal.azure.com)** 的左侧导航面板中，单击“Azure Active Directory”图标。 

    ![“Azure Active Directory”按钮][1]

2. 导航到“企业应用程序”。 然后转到“所有应用程序”。

    ![“企业应用程序”边栏选项卡][2]
    
3. 若要添加新应用程序，请单击对话框顶部的“新建应用程序”按钮。

    ![“新增应用程序”按钮][3]

4. 在搜索框中，键入“Vidyard”，在结果面板中选择“Vidyard”，然后单击“添加”按钮添加该应用程序。

    ![结果列表中的 Vidyard](./media/vidyard-tutorial/tutorial_vidyard_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>配置和测试 Azure AD 单一登录

在本部分中，将基于名为 Britta Simon 的测试用户配置和测试 Vidyard 的 Azure AD 单一登录。

若要运行单一登录，Azure AD 需要知道与 Azure AD 用户相对应的 Vidyard 用户。 换句话说，需要在 Azure AD 用户与 Vidyard 中相关用户之间建立链接关系。

若要配置和测试 Vidyard 的 Azure AD 单一登录，需要完成以下构建基块：

1. **[配置 Azure AD 单一登录](#configure-azure-ad-single-sign-on)** - 使用户能够使用此功能。
2. **[创建 Azure AD 测试用户](#create-an-azure-ad-test-user)** - 使用 Britta Simon 测试 Azure AD 单一登录。
3. **[创建 Vidyard 测试用户](#create-a-vidyard-test-user)** - 在 Vidyard 中创建 Britta Simon 的对应用户，并将其链接到用户的 Azure AD 表示形式。
4. **[分配 Azure AD 测试用户](#assign-the-azure-ad-test-user)** - 使 Britta Simon 能够使用 Azure AD 单一登录。
5. **[测试单一登录](#test-single-sign-on)** - 验证配置是否正常工作。

### <a name="configure-azure-ad-single-sign-on"></a>配置 Azure AD 单一登录

在本部分中，将在 Azure 门户中启用 Azure AD 单一登录并在 Vidyard 应用程序中配置单一登录。

**若要配置 Vidyard 的 Azure AD 单一登录，请执行以下步骤：**

1. 在 Azure 门户中，在 **Vidyard** 应用程序集成页上，单击“单一登录”。

    ![配置单一登录链接][4]

2. 在“单一登录”对话框中，选择“基于 SAML 的单一登录”作为“模式”以启用单一登录。
 
    ![“单一登录”对话框](./media/vidyard-tutorial/tutorial_vidyard_samlbase.png)

3. 在“Vidyard 域和 URL”部分中，如果要在 **IDP** 发起的模式下配置应用程序，请执行以下步骤：

    ![Vidyard 域和 URL 单一登录信息](./media/vidyard-tutorial/tutorial_vidyard_url2.png)

    a. 在“标识符”文本框中，使用以下模式键入 URL：`https://secure.vidyard.com/sso/saml/<unique id>/metadata`

    b. 在“回复 URL”文本框中，使用以下模式键入 URL：`https://secure.vidyard.com/sso/saml/<unique id>/consume`

4. 如果要在 SP 发起的模式下配置应用程序，请选中“显示高级 URL 设置”，并执行以下步骤：

    ![Vidyard 域和 URL 单一登录信息](./media/vidyard-tutorial/tutorial_vidyard_url1.png)

    在“登录 URL”文本框中，使用以下模式键入 URL：`https://secure.vidyard.com/sso/saml/<unique id>/login`

    > [!NOTE]
    > 这些不是实际值。 本教程稍后将介绍如何使用实际的登录 URL 和标识符来更新这些值

1. 在“SAML 签名证书”部分中，单击“证书(base64)”，并在计算机上保存证书文件。

    ![证书下载链接](./media/vidyard-tutorial/tutorial_vidyard_certificate.png) 

6. 单击“保存”按钮。

    ![配置单一登录“保存”按钮](./media/vidyard-tutorial/tutorial_general_400.png)

7. 在“Vidyard 配置”部分中，单击“配置 Vidyard”以打开“配置登录”窗口。 从“快速参考”部分中复制“SAML 单一登录服务 URL”

    ![Vidyard 配置](./media/vidyard-tutorial/tutorial_vidyard_configure.png)

8. 在另一个 Web 浏览器窗口中，以管理员身份登录到 Vidyard Software 公司站点。

9. 从 Vidyard 仪表板中，选择“组” > “安全性”

    ![Vidyard 配置](./media/vidyard-tutorial/configure1.png)

1. 单击“新建配置文件”选项卡。

    ![Vidyard 配置](./media/vidyard-tutorial/configure2.png)

11. 在“SAML 配置”部分中，执行以下步骤：

    ![Vidyard 配置](./media/vidyard-tutorial/configure3.png)

    a. 请在“配置文件名称”文本框中输入常规配置文件名称。

    b. 复制“SSO 用户登录页”值，将其粘贴到 Azure 门户上“Vidyard 域和 URL”部分中的“登录 URL”文本框中。

    c. 复制“ACS URL”值，将其粘贴到 Azure 门户上“Vidyard 域和 URL”部分中的“回复 URL”文本框中。

    d. 复制“颁发者/元数据 URL”值，将其粘贴到 Azure 门户上“Vidyard 域和 URL”部分中的“标识”文本框中。

    e. 在记事本中打开从 Azure 门户下载的证书，然后将其粘贴到“X.509 证书”文本框中。

    f. 在“SAML 终结点 URL”文本框中，粘贴从 Azure 门户复制的“SAML 单一登录服务 URL”值。

    g. 单击“确认”。

12. 从“单一登录”选项卡中，选择某个现有配置文件旁边的“分配”

    ![Vidyard 配置](./media/vidyard-tutorial/configure4.png)

    > [!NOTE]
    > 在创建 SSO 配置文件后，将其分配给用户需要通过 Azure 访问的任何组。 如果用户未存在于它们分配到的组中，则 Vidyard 将自动实时创建一个用户帐户并分配其角色。

13. 选择你的组织组，它显示在“可分配的组”中。

    ![Vidyard 配置](./media/vidyard-tutorial/configure5.png)

14. 可以在“当前分配的组”下看到已分配的组。 根据你的组织为组选择一个角色，然后单击“确认”。

    ![Vidyard 配置](./media/vidyard-tutorial/configure6.png)

    > [!NOTE]
    > 有关详细信息，请参阅[此文档](https://knowledge.vidyard.com/saml-single-sign-on-authentication/saml-based-single-sign-on-sso-in-vidyard)。

### <a name="create-an-azure-ad-test-user"></a>创建 Azure AD 测试用户

本部分的目的是在 Azure 门户中创建名为 Britta Simon 的测试用户。

   ![创建 Azure AD 测试用户][100]

**若要在 Azure AD 中创建测试用户，请执行以下步骤：**

1. 在 Azure 门户的左窗格中，单击“Azure Active Directory”按钮。

    ![“Azure Active Directory”按钮](./media/vidyard-tutorial/create_aaduser_01.png)

2. 若要显示用户列表，请转到“用户和组”，然后单击“所有用户”。

    ![“用户和组”以及“所有用户”链接](./media/vidyard-tutorial/create_aaduser_02.png)

3. 若要打开“用户”对话框，在“所有用户”对话框顶部单击“添加”。

    ![“添加”按钮](./media/vidyard-tutorial/create_aaduser_03.png)

4. 在“用户”对话框中，执行以下步骤：

    ![“用户”对话框](./media/vidyard-tutorial/create_aaduser_04.png)

    a. 在“姓名”框中，键入“BrittaSimon”。

    b. 在“用户名”框中，键入用户 Britta Simon 的电子邮件地址。

    c. 选中“显示密码”复选框，然后记下“密码”框中显示的值。

    d. 单击“创建”。
 
### <a name="create-a-vidyard-test-user"></a>创建 Vidyard 测试用户

本部分的目的是在 Vidyard 中创建名为 Britta Simon 的测试用户。 Vidyard 支持实时预配，这是默认启用的。 此部分不存在任何操作项。 尝试访问 Vidyard 期间，如果该用户尚不存在，则将创建一个新用户。
>[!Note]
>如果需要手动创建用户，请联系 [Vidyard 支持团队](mailto:support@vidyard.com)。

### <a name="assign-the-azure-ad-test-user"></a>分配 Azure AD 测试用户

在本部分中，通过向 Britta Simon 授予对 Vidyard 的访问权限使其能够使用 Azure 单一登录。

![分配用户角色][200] 

**若要将 Britta Simon 分配到 Vidyard，请执行以下步骤：**

1. 在 Azure 门户中打开应用程序视图，导航到目录视图，接着转到“企业应用程序”，并单击“所有应用程序”。

    ![分配用户][201] 

2. 在应用程序列表中，选择“Vidyard”。

    ![应用程序列表中的 Vidyard 链接](./media/vidyard-tutorial/tutorial_vidyard_app.png)  

3. 在左侧菜单中，单击“用户和组”。

    ![“用户和组”链接][202]

4. 单击“添加”按钮。 然后在“添加分配”对话框中选择“用户和组”。

    ![“添加分配”窗格][203]

5. 在“用户和组”对话框的“用户”列表中，选择“Britta Simon”。

6. 在“用户和组”对话框中单击“选择”按钮。

7. 在“添加分配”对话框中单击“分配”按钮。
    
### <a name="test-single-sign-on"></a>测试单一登录

在本部分中，使用访问面板测试 Azure AD 单一登录配置。

单击访问面板中的 Vidyard 磁贴时，应当会自动登录到 Vidyard 应用程序。
有关访问面板的详细信息，请参阅 [Introduction to the Access Panel](../active-directory-saas-access-panel-introduction.md)（访问面板简介）。 

## <a name="additional-resources"></a>其他资源

* [有关如何将 SaaS 应用与 Azure Active Directory 集成的教程列表](tutorial-list.md)
* [什么是使用 Azure Active Directory 的应用程序访问和单一登录？](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/vidyard-tutorial/tutorial_general_01.png
[2]: ./media/vidyard-tutorial/tutorial_general_02.png
[3]: ./media/vidyard-tutorial/tutorial_general_03.png
[4]: ./media/vidyard-tutorial/tutorial_general_04.png

[100]: ./media/vidyard-tutorial/tutorial_general_100.png

[200]: ./media/vidyard-tutorial/tutorial_general_200.png
[201]: ./media/vidyard-tutorial/tutorial_general_201.png
[202]: ./media/vidyard-tutorial/tutorial_general_202.png
[203]: ./media/vidyard-tutorial/tutorial_general_203.png

