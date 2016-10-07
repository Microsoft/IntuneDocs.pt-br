---
title: "Pré-requisitos para registro de dispositivo móvel | Microsoft Intune"
description: "Configure os pré-requisitos de MDM (gerenciamento de dispositivo móvel) e prepare-se para registrar diferentes sistemas operacionais."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 91385bdbe4aa4252311db106c04de7d04df5109c
ms.openlocfilehash: 5e94e4efa5a3ecb055ce416c3ee8dd21e56bad65


---

# Pré-requisitos para gerenciamento de dispositivo móvel no Intune
Para permitir que os funcionários registrem dispositivos móveis (incluindo [Android](set-up-android-management-with-microsoft-intune.md), [iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md), [Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md) e [Computadores Windows](set-up-windows-device-management-with-microsoft-intune.md)) com o Intune ou gerenciem dispositivos da empresa, você deve habilitar o registro de dispositivo. Para permitir o registro você deve definir uma autoridade de MDM (gerenciamento de dispositivo móvel), configurar o Portal da Empresa do Intune, atribuir licenças e habilitar o registro para a plataforma do dispositivo.

## Defina a autoridade de gerenciamento de dispositivos móveis
A autoridade de MDM define o serviço de gerenciamento que tem permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade de MDM incluem o Intune e o Configuration Manager com Intune. Se você definir o Configuration Manager como a autoridade de gerenciamento, nenhum outro serviço poderá ser usado para gerenciamento de dispositivo móvel.

>[!IMPORTANT]
> Considere atentamente se você quer gerenciar dispositivos móveis usando apenas o Intune (serviço online) ou o System Center Configuration Manager com Intune (solução de software local em conjunto com o serviço online). Depois de configurar a autoridade de gerenciamento de dispositivo móvel, ela não poderá ser alterada.



1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), selecione **Administrador** &gt; **Gerenciamento de Dispositivo Móvel**.

2.  Na lista **Tarefas** , clique em **Configurar autoridade de gerenciamento de dispositivo móvel**. A caixa de diálogo **Definir autoridade MDM** é aberta.

    ![Definir a caixa de diálogo de autoridade de MDM](../media/intune-mdm-authority.png)

3.  O Intune solicita a confirmação de que você deseja o Intune como autoridade MDM. Marque a caixa de seleção e escolha **Sim** para usar o Microsoft Intune para gerenciar dispositivos móveis.

## Configurar o Portal da Empresa do Intune

O Portal da Empresa do Intune é onde os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivo, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.

> [!TIP]
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.

Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais. Para fazer isso, basta fazer logon no [Console de administração do Microsoft Intune](https://manage.microsoft.com) como administrador de serviços ou locatário, escolher **Administrador** &gt; **Portal da Empresa** e definir as configurações do Portal da Empresa.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### Declaração de privacidade e informações de contato de empresa

O nome da empresa é exibido como o título do Portal da Empresa. Os detalhes e as informações de contato são exibidos para os usuários na tela Contatar TI do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |Nome da empresa|40|Este é o nome exibido como título do Portal da Empresa. **Observação**: apenas caracteres alfanuméricos. Este campo não dá suporte a caracteres especiais.|
    |Nome do contato do departamento de TI|40|Esse nome é exibido na página **Contatar TI**.|
    |Telefone do departamento de TI|20|Este número de contato é exibido na página **Contatar TI**.|
    |Endereço de email do departamento de TI|40|Este endereço de contato é exibido na página **Contatar TI**. Você deve inserir um endereço de email válido no formato **alias@domainname.com**.|
    |Informações adicionais|120|Estas informações são exibidas na página **Contatar TI**.|
    |URL de política de privacidade de empresa|79|Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve digitar uma URL válida no formato https://www.contoso.com.|

### Contatos de suporte
O site de suporte é exibido para os usuários no Portal da Empresa para que eles possam acessar o suporte online.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |URL do site de suporte|150|Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato https://www.contoso.com. Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa.|
    |Nome do site|40|Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, **Ir para o site da TI** será exibido na página **Contatar IT** do Portal da Empresa.|


### Personalização da identidade visual da empresa

Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e uma tela de fundo.

|Nome do campo|Mais informações|
    |----------|----------------|
    |Cores do tema|Selecione uma cor de tema para aplicar ao Portal da Empresa.|
    |Incluir o logotipo da empresa|Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa. Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada. Cada logotipo deve ser um arquivo .png ou .jpg, ter a resolução mínima de 400 x 100 pixels e ter 750 KB ou menos em tamanho.|
    |Escolha um plano de fundo para o aplicativo do Portal da Empresa do [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|Esta configuração afeta somente a tela de fundo do aplicativo do Portal da Empresa do [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Depois de salvar suas alterações, é possível usar os links fornecidos na parte inferior da página do **Portal da Empresa** do console de administração para exibir o site do Portal da Empresa. Esses links não podem ser alterados. Quando um usuário entra, esses links exibem o Portal da Empresa das suas assinaturas.

## Atribuir uma licença de usuário do Intune

Você usa o **Portal de gerenciamento do Office 365** para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD (Azure Active Directory).

1.  Entre no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) usando suas credenciais de administrador de locatário.

2.  Selecione a conta de usuário a que deseja atribuir uma licença de usuário do Intune e marque a caixa de seleção **Microsoft Intune** nas propriedades da conta de usuário.

3.  Agora a conta de usuário será adicionada ao grupo de usuários do Microsoft Intune, o que concede ao usuário permissões para usar o serviço e registrar seus dispositivos para gerenciamento.

## Configurar gerenciamento de dispositivo
Depois de configurar a autoridade de MDM, você precisa configurar o gerenciamento de dispositivos para os sistemas operacionais aos quais sua organização quer dar suporte. As etapas necessárias para configurar o gerenciamento de dispositivos variam de acordo com o sistema operacional. Por exemplo, o sistema operacional Android não requer nenhuma ação no console de administração do Intune. Por outro lado, o Windows e iOS exigem uma relação de confiança entre os dispositivos e o Intune para permitir o gerenciamento.

Configurar o gerenciamento para as seguintes plataformas:
- [Android](set-up-android-management-with-microsoft-intune.md)
- [iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [PCs e laptops Windows](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile e Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

Você também pode:
 - Usar a [conta do gerenciador de registro de dispositivos](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) para registrar vários dispositivos.
 - [Especificar dispositivos da empresa usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) para ajudar a registrar dispositivos e a direcionar a política.



<!--HONumber=Sep16_HO3-->

