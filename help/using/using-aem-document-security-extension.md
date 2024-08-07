---
title: 使用 AEM Document Security Extension for Microsoft&reg; Office
description: 无论受策略保护的文件的分布范围如何宽广，您都可以控制收件人使用受策略保护的文件的方式。本文档说明如何保护文件以及如何使用受保护的文件。
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 6cf19ed9439e5be5a4c2e2fa2458879f37c25b96
workflow-type: ht
source-wordcount: '6136'
ht-degree: 100%

---

# 使用 AEM Document Security Extension for Microsoft® Office{#using-aem-document-security-extension-for-microsoft-office}

## 使用 AEM Document Security Extension 保护文件 {#usingaemdocumentsecurityextensiontoprotectfiles}

无论在多大范围内分发受策略保护的文件，均可控制收件人使用这些文件的方式。

使用 Document Security Extension for Microsoft® Office 可执行以下这些任务：

* 配置与 Document Security 的连接
* 应用策略到文件
* 打开 Document Security Web 页面以创建和管理用户策略
* 从文件中删除策略保护
* 更改应用到文件的策略
* 打开 Document Security Web 页面以撤销对文件的访问权限或更改文件的策略
* 打开 Document Security Web 页面以查看文件的审核历史记录

### 连接到 Document Security 服务器 {#connect-to-a-document-security-server}

如果要将策略应用于文件，则必须配置 Document Security 的连接设置。根据 Document Security Extension for Microsoft® Office 的安装方式，您可能已有默认连接设置。您可以为 Document Security 的一个或多个实例添加连接设置。可从 Document Security 管理员获取服务器信息。

将您要用于保护文件或管理受保护文件的服务器设置为默认服务器。将策略应用于新文件或打开 Document Security 网页时，Document Security Extension for Microsoft® Office 连接到默认服务器。如果您使用 Document Security 的多个实例保护文件，则在这些服务器之间切换时必须更改默认服务器设置。您可以打开受 Document Security 任意实例保护的文件，只要您获得了授权可以打开文件。

如果您的 Document Security 服务器采用基于证书的身份验证，则必须将您收到的证书装入您的本地计算机。您需要选择证书身份验证，并提供要用于身份验证的证书。

在一个 Microsoft® Office 应用程序中配置某个 Document Security 实例的连接设置之后，即为所有 Word、Excel 和 PowerPoint 配置该实例。

#### 安装客户端证书 {#install-the-client-side-certificate}

如果您需要通过证书身份验证或双向身份验证访问 Document Security 网页，则您将收到必须安装在本地计算机上的证书。您收到证书文件（.PFX 或 .P12 文件）及其密码。

1. 将证书文件保存在本地计算机上。
1. 双击证书文件以打开证书导入向导，然后单击&#x200B;**下一步**。
1. 如果文件名框中列出了证书文件，单击&#x200B;**下一步**。如果您要定位其他证书，请单击&#x200B;**浏览**。
1. 输入您收到的密码，然后单击&#x200B;**下一步**。
1. 在“证书存储”对话框中，选择“将所有证书放在以下存储中”，然后单击&#x200B;**浏览**。
1. 在“选择证书存储”对话框中，选择“个人”，单击&#x200B;**确定**，单击&#x200B;**下一步**，然后单击&#x200B;**完成**。

#### 配置连接设置 {#configure-connection-settings}

1. 在 Document Security Extension for Microsoft® Office 2010 和 Office 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**选择服务器**。
1. 单击&#x200B;**新建**&#x200B;以创建连接设置，或者选择现有连接并单击&#x200B;**编辑**。
1. 在&#x200B;**名称**&#x200B;框中键入连接的名称。可以使用任意名称。
1. 在&#x200B;**服务器地址**&#x200B;框中键入服务器的地址。
1. 在&#x200B;**端口**&#x200B;框中键入服务器端口。
1. （可选）如果您要记住用户名和密码，请选择&#x200B;**在这台计算机上记住密码**，然后在对应的框中键入您的用户名和密码。如果其他人可能会访问该计算机，建议您不要选择此选项。
1. 单击&#x200B;**连接到此服务器**。Document Security Extension for Microsoft® Office 尝试连接到您指定的服务器。根据指定的身份验证类型，执行以下操作：

   **用户名和密码**

   输入从 Document Security 管理员那里收到的用户名和密码。

   **证书身份验证**

   选择此选项以选择您收到并安装在个人证书存储中的证书。

   如果在 Document Security 上只配置了一种身份验证类型，则仅显示该选项。

>[!NOTE]
>
>如果无法连接到服务器，请尝试在 Internet Explorer 中打开 Document Security Web 页面。如果无法使用 Internet Explorer 连接到服务器或如果有对话框显示关于服务器证书的警告，则 Document Security Extension for Microsoft® Office 无法连接到服务器。请联系服务器管理员寻求协助。

>[!NOTE]
>
>如果无法连接到 Document Security，会显示一条消息，其中表示“用户名和密码不正确，请检查配置设置并重试”。如果由于其他原因而无法连接，则会显示此消息。如果你是首次连接到服务器，请确保选择了正确的服务器名称和端口。

#### 指定默认服务器 {#specify-the-default-server}

1. 执行以下操作：

   * 在 Document Security Extension for Microsoft® Office 2010 和 Office 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**选择服务器**。

