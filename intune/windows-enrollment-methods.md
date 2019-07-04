---
title: Métodos de registro do Intune para dispositivos Windows
titleSuffix: Microsoft Intune
description: Conheça as diferentes maneiras como você pode registrar dispositivos Windows no Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: eda0d77fc5cdb11fa4bc5b21f48ceb7616ecfb15
ms.sourcegitcommit: a63b9eaa59867ab2b0a6aa415c19d9fff4fda874
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67389256"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Métodos de registro do Intune para dispositivos Windows

Para gerenciar dispositivos no Intune, eles primeiramente deverão ser registrados no serviço do Intune. Dispositivos pessoais e corporativos podem ser registrados para o gerenciamento do Intune. 

Há duas maneiras de registrar dispositivos no Intune:
- os usuários podem registrar automaticamente seus computadores Windows 
- os administradores podem configurar políticas para forçar o registro automático sem qualquer envolvimento do usuário

## <a name="user-self-enrollment-in-intune"></a>Registro automático do usuário no Intune

Os usuários podem registrar automaticamente seu dispositivo Windows usando qualquer um destes métodos:

- [BYOD (Traga seu próprio dispositivo)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): os usuários registram seus dispositivos pessoais optando por conectar uma conta **corporativa e de estudante** de **Configurações** do dispositivo. Este processo:
    - registra o dispositivo com o Azure Active Directory para obter acesso a um recurso corporativo como email.
    - registra o dispositivo no Intune como um dispositivo pessoal (BYOD).
Se um administrador tiver configurado o Registro automático (disponível com as assinaturas premium do Azure AD), o usuário só precisará inserir suas credenciais uma vez. Caso contrário, será necessário registrar separadamente somente por meio do registro de MDM e inserir novamente suas credenciais.  
- **Somente registro de MDM** permite que os usuários registrem um grupo de trabalho existente, o Active Directory ou um PC ingressado no Azure Active Directory no Intune. Os usuários registram de Configurações no computador Windows existente. Esse método não é recomendado porque ele não registra o dispositivo no Azure Active Directory. Ele também impede o uso de recursos como o Acesso condicional.
- [Ingresso no Azure AD (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) – ingressa o dispositivo com o Azure Active Directory e permite que usuários entrem no Windows com suas credenciais do Azure AD. Se o Registro automático estiver habilitado, o dispositivo será registrado automaticamente no Intune. O benefício do registro automático é um processo de etapa única para o usuário. Caso contrário, será necessário registrar separadamente somente por meio do registro de MDM e inserir novamente suas credenciais. Os usuários registram dessa maneira durante a OOBE inicial do Windows ou em Configurações. O dispositivo é marcado como corporativo no Intune.
- [AutoPilot](enrollment-autopilot.md) – automatiza o ingresso no Azure AD e registra novos dispositivos corporativos no Intune. Esse método simplifica a configuração inicial pelo usuário e acaba com a necessidade de aplicar imagens do sistema operacional personalizadas nos dispositivos. Quando os administradores usam o Intune para gerenciar dispositivos Autopilot, eles poderão gerenciar políticas, perfis, aplicativos e mais após serem registrados.  Há dois tipos de implantação do Autopilot: [Modo de Autoimplantação](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (para quiosques, sinalização digital ou um dispositivo compartilhado) e [Modo Controlado pelo Usuário](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (para usuários tradicionais). 

## <a name="administrator-based-enrollment-in-intune"></a>Registro com base em administrador no Intune

Os administradores podem configurar os seguintes métodos de registro que não exigem nenhuma interação do usuário:

- [Ingresso no Azure AD Híbrido](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) permite que os administradores configurem a política de grupo do Azure Active Directory para registrar automaticamente dispositivos com ingresso híbrido no Azure AD. 
- O [Cogerenciamento do Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview) permite que os administradores registrem seus dispositivos gerenciados do Configuration Manager existente no Intune para obter os benefícios duplos do Intune e do Configuration Manager. 
- O [DEM](device-enrollment-manager-enroll.md) (gerenciador de registros de dispositivos) é uma conta de serviço especial. As contas do DEM têm permissões que permitem que os usuários autorizados registrem e gerenciem vários dispositivos corporativos. Esses tipos de dispositivos são bons, por exemplo, para aplicativos de ponto de venda ou utilitários, mas não para usuários que precisam acessar os recursos ou o email da empresa. Esse método não permite o uso de recursos como o Acesso Condicional. 
- O [registro em massa](windows-bulk-enroll.md) permite que um usuário autorizado ingresse grandes quantidades de novos dispositivos corporativos no Azure Active Directory e no Intune. Crie um pacote de provisionamento com o aplicativo WCD (Windows Configuration Designer). Em seguida, usando a mídia USB durante a configuração inicial pelo usuário do Windows ou de um computador Windows existente, instale o pacote de provisionamento para registrar automaticamente os dispositivos no Intune. Esse método não permite o uso do Acesso Condicional. 
- O [registro de dispositivos do Windows IoT Core](https://docs.microsoft.com/en-us/windows/iot-core/manage-your-device/intunedeviceenrollment) é realizado usando o painel do Windows IoT Core para preparar o dispositivo e, em seguida, usando o Designer de configuração do Windows para criar um pacote de provisionamento. Em seguida, usando mídia de cartão SD durante a inicialização, ele instala o pacote de provisionamento para registrar automaticamente os dispositivos no Intune.

## <a name="next-steps"></a>Próximas etapas

[Conheça as funcionalidades dos métodos de registro do Windows](enrollment-method-capab.md)
