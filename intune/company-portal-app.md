---
title: Como configurar o aplicativo do Portal da Empresa
titleSuffix: Microsoft Intune
description: Saiba como você pode aplicar a identidade visual específica à empresa ao aplicativo do Portal da Empresa do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61d58c794015b0b87f4c9949d9c53e7166925022
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Como configurar o aplicativo Portal da Empresa do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Portal da Empresa do Microsoft Intune é o local em que os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivos, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.        

> [!Tip]        
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.       

Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais. Para isso, na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Identidade Visual do Portal de Empresa** e defina as configurações necessárias.  

> [!Note]       
> Agora, o Portal da Empresa para Windows 10 envia logs de aplicativo diretamente à Microsoft quando o usuário inicia o fluxo de trabalho para obter ajuda com um problema. Isso facilitará a solução de problemas enviados para a Microsoft.  

## <a name="company-contact-information-and-privacy-statement"></a>Declaração de privacidade e informações de contato de empresa        
O nome da empresa é exibido como o título do Portal da Empresa. Os detalhes e as informações de contato são exibidos para os usuários na tela **Contatar TI** do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

Os campos marcados com um asterisco (*) são obrigatórios.       


| Nome do campo | Comprimento máx. | Mais informações |
|---|---|---|
|**Nome da empresa**| 40 | Este é o nome exibido como título do Portal da Empresa. |
|**Nome do contato do departamento de TI** | 40 | Esse nome é exibido na página **Contatar TI**. |
|**Telefone do departamento de TI** | 20 | Este número de contato é exibido na página **Contatar TI**. |
|**Endereço de email do departamento de TI**| 40 | Este endereço de contato é exibido na página **Contatar TI**. Você deve inserir um endereço de email válido no formato `alias@domainname.com`. |
| **Informações adicionais**|    120     | Exibido na página **Contatar TI**. |
| **URL da política de privacidade da empresa** |     79     | Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve inserir uma URL válida no formato `<https://www.contoso.com>`. |

## <a name="support-contacts"></a>Contatos de suporte     
O site de suporte é exibido para os usuários no Portal da Empresa para que eles possam acessar o suporte online.        

|Nome do campo|Comprimento máx.|Mais informações|
|---|---|---|
|**URL do site de suporte**|150|Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato **https://www.contoso.com**. Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa.|
|**Nome do site de suporte**|40|Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, Ir para o site da TI será exibido na página **Contatar IT** do Portal da Empresa.

## <a name="company-branding-customization"></a>Personalização da identidade visual da empresa       
Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano.     

|Nome do campo|Mais informações|
|---|---|
|**Cor de tema**|Selecione uma cor de tema para aplicar ao Portal da Empresa. Você pode escolher entre o seletor de cor ou inserir um código hexadecimal específico.|
|**Mostrar logotipo da empresa**|Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa. Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada. Cada logotipo deve ser um tipo de arquivo .png ou .jpg e ter uma resolução máxima de 400 x 100 pixels e ter 750 KB ou menos em tamanho.<br>Também é possível mostrar o nome da empresa que você inseriu ao lado do logotipo carregado.|

Depois de salvar suas alterações, você pode escolher **Visualizar as configurações no Portal da Web Intune** para ver a aparência de suas configurações.
