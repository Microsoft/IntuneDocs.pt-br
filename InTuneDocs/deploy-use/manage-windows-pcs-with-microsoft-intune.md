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
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: 21e83b68bb68384a8916db8d7f779cddde18a8a6


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Gerenciar computadores Windows com o software cliente de computador do Intune
Em vez de [registrar computadores Windows como dispositivos móveis](set-up-windows-device-management-with-microsoft-intune.md), você pode registrar e gerenciar computadores Windows instalando o software cliente do Intune.

O Intune gerencia computadores Windows usando políticas, de modo semelhante ao usado pelos GPOs (Objetos de Política de Grupo) do AD DS (Active Directory Domain Services) do Windows Server. Se você for gerenciar computadores ingressados no domínio do Active Directory com o Intune, [verifique se as políticas do Intune não entram em conflito com os GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) em vigor para sua organização. Você pode ler mais sobre [GPOs](https://technet.microsoft.com/library/hh147307.aspx).

Embora o cliente de software do Intune dê suporte a [funcionalidades de gerenciamento que ajudam a proteger computadores](policies-to-protect-windows-pcs-in-microsoft-intune.md) gerenciando atualizações de software, o Firewall do Windows e o Endpoint Protection, computadores gerenciados com o cliente de software do Intune não podem ser afetadas por outras políticas do Intune, incluindo as configurações de política do **Windows** específicas ao gerenciamento de dispositivo móvel. 

Ao usar o cliente de software do Intune para gerenciar computadores Windows, você pode usar apenas as políticas mostradas na seção **Gerenciamento de Computador**.

  ![Selecione o modelo para a nova política de computador Windows](../media/select-template-for-pc-policy.png)

Para obter descrições detalhadas das políticas que você pode definir, consulte:

- [Usar políticas para ajudar a proteger computadores Windows que executam o software cliente do Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Ajudar a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Além disso, ao implantar aplicativos, você pode usar apenas o Windows Installer (.exe, .msi).

  ![Selecione a plataforma e um local para os arquivos de software cliente do computador](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> É possível gerenciar dispositivos Windows 8.1 ou posterior como computadores, usando o cliente do Intune, ou como dispositivos móveis, usando a funcionalidade MDM (gerenciamento de dispositivo móvel). Você não pode usar ambos os métodos juntos, por isso considere atentamente sua decisão antes de decidir gerenciar computadores usando o cliente de software do Intune. Este tópico se aplica somente ao gerenciamento de dispositivos como computadores com a execução do cliente de software do Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Requisitos para o gerenciamento de cliente de computador do Intune

**Hardware**: veja a seguir os requisitos mínimos de hardware para instalar o cliente do Intune:

|Requisito|Mais informações|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

**Software**: veja a seguir os requisitos de software para a instalação do cliente:

|Requisito|Mais informações|
|---------------|--------------------|
|Sistema operacional | Dispositivo Windows executando o Windows Vista ou posterior. </br></br>**Não há suporte para versões Home Edition.**|
|Permissões administrativas|A conta que instala o software cliente deve ter permissões de administrador local nesse dispositivo.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.<br /><br />Para exibir a versão do Windows Installer em um PC cliente:<br /><br />  No computador, clique com o botão direito do mouse em **%windir%\System32\msiexec.exe** e clique em **Propriedades**.<br /><br />Você pode baixar a versão mais recente do Windows Installer em [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) no site do Microsoft Developer Network.|
|Remover o software cliente incompatível|Antes de instalar o software cliente do Intune, desinstale qualquer software cliente do Configuration Manager, do Operations Manager, do Operations Management Suite e do Service Manager do computador.|

## <a name="computer-management-capabilities-with-the-intune-software-client"></a>Recursos de gerenciamento do computador com o cliente de software do Intune

Depois que o software cliente do Intune for instalado, as funcionalidades de gerenciamento incluirão: 

- [Gerenciamento de aplicativo](deploy-apps-in-microsoft-intune.md)

- [Monitoramento em tempo real e Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

 > [!NOTE]
 > Endpoint Protection é a mesma coisa que Windows Defender. O Endpoint Protection se aplica ao Windows 7 e Windows 8. Para o Windows 10 e posterior, o nome do produto foi alterado para Windows Defender.

- [Gerenciamento de configurações do Firewall do Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventário de hardware e software, controle remoto (por meio de solicitações de assistência remota)

- [Configurações de atualização de software](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Relatórios de configurações de conformidade

No console de administração do Intune, determinadas seções como “Atualizações”, “Proteção” e “Licenças” serão exibidas somente se os dispositivos registrados usarem o cliente de software do Intune.

  ![Itens do console de administração que aparecem somente para clientes de computadores](../media/admin-console-settings-only-for-pc-agent.png)

Você também pode usar o console de administração do Intune para realizar outras [tarefas comuns de gerenciamento de computador](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) em computadores Windows que têm o cliente instalado:

-   Exibir informações de inventário de hardware e software sobre os computadores gerenciados

-   Reiniciar remotamente um computador

-   Desativar um computador para desinstalar o software cliente e removê-lo do gerenciamento com o Intune

-   Vincular usuários a computadores gerenciados específicos

-   Responder a solicitações de assistência remota

## <a name="management-limitations-of-the-intune-software-client"></a>Limitações de gerenciamento de cliente de software do Intune

Algumas opções de gerenciamento, que podem ser usadas para gerenciar computadores como dispositivos móveis, não podem ser usadas para computadores gerenciados com o cliente de software do Intune:

-   Apagamento completo (o apagamento seletivo está disponível)

-   Acesso condicional

## <a name="help-with-troubleshooting"></a>Ajuda com solução de problemas

O agente cliente Intune geralmente é executado silenciosamente em segundo plano sem necessidade de muita interação do usuário nem solução de problemas. Se você precisar solucionar problemas de gerenciamento de computador, verifique os logs. O cliente de software do Intune e seus logs correspondentes são instalados no diretório %Program Files%\Microsoft\OnlineManagement.

Você também pode examinar [Solucionar problemas de instalação de cliente no Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) para ver os problemas que podem ocorrer, bem como resoluções ou soluções alternativas.



<!--HONumber=Feb17_HO2-->


