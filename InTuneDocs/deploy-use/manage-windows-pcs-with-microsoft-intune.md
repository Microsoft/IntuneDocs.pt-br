---
title: Gerenciar computadores com software cliente | Microsoft Docs
description: Gerenciar computadores Windows instalando o software cliente do Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Gerenciar computadores Windows com o software cliente de computador do Intune
[Registrar PCs do Windows como dispositivos móveis](set-up-windows-device-management-with-microsoft-intune.md) é o método preferencial de registro de PCs com Windows no Intune, mas você também pode optar por registrar e gerenciar PCs do Windows instalando o software cliente do Intune, conforme descrito neste tópico.

O Intune gerencia computadores Windows usando políticas, de modo semelhante ao usado pelos GPOs (Objetos de Política de Grupo) do AD DS (Active Directory Domain Services) do Windows Server. Se você for gerenciar computadores ingressados no domínio do Active Directory com o Intune, [verifique se as políticas do Intune não entram em conflito com os GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) em vigor para sua organização. Você pode ler mais sobre [GPOs](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Políticas e implantações de aplicativo do software cliente do Intune

Embora o software cliente do Intune dê suporte a [funcionalidades de gerenciamento que ajudam a proteger computadores](policies-to-protect-windows-pcs-in-microsoft-intune.md) gerenciando atualizações de software, o Firewall do Windows e o Endpoint Protection, computadores gerenciados com o software cliente do Intune não podem ser afetados por outras políticas do Intune, incluindo as configurações de política do **Windows** específicas ao gerenciamento de dispositivo móvel. 

Ao usar o software cliente do Intune para gerenciar computadores Windows, você pode usar apenas as políticas mostradas na seção **Gerenciamento de Computador**.

  ![Selecione o modelo para a nova política de computador Windows](../media/select-template-for-pc-policy.png)

Para obter descrições detalhadas das políticas que você pode definir, consulte:

- [Usar políticas para ajudar a proteger computadores Windows que executam o software cliente do Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Ajudar a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Além disso, ao implantar aplicativos, você pode usar apenas o Windows Installer (.exe, .msi).

  ![Selecione a plataforma e um local para os arquivos de software cliente do computador](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> É possível gerenciar dispositivos Windows 8.1 ou posterior como computadores, usando o software cliente do Intune ou como dispositivos móveis, usando a funcionalidade de gerenciamento de dispositivo móvel (MDM). Você não pode usar ambos os métodos juntos, por isso, pense com cuidado antes de decidir gerenciar computadores usando o software cliente do Intune. Este tópico se aplica somente ao gerenciamento de dispositivos como PCs executando o software cliente do Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Requisitos para o gerenciamento de cliente de computador do Intune

**Hardware**: veja a seguir os requisitos mínimos de hardware para instalar o software cliente do Intune:

|Requisito|Mais informações|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

**Software**: veja a seguir os requisitos de software para a instalação do software cliente:

|Requisito|Mais informações|
|---------------|--------------------|
|Sistema operacional | Dispositivo Windows executando o Windows Vista ou posterior. </br></br>**Não há suporte para versões Home Edition.**|
|Permissões administrativas|A conta que instala o software cliente deve ter permissões de administrador local nesse dispositivo.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.<br /><br />Para exibir a versão do Windows Installer em um PC cliente:<br /><br />  No computador, clique com o botão direito do mouse em **%windir%\System32\msiexec.exe** e clique em **Propriedades**.<br /><br />Você pode baixar a versão mais recente do Windows Installer em [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) no site do Microsoft Developer Network.|
|Remover o software cliente incompatível|Antes de instalar o software cliente do Intune, desinstale qualquer software cliente do Configuration Manager, do Operations Manager, do Operations Management Suite e do Service Manager do computador.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Recursos de gerenciamento do computador com o software cliente do Intune

Depois que o software cliente do Intune for instalado, as funcionalidades de gerenciamento incluirão: 

- [Gerenciamento de aplicativo](deploy-apps-in-microsoft-intune.md)

- [Monitoramento em tempo real e Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – Endpoint Protection é o mesmo que o Windows Defender. O Endpoint Protection se aplica ao Windows 7 e Windows 8. Para o Windows 10 e posterior, o nome do produto foi alterado para Windows Defender.

- [Gerenciamento de configurações do Firewall do Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventário de hardware e software, controle remoto (por meio de solicitações de assistência remota)

- [Configurações de atualização de software](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Relatórios de configurações de conformidade

No console de administração do Intune, determinadas seções, como “Atualizações”, “Proteção” e “Licenças”, serão exibidas somente se os dispositivos registrados usarem o software cliente do Intune.

  ![Itens do console de administração que aparecem somente para clientes de computadores](../media/admin-console-settings-only-for-pc-agent.png)

Você também pode usar o console de administração do Intune para realizar outras tarefas comuns de gerenciamento de computador em computadores Windows que têm o cliente instalado:

-   Exibir informações de inventário de hardware e software sobre os computadores gerenciados
-   Reiniciar remotamente um computador
-   Desativar um computador para desinstalar o software cliente e removê-lo do gerenciamento com o Intune
-   Vincular usuários a computadores gerenciados específicos
-   Responder a solicitações de assistência remota

Para obter mais informações sobre as tarefas acima, consulte [tarefas comuns de gerenciamento do computador](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Limitações de gerenciamento do software cliente do Intune

Algumas opções de gerenciamento, que podem ser usadas para gerenciar computadores como dispositivos móveis, não podem ser usadas para computadores gerenciados com o software cliente do Intune:

-   Apagamento completo (o apagamento seletivo está disponível)

-   Acesso condicional

## <a name="help-with-troubleshooting"></a>Ajuda com solução de problemas

O software cliente do Intune geralmente é executado silenciosamente, em segundo plano, sem necessidade de muita interação do usuário ou solução de problemas. Se você precisar solucionar problemas de gerenciamento de computador, verifique os logs. O software cliente do Intune e seus logs correspondentes são instalados no diretório %Program Files%\Microsoft\OnlineManagement.

Você também pode examinar [Solucionar problemas de instalação de cliente no Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) para ver os problemas que podem ocorrer, bem como resoluções ou soluções alternativas.

