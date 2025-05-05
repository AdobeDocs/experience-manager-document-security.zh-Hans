---
title: AEM Document Security Extension for Microsoft&reg; Office 简介
description: 可使用 Document Security Extension for Microsoft&reg; Office 将预定义的机密性设置应用于 Microsoft&reg; Office 文件。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: ht
source-wordcount: '1248'
ht-degree: 100%

---

# AEM Document Security Extension for Microsoft® Office 简介{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office 确保只有您授权的人可以使用包含您知识产权的 Word、Excel 和 PowerPoint 文件。可使用 Document Security Extension for Microsoft® Office 将预定义的机密性设置应用于文件。

Microsoft® Office 的文档安全扩展增强了 LiveCycle 权限管理和 Adobe Experience Manager Forms 的文档安全性。它保护Office 文件并允许授权用户根据既定的机密性设置访问受策略保护的文件。

## Document Security 如何保护知识产权 {#how-document-security-protects-intellectual-property}

Document Security 确保只有您授权的人可以使用包含您知识产权的文件。使用 Document Security，您可以使用机密性策略保护文件。*策略*&#x200B;是包含机密性设置和授权用户列表的信息的集合。您在策略中指定的设置确定收件人可以如何使用您应用了策略的文件。例如，您可以指定收件人是否可以打印或复制文本或者保存更改。

Document Security 管理员和用户创建策略。管理员创建对所有授权用户可用的组织策略。管理员或策略集协调员也可以创建称为&#x200B;*策略集*&#x200B;的策略组，策略组可供一部分用户使用。用户可以创建自己的策略，这些策略只有自己能使用。管理员、策略集协调员和用户使用 Document Security 以创建策略。

虽然策略存储在 Document Security 中，您可通过 Word、Excel 或 PowerPoint 将它们应用到文件。将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发受策略保护的文件时，只有授权的接收者才能访问其内容。

使用受策略保护文件让您可以持续控制文件，即使在您分发文件之后。您可以审核事件来追踪收件人何时以及如何使用您的文件。您还可以对策略进行更改，阻止用户继续访问文件，以及更改附加到文件的策略。

## 策略的工作方式 {#how-policies-work}

策略包含有关授权用户的信息以及应用到知识产权的机密性设置。文档安全可识别链接 LDAP 或 Active Directory 列表中包含的用户。用户也可以是受邀注册 Document Security 的人或者管理员为其创建了帐户的人。

策略中的机密性设置确定收件人可以如何使用受策略保护的文件。例如，策略指定收件人是否可以打印文件、将内容复制到其他文件或者将更改保存到受保护文件。策略还可以为不同用户指定不同的机密性设置。

将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发文件时，Document Security 对尝试打开文件的收件人进行身份验证，并根据在策略中指定的权限授权访问权限。

将某个策略应用于文件后，可随时更改该策略的机密性设置。这样做使您可添加或删除授权用户，或在用户收到文件后更改用户的权限。可以更改应用于文件的策略。并且可以撤销对该文件的访问权限，以便任何拥有该文件副本的人都无法再打开它。

如果策略允许离线访问，收件人还可以在策略指定的时段内离线使用受策略保护的文件（无需活动的 Internet 或网络连接）。

## 受策略保护的文件的工作方式 {#how-policy-protected-files-work}

为了让用户打开和使用受策略保护的 Word, Excel, 和 PowerPoint 文件，该策略必须将用户作为收件人。或者，它必须允许匿名访问。并且，用户必须安装Microsoft® Office 的文档安全扩展。要将受策略保护的文件提供给没有 Microsoft® Office，文档安全扩展的人，您可以向他们提供该软件的副本。或者，您可以告诉他们如何从您的网站下载它。如果您没有安装程序，可从[下载页面](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-document-security/using/download-installer)下载它。

当用户尝试打开受策略保护的文件时，Document Security Extension for Microsoft® Office 连接到 Document Security 以验证该用户的身份。如果配置 Document Security 审核文件使用情况，则用户可以看到通知，指示要审核文件使用情况。Document Security 确定将哪些文件权限授予用户，然后用户可以按照以下条件，根据策略设置使用文件：

* 在策略指定的有效期内。
* 在管理员或者应用策略的人撤销对文件的访问权限或者更改策略之前。

  如果应用策略的人更改策略或撤销对文件的访问权限，则即使该用户已拥有该文件，仍将更改或删除该用户对该文件的权限。如果撤销了文件本身，则可能为用户提供一个 URL 以获取更新的副本。

  如果策略允许离线访问，则用户可以在指定的离线租用期内无需 Internet 或网络连接即可打开受策略保护的文件。离线租赁期结束时，用户必须上线并与 Document Security 同步，它会启动新的租赁期。

  如果策略允许离线访问，则用户可以在指定的离线租用期内无需 Internet 或网络连接即可打开受策略保护的文件。与原始文件一样，尝试打开新文件之类的事件也将被审核并记录。

## 使用 Document Security 保护文件 {#using-document-security-to-protect-your-files}

可使用策略在多种情况下保护文件。

例如，一家制造商正在从为新产品提供零部件的供应商接受投标。该制造商必须为投标人提供专有信息以最终敲定其提交的标书。制造商使用 Document Security 保护文件，其策略允许投标人打开文件和查看信息。但是，阻止投标人更改、打印或复制文件，并阻止任何没有权限的人打开文件。

接受投标后，制造商会更新政策，授予中标者在本地打印、复制和保存更改的权限。制造商还会删除未中标的竞标者，撤销他们打开文件的权限。

在与中标人一起工作时，该制造商的工程师更改了文件中的一些设计规格。为了发布新的规格，制造商撤销对一些文件的访问权限并发布新的版本。当中标人的工程师尝试打开文件时，他们会看到消息，说明对文件的访问权限已撤销。该消息包含可用于下载文件新版本的 URL。

## 附加信息 {#additional-information}

此表中的资源可帮助您详细了解 AEM Document Security：

<table >
 <tbody>
  <tr>
   <th><p>有关信息</p> </th>
   <th><p>请参阅</p> </th>
  </tr>
  <tr>
   <td><p>AEM forms 管理员帮助</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">管理员帮助</a> 或者，在 Document Security 管理页面上，单击页面右上角的“帮助”链接。</p> </td>
  </tr>
  <tr>
   <td><p>有关此产品版本的修补程序更新、技术说明和附加信息</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/zh-hans?support-solution=General&amp;support-tab=home#support">Experience Cloud 技术支持</a></p> </td>
  </tr>
 </tbody>
</table>
