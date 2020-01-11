---
title: O dispositivo não tem um certificado | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 9ac79311881b2f245cbdedcb6c9ac9763ba7cbf3
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75857142"
---
# <a name="install-missing-certificate-required-by-your-organization"></a>Instalar o certificado ausente exigido pela sua organização  

Se o dispositivo não estiver registrado no Intune e não tiver um certificado necessário, você não conseguirá entrar no aplicativo Portal da Empresa. Quando você tentar entrar, verá a seguinte mensagem:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Há duas opções que você pode tentar baixar o certificado necessário e obter seu dispositivo registrado. 

- Habilite o acesso do navegador no aplicativo Portal da Empresa.
- Identificar o certificado que está faltando em um computador corporativo ou de estudante. Em seguida, pesquise a Internet para baixar o certificado ausente. 

Conclua as etapas para habilitar o acesso ao navegador primeiro. Depois disso, se você ainda não puder registrar seu dispositivo, siga as etapas para localizar o certificado na Internet. 

## <a name="enable-browser-access"></a>Habilitar o acesso ao navegador
Conclua estas etapas para habilitar o acesso ao navegador. Depois de habilitar o acesso, o Portal da Empresa instalará o certificado apropriado e continuará o registro.    

1. No aplicativo Portal da Empresa, vá para o canto direito e selecione o menu.  
2. Selecione **Configurações**.  
3. Ao lado de **habilitar o acesso ao navegador** , selecione **habilitar**.  
4. Na tela administrador do dispositivo, selecione **Ativar**. 

## <a name="identify-and-download-the-missing-certificate-through-web-search"></a>Identificar e baixar o certificado ausente por meio da pesquisa na Web
Conclua estas etapas para identificar e instalar manualmente o certificado em seu dispositivo.  

1. Em um computador, abra o Internet Explorer. Se você não tiver um computador para usar para essa finalidade, entre em contato com o suporte de sua empresa. Para obter as informações de contato do suporte de sua empresa, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).

2. Acesse o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) e entre usando suas credenciais corporativas ou de estudante.

3. Na extremidade direita da barra de endereços do navegador, escolha o símbolo que se parece com um cadeado, conforme mostrado a captura de tela abaixo.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Se você não vir o símbolo de cadeado, pare e entre em contato com o suporte de sua empresa. O cadeado significa que você está conectado com segurança, portanto, você não deve continuar a menos que veja esse símbolo.

4. Escolha **Exibir certificados**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. Escolha a guia **Caminho de certificação** e identifique o certificado que precisa ser obtido da Internet. O nome do certificado de que você precisa estará na mesma posição que o que está realçado na captura de tela de exemplo anterior.

6. Usando um mecanismo de pesquisa como o Bing ou o Google, pesquise o nome do certificado que está faltando identificado na seção anterior. O certificado pode terminar com “extensões” diferentes, como ".crt" ou ".pem" etc.

7. Baixe o certificado raiz do site.

8. Após o certificado ser baixado, arraste a parte superior da tela para baixo para abrir suas notificações e toque no nome do certificado na lista de notificações.

4. Na caixa de diálogo **Nome do Certificado** mostrada na captura de tela abaixo, aceite o nome de certificado padrão.

5. Certifique-se de que o **Uso da Credencial** é definido como **Usado para aplicativos e VPN**, e, em seguida, toque em **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Feche o aplicativo Portal da Empresa.

7. Abra o aplicativo Portal da Empresa. Agora, você poderá entrar no aplicativo Portal da Empresa. Se precisar de ajuda, entre em contato com o suporte de sua empresa.

Se você vir a mesma mensagem de “certificado faltando” mostrada acima e já tiver seguido o procedimento, provavelmente ainda há outro certificado que o suporte de sua empresa precisará ajudá-lo a instalar. Contate o suporte de sua empresa para obter ajuda usando as informações de contato disponíveis no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).

## <a name="next-steps"></a>Próximas etapas  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
