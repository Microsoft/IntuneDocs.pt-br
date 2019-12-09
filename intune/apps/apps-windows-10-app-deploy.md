---
title: Implantação de aplicativo do Windows 10 usando o Microsoft Intune
titleSuffix: ''
description: Saiba mais sobre os cenários de implantação de aplicativo do Windows 10 disponíveis no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9d792bd07ae8d7d712748874d64314dd258c5e8
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563938"
---
# <a name="windows-10-app-deployment-by-using-microsoft-intune"></a>Implantação de aplicativo do Windows 10 usando o Microsoft Intune 

O Microsoft Intune dá suporte a uma variedade de tipos de aplicativos e cenários de implantação em dispositivos Windows 10. Depois de adicionar um aplicativo ao Intune, você pode atribuí-lo a usuários e dispositivos. Este artigo fornece mais detalhes sobre os cenários com suporte do Windows 10 e também abrange os principais detalhes a serem observados ao implantar aplicativos no Windows. 

Os aplicativos LOB (linha de negócios) e os aplicativos da Microsoft Store para Empresas são os tipos de aplicativo compatíveis com dispositivos Windows 10. As extensões do arquivo para aplicativos do Windows incluem .msi, .appx e .appxbundle.  

> [!Note]
> Para implantar aplicativos modernos, você precisa de pelo menos:
> - Para Windows 10 1803, [23 de maio de 2018 – KB4100403 (build do sistema operacional 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Para Windows 10 1709 [21 de junho de 2018 – KB4284822 (build do sistema operacional 16299.522)](https://support.microsoft.com/help/4284822).
>
> Somente o Windows 10 1803 e superior são compatíveis com a instalação de aplicativos quando não há um usuário primário associado.
>
> Não há compatibilidade para a implantação de aplicativos de linha de negócios em dispositivos que executam o Windows 10 Home Edition.

## <a name="windows-10-lob-apps"></a>Aplicativos de linha de negócios do Windows 10

Você pode assinar e carregar aplicativos de linha de negócios do Windows 10 no console de administração do Intune. Eles podem incluir aplicativos modernos, como aplicativos da UWP (Plataforma Universal do Windows) e Pacotes de Aplicativos do Windows (AppX), além de aplicativos Win 32, como arquivos simples de pacote do Microsoft Installer (MSI). O administrador deve carregar e implantar manualmente atualizações de aplicativos de linha de negócios. Essas atualizações são instaladas automaticamente nos dispositivos de usuários que instalaram o aplicativo. Nenhuma intervenção do usuário é necessária, e o usuário não tem controle sobre as atualizações. 

## <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para Empresas

Os aplicativos da Microsoft Store para Empresas são aplicativos modernos adquiridos no portal de administração da Microsoft Store para Empresas. Eles são sincronizados com o Microsoft Intune para gerenciamento. Os aplicativos podem ser licenciados online ou offline. A Microsoft Store gerencia diretamente as atualizações, sem nenhuma ação adicional exigida pelo administrador. Você também pode impedir atualizações em aplicativos específicos usando o URI (Uniform Resource Identifier) personalizado. Para obter mais informações, confira [Gerenciamento de aplicativos empresariais – Impedir atualizações automáticas do aplicativo](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). O usuário final também pode desabilitar as atualizações de todos os aplicativos da Microsoft Store para Empresas no dispositivo. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Categorizar aplicativos da Microsoft Store para Empresas 
Para categorizar aplicativos da Microsoft Store para Empresas: 

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos**. 
3. Selecione os aplicativos da Microsoft Store para Empresas. Em seguida, selecione **Propriedades** > **Informações do Aplicativo** > **Categoria**. 
4. Selecione uma categoria.

## <a name="install-apps-on-windows-10-devices"></a>Instalar aplicativos em dispositivos Windows 10
Dependendo do tipo de aplicativo, é possível instalá-lo em um dispositivo Windows 10 de uma das maneiras a seguir:

- **Contexto de usuário**: quando o aplicativo for implantado no contexto do usuário, sua versão gerenciada será instalada no dispositivo do usuário quando este conectar o dispositivo. Observe que a instalação do aplicativo não funcionará enquanto o usuário não conectar o dispositivo. 
  - Os aplicativos de linha de negócios modernos e os aplicativos da Microsoft Store para Empresas (online e offline) podem ser implantados no contexto do usuário. Os aplicativos dão suporte às intenções Necessário e Disponível.
  - Os aplicativos Win32 criados como Modo de usuário ou Modo Dual podem ser implantados no contexto do usuário e dão suporte às intenções Necessário e Disponível. 
- **Contexto de dispositivo**: quando um aplicativo é implantado no contexto do dispositivo, sua versão gerenciada é instalada diretamente no dispositivo pelo Intune.
  - Somente os aplicativos de linha de negócios modernos e os aplicativos licenciados offline da Microsoft Store para Empresas podem ser implantados no contexto do dispositivo. Esses aplicativos dão suporte apenas à intenção Necessário.
  - Os aplicativos Win32 criados como Modo de Máquina ou Modo Dual podem ser implantados no contexto do dispositivo e dão suporte apenas à intenção Necessário.

> [!NOTE]
> Para aplicativos Win32 criados como Modo Dual, o administrador precisará escolher se o aplicativo funcionará como Modo de Usuário ou Modo de Máquina para todas as atribuições associadas a essa instância. O contexto de implantação não pode ser alterado por atribuição.  

Quando um aplicativo for implantado no contexto de dispositivo, a instalação terá êxito apenas quando for direcionada para um dispositivo que dê suporte ao contexto do dispositivo. Além disso, a implantação no contexto de dispositivo dá suporte às seguintes condições:
- se um aplicativo for implantado no contexto do dispositivo e direcionado para um usuário, a instalação falhará. O status e o erro a seguir aparecem no console administrativo:
  - Status: Falha.
  - Erro: Um usuário não pode ser direcionado com uma instalação de contexto do dispositivo.
- Se um aplicativo for implantado no contexto do dispositivo, mas direcionado para um dispositivo sem suporte a esse contexto, a instalação falhará. O status e o erro a seguir aparecem no console administrativo:
  - Status: Falha.
  - Erro: essa plataforma não dá suporte a instalações de contexto de dispositivo. 

> [!Note]
> Depois de salvar uma atribuição de aplicativo com uma implantação específica, não é possível alterar o contexto dela, exceto em aplicativos modernos. No caso de aplicativos modernos, é possível alterar de contexto do usuário para o contexto do dispositivo. 

Se houver um conflito nas políticas em um único usuário ou dispositivo, as seguintes prioridades serão aplicadas:
- Uma política de contexto de dispositivo tem uma prioridade mais alta do que uma política de contexto de usuário. 
- Uma política de instalação tem uma prioridade mais alta do que uma política de desinstalação.

Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md). Para obter mais informações sobre os tipos de aplicativo no Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md)
- [Como monitorar aplicativos](apps-monitor.md)
