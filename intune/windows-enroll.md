---
title: Configurar o registro para dispositivos Windows usando o Microsoft Intune
titlesuffix: ''
description: Configurar o registro para dispositivos Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 02cc111f8991a855db4f05360e54598af511f28f
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223485"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Configurar o registro para dispositivos Windows

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a simplificar o registro do Windows para os seus usuários. Depois que você [configurar o Intune](setup-steps.md), os usuários registram os dispositivos Windows [entrando](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) com sua conta corporativa ou de estudante.  

Como administrador do Intune, é possível simplificar o registro das seguintes maneiras:
- [Habilitar o registro automático](#enable-windows-10-automatic-enrollment) (Azure AD Premium necessário)
- [Registro de CNAME](#simplify-windows-enrollment-without-azure-ad-premium)
- [Habilitar o registro em massa](windows-bulk-enroll.md) (Azure AD Premium e Designer de Configuração do Windows necessários)

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

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Simplificar a inscrição do Windows sem o Azure AD Premium
É possível simplificar o registro para os usuários criando um alias DNS (servidor de nomes de domínio) (tipo de registro CNAME) que redireciona automaticamente as solicitações de registro para os servidores do Intune. Se você não criar um registro de recurso DNS CNAME, os usuários que tentarem se conectar ao Intune deverão inserir o nome do servidor Intune durante o registro.

**Etapa 1: Criar um CNAME** (opcional)<br>
Criar registros de recurso DNS CNAME para o domínio da sua empresa. Por exemplo, se o site da empresa fosse contoso.com, você criaria um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

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

`EnterpriseEnrollment-s.manage.microsoft.com` – Dá suporte ao redirecionamento para o serviço Intune com o reconhecimento de domínio a partir do nome de domínio do email

Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

**Etapa 2: Verifique o CNAME** (opcional)<br>
No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Registro do Windows**. Digite a URL do site da empresa na caixa **Especificar um nome de domínio verificado** e escolha **Testar Detecção Automática**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informe aos usuários como registrar dispositivos Windows
Informe aos usuários como registrar seus dispositivos Windows e o que esperar quando eles forem incluídos no gerenciamento.

> [!NOTE]
> Os usuários finais devem acessar o site do Portal da Empresa por meio do Microsoft Edge para exibir aplicativos Windows atribuídos a você para versões específicas do Windows. Outros navegadores, incluindo o Google Chrome, Mozilla Firefox e Internet Explorer, não são compatíveis com esse tipo de filtragem.

Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo Windows no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Você também pode pedir para os usuários lerem [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Se o registro de MDM automático não estiver habilitado, mas você tiver dispositivos com Windows 10 que ingressaram no Azure AD, dois registros estarão visíveis no console do Intune após o registro. É possível interromper isso certificando-se de que esses usuários com dispositivos ingressados no Azure AD acessem **Contas** > **Acessar trabalho ou escola** e **Conectar** usando a mesma conta. 

Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md).

## <a name="next-steps"></a>Próximas etapas

- [Considerações ao gerenciar dispositivos Windows usando o Intune no Azure](/intune-classic/deploy-use/intune-on-azure).
