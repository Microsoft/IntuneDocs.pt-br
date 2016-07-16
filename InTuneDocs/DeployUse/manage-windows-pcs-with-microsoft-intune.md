---
title: Gerenciar computadores Windows com o Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0335b80afa8e330263baad054f0e902f019f75bb
ms.openlocfilehash: 92f4ddde3336fd4cf07c701596f5ebe4c0aeb49f


---

# Gerenciar PCs com Windows com o Microsoft Intune
Além de registrar dispositivos, você também pode usar o Intune para gerenciar computadores Windows que executam sistemas operacionais com suporte usando o software cliente do computador do Windows Intune. Os requisitos de hardware e software para executar o cliente do computador são mínimos. Basicamente, há suporte para qualquer sistema capaz de executar o Windows 7 ou posterior.  O software cliente também pode ser facilmente instalado em computadores que ingressaram no domínio (em qualquer domínio) ou computadores que não ingressaram no domínio.

O Intune gerencia computadores Windows usando as políticas de modo semelhante ao usado pelos GPOs (objetos de política de grupo) do AD DS (Serviços de Domínio do Active Directory) do Windows Server. Se você estiver gerenciando computadores ingressados em domínio do Active Directory com o Intune, [certifique-se de que as políticas do Intune não entrem em conflito com GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) em vigor para a sua organização.

> [!NOTE]
> O Microsoft Intune, como um serviço independente, oferece estes recursos para o gerenciamento de computadores. Os dispositivos que executam o Windows 8.1 podem ser gerenciados usando o cliente Intune ou podem ser registrados como dispositivos móveis. As informações a seguir se aplicam a computadores que executam o cliente Intune.

## Requisitos para o gerenciamento de computadores no Intune

**Hardware**: veja a seguir os requisitos mínimos de hardware para instalar o cliente do Intune:

|Requisito|Mais informações|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

**Software**: veja a seguir os requisitos de software para a instalação do cliente:

|Requisito|Mais informações|
|---------------|--------------------|
|Permissões administrativas|A conta que instalará o software cliente deve ter permissões de administrador local para esse PC.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.<br /><br />Para exibir a versão do Windows Installer em um PC cliente:<br /><br />-   No PC, clique com o botão direito do mouse em **%windir%\System32\msiexec.exe** e, em seguida, clique em **Propriedades**.<br /><br />Você pode baixar a versão mais recente do Windows Installer em [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) no site do Microsoft Developer Network.|
|Remover o software cliente incompatível|Antes de instalar o software do cliente do Intune, você deve desinstalar qualquer software cliente do Configuration Manager ou System Management Server do computador.|

## Instalar o cliente de computador Intune
A primeira etapa no gerenciamento de computadores Windows com o Intune é instalar o cliente. O software cliente pode ser instalado quando um computador é registrado no gerenciamento pelo serviço do Intune de uma das seguintes maneiras:

-   Você pode [implantar manualmente o software cliente Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Nesse tipo de implantação, um administrador baixa o software cliente Intune e instala-o manualmente em cada PC.

    Para baixar o software cliente Intune, abra o console de administração do Intune e, na área de Download de Software Cliente, baixe o pacote de software do cliente. Depois que o software cliente está instalado, o Intune instala automaticamente o software adicional conforme necessário para gerenciar o computador.

-   Você pode usar os mesmos arquivos de download para instalar manualmente o cliente Intune para [implantar o cliente em computadores ingressados em domínio usando GPOs do Active Directory](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy).

-   [Os usuários finais podem registrar cada um dos seus computadores automaticamente](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers) por meio do Portal de empresa do Intune. Cada computador registrado é automaticamente vinculado à conta de usuário usada para instalar o software cliente do Intune.

-   Por fim, você também pode implantar o software cliente Intune em computadores como parte de uma [implantação de sistema operacional](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image).

## Gerenciamento do computador com o cliente do computador Intune
Depois que o cliente do Intune estiver instalado, o software cliente permite vários recursos de gerenciamento de computador, incluindo: [gerenciamento de aplicativos](deploy-apps-in-microsoft-intune.md), Endpoint Protection, inventário de hardware e software, controle remoto (por meio de solicitações de assistência remota), atualizações de software e relatórios de configurações de conformidade.

Várias tarefas de gerenciamento de computador habilitadas pelo cliente de computador são gerenciadas usando políticas do Intune, como:

-   Definir as [configurações do Firewall do Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) nos computadores gerenciados.

-   Definir as [configurações de atualização de software](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) para os computadores gerenciados procurarem, e baixarem, as atualizações de software necessárias.

-   Ajudando a proteger computadores gerenciados contra possíveis ameaças e softwares mal-intencionados através de gerenciamento de [monitoramento em tempo real e Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

Além das ações de agente cliente do Intune executadas localmente em computadores individuais, você também pode usar o console de administração do Intune para realizar outras [tarefas comuns de gerenciamento de computador](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) em computadores Windows com o cliente instalado para:

-   Exibir informações de inventário de hardware e software sobre os computadores gerenciados

-   Reiniciar remotamente um computador

-   Desativar um computador para desinstalar o software cliente e removê-lo do gerenciamento com o Intune

-   Vincular usuários a computadores gerenciados específicos

-   Responder a solicitações de assistência remota

O agente cliente Intune geralmente é executado silenciosamente em segundo plano sem necessidade de muita interação do usuário nem solução de problemas. No entanto, se você precisar de ajuda na resolução de problemas de gerenciamento do computador, haverá vários [recursos disponíveis para ajudá-lo a resolvê-los](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Jun16_HO4-->


