---
title: Configurar perfis de certificado | Microsoft Intune
description: Saiba como criar um perfil de certificado do Intune.
keywords: 
author: nbigman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: c51c5ae199ca2950dc0371b400727af534a70f09


---

# Configurar perfis de certificado do Intune
Depois de configurar a infraestrutura e os certificados conforme descrito em [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) (Configurar infraestrutura de certificado para SCEP) ou [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md) (Configurar a infraestrutura de certificado para PFX), você pode criar perfis de certificado. Este é o processo:

- **Tarefa 1**: exportar o certificado de AC Raiz Confiável
- **Tarefa 2**: criar perfis de certificado Confiável
- **Tarefa 3**: criar um dos dois tipos de perfil de certificado:
  - Perfis de certificado SCEP
  - Perfis de certificado .PFX

## **Tarefa 1**: exportar o certificado de AC Raiz Confiável
Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora. Não exporte a chave privada.

Ao configurar um perfil de certificado confiável, você importará esse certificado.

## **Tarefa 2**: criar perfis de certificado Confiável
Você deve criar um perfil de certificado Confiável para poder criar um protocolo de registro de certificado simples (SCEP) ou um perfil de certificado PKCS 12 (.PFX). Você precisa de um perfil de certificado confiável e um perfil SCEP ou .PFX para cada plataforma de dispositivo móvel.

### Para criar um perfil de certificado Confiável

1.  No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.
2.  Adicione um destes tipos de política:
    - **Android &gt; Perfil de certificado confiável (Android 4 e posterior)**
    - **iOS &gt; Perfil de Certificado Confiável (iOS 8.0 e posterior)**
    - **Mac OS X &gt; Perfil de certificado confiável (Mac OS X 10.9 e posterior)**
    - **Windows &gt; Perfil de certificado confiável (Windows 8.1 e posterior)**
    - **Windows &gt; Perfil de certificado confiável (Windows Phone 8.1 e posterior)**

    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).

3.  Insira as informações solicitadas para definir as configurações de perfil de certificado Confiável para Android, iOS, Mac OS X, Windows 8.1 ou Windows Phone 8.1. 
4.  Na configuração **Arquivo de certificado**, importe o Certificado de AC raiz confiável (arquivo .cer) que você exportou da AC emissora. A configuração **Repositório de destino** se aplica apenas aos dispositivos que executam o Windows 8.1 e posterior e apenas se o dispositivo tiver mais de um repositório de certificados.
    
4.  Escolha **Salvar Política**.

A nova política é mostrada no espaço de trabalho **Política**. Agora você pode implantá-la.

## **Tarefa 3**: criar perfis de certificado SCEP ou .PFX
Depois de criar um perfil de certificado de Autoridade de Certificação confiável, crie perfis de certificado SCEP ou .PFX para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, deve especificar um perfil de certificado confiável para essa mesma plataforma. Isso vincula os dois perfis de certificado, mas você ainda deve implantar cada perfil separadamente.

### Para criar um perfil de certificado SCEP

1.  No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.
2.  Adicione um destes tipos de política:
    - **Android &gt; Perfil de certificado SCEP (Android 4 e posterior)**
    - **iOS &gt; Perfil de Certificado SCEP (iOS 8.0 e posterior)**
    - **Mac OS X &gt; Perfil de certificado SCEP (Mac OS X 10.9 e posterior)**
    - **Windows &gt; Perfil de certificado SCEP (Windows 8.1 e posterior)**
    - **Windows &gt; Perfil de certificado SCEP (Windows Phone 8.1 e posterior)**

    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).

3.  Siga as instruções na página de configuração do perfil para definir as configurações de perfil de certificado SCEP.
    > [!NOTE]
    >
    > Em **Formato de nome da entidade**, selecione **Personalizado** para inserir um formato de nome da entidade personalizado (somente em perfis do iOS).
    >
    > As duas variáveis que atualmente têm suporte para o formato personalizado são `Common Name (CN)` e `Email (E)`. Usando uma combinação dessas variáveis e cadeias de caracteres estáticas, você pode criar um formato de nome de entidade personalizado, como este:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > No exemplo, o administrador criou um formato de nome de entidade que, além das variáveis `CN` e `E`, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País. [Função CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) listas cadeias de caracteres com suporte.

4.  Escolha **Salvar Política**.

A nova política é mostrada no espaço de trabalho **Política**. Agora você pode implantá-la.

### Para criar um perfil de certificado .PFX

1.  No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.
2.  Adicione um destes tipos de política:
  - **Android &gt; Perfil de certificado .PFX (Android 4 e posterior)**
  - **Windows &gt; Perfil de Certificado PKCS nº 12 (.PFX) (Windows 10 e posterior)**
  - **Windows &gt; Perfil de Certificado PKCS nº 12 (.PFX) (Windows Phone 10 e posterior)**
  - **iOS > Perfil de Certificado PKCS nº 12 (.PFX) (iOS 8.0 e posterior)**    
    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).
3.  Insira as informações solicitadas no formulário de política.
4.  Escolha **Salvar Política**.

A nova política é mostrada no espaço de trabalho **Política**. Agora você pode implantá-la.

## Implantar perfis de certificado
Quando você implanta perfis de certificado, o arquivo de certificado do perfil de certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o protocolo SCEP ou. o perfil de certificado .PFX para criar uma solicitação de certificado pelo dispositivo.

Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.

-   Você pode implantar perfis de certificado para coleções de usuários ou coleções de dispositivos.

    > [!TIP]
    > Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, implante o perfil de certificado para um grupo de usuários em vez de um grupo de dispositivos. Se você implantar um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.

-   Embora você implante cada perfil separadamente, também precisa implantar a Autoridade de Certificação Raiz Confiável e o protocolo SCEP ou o perfil .PFX. Caso contrário, a política de certificado SCEP ou .PFX falhará.

Implante os perfis de certificado da mesma maneira que implanta outras políticas para o Intune:

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.
2.  Na caixa de diálogo **Gerenciar implantação** :
    -   **Para implantar a política**, selecione um ou mais grupos nos quais implantar a política e escolha **Adicionar** &gt; **OK**.
    -   **Para fechar a caixa de diálogo sem implantá-la**, escolha **Cancelar**.

Ao selecionar uma política implantada, você pode ver mais informações sobre a implantação na parte inferior da lista de políticas.

### Próximas etapas

Em seguida, saiba como usar certificados para proteger emails, Wi-Fi e perfis de VPN.

-  [Configurar o acesso a email corporativo usando perfis de email](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Conexões Wi-Fi no Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Conexões VPN no Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->


