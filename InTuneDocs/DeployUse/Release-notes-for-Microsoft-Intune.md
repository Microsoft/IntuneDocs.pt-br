---
title: "Notas de versão do Microsoft Intune | Microsoft Intune"
description: "Notas de versão do Intune"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: b7643ccb64185adb1eb4326a19d56814d8667462


---

# Notas de versão do Microsoft Intune
O Microsoft Intune é uma solução integrada de gerenciamento de cliente baseado em nuvem que fornece ferramentas, relatórios e licenças de atualização para a versão mais recente do Windows, e o ajuda a manter seus computadores atualizados e protegidos. Além disso, o Intune permite que você gerencie dispositivos móveis na rede pelo Exchange ActiveSync ou diretamente pelo Intune. As notas de versão a seguir descrevem informações importantes e problemas conhecidos no Microsoft Intune.


## Os usuários do Android não podem enviar email quando o acesso condicional para o Exchange Online é implementado

Usuários que executam Samsung Android 5.1.1 e superior em seus dispositivos não conseguem enviar email quando o acesso condicional para Exchange Online foi configurado. A Samsung reconhece que o problema está no seu cliente de email interno no Android 5.1.1 e superior e está investigando uma correção no momento.

**Solução alternativa 1:** orientar aos usuários finais a usarem o aplicativo do Outlook para Android.

**Solução alternativa 2:** para habilitar que os usuários afetados enviem email, você pode seguir estas etapas:

1. Coloque o usuário afetado em um grupo de segurança na seção "grupos isentos" da política de acesso condicional para o Exchange Online.
2. Permita que o usuário sincronize email temporariamente no cliente de email interno.
3. Remova o usuário afetado do grupo isento e confirme se o usuário agora pode enviar email.

A Microsoft continuará a trabalhar em conjunto com Samsung em uma correção ou soluções alternativas adicionais.



## A alteração de perfis de acesso de recursos entre grupos para iOS e Android pode falhar
**Problema:** quando você altera o email perfis de acesso de recurso de protocolo SCEP entre os grupos, os perfis podem entrar em conflito e falhar. Por exemplo, digamos que você tem um perfil existente apontando para o servidor Exchange local, direcionado ao Grupo A e, em seguida, crie um novo perfil de email que aponta para o Exchange online, direcionado ao Grupo B. Quando você move usuários do Grupo A para o Grupo B, os dispositivos manterão o perfil de email do Exchange local e tentarão instalar o perfil de email online do Exchange que está direcionado ao Grupo B.

Neste ponto, ocorre o seguinte: 
* Se os perfis de email A e B são idênticos, o dispositivo rejeita o perfil de email B, pois o perfil de email B já contêm o perfil de email A.
* Se o perfil de email A for diferente do perfil de email B, conforme mencionado no exemplo acima, o dispositivo pode acabar com dois perfis de email.

**Observação:** o nome do host e o atributo usado para o nome de usuário são verificados para diferenciar um perfil de email do outro.

Em ambos os casos acima, o perfil de acesso de recursos (perfil de email) não foi removido do dispositivo para evitar a remoção não intencional de um acesso do usuário ao email ou ao certificado SCEP do cliente.

**Solução alternativa:** nenhuma.

## Quando você registra um dispositivo Windows 8.1 que deve ser autenticado em um servidor proxy, o processo de registro falha sem motivo aparente
**Problema:** quando você registra um dispositivo Windows 8.1 e o dispositivo deve ser autenticado em um servidor proxy durante o processo de registro, o registro falha se o dispositivo não tiver credenciais do servidor proxy em cache. Quando as credenciais do servidor proxy não estão em cache no dispositivo, o processo de registro deve aguardar até que o usuário insira as credenciais. No entanto, o aviso para fornecer credenciais do servidor proxy não é exibido durante o processo de registro. O resultado é que o processo de registro não pode autenticar o servidor proxy e nenhum motivo aparente dessa falha é apresentado ao usuário.

**Solução alternativa:** para dispositivos Windows 8.1 que devem ser registrados em uma rede que requer uso de servidor proxy autenticado, configure e salve as credenciais do servidor proxy antes do registro do dispositivo. Para configurar e salvar as credenciais em um dispositivo Windows 8.1:

1.  No dispositivo Windows 8.1, abra o **Internet Explorer**.

2.  Quando solicitadas as credenciais do servidor proxy, insira as credenciais e então selecione a opção **Lembrar minhas credenciais**.

3.  Registre o dispositivo.

## Os dispositivos Windows Phone 8.1 não conseguem se registrar no Microsoft Intune quando a autenticação do dispositivo está habilitada no AD FS
**Problema:** quando você registra um dispositivo Windows Phone 8.1, o registro falhará se a configuração opcional para a autenticação do dispositivo estiver habilitada como parte da política de autenticação global no Active Directory Federated Services (AD FS).

**Solução alternativa** : desabilite a autenticação de dispositivos no servidor do AD FS desmarcando **Habilitar a autenticação de dispositivo** em **Editar política de autenticação global**. Para obter mais informações, consulte [Configurando políticas de autenticação](http://technet.microsoft.com/library/dn486781.aspx)


## A Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android não tem nenhum recurso interno de desinstalação
**Problema:** a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android** não tem uma funcionalidade interna de desinstalação da ferramenta.

**Solução alternativa:** navegue até o local em que você instalou a ferramenta e exclua o diretório. O local de instalação padrão é: **C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Para saber mais sobre a ferramenta de encapsulamento de aplicativos, consulte [Prepare Android apps for management with App Wrapping Tool (Preparar aplicativos Android para o gerenciamento com a Ferramenta de Encapsulamento de Aplicativos)](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## A assistência remota não está disponível em computadores que executam o Windows 8 ou o Windows 8.1
**Problema:** nessa versão, o recurso de assistência remota não está disponível em computadores que executam Windows 8 ou Windows 8.1.

**Solução alternativa:** nenhuma.

## Talvez não funcionem as notificações de alerta para os destinatários que são adicionados manualmente
**Problema:** se um destinatário for adicionado automaticamente a uma notificação de alerta, nem sempre ele poderá receber uma notificação.

**Solução alternativa:** para assegurar que os destinatários recebam a notificação de mensagem, você deve adicionar destinatários manualmente a notificações de alerta.

## Suporte a idiomas na Versão Prévia do Portal do Azure
A Versão Prévia do Portal do Azure foi criada em uma nova plataforma e tem suporte nos seguintes idiomas: chinês (simplificado), chinês (tradicional), tcheco, holandês, inglês, alemão, húngaro, italiano, japonês, português (Brasil), português (Portugal), russo, espanhol, inglês, francês, coreano, polonês, sueco e turco.

O Console de Administração do Intune e as experiências móveis do usuário final têm suporte nos idiomas dinamarquês, grego, finlandês, norueguês e romeno, além de todos os idiomas com suporte na Versão Prévia do Portal do Azure.



<!--HONumber=Jul16_HO3-->


