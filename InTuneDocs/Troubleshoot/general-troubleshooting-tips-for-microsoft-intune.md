---
title: "Dicas de solução de problemas gerais | Microsoft Docs"
description: Recursos gerais para ajudar a resolver problemas com o Intune.
keywords: 
author: staciebarker
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: ef6c482a45a7c759cec1062b129d2644562d0da2


---

# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Dicas de solução de problemas gerais para o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Após implantar o Microsoft Intune, você poderá ter problemas com a configuração ou com os dispositivos cliente. Use os seguintes recursos para descobrir o que está causando o problema e resolvê-lo.

> [!NOTE]
> Para criar uma solicitação de suporte ou para exibir uma solicitação, [visite o Centro de administração do Office 365](https://portal.office.com/admin/default.aspx). Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

## <a name="define-the-problem"></a>Definir o problema

-   Qual é o comportamento?

-   Quem passa por esse comportamento e em quais plataformas e dispositivos?

-   O dispositivo funcionou corretamente anteriormente?

-   Quais alterações você fez no Intune ou na configuração do dispositivo?

-   Outras alterações foram feitas ao ambiente no qual você opera, em vez de alterações de configuração?

-   Com qual frequência esse problema ocorre? É esporádicas ou consistente?

-   O usuário poderia estar enfrentando um problema de autenticação? Se essa for uma possibilidade, verifique se o usuário pode entrar em outros serviços que usam o Azure Active Directory. Verifique também se o usuário pode entrar em um dispositivo diferente.

-   Você verificou o status do serviço? Você pode monitorar a integridade do serviço Intune no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx). Escolha **Integridade do Serviço** no painel esquerdo.

## <a name="collect-available-data"></a>Coletar dados disponíveis

-   Os recursos a seguir podem ajudá-lo a aprender a coletar logs de dispositivo:
  - [Enviar logs de dados de diagnóstico do Android para o administrador de TI usando um cabo USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Enviar logs de dados de diagnóstico do Android para o administrador de TI usando o email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Enviar erros de registro do Android para o administrador de TI](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Enviar erros de registro do iOS para o administrador de TI](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Com os dados de console de administração (por exemplo, para problemas de implementação de política), examine a política desejada e o status dessa política, conforme descrito em [Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="research-the-solution"></a>Pesquisar a solução

-   Pesquise uma solução na Web. Por exemplo, se você receber o erro 0x80073CF0, pesquise por **technet intune 0x80073cf0** na Web e localize o artigo [Solucionar problemas de implantação de aplicativo no Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md). Esse artigo oferece sugestões para resolver o problema.

-   Pesquise uma resposta no [Fórum TechNet do Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Se o problema não tiver sido resolvido anteriormente, poste a pergunta para ver quais sugestões a comunidade pode dar.

-   Abrir uma solicitação de suporte. O Suporte do Intune estará mais capacitado para ajudá-lo a resolver um problema quando você o tiver definido e coletado os dados disponíveis.

    Para criar uma solicitação de suporte [visite o centro de administração do Office 365](https://portal.office.com/admin/default.aspx). Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

## <a name="find-community-resources"></a>Encontre os recursos da comunidade
Você pode encontrar outras informações úteis nestes recursos da comunidade:

-   O [Guia de Sobrevivência do Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contém links para vários recursos que podem ajudá-lo a configurar, manter e solucionar problemas do Intune.

-   [O blog do Intune](http://blogs.technet.com/b/windowsintune/)

-   [Siga o Intune no Twitter](https://twitter.com/MSIntune)

-   [Os fóruns do Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Próximas etapas
Os tópicos listados abaixo contêm soluções de problemas específicos. Se essas informações não ajudarem, contate o Suporte da Microsoft conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

[Solucionar problemas do Endpoint Protection no Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Solucionar problemas de acesso ao recurso da empresa com o Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Solucionar problemas de implantação de aplicativo no Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Solucionar problemas de registro de dispositivo no Intune](troubleshoot-device-enrollment-in-intune.md)

[Solucionar problemas com políticas no Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Solucionar problemas de instalação do cliente no Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Solucionar problemas de atualização de software no Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


