---
title: AEM Document Security Extension for Microsoft&reg; Office 简介
description: 使用Document Security Extension for Microsoft&amp；reg； Office，您可以将预定义的机密性设置应用于Microsoft&amp；reg； Office文件。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 68%

---

# AEM Document Security Extension for Microsoft® Office 简介{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office 确保只有您授权的人可以使用包含您知识产权的 Word、Excel 和 PowerPoint 文件。可使用 Document Security Extension for Microsoft® Office 将预定义的机密性设置应用于文件。

Document Security Extension for Microsoft® Office增强了Adobe Experience Manager Forms的LiveCycleRights Management和Document Security。 它可保护Office文件，并使授权用户能够根据已建立的机密性设置访问受策略保护的文件。

## Document Security 如何保护知识产权 {#how-document-security-protects-intellectual-property}

Document Security 确保只有您授权的人可以使用包含您知识产权的文件。使用 Document Security，您可以使用机密性策略保护文件。*策略*&#x200B;是包含机密性设置和授权用户列表的信息的集合。您在策略中指定的设置确定收件人可以如何使用您应用了策略的文件。例如，您可以指定收件人是否可以打印或复制文本或者保存更改。

Document Security 管理员和用户创建策略。管理员创建对所有授权用户可用的组织策略。管理员或策略集协调员也可以创建称为&#x200B;*策略集*&#x200B;的策略组，策略组可供一部分用户使用。用户可以创建自己的策略，这些策略只有自己能使用。管理员、策略集协调员和用户使用Document Security网页创建策略。

虽然策略存储在Document Security中，但您可以通过Word、Excel或PowerPoint将它们应用到文件。 将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发受策略保护的文件时，只有授权的收件人才能访问其内容。

使用受策略保护文件让您可以持续控制文件，即使在您分发文件之后。您可以审核事件以跟踪收件人何时以及如何使用您的文件。 您还可以更改策略，阻止用户继续访问文件，以及更改附加到文件的策略。

## 策略的工作方式 {#how-policies-work}

策略包含有关授权用户的信息以及应用到知识产权的机密性设置。Document Security可识别链接的LDAP或Active Directory列表中包含的用户。 用户也可以是受邀注册 Document Security 的人或者管理员为其创建了帐户的人。

策略中的机密性设置确定收件人可以如何使用受策略保护的文件。例如，策略指定收件人是否可以打印文件、将内容复制到其他文件或者将更改保存到受保护文件。策略还可以为不同用户指定不同的机密性设置。

将策略应用到文件时，该文件中包含的信息受在策略中指定的机密性设置保护。当您分发文件时，Document Security 对尝试打开文件的收件人进行身份验证，并根据在策略中指定的权限授权访问权限。

将某个策略应用于文件后，可随时更改该策略的机密性设置。您可以在用户收到文件后添加或删除授权用户或更改用户权限。 应用到文件的策略可以更改。 并且，对文件的访问权限可以撤销，这样拥有该文件副本的任何人都无法再打开它。

如果策略允许离线访问，收件人还可以在策略指定的时段内离线使用受策略保护的文件（无需活动的 Internet 或网络连接）。

## 受策略保护的文件的工作方式 {#how-policy-protected-files-work}

对于打开和使用受策略保护的Word、Excel和PowerPoint文件的用户，策略必须包括用户作为收件人。 或者，它必须允许匿名访问。 并且，用户必须安装Document Security Extension for Microsoft® Office。 要为没有Document Security Extension for Microsoft® Office的用户提供受策略保护的文件，您可以为他们提供软件的副本。 或者，您可以告诉他们如何从您的网站下载它。 如果您没有安装程序，可从[下载页面](https://experienceleague.adobe.com/en/docs/experience-manager-document-security/using/download-installer)下载它。

当用户尝试打开受策略保护的文件时，Document Security Extension for Microsoft® Office连接到Document Security以对用户进行身份验证。 如果配置 Document Security 审核文件使用情况，则用户可以看到通知，指示要审核文件使用情况。Document Security 确定将哪些文件权限授予用户，然后用户可以按照以下条件，根据策略设置使用文件：

* 在策略指定的有效期内。
* 在管理员或者应用策略的人撤销对文件的访问权限或者更改策略之前。

  如果应用策略的人更改策略或撤销对文件的访问权限，则即使该用户已拥有该文件，仍将更改或删除该用户对该文件的权限。如果撤销了文件本身，则可能为用户提供一个 URL 以获取更新的副本。

  如果策略允许离线访问，则用户可以在指定的离线租赁期内打开受策略保护的文件，而无需通过Internet或网络连接。 离线租赁期结束时，用户必须上线并与 Document Security 同步，它会启动新的租赁期。

  如果策略允许离线访问，则用户可以在指定的离线租赁期内打开受策略保护的文件，而无需通过Internet或网络连接。 与原始文件一样，尝试打开新文件之类的事件也将被审核并记录。

## 使用 Document Security 保护文件 {#using-document-security-to-protect-your-files}

可使用策略在多种情况下保护文件。

例如，一家制造商正在从为新产品提供零部件的供应商接受投标。该制造商必须为投标人提供专有信息以最终敲定其提交的标书。制造商使用 Document Security 保护文件，其策略允许投标人打开文件和查看信息。但是，阻止投标人更改、打印或复制文件，并阻止任何没有权限的人打开文件。

接受竞价后，制造商将更新策略以授予中标人权限以在本地打印、复制和保存更改。 制造商还会删除未中标的人，撤销他们打开文件的权限。

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
   <td><p><a href="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">管理员帮助</a> 或者，在 Document Security 管理页面上，单击页面右上角的“帮助”链接。</p> </td>
  </tr>
  <tr>
   <td><p>有关此产品版本的修补程序更新、技术说明和附加信息</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloud 技术支持</a></p> </td>
  </tr>
 </tbody>
</table>
