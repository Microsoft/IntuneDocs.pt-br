---
title: "Proteger dispositivos Windows com autenticação multifator | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2023d7bc1d35b423a216ece195cdca9a6a542446
ms.openlocfilehash: 15e546b93c2a3aff551efa36ac80ff212ada5812


---

# Protect Windows devices with multi-factor authentication
O Microsoft Intune integra a MFA (autenticação multifator) para ajudar você a proteger seus recursos corporativos. A MFA requer fatores de autenticação, como autenticação de texto, além de nomes de usuário e senhas. O Intune dá suporte ao uso de MFA durante o registro de dispositivos Windows 8.1 ou posterior, Windows Phone 8.1 ou posterior ou Windows 10 Desktop ou Mobile. 

## Requisitos de infraestrutura local para MFA do ADFS
Para configurar a autenticação multifator, você precisará de:

-   **Um domínio do Active Directory ao qual o servidor ADFS está associado.**

-   **Servidor dos Serviços de Federação do Active Directory (ADFS), configurado para MFA.** Um servidor executando Windows Server 2012 R2, configurado como servidor do AD FS. Para obter mais informações, consulte [Secure cloud and on-premises resources using Azure Multi-Factor Authentication Server with Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/) (Proteger recursos locais e da nuvem usando o Servidor Azure Multi-Factor Authentication com o Windows Server 2012 R2 AD FS)

Todos os servidores listados acima devem atender aos requisitos de sistema fornecidos em [Requisitos do sistema e informações de instalação do Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

#### MFA com o Intune
Se sua organização tem uma infraestrutura de TI local que inclui um domínio do Active Directory com ADFS (Serviços de Federação do Active Directory), você pode configurar a MFA no servidor de federação e habilitar a MFA para registro no Intune. Ao configurar a MFA no Intune, você habilita que os usuários possam se autenticar uma vez e durante o registro e ser capaz de acessar recursos corporativos sem repetir o processo de MFA a cada vez.

>[!NOTE]
>A MFA pode ser necessária por usuário ou por grupo no servidor de ADFS.  

#### MFA sem Intune
Se você configurar a MFA no servidor de federação, mas não habilitar a MFA para registro no Intune, os usuários precisarão usar a MFA sempre que acessarem os recursos corporativos (e não somente no registro do dispositivo).

Você também pode usar a MFA AAD (Azure Active Directory) para exigir a MFA sempre que os usuários acessarem os recursos corporativos, por usuário. A MFA do AD é um serviço de nuvem que não requer nenhuma infraestrutura de TI local. Para saber como configurar a MFA do AAD, consulte [Getting started with Azure Multi-Factor Authentication in the cloud (Introdução ao Azure Multi-Factor Authentication na nuvem)](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Exigir MFA do ADFS durante o registro de dispositivos Windows
Para obter informações sobre como habilitar a MFA no ADFS, consulte [Gerenciar riscos com autenticação multifator adicional para aplicativos confidenciais](http://technet.microsoft.com/library/dn280949.aspx).

## Configurar a MFA de registro de dispositivo no Intune
>[!Important]  
>Habilite a MFA em seu ambiente de locatário ou local do AD do Azure antes de exigir a MFA para o registro de dispositivos Windows no Intune. Se você não fizer isso, os usuários receberão uma mensagem de erro ao tentar registrar seus dispositivos Windows ou quando tentarem ingressar seus dispositivos no Azure AD, se o registro automático durante o Ingresso no Azure AD estiver configurado.

1.  No console de administração do Intune, clique em **Administração** &gt; **Gerenciamento de dispositivo móvel** &gt; **Multi-factor Authentication**.

2.  Clique em **Configurar Multi-factor Authentication** e em **Habilitar Multi-factor Authentication**.




<!--HONumber=Jun16_HO4-->


