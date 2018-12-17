---
title: Configurar o registro para dispositivos Windows usando o Microsoft Intune
titlesuffix: ''
description: Configurar o registro para dispositivos Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9562eb2c8fae49628ac042f28f172fb9f8fd5106
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112537"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Configurar o registro para dispositivos Windows

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a simplificarem o registro do Windows para os usuários. Depois que você [configurar o Intune](setup-steps.md), os usuários registram os dispositivos Windows [entrando](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) com sua conta corporativa ou de estudante.  

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

## <a name="multi-user-support"></a>Compatibilidade multiusuário

O Intune é compatível com o multigerenciamento para dispositivos que executam a atualização do Windows 10 para Criadores e foram ingressados no domínio do Azure Active Directory. Quando os usuários padrão entrarem com as credenciais do Microsoft Azure AD, eles receberão os aplicativos e políticas atribuídas ao nome de usuário deles. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Simplificar a inscrição do Windows sem o Azure AD Premium
Para simplificar o registro, crie um alias (tipo de registro CNAME) de DNS (servidor de nomes de domínio) que redireciona as solicitações de registro para os servidores do Intune. Caso contrário, os usuários que tentarem se conectar ao Intune precisam inserir o nome do servidor do Intune durante o registro.

**Etapa 1: criar um CNAME** (opcional)<br>
Criar registros de recurso DNS CNAME para o domínio da sua empresa. Por exemplo, se o site da empresa fosse contoso.com, você criaria um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

Embora a criação de entradas de DNS CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum registro CNAME no registro, os usuários deverão inserir manualmente o nome do servidor MDM: enrollment.manage.microsoft.com.

|Tipo|Nome do host|Aponta para|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

Se a empresa usar mais de um sufixo UPN, você precisará criar um CNAME para cada nome de domínio e apontar cada um para EnterpriseEnrollment-s.manage.microsoft.com. Por exemplo, os usuários da Contoso usam os seguintes formatos como seu email/UPN:

- name@contoso.com
- name@us.contoso.com
- name@eu.constoso.com\

O administrador de DNS da Contoso precisarão criar os seguintes CNAMEs:

|Tipo|Nome do host|Aponta para|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hora|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hora|

`EnterpriseEnrollment-s.manage.microsoft.com` – Dá suporte ao redirecionamento para o serviço Intune com o reconhecimento de domínio a partir do nome de domínio do email

Alterações em registros DNS podem levar até 72 horas para serem propagadas. Não é possível verificar a alteração do DNS no Intune até que o registro de DNS seja propagado.

**Etapa 2: verifique o CNAME** (opcional)<br>
1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Validação de CNAME**.
2. Na caixa **Domínio**, digite o site da empresa e escolha **Testar**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informe aos usuários como registrar dispositivos Windows
Informe aos usuários como registrar seus dispositivos Windows e o que esperar quando eles forem incluídos no gerenciamento.

> [!NOTE]
> Os usuários finais devem acessar o site do Portal da Empresa por meio do Microsoft Edge para exibir aplicativos Windows atribuídos a você para versões específicas do Windows. Outros navegadores, incluindo o Google Chrome, Mozilla Firefox e Internet Explorer, não são compatíveis com esse tipo de filtragem.

Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Você também pode pedir para os usuários lerem [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Se o registro de MDM automático não estiver habilitado, mas você tiver dispositivos com Windows 10 que ingressaram no Azure AD, dois registros estarão visíveis no console do Intune após o registro. É possível interromper isso certificando-se de que esses usuários com dispositivos ingressados no Azure AD acessem **Contas** > **Acessar trabalho ou escola** e **Conectar** usando a mesma conta. 

Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md).

## <a name="next-steps"></a>Próximas etapas

- [Considerações ao gerenciar dispositivos Windows usando o Intune no Azure](intune-legacy-pc-client.md).
