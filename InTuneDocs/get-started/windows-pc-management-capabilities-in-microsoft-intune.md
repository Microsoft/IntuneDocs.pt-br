---
title: Funcionalidades do cliente de software de computador do Intune | Microsoft Docs
description: Saiba mais sobre os recursos do Intune ao gerenciar computadores Windows com o cliente de software Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Recursos de gerenciamento de computadores Windows quando você usa o cliente de software do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Na maioria dos cenários, você registrará os dispositivos no Microsoft Intune, que fornece um maior conjunto de recursos. No entanto, você também pode gerenciar computadores usando o cliente de software Intune, que fornece os seguintes recursos:

-   **[Gerenciamento de atualização de software](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** – você pode manter os computadores atualizados e decidir quando as atualizações serão aplicadas.

-   **[Política de Firewall do Windows](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** – ajuda a garantir que nenhum computador usado pela sua empresa tenha um Firewall do Windows inativo ou configurado incorretamente.

-   **[Proteção antimalware](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** – o Intune conta com o Endpoint Protection, que ajuda a proteger seus computadores contra malware.

-   **[Assistência remota](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** – o Intune permite que os usuários entrem em contato com a equipe de suporte de TI, que poderá fornecer assistência usando um recurso de área de trabalho remota que está incluído no Intune (requer o software TeamViewer).

-   **[Gerenciamento de licenças de software](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** – controle quantas licenças de software estão disponíveis e quantas licenças disponíveis estão sendo usadas.
-   **[Implantação de aplicativo](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** – implante software nos computadores que você gerencia. Alguns recursos de gerenciamento de aplicativos não estão disponíveis quando você gerencia computadores com o cliente de software.


O Intune dá suporte à instalação do cliente de software em até 7.000 dispositivos Windows.

## <a name="operating-system-requirements"></a>Requisitos de sistema operacional
O Intune pode gerenciar computadores que executam as seguintes versões do Windows (32 e 64 bits):


-   **Windows Vista** - versões Business, Enterprise e Ultimate

-   **Windows 7** - Versões Pro, Enterprise e Ultimate (sem service pack ou com SP1)

-   **Windows 8** - Versões Pro e Enterprise

-   **Windows 8.1** - Versões Pro e Enterprise

- **Windows 10** - Versões Pro, Education e Enterprise


## <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware
Veja a seguir os requisitos mínimos de hardware para instalar o cliente de software Intune:

|Requisito|Detalhes|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

## <a name="further-requirements"></a>Requisitos adicionais
Veja a seguir os requisitos de software para instalar o cliente de software Intune:

|Requisito|Detalhes|
|---------------|--------------------|
|Permissões administrativas|A conta que instalará o software cliente deve ter permissões de administrador local para esse computador.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.|
|Remover o software cliente incompatível|Antes de instalar o software cliente de computador do Intune, você deve desinstalar o seguinte software cliente do computador:<br /><br />- Qualquer versão do Configuration Manager<br />- Qualquer versão do Microsoft SMS (Systems Management Server)|

### <a name="see-also"></a>Consulte também
[Recursos de gerenciamento de dispositivos registrados do Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


