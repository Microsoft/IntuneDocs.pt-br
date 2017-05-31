---
title: Registrar os dispositivos Windows
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: habilitar o MDM (gerenciamento de dispositivo móvel) do Intune para dispositivos do Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 687be18cedd063b3c2701937f2522e801e51644b
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-windows-devices"></a>Registrar os dispositivos Windows

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Este tópico ajuda os administradores de TI a simplificar o registro do Windows para os seus usuários.  Dispositivos do Windows podem ser registrados sem etapas adicionais, mas você pode facilitar o registro para os usuários.

Os dispositivos que executam a Atualização do Windows 10 para Criadores, e que estão ingressados no domínio do Azure Active Directory, agora têm suporte para o gerenciamento de vários usuários do Intune. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento como a instalação de aplicativos.

Dois fatores determinam como você pode simplificar o registro de dispositivos do Windows:

- **Você usa o Azure Active Directory Premium?** <br>[O Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) está incluído no Enterprise Mobility + Security e outros planos de licenciamento.
- **Quais versões de clientes Windows serão registradas?** <br>Dispositivos Windows 10 podem registrar automaticamente adicionando uma conta corporativa ou escolar. Versões anteriores devem ser registrados usando o aplicativo de Portal da Empresa.

||**Azure AD Premium**|**Outro AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Registro automático](#enable-windows-10-automatic-enrollment) |[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|
|**Versões anteriores do Windows**|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Habilitar o registro do Windows sem o Azure AD Premium
Você pode permitir aos usuários o registro de seus dispositivos sem registro automático do Azure AD Premium. Depois de atribuir licenças, os usuários podem registrar depois de adicionar sua conta corporativa aos seus dispositivos pessoais ou ingressar seus dispositivos corporativos ao Azure AD. Criar um alias DNS (tipo de registro CNAME) facilita para os usuários registrarem seus dispositivos. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem precisar inserir um nome do servidor Intune.

**Etapa 1: Criar um CNAME** (opcional)<br>
Criar registros de recurso DNS CNAME para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

Embora a criação de entradas de DNS CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum registro CNAME no registro, os usuários deverão inserir manualmente o nome do servidor MDM: https://enrollment.manage.microsoft.com.

|Tipo|Nome do host|Aponta para|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|

Se você tiver mais de um sufixo UPN, você precisará criar um CNAME para cada nome de domínio e apontar cada um para EnterpriseEnrollment-s.manage.microsoft.com. Por exemplo, se os usuários da Contoso usarem name@contoso.com, mas também usarem name@us.contoso.com e name@eu.constoso.com como seu email/UPN, o administrador de DNS da Contoso precisará criar os seguintes CNAMEs.

|Tipo|Nome do host|Aponta para|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|

`EnterpriseEnrollment-s.manage.microsoft.com` – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

**Etapa 2: Verifique o CNAME** (opcional)<br>
No portal do Azure Intune, selecione **Mais serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Registro do Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informe aos usuários como registrar dispositivos Windows
Informe aos usuários como registrar seus dispositivos Windows e o que esperar quando eles forem incluídos no gerenciamento. Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Você também pode informar aos usuários [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

