---
title: Localize o usuário principal de um dispositivo do Microsoft Intune.
titleSuffix: ''
description: Localize o usuário principal (ou Afinidade de Dispositivo de Usuário) de um dispositivo do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 312aee3752525ab2898c6d4e4ea06da685d1cdec
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728358"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Localizar o usuário principal de um dispositivo do Intune

Usuário principal, também conhecido como Afinidade de Dispositivo de Usuário, é uma propriedade de cada dispositivo do Intune. Um dispositivo do Intune pode ter zero ou um usuário principal atribuído a ele. Quando não há nenhum usuário primário atribuído, o dispositivo é referenciado como "Dispositivo Compartilhado".

## <a name="how-to-find-a-devices-primary-user"></a>Como localizar o usuário principal de um dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Escolha **Dispositivos** > escolha um dispositivo.
3. Na página **Visão geral**, escolha **Ver mais** e você verá que o usuário principal listado.

## <a name="what-is-the-primary-user"></a>O que é o usuário principal?
A propriedade de usuário principal é usada para mapear um usuário licenciado do Intune para seus dispositivos nos seguintes casos:
- O aplicativo do Portal da Empresa
- Site do usuário final
- Experiência de profissionais de TI, como a solução de problemas de páginas no portal do Azure. Essas páginas mapeiam contas de usuário em busca de dispositivos usando o usuário principal.    

### <a name="company-portal-app"></a>Aplicativo do Portal da Empresa
O aplicativo de Portal da Empresa espera que a conta do usuário que está conectada ao Portal da Empresa seja o usuário principal deste dispositivo. Se outro usuário tiver sido atribuído como o usuário principal, o Portal da Empresa mostra um aviso:

“Este dispositivo já está atribuído a alguém em sua organização. Entre em contato com o suporte da empresa para saber como se tornar o usuário principal do dispositivo. Você pode continuar a usar o Portal da Empresa, mas a funcionalidade será limitada”.

Se um dispositivo do Intune não tiver usuário primário atribuído, o aplicativo Portal da Empresa o detectará como um dispositivo compartilhado. Dispositivos compartilhados são visualmente identificáveis com um rótulo "compartilhado" aparecendo no bloco do dispositivo. Nesse modo, o Portal da Empresa ainda pode ser usado para solicitar e instalar aplicativos disponíveis. No entanto, ações de autoatendimento (redefinir/renomear/desativar) não estão disponíveis.  

Para aparecer no Portal da Empresa em dispositivos compartilhados, os aplicativos disponíveis devem ser atribuídos a um grupo de usuários. Eles serão instalados no contexto do sistema ou no contexto do usuário, dependendo de como o aplicativo tiver sido configurado pelo administrador de TI. Para saber mais sobre o contexto do aplicativo, confira [Instalando aplicativos em dispositivos com Windows 10](../apps/apps-windows-10-app-deploy.md#installing-apps-on-windows-10-devices). O Portal da Empresa versão 10.3.4651.0 ou posterior é necessário para usar este recurso.


## <a name="who-is-assigned-as-the-primary-user"></a>Quem está atribuído como o usuário principal?
O Intune automaticamente adiciona o usuário principal a dispositivos durante ou logo após o registro. O método de registro determina quando o usuário principal é adicionado a um dispositivo.

| Plataforma | Método de registro | Usuário principal atribuído | O usuário principal está atribuído |
| ---- | ---- | ---- | ---- |
| Windows | Adicionar trabalho ou escola (controlado pelo usuário) | Registrando usuário | Durante o registro |   
| Windows | Entrada de aplicativos modernos (controlada pelo usuário) | Registrando usuário | Durante o registro | 
| Windows | Registrar apenas o MDM (controlado pelo usuário) | Registrando usuário | Durante o registro | 
| Windows | Ingresso no Azure AD (experiência de configuração inicial pelo usuário) | Registrando usuário | Durante o registro | 
| Windows | Ingresso no Azure AD (experiência de configuração inicial pelo usuário do Autopilot) | Registrando usuário | Durante o registro | 
| Windows | Registrar-se apenas no MDM | Registrando usuário | Durante o registro | 
| Windows | AADJ híbrido + GPO de registro automático | Primeiro usuário a entrar no Windows | Quando o primeiro usuário entra no Windows| 
| Windows | Cogerenciamento | Primeiro usuário a entrar no Windows | Quando o primeiro usuário entra no Windows | 
| Windows | Ingresso no Azure AD (token de registro em massa) | Não | Não Aplicável | 
| Windows | Ingresso do Azure AD (modo de autoimplantação do Autopilot) | Não | Não Aplicável | 
| Plataforma cruzada | Registro controlado pelo usuário com o aplicativo Portal da Empresa | Registrando usuário | Durante o registro |
| Plataforma cruzada | DEM (Gerenciador de registro de dispositivos) | Registrando usuário do DEM | Durante o registro |
| iOS, macOS | Registro de Dispositivo Automatizado da Apple (DEP com afinidade do usuário | Registrando usuário | Durante o registro |
| iOS, macOS | Registro de Dispositivo Automatizado da Apple (DEP sem afinidade do usuário) | Não | Não Aplicável |
| Android | Dispositivos dedicados de propriedade corporativa do Android | Não | Não Aplicável |

## <a name="primary-user-and-azure-ad-device-owner"></a>Usuário principal e proprietário do dispositivo do Azure AD
Em alguns casos, o usuário principal do Intune pode ser diferente da propriedade **Proprietário** do dispositivo do Azure AD (visível em **Dispositivos** > **Dispositivos do Azure AD**). O proprietário do dispositivo do Azure AD é adicionado durante o registro do dispositivo no Azure Active Directory.

## <a name="next-steps"></a>Próximas etapas
[Gerencie seus dispositivos do Intune.](device-management.md)
