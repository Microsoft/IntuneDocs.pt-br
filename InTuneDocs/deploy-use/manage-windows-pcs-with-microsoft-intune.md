---
title: Gerenciar computadores com software cliente | Microsoft Docs
description: Gerenciar computadores Windows instalando o software cliente do Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d2f3a7233ea7a5127baf5a08be1ccb41f717244
ms.openlocfilehash: 4344251ede6d8cc338d84782d224d87fd78d5bd8


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Gerenciar computadores Windows com o software cliente de computador do Intune
Em vez de [registrar computadores Windows como dispositivos móveis](set-up-windows-device-management-with-microsoft-intune.md), você pode registrar e gerenciar computadores Windows instalando o software cliente do Intune.

O Intune gerencia computadores Windows usando políticas, de modo semelhante ao usado pelos GPOs (Objetos de Política de Grupo) do AD DS (Active Directory Domain Services) do Windows Server. Se você for gerenciar computadores ingressados no domínio do Active Directory com o Intune, [verifique se as políticas do Intune não entram em conflito com os GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) em vigor para sua organização.

Embora o cliente de software do Intune dê suporte a [funcionalidades de gerenciamento que ajudam a proteger computadores](policies-to-protect-windows-pcs-in-microsoft-intune.md) gerenciando atualizações de software, o Firewall do Windows e o Endpoint Protection, computadores gerenciados com o cliente de software do Intune não podem ser afetadas por outras políticas do Intune, incluindo as configurações de política do **Windows** específicas ao gerenciamento de dispositivo móvel.

> [!NOTE]
> É possível gerenciar dispositivos Windows 8.1 ou posterior como computadores, usando o cliente do Intune, ou como dispositivos móveis, usando a funcionalidade MDM (gerenciamento de dispositivo móvel). Não é possível usar os dois métodos juntos. Este tópico se aplica somente ao gerenciamento de dispositivos como computadores com a execução do cliente de software do Intune.

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
|Sistema operacional | Dispositivo Windows executando o Windows Vista ou posterior. Não há suporte para versões Home Edition.|
|Permissões administrativas|A conta que instala o software cliente deve ter permissões de administrador local nesse dispositivo.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.<br /><br />Para exibir a versão do Windows Installer em um PC cliente:<br /><br />  No computador, clique com o botão direito do mouse em **%windir%\System32\msiexec.exe** e clique em **Propriedades**.<br /><br />Você pode baixar a versão mais recente do Windows Installer em [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) no site do Microsoft Developer Network.|
|Remover o software cliente incompatível|Antes de instalar o software cliente do Intune, desinstale qualquer software cliente do Configuration Manager, do Operations Manager, do Operations Management Suite e do Service Manager do computador.|

## <a name="computer-management-with-the-intune-computer-client"></a>Gerenciamento do computador com o cliente do computador Intune
Depois que o software cliente do Intune for instalado, as funcionalidades de gerenciamento incluirão: 

- [Gerenciamento de aplicativo](deploy-apps-in-microsoft-intune.md)

- [Monitoramento em tempo real e Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

- [Gerenciamento de configurações do Firewall do Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventário de hardware e software, controle remoto (por meio de solicitações de assistência remota)

- [Configurações de atualização de software](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Relatórios de configurações de conformidade

Algumas opções de gerenciamento disponíveis para computadores gerenciados como dispositivos móveis não estão disponíveis para computadores gerenciados por cliente de software, incluindo:

-   Apagamento completo (o apagamento seletivo está disponível)

-   Acesso condicional

-   Políticas do Windows diferentes de políticas de **Gerenciamento do computador**

  ![Modelo de políticas para computadores Windows](../media/pc_policy_template.png)

Além das ações de agente cliente do Intune executadas localmente em computadores individuais, você também pode usar o console de administração do Intune para realizar outras [tarefas comuns de gerenciamento de computador](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) em computadores Windows com o cliente instalado para:

-   Exibir informações de inventário de hardware e software sobre os computadores gerenciados

-   Reiniciar remotamente um computador

-   Desativar um computador para desinstalar o software cliente e removê-lo do gerenciamento com o Intune

-   Vincular usuários a computadores gerenciados específicos

-   Responder a solicitações de assistência remota

O agente cliente Intune geralmente é executado silenciosamente em segundo plano sem necessidade de muita interação do usuário nem solução de problemas. No entanto, se você precisar de ajuda na resolução de problemas de gerenciamento do computador, haverá vários [recursos disponíveis para ajudá-lo a resolvê-los](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Dec16_HO3-->


