---
title: Implantação de aplicativo do Windows 10 usando o Microsoft Intune
titleSuffix: ''
description: Saiba mais sobre os cenários de implantação de aplicativo do Windows 10 disponíveis no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2020
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
ms.openlocfilehash: fa4510b95e1e84d9f94158833dac555daa33c690
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912549"
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

## <a name="supported-windows-10-app-types"></a>Tipos de aplicativo do Windows 10 com suporte

Os tipos de aplicativo específicos são compatíveis com base na versão do Windows 10 que os usuários estão executando. A tabela a seguir fornece o tipo de aplicativo e a compatibilidade com o Windows 10.

| Tipo de aplicativo | Início | Pro | Empresas | Enterprise | Educação | Modo S | Hololense | SurfaceHub | WCOS | Celular |
|----------------|------|-----|----------|------------|-----------|--------|-----------|------------|------|--------|
|  .MSI | Não | Sim | Sim | Sim | Sim | Não | Não | Não | Não | Não |
| .IntuneWin | Não | Sim | Sim | Sim | Sim | 19H2+ | Não | Não | Não | Não |
| Office C2R | Não | Sim | Sim | Sim | Sim | Não | Não | Não | Não | Não |
| LOB: APPX/MSIX | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim |
| MSFB Offline | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim |
| MSFB Online | Sim | Sim | Sim | Sim | Sim | Sim | RS4+ | Sim | Sim | Sim |
| Aplicativos Web | Sim | Sim | Sim | Sim | Sim | Sim | Sim<sup>1 | Sim<sup>1 | Sim | Sim |
| Link da Store | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim |

<sup>1</sup> Iniciar somente a partir do Portal da Empresa.

> [!NOTE]
> Todos os tipos de aplicativos do Windows exigem registro.

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
  - Os aplicativos LOB modernos e os aplicativos da Microsoft Store para Empresas (online e offline) podem ser implantados no contexto do usuário. Os aplicativos dão suporte às intenções Necessário e Disponível.
  - Os aplicativos Win32 criados como Modo de usuário ou Modo Dual podem ser implantados no contexto do usuário e dão suporte às intenções Necessário e Disponível. 
- **Contexto de dispositivo**: quando um aplicativo é implantado no contexto do dispositivo, sua versão gerenciada é instalada diretamente no dispositivo pelo Intune.
  - Somente os aplicativos LOB modernos e os aplicativos licenciados offline da Microsoft Store para Empresas podem ser implantados no contexto do dispositivo. Esses aplicativos dão suporte apenas à intenção Necessário.
  - Os aplicativos Win32 criados como Modo de Máquina ou Modo Dual podem ser implantados no contexto do dispositivo e dão suporte apenas à intenção Necessário.

> [!NOTE]
> Para aplicativos Win32 criados como Modo Dual, o administrador precisará escolher se o aplicativo funcionará como Modo de Usuário ou Modo de Máquina para todas as atribuições associadas a essa instância. O contexto de implantação não pode ser alterado por atribuição.  

Os aplicativos só podem ser instalados no contexto do dispositivo quando compatíveis com o dispositivo e com o tipo de aplicativo do Intune. Você pode instalar os seguintes tipos de aplicativo no contexto do dispositivo e atribuir esses aplicativos a um grupo de dispositivos:

- Aplicativos Win32
- Aplicativos offline licenciados da Microsoft Store para Empresas
- Aplicativos LOB (MSI, APPX e MSIX)
- Office 365 ProPlus

Os aplicativos LOB do Windows (especificamente APPX e MSIX) e os aplicativos Microsoft Store para Empresas (aplicativos offline) que você selecionou para instalar no contexto do dispositivo devem ser atribuídos a um grupo de dispositivos. A instalação falhará se um desses aplicativos for implantado no contexto do usuário. O status e o erro a seguir aparecem no console administrativo:
  - Status: Falha.
  - Erro: Um usuário não pode ser direcionado com uma instalação de contexto do dispositivo.

> [!IMPORTANT]
> Quando usado em combinação com um cenário de provisionamento diferenciado do Autopilot, não há nenhum requisito para aplicativos LOB e aplicativos da Microsoft Store para Empresas implantados no contexto do dispositivo destinado ao grupo de dispositivos. Para saber mais, confira [Implantação diferenciada do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove).

> [!Note]
> Depois de salvar uma atribuição de aplicativo com uma implantação específica, não é possível alterar o contexto dela, exceto em aplicativos modernos. No caso de aplicativos modernos, é possível alterar de contexto do usuário para o contexto do dispositivo. 

Se houver um conflito nas políticas em um único usuário ou dispositivo, as seguintes prioridades serão aplicadas:
- Uma política de contexto de dispositivo tem uma prioridade mais alta do que uma política de contexto de usuário. 
- Uma política de instalação tem uma prioridade mais alta do que uma política de desinstalação.

Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md). Para obter mais informações sobre os tipos de aplicativo no Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md)
- [Como monitorar aplicativos](apps-monitor.md)
