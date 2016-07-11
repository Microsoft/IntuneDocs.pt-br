---
title: "Dicas de solução de problemas gerais | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 6b2d1d5eecb543e45fca5fbb8aa1854c88ec4f9c


---

# Dicas de solução de problemas gerais para o Microsoft Intune
Você pode perceber que, depois de implantar o Microsoft Intune, encontrará problemas com sua configuração ou com clientes. Os recursos abaixo podem ajudá-lo a descobrir qual pode ser a causa do problema para que você possa resolvê-lo.

> [!NOTE]
> Para criar uma solicitação de suporte ou para exibir uma solicitação, [visite o Centro de administração do Office 365](https://portal.office.com/admin/default.aspx). Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).
## Definir o problema

-   Qual é o comportamento?

-   Quem passa por esse comportamento e em quais plataformas e dispositivos?

-   O dispositivo funcionou corretamente anteriormente?

-   Quais alterações você fez no Intune ou na configuração do dispositivo?

-   Considere se outras alterações foram feitas ao ambiente no qual você opera, em vez de alterações de configuração.

-   Com qual frequência esse problema ocorre? É esporádicas ou consistente?

-   O usuário poderia estar enfrentando um problema de autenticação? Se esta for uma possibilidade, verifique se o usuário pode fazer logon em outros serviços que usam o Azure Active Directory. Consulte também se o usuário pode fazer logon de um dispositivo diferente.

-   Você verificou o status do serviço? Você pode monitorar a integridade do serviço Intune no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx). Escolha **Integridade do Serviço** no painel esquerdo.

## Coletar dados disponíveis

-   Logs de dispositivo. Saiba como coletar logs do dispositivo em:
  - [Enviar logs de dados de diagnóstico do Android para o administrador de TI usando um cabo USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Enviar logs de dados de diagnóstico do Android para o administrador de TI usando o email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Enviar erros de registro do Android para o administrador de TI](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Enviar erros de registro do iOS para o administrador de TI](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Dados de console do administrador, por exemplo, para problemas de implementação de política, você deve examinar a política desejada e o status dessa política, conforme descrito em [Use groups to manage users and devices with Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).

## Pesquisar a solução

-   Pesquise uma solução na Web. Por exemplo, se você receber o erro 0x80073CF0, poderá pesquisar por **technet intune 0x80073cf0** na Web e localizar o artigo [Solucionar problemas de implantação de aplicativo no Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md), que oferece sugestões para resolver o problema.

-   Você pode pesquisar uma resposta no [Fórum TechNet do Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Se o problema não for resolvido anteriormente, você deverá postar a pergunta para ver quais são a sugestões que a comunidade pode dar.

-   Você pode abrir uma solicitação de suporte. O Suporte do Intune estará mais capacitado a ajudar você a resolver um problema quando você tiver definido o problema e coletado os dados disponíveis.

    Para criar uma solicitação de suporte [visite o Centro de administração do Office 365](https://portal.office.com/admin/default.aspx). Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

## Recursos da comunidade
Você pode encontrar outras informações úteis nestes recursos da comunidade:

-   O [Guia de Sobrevivência do Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contém links para vários recursos que podem ajudá-lo a configurar, manter e solucionar problemas do Intune.

-   [O blog do Intune](http://blogs.technet.com/b/windowsintune/)

-   [Siga o Intune no Twitter](https://twitter.com/MSIntune)

-   [Os fóruns do Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Próximas etapas
Os tópicos listados abaixo têm ajuda de solução para problemas específicos. Se essas informações não ajudarem, contate o Suporte da Microsoft conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Solucionar problemas de acesso ao recurso da empresa com o Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Solucionar problemas de implantação de aplicativo no Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Solução de problemas de registro de dispositivo no Intune](troubleshoot-device-enrollment-in-intune.md)

[Solução de problemas com políticas no Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Solucionar problemas de instalação do cliente no Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Solucionar problemas de atualização de software no Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jul16_HO1-->


