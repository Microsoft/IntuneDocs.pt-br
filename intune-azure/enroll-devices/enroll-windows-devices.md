---
title: Registrar os dispositivos Windows
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: habilitar o MDM (gerenciamento de dispositivo móvel) do Intune para dispositivos do Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a95aca706a4996d40e268a80c7c334ebb9854df5
ms.openlocfilehash: 6cbaf8414452f11f0aa97616bbed2cf164b49ac0
ms.lasthandoff: 03/15/2017


---

# <a name="enroll-windows-devices"></a>Registrar os dispositivos Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use um dos métodos a seguir para configurar o registro para dispositivos do Windows:

- [**Registro automático do Windows 10 e Windows 10 Mobile com o Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Esse método é aplicável somente a dispositivos Windows 10 e Windows 10 Mobile.
 -  Você deve ter o Azure Active Directory Premium para usar esse método. Caso contrário, use o método de registro para Windows 8.1 e Windows Phone 8.1.
 -  Se você optar por não habilitar o registro automático, use o método de registro para Windows 8.1 e Windows Phone 8.1.

- [**Registro do Windows 8.1 e Windows Phone 8.1 configurando CNAME**](#simplify-enrollment-by-configuring-cname)
 - Você deve usar esse método para registrar dispositivos Windows 8.1 e Windows Phone 8.1.
 - Você também pode usar esse método se não tiver o Azure Active Directory (AD) Premium.


## <a name="prerequisites"></a>Pré-requisitos

Se alguns dos seguintes pré-requisitos não estiverem na versão prévia do Intune Azure ainda, você precisará executá-las no console de administração clássico do Intune.

- [Configurar um nome de domínio personalizado](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a autoridade de MDM (gerenciamento de dispositivo móvel)](set-mdm-authority.md) como **Microsoft Intune**
- [Configurar o aplicativo do Portal da Empresa](/intune-azure/manage-apps/company-portal-app.md)
- Atribuir licenças a usuários

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-workplace-enrollment"></a>Habilitar o registro do local de trabalho do Windows

Você pode permitir aos usuários a instalação e o registro de seus dispositivos sem registro automático do Azure AD Premium. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem inserir um nome do servidor.

1. **Criar CNAMEs** (opcional)<br>
 Criar registros de recurso DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

    Embora a criação de entradas de DNS CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum CNAME de registro, os usuários deverão inserir manualmente o nome do servidor MDM, enrollment.manage.microsoft.com.

    Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recursos de CNAME deve conter as seguintes informações:

    Registros de recursos de CNAME devem conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  `EnterpriseEnrollment-s.manage.microsoft.com` – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

  Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

2.  **Verificar CNAME**<br>No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Registro do Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

3.  **Diga aos usuários como registrar seus dispositivos e o que esperar quando tais dispositivos forem incluídos no gerenciamento.**

    Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Você também pode direcionar os usuários para [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

    Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Nenhum trabalho adicional é necessário, a menos que você vá implantar o Portal da Empresa em dispositivos.  As etapas 2 e 3 no console do administrador podem ser ignoradas com segurança.

