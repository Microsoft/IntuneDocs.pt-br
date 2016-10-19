---
title: "Usar políticas de configuração de aplicativo móvel Android for Work | Microsoft Intune"
description: "Use políticas de configuração de aplicativo móvel no Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo Android for Work."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: a986e859e38e0936f53c57a75872dc86de3ee181


---

# Configurar aplicativos Android for Work com as políticas de configuração de aplicativo móvel no Microsoft Intune
Use políticas de configuração de aplicativo móvel no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

-   Um número da porta personalizado.

-   Configurações de idioma.

-   Configurações de identidade visual, como um logotipo da empresa.

Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

Políticas de configuração de aplicativo móvel podem ajudar a eliminar esses problemas, permitindo que você implante essas configurações para os usuários antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

Para utilizar as políticas de configuração do aplicativo, as configurações de aplicativo corporativo devem ter sido expostas pelo desenvolvedor quando foram criadas. Por exemplo, o Google Chrome expõe as configurações que permitem que você defina indicadores padrão, sites autorizados e negados e muito mais. Entre em contato com o desenvolvedor do aplicativo para saber se há suporte para essas configurações e como especificá-las na política.

A política de configuração do aplicativo é implantada para os mesmos usuários para os quais você implantou o aplicativo que deseja configurar. As configurações de política serão usadas sempre que o aplicativo for executado.

## Configurar uma política de configuração do aplicativo móvel

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.

2.  Na lista de políticas, expanda **Android for Work**, escolha **Política de Configuração do Aplicativo Móvel (Android for Work)** e, em seguida, escolha **Criar Política**.

    > [!TIP]
    > Você só pode definir configurações personalizadas para esse tipo de política. Configurações recomendadas não estão disponíveis.

3.  Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo móvel.

4. Na seção **Política de Configuração do Aplicativo Móvel** da página, especifique as seguintes informações:
    - **ID do pacote do aplicativo ao qual essa configuração se aplica** – A ID do pacote pode ser encontrada na seção 'id =' da URL da página do aplicativo no Google Play. Por exemplo, a ID do pacote do aplicativo Microsoft Excel é **com.microsoft.office.excel**.
    - Na caixa de texto, insira os dados para as configurações do aplicativo que deseja configurar. Você pode obter essas configurações por meio do fornecedor do aplicativo. Nem todos os aplicativos dão suporte a essas configurações.
5.  Clique em **Validar** para garantir que os dados que você inseriu estão em um formato de lista de propriedades válido.

    > [!IMPORTANT]
    > Quando você clica em **Validar**, o Intune verifica se os dados de configuração que você inseriu estão em um formato válido. Ele não verifica se os dados funcionarão com o aplicativo a que estão associados.

6.  Quando terminar, clique em **Salvar Política**.

A nova política é exibida no nó **Políticas de Configuração**.


## Implantar a política de configuração do aplicativo
Depois de criar uma política de configuração de aplicativo móvel, você deve implantá-la para os mesmos usuários para os quais você implantará o aplicativo ao qual tais configurações se aplicam.

Para obter mais informações sobre como implantar políticas, consulte [implantar uma política de configuração](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)

Para obter informações sobre como implantar aplicativos em dispositivos Android for Work, consulte [Como implantar aplicativos Android for Work com o Intune](android-for-work-apps.md).

Quando o aplicativo implantado é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo móvel.

> [!TIP]
> Apenas uma política de configuração de aplicativo para cada aplicativo deve ser implantada para o usuário.







<!--HONumber=Oct16_HO2-->


