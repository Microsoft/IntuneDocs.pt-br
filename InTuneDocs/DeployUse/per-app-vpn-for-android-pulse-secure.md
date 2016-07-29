---
title: VPN por aplicativo para Android usando Pulse Secure | Microsoft Intune
description: "Você pode criar um perfil de VPN por aplicativo para dispositivos Android gerenciados pelo Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: d6d929b83b967cc4efdc84ecc3262c5c1f509351


---

# Usar uma política personalizada para criar um perfil de VPN por aplicativo para dispositivos Android

Você pode criar um perfil de VPN por aplicativo para dispositivos Android gerenciados pelo Intune. Primeiro, você criará um perfil de VPN que usa o tipo de conexão Pulse Secure e uma política de configuração personalizada que associa esse perfil a aplicativos específicos. Depois de implantar as políticas para os grupos de usuário ou dispositivo Android, a abertura de um dos aplicativos especificados nesses dispositivos abrirá uma conexão VPN para esse aplicativo.

### Etapa 1: criar um perfil de VPN

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** > **Adicionar Política**.
2. Selecione um modelo para a nova política expandindo **Android** e escolha **Perfil de VPN (Android 4 e posterior)**.

3. No modelo, para **Tipo de conexão**, escolha **Pulse Secure**.
4. Conclua e salve o perfil de VPN. Para obter mais detalhes sobre perfis de VPN, consulte [Conexões VPN](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Anote o nome do perfil de VPN para uso na próxima etapa. Por exemplo, **MyAppVpnProfile**.

### Etapa 2: criar uma política de configuração personalizada

   1. No console de administração do Intune **Política** -> **Adicionar Política** -> **Android** -> **Configuração personalizada** -> **Criar Política**.
   2. Forneça um nome para a política.
   3. Em **Configurações OMA-URI**, clique em **Adicionar**.
   4. Forneça um nome de configuração.
   5. Para **Tipo de dados** especifique **Cadeia de caracteres**.
   6. para **OMA-URI** especifique essa cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, em que *Name* é o nome do perfil de VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
   7.   Em **Valor**, forneça uma lista separada por ponto e vírgula de pacotes que devem ser associados ao perfil.  Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.


   ![Exemplo de política personalizada de VPN por aplicativo Android](..\media\android_per_app_vpn_oma_uri.png)
#### Definir sua lista de aplicativos como lista negra ou lista branca (opcional)
Você pode especificar que a sua lista de aplicativos *não* terá permissão para usar a conexão VPN, usando o valor **BLACKLIST**.  Todos os outros aplicativos se conectarão por meio de VPN.

Como alternativa, você pode especificar que *somente* os aplicativos especificados poderão usar a conexão VPN, usando o valor **WHITELIST**.


1.  Em Configurações OMA-URI, clique em **Adicionar**.
2.  Forneça um nome de configuração.
3.  Para **Tipo de dados** especifique **Cadeia de caracteres**.
4.  para **OMA-URI** especifique essa cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, em que *Name* é o nome do perfil de VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
5.  Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.



### Etapa 3: implantar ambas as políticas

Você deve implantar *ambas* políticas para o *mesmo* grupo do Intune.

   1.  No espaço de trabalho **Política** , selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos ao qual você deseja implantar a política, clique **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - clique em **Cancelar**.

Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.



<!--HONumber=Jul16_HO4-->