1. 选择服务器以指定作为默认服务器，然后单击&#x200B;**设为默认值**。默认服务器旁边将显示一个星号。

### 使用第三方身份验证提供程序 {#using-third-party-authentication-providers}

可将第三方身份验证提供程序与 AEM Forms Document Security 一并使用。这些身份验证提供程序帮助您将额外的访问层添加到受保护的文档。AEM Forms Document Security 支持以下扩展身份验证工作流程：

* 使用默认 AEM Forms URL 的扩展身份验证
* 使用自定义 URL 的扩展身份验证
* 在 JEE 服务器的 AEM Forms 上配置了使用第三方身份提供程序的默认扩展身份验证工作流
* 在 JEE 服务器的 AEM Forms 上配置了使用第三方身份提供程序的自定义扩展身份验证工作流
* 为列出 SAML 身份验证使用自定义页面的扩展身份验证

#### 使用默认 AEM Forms URL 的扩展身份验证 {#extended-authentication-using-default-aem-forms-url}

可以为扩展身份验证使用 AEM Forms URL。默认登录页面包含 Adobe 品牌。此外，为扩展身份验证使用默认 AEM Forms URL 时，将使用默认的 AEM Forms 设置。

执行以下步骤以启用使用默认 Adobe 登录 URL 的扩展身份验证：

1. 打开 AEM Forms 管理 UI。
1. 导航到“服务”>“Document Security”>“配置”>“服务器配置”。
1. 启用“允许扩展身份验证”选项。
1. 指定默认 URL 扩展身份验证登录 URL。默认 URL 为 http://localhost:8080/edc/extendedauthentication/welcome.jsp。

   单击&#x200B;**[!UICONTROL 保存]**。

   >[!NOTE]
   >
   >在 URL 中使用完全限定的主机名。Adobe 建议您使用 HTTPS 协议。

   现在，AEM Forms Document Security 配置为使用具有默认 AEM Forms 登录 URL 的扩展身份验证。

   ![](assets/third-party-authentication.png)

#### 具有自定义登录 URL 的扩展身份验证 {#extended-authentication-with-a-custom-landing-url}

可以为扩展身份验证使用自定义 URL。它提供了灵活性，可以显示具有自定义品牌的自定义身份验证页面。例如，您的组织的品牌。

可将自定义身份验证页面打包为一个 war 文件，然后将该 war 文件部署到 AEM Forms 服务器。该 war 文件包含用于接受用户凭据并对照 AEM Forms 服务器进行身份验证的完整逻辑。AEM Forms Document Security 对自定义身份验证页面具有以下要求：

* 身份验证页面应该将用户名作为 j_username 发送，将密码作为 j_password 发送。页面还应该将 source_url 和 login_url 作为隐藏参数发送。
* 在成功进行身份验证之后，页面应自动关闭。

要用自定义登陆 URL 实现扩展身份验证，请执行以下操作：

