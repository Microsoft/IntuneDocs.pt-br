---
title: Registrar os dispositivos Windows
titleSuffix: Intune on Azure
description: "Habilite o MDM (gerenciamento de dispositivo móvel) do Intune em dispositivos Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 08/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b5b5e2cdf2b31c33a02a90560e4abf955d398b0
ms.sourcegitcommit: d5b5cb9b6dcb59094e436e07f8ed46924b37ac94
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2017
---
# <a name="enroll-windows-devices"></a>Registrar os dispositivos Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a simplificar o registro do Windows para os seus usuários. Depois que você [configurar o Intune](setup-steps.md), os usuários registram os dispositivos Windows [entrando](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) com sua conta corporativa ou de estudante.  

Como um administrador do Intune, você pode simplificar o registro das seguintes maneiras:
- Habilitar o registro automático (Azure AD premium necessário)
- Registro de CNAME
- Habilitar o registro em massa (Azure AD premium e Designer de Configuração do Windows necessários)

Dois fatores determinam como você pode simplificar o registro de dispositivos do Windows:

- **Você usa o Azure Active Directory Premium?** <br>[O Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) está incluído no Enterprise Mobility + Security e outros planos de licenciamento.
- **Quais versões de clientes Windows os usuários registrarão?** <br>Dispositivos Windows 10 podem registrar automaticamente adicionando uma conta corporativa ou escolar. Versões anteriores devem ser registrados usando o aplicativo de Portal da Empresa.

||**Azure AD Premium**|**Outro AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Registro automático](#enable-windows-10-automatic-enrollment) |[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|
|**Versões anteriores do Windows**|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|

As organizações que podem usar o registro automático também podem configurar [dispositivos de registro em massa](windows-bulk-enroll.md) usando o aplicativo de Designer de Configuração do Windows.

**Suporte a vários usuários**<br>
Os dispositivos que executam a Atualização do Windows 10 para Criadores, e que estão ingressados no domínio do Azure Active Directory, agora têm suporte para o gerenciamento de vários usuários do Intune. Quando os usuários padrão fizerem logon com suas credenciais do Azure AD, eles receberão aplicativos e políticas atribuídas ao nome de usuário deles. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Habilitar o registro do Windows sem o Azure AD Premium
É possível simplificar o registro para os usuários criando um alias DNS (tipo de registro CNAME) que redireciona automaticamente as solicitações de registro para os servidores do Intune. Se você não criar um registro de recurso DNS CNAME, os usuários que tentarem se conectar ao Intune deverão inserir o nome do servidor Intune durante o registro.

**Etapa 1: Criar um CNAME** (opcional)<br>
Criar registros de recurso DNS CNAME para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

Embora a criação de entradas de DNS CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum registro CNAME no registro, os usuários deverão inserir manualmente o nome do servidor MDM: enrollment.manage.microsoft.com.

|Tipo|Nome do host|Aponta para|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

Se você tiver mais de um sufixo UPN, você precisará criar um CNAME para cada nome de domínio e apontar cada um para EnterpriseEnrollment-s.manage.microsoft.com. Se os usuários da Contoso usarem name@contoso.com, mas também usarem name@us.contoso.com e name@eu.constoso.com como seu email/UPN, o administrador de DNS da Contoso deverá criar os seguintes CNAMEs:

|Tipo|Nome do host|Aponta para|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|

`EnterpriseEnrollment-s.manage.microsoft.com` – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

**Etapa 2: Verifique o CNAME** (opcional)<br>
No portal do Azure Intune, selecione **Mais serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Registro do Windows**. Digite a URL do site da empresa na caixa **Especificar um nome de domínio verificado** e escolha **Testar Detecção Automática**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informe aos usuários como registrar dispositivos Windows
Informe aos usuários como registrar seus dispositivos Windows e o que esperar quando eles forem incluídos no gerenciamento. Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Você também pode pedir para os usuários lerem [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md).
