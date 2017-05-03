---
title: Configurar o gerenciamento de dispositivo Windows com o Microsoft Intune | Microsoft Docs
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Windows com o Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 66be6716df38d868e8247131b49ffb50fc48e60b
ms.openlocfilehash: 1d9bd55a8abee4175d2e71727d7ff18274defd3d
ms.lasthandoff: 04/15/2017


---

# <a name="set-up-windows-device-management"></a>Configurar o gerenciamento do dispositivo Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico ajuda os administradores de TI a simplificar o registro do Windows para os seus usuários.  Dispositivos do Windows podem ser registrados sem etapas adicionais, mas você pode facilitar o registro para os usuários.

Dois fatores determinam como você pode simplificar o registro de dispositivos do Windows:
- **Você usa o Azure Active Directory Premium?** <br>[O Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) está incluído no Enterprise Mobility + Security e outros planos de licenciamento.
- **Quais versões de clientes Windows serão registradas?** <br>Dispositivos Windows 10 podem registrar automaticamente adicionando uma conta corporativa ou escolar. Versões anteriores devem ser registrados usando o aplicativo de Portal da Empresa.

||**Azure AD Premium**|**Outro AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Registro automático](#enable-windows-10-automatic-enrollment) |[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|
|**Versões anteriores do Windows**|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|[Registro de usuário](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Habilite o registro do Windows sem registro automático
Você pode permitir aos usuários o registro de seus dispositivos sem registro automático do Azure AD Premium. Depois de atribuir licenças, os usuários podem registrar depois de adicionar sua conta corporativa aos seus dispositivos pessoais ou ingressar seus dispositivos corporativos ao Azure AD. Criar um alias DNS (tipo de registro CNAME) facilita para os usuários registrarem seus dispositivos. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem precisar inserir um nome do servidor Intune.

**Etapa 1: Criar CNAMEs** (opcional)<br>
Criar registros de recurso DNS CNAME para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

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

**Etapa 2: Verifique o CNAME** (opcional)<br>
No [console de administração do Intune](http://manage.microsoft.com), escolha **Admin** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informe aos usuários como registrar dispositivos Windows
Informe aos usuários como registrar seus dispositivos Windows e o que esperar quando eles forem incluídos no gerenciamento.
Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Você também pode direcionar os usuários para [O que meu administrador de TI poderá ver em meu dispositivo](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md)