1. 将自定义身份验证 WAR 文件部署到 AEM Forms Server。
1. 打开 AEM Forms 管理 UI。
1. 导航到“服务”>“Document Security”>“配置”>“服务器配置”。
1. 启用“允许扩展身份验证”选项并指定自定义扩展身份验证登录 URL。
1. 将以下条目添加到 `config.xml` 文件中 SSO 节点下的条目&#x200B;*&lt;node name=&quot;AllowedUrls&quot;>之后*：

   >[!NOTE]
   >
   >&lt;entry key=&quot;sso-l&quot; value=&quot;/ sample_/login.jsp&quot;/>`!!discoiqbr!!`&lt;entry key=&quot;sso-s&quot; value=&quot;/ sample_/welcome.jsp&quot;>`!!discoiqbr!!`&lt;entry key=&quot;sso-o&quot; value=&quot;/ sample_/logout.jsp&quot;/>`!!discoiqbr!!`

   有关更新 config.xml 文件的分步信息，请参阅[手动编辑文档安全配置文件](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions#manually_editing_the_document_security_configuration_file)。

   现在，AEM Forms Document Security 配置为使用具有自定义登录 URL 的扩展身份验证

#### 在 AEM Forms 服务器上配置了第三方身份提供程序的默认扩展身份验证工作流 {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

扩展身份验证可使用 AEM Forms 服务器上提供的各种类型的身份验证。例如，SAML，[还有更多示例吗]。

注意：如果在 AEM Forms 服务器上配置了 SAML 提供程序，则在显示登陆 URL 之前显示一个页面，其中包含为 SAML 身份验证配置的所有身份提供程序。

在 Acrobat 中打开受保护的文档时显示以下屏幕。

#### 在 AEM Forms 服务器上配置了 SAML 提供程序时的自定义扩展身份验证工作流 {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

如果在 AEM Forms 服务器上配置了 SAML 提供程序，则在显示登陆 URL 之前显示一个页面，其中包含为 SAML 身份验证配置的所有身份提供程序。

在 AEM Forms 服务器上配置了 SAML 提供程序时配置自定义扩展身份验证工作流的先决条件：

* 在 AEM Forms 服务器上配置了 SAML 身份验证
* 将自定义 war（包含用于接受用户凭据并对照 AEM Forms 服务器进行身份验证的完整逻辑）部署到 AEM Forms 服务器。

#### 使用自定义页面列出 SAML 身份验证 {#using-custom-page-for-listing-saml-authentications}

还可显示自定义页面以包括所有在 AEM Forms 服务器上配置的身份验证提供程序。要创建此类页面，请执行以下操作：

1. 将自定义身份验证文件打包为一个 war 文件，然后将该 war 文件部署到 AEM Forms 服务器。该 war 文件包含用于接受用户凭据并对照 AEM Forms 服务器进行身份验证的完整逻辑。
1. 打开 AEM Forms 管理 UI 并导航到&#x200B;**[!UICONTROL 设置]**> **[!UICONTROL 用户管理]** > **[!UICONTROL 配置]** > **[!UICONTROL SAML 服务提供程序配置]**。
1. 将以下内容添加到“自定义属性”字段，然后单击&#x200B;**[!UICONTROL 保存]**。

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   现在，AEM Forms Document Security 配置为显示包含所有已配置身份验证提供程序的自定义页面。

### 获取用户帐户 {#obtaining-a-user-account}

如果您还没有 Document Security 帐户，Document Security 可能会在发生以下事件时启动注册流程：

* 一位想要向您发送受策略保护文件的 Document Security 用户将您添加到策略中。
* Document Security 管理员为您创建了帐户。

在你注册并激活帐户之后，可以使用通过策略向你提供了授权的受策略保护文件。

>[!NOTE]
>
>如果您收到受策略保护的文件并且没有 Document Security 帐户，或者您收到了邀请来注册，请联系向您发送文件的人以获取帮助。同样，如果您收到注册邀请，请联系发件人寻求帮助。

如果您从 Document Security 收到了电子邮件注册邀请，则可以使用电子邮件中的 URL 打开在线注册页面以注册。在注册之后，您会收到有关激活帐户的第二个通知。

#### 获取外部用户帐户 {#obtain-an-external-user-account}

1. 打开 Document Security 注册电子邮件。邮件包含的 URL 是 Document Security 外部用户注册页面的链接。如果您没有收到注册邮件，请联系向您发送文件的人以获取帮助。
1. 单击 URL 或者复制并将其粘贴到浏览器中。
1. 在对应的框中键入您的姓名、组织和密码。您的密码可以是任意八个字符的组合。

   >[!NOTE]
   >
   >请确保您选择了容易记住的密码，没有任何方法可以用于查找忘记的密码。

1. 单击&#x200B;**注册**。此时会显示一条消息，通知您检查电子邮件中的激活电子邮件消息。
1. 打开 Document Security 注册确认电子邮件。
1. 单击邮件中显示的 URL。
1. 单击登录页面的链接。
1. 在&#x200B;**用户名**&#x200B;框中，键入您在 Document Security 下注册的电子邮件地址。此电子邮件地址是您的默认 Document Security 用户名。
1. 在&#x200B;**密码**&#x200B;框中，键入在注册时创建的密码。
1. 单击&#x200B;**登录**。

### 创建和管理策略 {#creating-and-managing-policies}

如果您从 Document Security 管理员获得了权限，则可以在 Document Security 网页的“策略”页面上创建策略以应用到自己的文件。

一些可用于在 Document Security 网页中创建策略的策略设置，在 Word、Excel 和 PowerPoint 文件中不受支持。下表描述了如何将策略权限映射到 Word、Excel 和 PowerPoint 功能。

<table>
 <thead>
  <tr>
   <th><p>权限</p></th>
   <th><p>Word、Excel 和 PowerPoint 支持</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>打印 &gt; 不允许</p></td>
   <td><p>不允许打印文件。</p></td>
  </tr>
  <tr>
   <td><p>打印 &gt; 允许</p></td>
   <td><p>允许打印文件。</p><p><strong>注意</strong>：<i>如果策略提供了“复制”权限但未提供“打印”权限，则复制到其他文件的内容可以打印。</i></p></td>
  </tr>
  <tr>
   <td><p>打印 &gt; 仅限低分辨率</p></td>
   <td><p>不适用。</p></td>
  </tr>
  <tr>
   <td><p>更改 &gt; 任意</p></td>
   <td><p>文件可以更改。</p><p>未提供此权限时，您无法修改受保护的 Word 和 Excel 文件。可以修改 PowerPoint 文件，但无法保存更改或查看已修改文件的幻灯片。</p></td>
  </tr>
  <tr>
   <td><p>更改 &gt; 不允许</p></td>
   <td><p>用户无法修改受保护文件。</p></td>
  </tr>
  <tr>
   <td><p>更改 &gt; 变更页面</p></td>
   <td><p>不适用。</p><p>它包括插入、删除和旋转页面。</p></td>
  </tr>
  <tr>
   <td><p>更改 &gt; 填写并签名</p></td>
   <td><p>不适用。</p></td>
  </tr>
  <tr>
   <td><p>离线</p></td>
   <td><p>文件无法离线打开。</p></td>
  </tr>
  <tr>
   <td><p>复制</p></td>
   <td><p>文件内容可以复制到其他文件。</p></td>
  </tr>
  <tr>
   <td><p>屏幕阅读器 </p></td>
   <td><p>屏幕阅读器（面向视力障碍用户的设备）可以阅读文件内容。</p></td>
  </tr>
  <tr>
   <td><p>权限有效性</p></td>
   <td><p>支持。</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>常规设置</p></th>
   <th><p>Word、Excel 和 PowerPoint 支持</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>有效期</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>审核文档</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>自动离线租赁期</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>外部授权提供程序</p></td>
   <td><p>支持。</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>高级设置</p></th>
   <th><p>Word、Excel 和 PowerPoint 支持</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>动态水印</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>认证插件</p></td>
   <td><p>不适用。</p></td>
  </tr>
  <tr>
   <td><p>加密算法和密钥长度 </p></td>
   <td><p>支持所有选项。</p></td>
  </tr>
  <tr>
   <td><p>文档限制</p></td>
   <td><p>不论策略中如何设置，所有文件内容始终加密。</p></td>
  </tr>
  <tr>
   <td><p>访问被拒绝错误消息</p></td>
   <td><p>支持。</p></td>
  </tr>
 </tbody>
</table>

有关创建和管理策略的更多信息，请参阅 [Document Security 最终用户帮助](https://help.adobe.com/zh_CN/AEMForms/6.1/RMHelp/)。

### 应用策略 {#applying-policies}

您可以将任意可用策略应用到文件，包括您创建的策略以及策略集中您可以访问的部分。在应用策略前，必须保存文件。

在应用策略后，该策略将添加到 AEM Document Security 菜单的“最近使用”列表中，让您可以更轻松地应用最常用策略。“最近使用”列表仅显示您所连接的服务器或默认服务器的策略（如果您尚未登录到另一个文档安全实例）。

>[!NOTE]
>
>策略只能应用于 Microsoft® Office 2010 和 2013 中的 Word (.doc、.docx、.docm)、Excel (.xls、.xlsx、.xlsm) 和 PowerPoint (.ppt、.pptx、.pptm) 文件。而无法将策略应用于 Word 模板文件 (.dot)、Excel 模板文件 (.xlt) 和 PowerPoint 设计模板文件 (.pot)。

#### 应用策略 {#apply-a-policy}

1. 在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**安全 > 选择策略**。

   如果在服务器上选择用户名和密码作为身份验证方法并且还没有提供 Document Security 的登录信息，则对话框将提示您输入用户名和密码。

1. 从列表中选择策略并单击&#x200B;**应用**。
1. 保存文件。

#### 应用最近使用的策略 {#apply-a-recently-used-policy}

1. 在Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**安全** > *[策略名称]*。
1. 保存文件。

## 使用受策略保护的文件 {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

文件发布者拥有受策略保护的文件的知识产权，这些文件受到文档安全的保护。

无论您在文件发布者的组织之内还是之外，您均可使用受策略保护的文件。文档安全必须识别您才能打开受策略保护的文件。它必须通过 LDAP/Active Directory 来实现。或者，必须作为 JEE 上 LiveCycle/AEM 表单的本地用户来执行此操作，或者通过邀请后注册。

如果您收到受策略保护的文件但没有文档安全帐户，请联系发件人寻求帮助。同样，如果您收到注册邀请，请联系发件人寻求帮助。

### 在 Microsoft® Office 中使用受策略保护的文件 {#working-with-policy-protected-files-in-microsoft-office}

Document Security Extension for Microsoft® Office 限制特定 Word、Excel 和 PowerPoint 功能以保护文件发布者的知识产权。如果您没有权限更改文件，则无法将修改保存到其中。

如果您在使用受策略保护的文件，一些产品功能可能不可用或者可能无法正常使用。如果打开了不受保护的文件，则大多数功能都会启用，但那些允许您从受策略保护的文件导入或复制内容（无需复制或导出权限）的功能除外。

>[!NOTE]
>
>使用 Document Security Extension 支持的 Office 应用程序时，建议您禁用 Windows DEP 设置。此外，在具有 Document Security Extension 并为 McAfee VirusScan 启用了 On-Access Scan 的计算机上，为了确保 Office 应用程序顺利启动，请在 McAfee VirusScan 控制台中禁用 Buffer Overflow Protection 选项。这种调整有助于防止潜在的冲突。

如果某个功能不可用，则菜单上的命令名称和相关的工具栏按钮将不可用。在 Document Security Extension for Microsoft® Office 中，当您将鼠标指针悬停在命令或按钮上时，将显示一个工具提示，表示 Document Security 使命令不可用。

### 打开受策略保护的文件 {#opening-policy-protected-files}

您可以使用与打开任何其他文件相同的方法打开受策略保护的文件。如果您尚未登录 Document Security，系统将提示您登录。也就是说，如果您没有连接到互联网，您可以离线打开该文件。如果您取消登录过程，则会拒绝访问。

如果您没有权限打开文件，则会通知您访问被拒绝。如果撤销了文件访问权限，您也可能会被定向到该文件的更新版本（如果可用）。如果您无法打开受策略保护的文件并需要更多帮助，请联系文件发布者。

打开受保护文件时，文件名之后标题栏中的文本将说明文件受 AEM Document Security 保护。

从 SharePoint Server 在 Document Security Extension for Microsoft® Office 中打开受保护的文档时，请确保已打开与该文件类型关联的 Microsoft® Office 程序，例如 Microsoft® Word、Microsoft® Excel 或 Microsoft® PowerPoint。如果尝试打开文件但未打开关联的应用程序，则该文档可能不会打开，并显示一条错误消息，表示必须安装适用的插件。除了打开所需的应用程序外，Adobe 还建议您清除缓存文件夹。在SharePoint 服务器的Office 文档安全扩展中打开受保护的文档之前，请执行此操作。此外，在从 SharePoint Server 打开受保护文档时，文档上的所有权限将禁用，不论应用了什么策略。

根据在 Document Security 上实施的身份验证方法，在您打开受保护文档时，系统可能会提示选择身份验证方法。如果 Document Security 支持多种身份验证方法，则会向您显示身份验证选项。例如，如果 Document Security 服务器提供用户名/密码和证书身份验证，您可以选择合适的身份验证方法。如果启用了基于证书的身份验证，系统会提示您使用已经收到并安装的证书。

打开受保护文件时的用户体验取决于服务器上的相互身份验证配置。如果只安装了一个有效客户端证书，则不会显示身份验证对话框，文件成功打开。但是，如果在计算机上安装了多个客户端证书，则会显示身份验证对话框。用户必须选择有效的证书以打开受保护的文件。

### 从文件中删除策略保护 {#removing-policy-protection-from-a-file}

如果允许，您可以从已受保护的文件中删除策略保护。如果这样做，该文件不再受 Document Security 的保护。

1. 在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**删除**。

   如果还没有提供 Document Security 的登录信息，则对话框将提示您输入用户名和密码。

>[!NOTE]
>
>如果您无法从您保护的文件上删除策略，请联系 Document Security 管理员。

### 查看安全设置 {#viewing-security-settings}

您可以查看您对当前打印文件的权限。除了文件有效期之外，还可查看您对当前文件在离线复制、更改和访问时的权限以及文件有效期。

在 Document Security Extension for Microsoft® Office 2010 中，“Document Security”选项卡上的“安全状态”组显示您对文件的权限。

执行以下操作：

* 在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上的&#x200B;**安全状态**&#x200B;组中，单击任意项目。

### 在启用了自动应用策略时保存文档 {#saving-documents-when-auto-apply-policy-is-enabled}

如果管理员启用了自动应用策略功能，则在保存任何创建或编辑的文档时将自动保护该文档。

如果启用了自动应用策略，则 Document Security Extension for Microsoft® Office 提示您登录到 Document Security 服务器。输入您的用户名和密码，以便服务器可以验证您的身份。如果提供了正确的登录凭据，则将保存并保护该文档。

>[!NOTE]
>
>如果您无法登录 Document Security，则文档可能会保存，也可能会不保存。这种情况取决于管理员如何配置自动应用策略。请与管理员确认这种情况下会如何处理文档。

### 为离线访问同步 {#synchronizing-for-offline-access}

策略可以允许您在离线并且未连接到 Document Security 时打开文件。您必须以前登录过 Document Security 以与服务器建立凭据，然后才能离线工作。如果您计划离线处理文件，Adobe 建议您与 Document Security 同步。断开连接之前请执行此操作，以确保文件的策略设置与服务器保持同步。Adobe 还建议您在离线打开文件之前还要在线打开文件一次。如果您未在线打开文件一次或者未与服务器同步，则可能会无法在离线时使用受策略保护的文件。但是，离线租赁期必须未过期，并且文件的策略设置在上次与服务器手动或自动同步后不能发生更改。

执行以下操作：

* 在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**离线同步**。

  ***注意&#x200B;**：“离线同步”按钮可用，即使用户没有文档的离线权限。但是，选择该按钮没有任何效果。*

### 使用动态水印 {#working-with-dynamic-watermarks}

Document Security Extension for Microsoft® Office 支持在受策略保护的文档中加入动态文本式的水印。动态水印可以包含可能会更改的信息，例如日期、时间、用户名或策略的名称。如果用户打印受策略保护的文件，并且该文件包含动态水印和打印的权限，则水印显示在输出中。

文档安全扩展不支持丰富的水印功能。丰富的水印功能包括基于 PDF 的水印、水印中的多种元素以及文本格式选项等。它们还包括页面范围。

您可以使用 Document Security 网页创建动态水印。有关详细信息，请参阅 [文档安全最终用户帮助](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/forms/administrator-help/work-with-document-security/document-security)。

Document Security Extension for Microsoft® Office 支持以下这些水印功能：

<table>
 <thead>
  <tr>
   <th><p>Document Security 水印选项</p></th>
   <th><p>Word、Excel 和 PowerPoint 支持</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>策略名称</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>水印名称</p></td>
   <td><p>支持。</p></td>
  </tr>
  <tr>
   <td><p>用作背景</p></td>
   <td><p>无论是否选择“用作背景”，动态水印的显示行为相同。</p><p>对于 Word 2010 和 2013，动态水印仅显示在打印布局和打印预览视图中。 </p><p>同样对于 Excel 2010 和 2013，它仅显示在打印预览和打印布局视图中。</p></td>
  </tr>
  <tr>
   <td><p>垂直位置</p></td>
   <td><p>支持</p></td>
  </tr>
  <tr>
   <td><p>水平位置</p></td>
   <td><p>支持</p><p>对于 Excel 2010 和 2013，使用点的水印水平定位不起作用。</p></td>
  </tr>
  <tr>
   <td><p>缩放</p></td>
   <td><p>支持</p></td>
  </tr>
  <tr>
   <td><p>位置</p></td>
   <td><p>支持</p></td>
  </tr>
  <tr>
   <td><p>不透明度</p></td>
   <td><p>支持</p></td>
  </tr>
 </tbody>
</table>

### 打开 Document Security 网页 {#opening-the-document-security-web-pages}

您可以打开 Document Security Web 页面以创建和更新用户策略，并查看受策略保护文件的状态和审核信息。还可以使用 Document Security Web 页面更改或撤销对受策略保护文件的访问权限。

要打开 Document Security 网页，请在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上选择&#x200B;**创建和管理策略**。如果您尚未提供登录信息，则浏览器打开到服务器登录页面。

### 更改策略 {#changing-policies}

如果您具有权限，通常是作为 Document Security 管理员或文件发布者，您可以稍后应用不同的策略到文件或者更改当前已应用策略的设置。

要更改策略的设置，请使用 Document Security Web 页面。

1. 执行以下操作：

   * 在 Document Security Extension for Microsoft® Office 2010 或 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**安全 > 更改安全性**。

1. 从列表中选择一个策略，然后单击&#x200B;**应用**。

### 撤销文件访问权限 {#revoking-file-access-privileges}

您可以撤销打开您保护的文件的能力。撤销文件访问权限时，您可以指定当用户尝试打开文件时显示的消息，并在用修订副本替换文件时提供更新版本的 URL。

1. 执行以下操作：

   * 在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**撤销**。

   Document Security Web 页面打开到“撤销文档”页面。

1. 指定要显示的消息和更新版本的 URL（如果可用），然后单击&#x200B;**确定**。

有关撤销文件访问权限的更多信息，请参阅 [Document Security 最终用户帮助](https://help.adobe.com/zh_CN/AEMForms/6.1/RMHelp/)。

访问权限可以通过 Document Security Web 页面恢复。

### 查看文件审核历史记录 {#viewing-the-file-audit-history}

Document Security 可以保存受策略保护文件的审核历史记录，这样您可以审核用户在文件上执行的操作。

Word、Excel 和 PowerPoint 文件的审核事件包括下列：

**保护新文档** 策略应用到文件

**查看文档** 文件打开

**关闭文档** 文件关闭

**撤销文档** 删除了文件的访问权限

**取消撤销文档** 恢复了文件的访问权限

**修改文档** 在本地更改和保存了文件

**打印高分辨率** 文件打印

**更改安全处理程序** 从文件上删除了策略保护

**在文档上切换策略** 新策略从 Document Security 网页应用到文件

### 查看文件的审核历史记录 {#view-the-audit-history-for-a-file}

在 Document Security Extension for Microsoft® Office 2010 和 2013 中，在 **Document Security** 选项卡上，选择&#x200B;**审核历史记录**。

随后 Document Security Web 页面打开到“事件”页面，其中显示当前文件的已审核事件。

### Microsoft® Office 受限功能 {#microsoft-office-restricted-features}

为保护您的知识产权，在打开受策略保护的文件时，某些 Microsoft® Office 功能不可用。不可用的功能列表取决于向当前用户授予的权限。一些功能仅对受保护文件不可用，另一些则在受保护会话中对所有文件不可用。通常，从打开受策略保护文件开始直到关闭应用程序或会话到期为止，您处于受保护会话中。

大部分策略将完整权限授予文件发布者。其他用户可能会发现额外的功能限制。

如果某个命令不可用，则菜单中的命令名称和相关的工具栏按钮将灰显。

>[!NOTE]
>
>将策略应用到包含指向嵌入文件的链接的文件，不会将策略应用到链接的文件。Document Security for Microsoft® Office 并不将保护延伸到链接的文件。

* 受策略保护的 Word、Excel 和 PowerPoint 文件会被阻止在 Internet Explorer 浏览器窗口中打开。
* 仅授予了更改权限的用户无法从其他应用程序使用 Windows 剪贴板将内容复制到文件。用户可以通过启用 Microsoft® Office 剪贴板选项将内容复制到文件。
* 在 Microsoft® Office 中打开受策略保护的文件使得直到关闭应用程序或会话到期后 Print Screen 键才可用。
* Document Security for Microsoft® Office 不支持 Web 分布式创作和版本管理 (WebDAV)。一般无法从 WebDAV 文件夹打开受策略保护的文件。如果可打开受策略保护的文件，则无权保存、打印、更改或复制该文件。

应用于受策略保护的文件的常规安全措施包括以下限制：

在受保护的会话期间，Word、Excel 和 PowerPoint 中的多种常用功能可能会受限。

如果打开了受策略保护的文件，但不允许用户更改它，则以任何方式更改该文件的命令都不可用。只有打开或创建文档的命令以及更改应用程序首选项的命令可用。

#### Word 2010 和 Word 2013 限制 {#word-2010-and-word-2013-restrictions}

在 Word 中打开受策略保护的文件时，自动文件恢复信息无法保存，直到您关闭并重新启动 Word。此外，以下列出的功能在所描述的情况下受限制：

**文件 > 新建 > 从现有内容新建** 可用，但在任何受策略保护文件打开时，使用此命令创建的文件无法保存。新文件中的内容无法复制到其他文件。

**文件 > 保存** 受更改权限限制。

**文件 > 另存为** 所有选项受更改权限限制。

**文件 > 打印** 所有选项受打印权限限制。除非策略允许高分辨率打印，否则不可用。

**文件 > 保存和发送** 所有选项在受保护会话期间不可用。

**文件 > 信息 > 保护文档 > 使用密码加密、添加数字签名、标记为最终状态、限制人员权限** 在受保护会话期间不可用。

**文件 > 工作流** 在受保护会话期间不可用。

***注意&#x200B;**：在Word, Excel, 和 PowerPoint 2010 中启动工作流仅在Office Professional Plus 2010, Office Enterprise 2010、Office Ultimate 2010 和独立 2010 版本中可用。*

**博客文章 > 发布** 在受保护会话期间不可用。

**文件 > 服务器 > 文件服务器任务菜单** 在受保护会话期间不可用。

**主页 > 剪贴板 > 复制** 受复制权限限制。如果不允许复制，则复制的内容无法粘贴到任何其他文件或者 Office 剪贴板中。如果用户具有更改权限，则可以在受保护文件中复制内容。

**主页 > 剪贴板 > 粘贴** 受更改权限限制。

**主页 > 剪贴板 > 选择性粘贴** 受更改权限限制。

**插入 > 文本 > 对象** 在受保护会话期间不可用。受策略保护的文件无法随时插入。

**邮件** 此选项卡上的大部分选项在受保护会话期间不可用。

**审阅 > 校样 > 研究** 受复制权限限制。如果不允许复制则不可用。

**审阅 > 校样 > 辞典** 受复制权限限制。如果不允许复制则不可用。

**审核 > 语言 > 翻译 > 翻译文档** 随复制权限启用。

**审核 > 语言 > 翻译 > 翻译所选文本** 随复制权限启用。

**审核 > 语言 > 翻译 > 翻译屏幕提示** 随复制权限启用。

**审核 > 比较 > 比较** 在受保护会话期间不可用。受策略保护的文件无法随时比较。

**审核 > 保护 > 阻止作者** 在受保护会话期间不可用。

**审核 > 保护 > 限制编辑** 在受保护会话期间不可用。

**视图 > 宏** 复制权限限制了某些宏，除非允许复制，否则这些宏不可用。

**增益集** 在受保护会话期间无法添加或删除。

**在线协作** 在受保护会话期间不可用。

**主文档和子文档** 当您在主文档中打开子文档时，主文档策略会对其进行控制。如果单独打开，则子文档无法打印、复制或修改。

**重新总结** 在受保护会话期间不可用。

**框架（和所有相关命令）** 在受保护会话期间不可用。

**文档面板** 在受保护会话期间不可用。

**开发人员 > 文档面板** 在受保护会话期间不可用。要访问此命令，请选择“文件”>“选项”>“自定义”>“开发人员”选项卡 >“模板”>“文档模板”。

**大纲 > 主文档 > 创建子文档，插入子文档** 在受保护会话期间不可用。

#### Excel 2010 和 Excel 2013 限制 {#excel-2010-and-excel-2013-restrictions}

以下列出的功能在所描述的情况下受限制：

**文件 > 新建 > 从现有内容新建** 可用，但在受保护会话期间，使用此命令创建的文件无法保存。新文件中的内容无法复制到其他文件。

**文件 > 保存，另存为** 受更改权限限制。

**文件 > 另存为 > PDF** 在受保护会话期间不可用。

**文件 > 打印** 受打印权限限制。除非策略允许高分辨率打印，否则不可用。

**文件 > 信息 > 保护文档** 在受保护会话期间不可用。

**文件 > 信息 > 保护工作簿** 在受保护会话期间不可用。

**文件 > 保存和发送** 在受保护会话期间不可用。

**文件 > 选项 > 增益集** 在受保护会话期间无法添加或删除。

**文件 > 工作流** 在受保护会话期间不可用。

***注意&#x200B;**：在Word, Excel, 和 PowerPoint 2010 中启动工作流仅在Office Professional Plus 2010, Office Enterprise 2010、Office Ultimate 2010 和独立 2010 版本中可用。*

**文件 > 服务器 > 文件服务器任务菜单** 在受保护会话期间不可用。

**主页 > 剪贴板 > 复制** 受复制权限限制。如果不允许复制，则无法将所复制的内容粘贴到任何其他文件或 Microsoft® Office 剪贴板。如果用户具有更改权限，则可以在受保护文件中复制内容。

**主页 > 剪贴板 > 粘贴** 受更改权限限制。

**主页 > 剪贴板 > 选择性粘贴** 受更改权限限制。

**主页 > 单元格 > 格式 > 移动或复制工作表** 在受保护会话期间不可用。

**主页 > 单元格 > 插入 > 插入工作表** 在受保护会话期间不可用。

**主页 > 单元格 > 删除 > 删除工作表** 在受保护会话期间不可用。

**主页 > 编辑 > 填充 > 跨工作表** 受更改权限限制。

**插入 > 表 > 表** 受更改权限限制。

**插入 > 表 > 数据透视表** 无法在创建向导中选择受策略保护的文件。

**插入 > 文本 > 对象** 在受保护会话期间不可用。受策略保护的文件无法随时插入。

**插入 > 文本 > 页眉和页脚** 受更改权限限制。对受策略保护的文档不可用。

**数据 > 获取外部数据** 无法导入来自受策略保护文件的数据。

**数据 > 大纲 > 小计** 受更改权限限制。

**数据 > 数据工具 > 数据验证** 受更改权限限制。

**审阅 > 校样 > 研究** 受复制权限限制。

**审阅 > 校样 > 辞典** 受复制权限限制。

**审阅 > 语言 > 翻译** 受复制权限限制。

**审核 > 更改 > 保护工作表** 在受保护会话期间不可用。

**审核 > 更改 > 保护工作簿** 在受保护会话期间不可用。

**审核 > 更改 > 共享工作簿** 在受保护会话期间不可用。

**审核 > 更改 > 保护和共享工作簿** 在受保护会话期间不可用。

**审核 > 更改 > 允许用户编辑范围** 在受保护会话期间不可用。

**审核 > 更改 > 跟踪更改 > 突出显示更改** 对包含动态水印的受策略保护文件不可用。

**视图 > 宏** 受更改权限限制。

**视图 > 保存工作区** 命令不起作用。

**开发人员 > XML > 扩展包** 复制权限限制了某些宏，除非您允许复制，否则它们不可用。

**公式 > 公式审核 > 错误检查** 受更改权限限制。除非允许更改，否则不可用。

**在线协作** 在受保护会话期间不可用。

**保存自动恢复信息** 在受保护会话期间不可用。

***注意&#x200B;**：如果您尝试在未经许可的情况下更改受策略保护的文件中某个单元格，Excel 会错误地警告您使用“取消保护工作表”命令来取消保护。*

#### PowerPoint 2010 和 PowerPoint 2013 限制 {#powerpoint-2010-and-powerpoint-2013-restrictions}

以下列出的功能在所描述的情况下受限制：

**文件 > 新建 > 从现有内容新建** 可用，但在受保护会话期间，使用此命令创建的文件无法保存。新文件中的内容无法复制到其他文件。

**文件 > 保存** 受更改权限限制。

**文件 > 另存为** 所有选项受更改权限限制。

**文件 > 打印** 所有选项受打印权限限制。除非策略允许高分辨率打印，否则不可用。

**文件 > 保存和发送** 在受保护会话期间不可用。

**文件 > 信息 > 保护演示文稿 > 使用密码加密、添加数字签名、标记为最终状态、限制人员权限** 在受保护会话期间不可用。

**文件 > PowerPoint 选项 > 保存自动恢复信息** 在受保护会话期间不可用。

**文件 > 服务器 > 文件服务器任务菜单** 在受保护会话期间不可用。

**主页 > 剪贴板 > 复制** 受复制权限限制。如果不允许复制，则在文档中复制的内容无法粘贴到任何其他文件或者 Office 剪贴板中。如果用户具有更改权限，则可以在受保护文件中复制内容。

**主页 > 剪贴板 > 粘贴** 受更改权限限制。如果不允许复制，则复制的内容无法粘贴到文档中。

**主页 > 剪贴板 > 选择性粘贴** 受更改权限限制。

**主页 > 幻灯片 > 幻灯片（从大纲），重用幻灯片 >** 在受保护会话期间不可用。

**插入 > 文本 > 对象** 在受保护会话期间不可用。受策略保护的文件无法随时插入。

**设计 > 背景 > 背景样式、隐藏背景图形、设置背景格式** 对包含动态水印的受策略保护文件不可用。

**幻灯片放映 > 设置 > 录制幻灯片放映** 受更改权限限制。

**审阅 > 校样 > 辞典** 受复制权限限制。

**审阅 > 语言 > 翻译** 受复制权限限制。

**审核 > 语言 > 翻译 > 翻译屏幕提示** 随复制权限启用。

**视图 > 演示文稿视图 > 幻灯片放映** 受更改权限限制。如果不允许更改，则在修改文件后无法查看幻灯片放映。

**视图 > 宏** 复制权限限制了某些宏，除非允许复制，否则这些宏不可用。

**增益集** 在受保护会话期间无法添加或删除。

**在线协作** 在受保护会话期间不可用。

## 使用第三方身份验证提供程序 {#use-third-party-authentication-providers}

可将第三方身份验证提供程序与 AEM Forms Document Security 一并使用。这些身份验证提供程序帮助您将额外的访问层添加到受保护的文档。AEM Forms Document Security 支持以下扩展身份验证工作流程：

* 使用默认 AEM Forms URL 的扩展身份验证
* 使用自定义 URL 的扩展身份验证
* 在 JEE 服务器的 AEM Forms 上配置了使用第三方身份提供程序的默认扩展身份验证工作流
* 在 JEE 服务器的 AEM Forms 上配置了使用第三方身份提供程序的自定义扩展身份验证工作流
* 为列出 SAML 身份验证使用自定义页面的扩展身份验证

## 术语表 {#glossary}

有关 LiveCycle 和 AEM forms on JEE 的术语，请参阅[第 19 章：术语表](https://helpx.adobe.com/cn/content/dam/help/en/experience-manager/6-5/forms/pdf/using-designer.pdf)。
