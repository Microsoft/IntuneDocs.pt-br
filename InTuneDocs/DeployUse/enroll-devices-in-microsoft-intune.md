---
# required metadata

title: Registrar dispositivos | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos para gerenciamento no Intune
O MDM (Gerenciamento de Dispositivo Móvel) do Microsoft Intune usa o registro para trazer dispositivos para o gerenciamento e permitir acesso aos recursos. A maneira como você registra dispositivos depende do tipo de dispositivo, da propriedade e do nível de gerenciamento necessário. Cenários BYOD (Traga seu próprio dispositivo) e COD (Dispositivo de Propriedade da Empresa) exigem um processo de registro. Organizações que usam o Exchange ActiveSync, hospedado na nuvem ou local, podem habilitar gerenciamento mais leve sem requisitos de registro. Computadores Windows também podem ser gerenciados usando o software cliente Intune.

###  Plataformas de dispositivos com suporte

O Intune pode gerenciar as seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Habilitar registro de dispositivo  
 O registro permite que os usuários acessem os recursos da empresa em seus dispositivos pessoais e permite que o administrador verifique se esses dispositivos estão em conformidade com as políticas que protegem os recursos da empresa. Essa é a melhor maneira de habilitar cenários "traga seu próprio dispositivo" com o Intune. O administrador deve habilitar o registro no console do Intune, que pode exigir a criação de uma relação de confiança com o dispositivo e atribuição de licenças aos usuários. O dispositivo é então registrado, geralmente quando os usuários inserem suas credenciais corporativas ou de estudante. Em seguida, o dispositivo recebe a política do Intune e obtém acesso aos recursos.

[Preparar-se para registrar dispositivos no Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrar dispositivos de propriedade corporativa
COD (Dispositivos de Propriedade Corporativa) podem ser gerenciados com o console do Intune. Os dispositivos iOS podem ser registrados diretamente por meio de ferramentas fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

[Registrar dispositivos de propriedade corporativa](manage-corporate-owned-devices.md)

## Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Dispositivos móveis que não estão registrados, mas que conectam ao EAS (Exchange ActiveSync) podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local.



[Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Gerenciar PCs Windows com o Intune  
Você também pode usar o Microsoft Intune para gerenciar computadores Windows usando o software cliente do computador Windows com Intune. Computadores gerenciados com o cliente Intune podem:

 - Informar inventários de hardware e software
 - Instalar aplicativos da área de trabalho (por exemplo arquivos .exe e .msi)
 - Configurações de firewall

Computadores gerenciados com o software cliente Intune não podem ser apagados nem desativados seletivamente e não podem tirar proveito de muitos recursos de gerenciamento do Intune como acesso condicional, configurações de VPN e Wi-Fi ou implantação de certificados e configurações de email.

[Gerenciar PCs Windows com o Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


