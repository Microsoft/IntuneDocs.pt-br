---
title: Configurar o gerenciamento de dispositivo Windows com o Microsoft Intune | Microsoft Docs
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para computadores Windows, incluindo dispositivos Windows 10 com o Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 31d58d9973cca4023186731a5411c9c9e830e32a
ms.openlocfilehash: e24251a066349e23beb94b75a66c5710ba7e41f1


---

# <a name="set-up-windows-device-management"></a>Configurar o gerenciamento do dispositivo Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Como administrador do Intune, você pode habilitar o registro e o gerenciamento de computadores Windows de duas maneiras:

- **[Registro automático com o Azure Active Directory](#azure-active-directory-enrollment)** – os usuários do Windows 10 e do Windows 10 Mobile registram seus dispositivos adicionando uma conta corporativa ou de estudante ao dispositivo.

- **[Registro no Portal da Empresa](#set-up-company-portal-app-enrollment)** – usuários do Windows 8.1 e posteriores registram seus dispositivos baixando e instalando o aplicativo de Portal da Empresa e inserindo as credenciais de sua conta corporativa ou de estudante no aplicativo.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Configurar o registro do aplicativo de Portal da Empresa
Você pode permitir que os usuários instalem e registrem seus dispositivos usando o aplicativo do Portal da Empresa do Intune. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem inserir um nome do servidor.

1. **Configurar Intune**<br>
Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de MDM (gerenciamento de dispositivo móvel)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.

2. **Criar CNAMEs** (opcional)<br>Criar registros de recurso DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site da empresa for contoso.com, será necessário criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment.manage.microsoft.com.

    Se você tiver um CNAME no DNS que redireciona o EnterpriseEnrollment.contoso.com para manage.microsoft.com, sugerimos a substituição por um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com. Essa alteração é recomendada, pois o ponto de extremidade manage.microsoft.com está sendo desativado para inscrições em uma versão futura.

    Registros de recursos de CNAME devem conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  `EnterpriseEnrollment-s.manage.microsoft.com` – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  `EnterpriseRegistration.windows.net` – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrados no Azure Active Directory usando sua conta corporativa ou de estudante

  Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

  Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

3.  **Verificar CNAME**<br>No [console de administração do Intune](http://manage.microsoft.com), escolha **Admin** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

4.  **Etapas opcionais**<br>A etapa **Adicionar chaves de sideload** não é necessária para o Windows 10. A etapa **Carregar Certificado de Assinatura de Código** será necessária somente se você for distribuir aplicativos de LOB (linha de negócios) que não estão disponíveis da Windows Store para dispositivos.

6.  **Diga aos usuários como registrar seus dispositivos e o que esperar quando eles forem incluídos no gerenciamento.**

    Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO3-->


