---
title: "Notas de versão do Microsoft Intune | Microsoft Docs"
description: "Notas de versão do Intune"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: fd300a5dfe6d6976491988453ec69e99668889fb


---

# <a name="release-notes-for-microsoft-intune"></a>Notas de versão do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune é uma solução integrada de gerenciamento de clientes baseado em nuvem que fornece ferramentas, relatórios e licenças de atualização para a versão mais recente do Windows. Ele também ajuda a manter seus computadores atualizados e protegidos. Além disso, o Intune permite que você gerencie dispositivos móveis na rede pelo Exchange ActiveSync ou diretamente pelo Intune. As notas de versão a seguir descrevem informações importantes e problemas conhecidos no Microsoft Intune.


## <a name="android-users-cant-send-email-when-conditional-access-for-exchange-online-is-implemented"></a>Os usuários do Android não podem enviar email quando o acesso condicional para o Exchange Online é implementado

**Problema:** usuários que executam o Samsung Android 5.1.1 e versões posteriores em seus dispositivos não conseguem enviar email após o acesso condicional para o Exchange Online ser configurado. A Samsung reconhece que o problema está no seu cliente de email interno no Android 5.1.1 e versões posteriores e está investigando uma correção.

**Solução alternativa 1:** orientar os usuários a usarem o aplicativo Outlook para Android.

**Solução alternativa 2:** para permitir que os usuários afetados enviem email, você pode seguir estas etapas:

1. Coloque cada usuário afetado em um grupo de segurança na seção “grupos isentos” da política de acesso condicional para o Exchange Online.
2. Permita que o usuário sincronize o email temporariamente no cliente de email interno.
3. Remova o usuário afetado do grupo isento e confirme se ele pode enviar emails.

A Microsoft continuará a trabalhar em conjunto com Samsung em uma correção ou soluções alternativas adicionais.



## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>A alteração de perfis de acesso de recursos entre grupos para iOS e Android pode falhar
**Problema:** quando você altera o email ou perfis de acesso de recursos do protocolo SCEP entre os grupos, os perfis podem entrar em conflito e falhar. Por exemplo, digamos que você tem um perfil existente que aponta para o servidor Exchange local, direcionado ao Grupo A. Em seguida, você cria um novo perfil de email que aponta para o Exchange Online, direcionado ao Grupo B. Quando você move usuários do Grupo A para o Grupo B, os dispositivos manterão o perfil de email do Exchange local e tentarão instalar o perfil de email do Exchange Online que está direcionado ao Grupo B.

Neste ponto, ocorre o seguinte: 
* Se os perfis de email A e B são idênticos, o dispositivo rejeita o perfil de email B, pois o perfil de email B já contêm o perfil de email A.
* Se o perfil de email A for diferente do perfil de email B, conforme mencionado no exemplo, o dispositivo terá dois perfis de email.

> [!NOTE]
> O nome do host e o atributo usado para o nome de usuário são verificados para diferenciar um perfil de email do outro.

Em ambos os casos, o perfil de acesso de recursos (perfil de email) não foi removido do dispositivo para evitar a remoção não intencional do acesso de um usuário ao email ou ao certificado SCEP do cliente.

**Solução alternativa:** nenhuma.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Quando você registra um dispositivo Windows 8.1 que deve ser autenticado em um servidor proxy, o processo de registro falha sem motivo aparente
**Problema:** quando você registra um dispositivo Windows 8.1 e o dispositivo deve ser autenticado em um servidor proxy durante o processo de registro, o registro falha se o dispositivo não tiver credenciais do servidor proxy em cache. Quando as credenciais do servidor proxy não estão em cache no dispositivo, o processo de registro deve aguardar até que o usuário insira as credenciais. No entanto, o aviso para fornecer credenciais do servidor proxy não aparece durante o processo de registro. O resultado é que o processo de registro não pode autenticar o servidor proxy. Nenhum motivo aparente para essa falha é apresentado ao usuário.

**Solução alternativa:** para dispositivos Windows 8.1 que devem ser registrados em uma rede que requer o uso de um servidor proxy autenticado, configure e salve as credenciais do servidor proxy antes de registrar o dispositivo. Para configurar e salvar as credenciais em um dispositivo Windows 8.1:

1.  No dispositivo Windows 8.1, abra o Internet Explorer.
2.  Quando as credenciais do servidor proxy forem solicitadas, insira-as e então selecione a opção **Lembrar minhas credenciais**.
3.  Registre o dispositivo.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>Os dispositivos Windows Phone 8.1 não conseguem se registrar no Microsoft Intune quando a autenticação do dispositivo está habilitada no AD FS
**Problema:** quando você registra um dispositivo Windows Phone 8.1, o registro falha se a configuração opcional para a autenticação do dispositivo estiver habilitada como parte da política de autenticação global nos Serviços de Federação do Active Directory (AD FS).

**Solução alternativa**: desabilite a autenticação de dispositivos no servidor do AD FS desmarcando **Habilitar a autenticação de dispositivo** em **Editar política de autenticação global**. Para obter mais informações, consulte [Configurando Políticas de Autenticação](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>A Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android não tem nenhum recurso interno de desinstalação
**Problema:** a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android** não tem uma funcionalidade interna de desinstalação da ferramenta.

**Solução alternativa:** navegue até o local em que você instalou a ferramenta e exclua o diretório. O local de instalação padrão é: **C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Para saber mais sobre a ferramenta de encapsulamento de aplicativos, consulte [Preparar aplicativos Android para o gerenciamento com a Ferramenta de Encapsulamento de Aplicativos](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>A assistência remota não está disponível em computadores que executam o Windows 8 ou o Windows 8.1
**Problema:** nessa versão, o recurso de assistência remota não está disponível em computadores que executam Windows 8 ou Windows 8.1.

**Solução alternativa:** nenhuma.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Notificações de alerta para os destinatários adicionados manualmente podem não funcionar
**Problema:** se os destinatários forem adicionados automaticamente a uma notificação de alerta, nem sempre eles poderão receber uma notificação.

**Solução alternativa:** para assegurar que os destinatários recebam as notificações de mensagem, você deve adicioná-los manualmente às notificações de alerta.

## <a name="language-support-in-the-azure-portal"></a>Suporte a idiomas no Portal do Azure
O Portal do Azure têm suporte nos seguintes idiomas: chinês (simplificado), chinês (tradicional), tcheco, holandês, inglês, alemão, húngaro, italiano, japonês, português (Brasil), português (Portugal), russo, espanhol, inglês, francês, coreano, polonês, sueco e turco.

O Console de Administração do Intune e as experiências móveis do usuário têm suporte nos idiomas dinamarquês, grego, finlandês, norueguês e romeno, além de todos os idiomas com suporte no Portal do Azure.



<!--HONumber=Dec16_HO2-->


