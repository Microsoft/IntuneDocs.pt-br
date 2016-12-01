---
title: Personalizar o Portal da Empresa | Microsoft Intune
description: "O Portal da Empresa do Intune permite que os usuários executem tarefas comuns como registrar dispositivos, instalar aplicativos e localizar informações do departamento de IT."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 15ef5c5b7f4c8aa2ceaa6867306e0e82a9835b02


---

# <a name="customize-the-company-portal"></a>Personalizar o Portal da empresa
O Portal da Empresa do Intune é onde os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivo, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.

O Portal da Empresa do Intune fornece aos usuários acesso a aplicativos e dados da empresa. O Portal da Empresa está disponível em duas formas:

-   **O aplicativo do Portal da Empresa**: um aplicativo disponível em dispositivos que você gerencia com o Intune. Saiba mais sobre os aplicativos do Portal da Empresa para [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) e [Windows](/Intune/EndUser/using-your-windows-device-with-intune).


- **O site do Portal da Empresa**: um site que permite que usuários finais realizem a maioria das tarefas no aplicativo Portal da Empresa. A URL do Portal da Empresa do Intune é [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com). Saiba mais sobre esse site em [Using the Intune Company Portal website](/Intune/EndUser/using-the-intune-company-portal-website) (Usando o site do Portal da Empresa do Intune).

> [!TIP]
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.

Estas são algumas das tarefas que os usuários podem fazer no Portal da Empresa:

-   Registrar dispositivos
-   Exibir o status de seus dispositivos
-   Redefinir o dispositivo
-   Redefinir a senha
-   Bloquear o dispositivo remotamente
-   Baixar o software que é implantado pela organização
-   Contatar o departamento de TI para obter suporte

> [!NOTE]
> O aplicativo de Portal da Empresa ainda não está disponível em alguns países.
> __iOS__: o aplicativo de Portal da Empresa para iOS foi publicado para [todas as regiões disponíveis](https://go.microsoft.com/fwlink/?linkid=831284) da App Store do Apple iOS.
> __Android__: atualmente, o aplicativo de Portal da Empresa para Android não está disponível na China. Para esses países, uma solução alternativa é [efetuar o sideload da versão para Android do aplicativo de Portal da Empresa](https://www.microsoft.com/en-us/download/details.aspx?id=49140).  

## <a name="customize-company-portal-settings"></a>Personalizar configurações do Portal da Empresa
Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais. Faça o logon no [Console do administrador do Microsoft Intune](https://manage.microsoft.com) como administrador de serviços ou locatário, escolha **Administrador** &gt; **Portal da Empresa** e defina as configurações do Portal da Empresa.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>Declaração de privacidade e informações de contato de empresa
O nome da empresa é exibido como o título do Portal da Empresa. Os detalhes e as informações de contato são exibidos para os usuários na tela Contatar TI do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |Nome da empresa|40|Este é o nome exibido como título do Portal da Empresa.|
    |Nome do contato do departamento de TI|40|Esse nome é exibido na página **Contatar TI**.|
    |Telefone do departamento de TI|20|Este número de contato é exibido na página **Contatar TI**.|
    |Endereço de email do departamento de TI|40|Este endereço de contato é exibido na página **Contatar TI**. Você deve inserir um endereço de email válido no formato **alias@domainname.com**.|
    |Informações adicionais|120|Exibido na página **Contatar TI**.|
    |URL de política de privacidade de empresa|79|Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve digitar uma URL válida no formato https://www.contoso.com.|

## <a name="support-contacts"></a>Contatos de suporte
O site de suporte é exibido para os usuários no Portal da Empresa para que eles possam acessar o suporte online.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |URL do site de suporte|150|Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato https://www.contoso.com. Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa.|
    |Nome do site|40|Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, **Ir para o site da TI** será exibido na página **Contatar IT** do Portal da Empresa.|

## <a name="company-branding-customization"></a>Personalização da identidade visual da empresa
Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano.

|Nome do campo|Mais informações|
    |----------|----------------|
    |Cores do tema|Selecione uma cor de tema para aplicar ao Portal da Empresa.|
    |Incluir o logotipo da empresa|Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa. Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada. Cada logotipo deve ser um tipo de arquivo .png ou .jpg e ter uma resolução máxima de 400 x 100 pixels e ter 750 KB ou menos em tamanho.|
    |Escolha um plano de fundo para o aplicativo do Portal da Empresa do [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|Esta configuração afeta somente a tela de fundo do aplicativo do Portal da Empresa do [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Depois de salvar suas alterações, é possível usar os links fornecidos na parte inferior da página do **Portal da Empresa** do console do administrador para exibir o site do Portal da Empresa. Esses links não podem ser alterados. Quando um usuário entra, esses links exibem o Portal da Empresa das suas assinaturas.

### <a name="next-steps"></a>Próximas etapas
Parabéns! Você acabou de concluir a etapa 7 do *Guia de início rápido do Intune*.
>[!div class="step-by-step"]

>[&larr; **Criar políticas e aplicativos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Registrar dispositivos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Nov16_HO4-->


