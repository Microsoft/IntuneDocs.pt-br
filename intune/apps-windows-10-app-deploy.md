---
title: Implantação de aplicativo do Windows 10 usando o Microsoft Intune
titlesuffix: ''
description: Saiba mais sobre os cenários de implantação de aplicativo do Windows 10 disponíveis no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0ece7f3d5b7f0d01359a342da5e3dca9b8193a27
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642601"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Implantação de aplicativo do Windows 10 usando o Microsoft Intune 

Atualmente, o Microsoft Intune dá suporte a uma variedade de tipos de aplicativos e cenários de implantação em dispositivos Windows 10. Depois de adicionar um aplicativo ao Intune, você pode atribuí-lo a usuários e dispositivos. As informações a seguir fornecem mais detalhes relacionados aos cenários do Windows 10 compatíveis. Além disso, as informações a seguir fornecem detalhes importantes a serem observados ao implantar aplicativos no Windows. 

Os aplicativos LOB (linha de negócios) e os aplicativos da Microsoft Store para Empresas são os tipos de aplicativo compatíveis com dispositivos Windows 10. As extensões do arquivo para aplicativos do Windows incluem **.msi**, **.appx** e **.appxbundle**.  

> [!Note]
> As atualizações mínimas necessárias do Windows 10 para implantar aplicativos modernos são as seguintes:
> - Para Windows 10 1803, [23 de maio de 2018 – KB4100403 (build do sistema operacional 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Para Windows 10 1709 [21 de junho de 2018 – KB4284822 (build do sistema operacional 16299.522)](https://support.microsoft.com/help/4284822).

## <a name="windows-10-line-of-business-apps"></a>Aplicativos de linha de negócios do Windows 10

Os aplicativos LOB do Windows 10 são autenticados e carregados no console de administração do Intune e podem incluir aplicativos modernos, como aplicativos UWP (da Plataforma Universal do Windows) e Pacotes do Aplicativo do Windows (AppX), além de aplicativos do Win32, como arquivos de pacote simples do Microsoft Installer (MSI). As atualizações de aplicativos LOB precisam ser carregadas e implantadas manualmente todas as vezes pelo administrador. As atualizações implantadas são instaladas automaticamente em dispositivos do usuário final que instalaram o aplicativo sem nenhuma intervenção do usuário. O usuário não tem controle sobre as atualizações. 

## <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para Empresas

Aplicativos da Microsoft Store para Empresas que são aplicativos modernos adquiridos no portal de administração da Microsoft Store para Empresas e, em seguida, sincronizados com o Microsoft Intune para gerenciamento. Os aplicativos podem ser **licenciados online** ou **licenciados offline**. As atualizações dos aplicativos da Microsoft Store para Empresas são gerenciadas diretamente pela Microsoft Store, sem nenhuma ação adicional exigida pelo administrador. O administrador também pode impedir atualizações em aplicativos específicos usando o URI (Uniform Resource Identifier) personalizado. Para obter mais informações, confira [Gerenciamento de aplicativos empresariais – Impedir atualizações automáticas do aplicativo](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). No dispositivo, o usuário final também pode desabilitar atualizações de todos os aplicativos da Microsoft Store para Empresas no dispositivo. 

## <a name="installing-apps-on-windows-10-devices"></a>Instalando aplicativos em dispositivos Windows 10
Dependendo do tipo de aplicativo, o aplicativo pode ser instalado em um dispositivo Windows 10 de uma destas duas maneiras:

- **Contexto de usuário**: quando um aplicativo for implantado no contexto de usuário, o aplicativo gerenciado será instalado para esse usuário no dispositivo quando o usuário entrar no dispositivo. Observe que a instalação do aplicativo não funcionará enquanto o usuário não entrar no dispositivo. 
    - Os aplicativos de linha de negócios modernos e os aplicativos da Microsoft Store para Empresas (online e offline) podem ser implantados no contexto de usuário e darão suporte à intenção Obrigatória e Disponível.
    - Aplicativos do Win32 criados como **Modo de Usuário** ou **Modo Dual** podem ser implantados no contexto do usuário e dar suporte às intenções **Obrigatória** e **Disponível**. 
- **Contexto de dispositivo**: quando um aplicativo for implantado no contexto de dispositivo, o aplicativo gerenciado será instalado diretamente no dispositivo pelo Intune.
    - Somente os aplicativos de linha de negócios modernos e os aplicativos licenciados offline da Microsoft Store para Empresas podem ser implantados no contexto de dispositivo e darão suporte apenas à intenção Obrigatório.
    - Aplicativos do Win32 criados como **Modo do Computador** ou **Modo Dual** podem ser implantados no contexto do usuário e dar suporte apenas à intenção **Obrigatória**.

> [!NOTE]
> Para aplicativos do Win32 criados como **Modo Dual**, você (o administrador) precisará escolher se o aplicativo funcionará como **Modo de Usuário** ou **Modo do Computador** para todas as atribuições associadas a essa instância. O contexto de implantação não pode ser alterado por atribuição.  

Quando um aplicativo é implantado no contexto de dispositivo, a instalação terá êxito apenas quando for direcionada a um dispositivo que dê suporte ao contexto de dispositivo. Além disso, a implantação no contexto de dispositivo dá suporte às seguintes condições:
- Se um aplicativo for implantado no contexto de dispositivo e direcionado a um usuário, a instalação falhará com o seguinte status e o erro será exibido no console de administração:
    - Status: Falha.
    - Erro: um usuário não pode ser direcionado com uma instalação de contexto de Dispositivo.
- Se um aplicativo for implantado no contexto de dispositivo, mas direcionado a um dispositivo que não dê suporte ao contexto de dispositivo, a instalação falhará com o seguinte status e erro no console de administração:
    - Status: Falha.
    - Erro: essa plataforma não dá suporte a instalações de contexto de dispositivo. 

> [!Note]
> Depois que uma atribuição de aplicativo é salva com uma implantação específica, o contexto não pode ser alterado quanto à essa atribuição, exceto em aplicativos modernos. No caso de aplicativos modernos, o contexto pode ser alterado do contexto de usuário para o contexto de dispositivo. 

Se houver um conflito nas políticas em um único usuário/dispositivo, estas serão as prioridades de política que serão usadas para determinar a política final:
- Uma política de contexto de dispositivo tem uma prioridade mais alta do que uma política de contexto de usuário. 
- Uma política de instalação tem uma prioridade mais alta do que uma política de desinstalação.

Para obter mais informações sobre como atribuir aplicativos usando o Microsoft Intune, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md) e [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md). Para obter mais informações sobre os tipos de aplicativo no Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como atribuir aplicativos a grupos, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).
- Para saber mais sobre como monitorar as atribuições de aplicativo, consulte [Como monitorar aplicativos](apps-monitor.md).
