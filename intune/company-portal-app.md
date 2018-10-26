---
title: Como configurar o aplicativo do Portal da Empresa
titleSuffix: Microsoft Intune
description: Saiba como você pode aplicar a identidade visual específica à empresa ao aplicativo do Portal da Empresa do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01de402a48362f04680c569c40a812b6a4b83cc6
ms.sourcegitcommit: 38afcff149f9c86e92e5f1eccaa927859c395926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49307399"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Como configurar o aplicativo Portal da Empresa do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Portal da Empresa do Microsoft Intune é o local em que os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivos, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.        

> [!Tip]        
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.       

Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais. Para isso, na carga de trabalho **Aplicativos clientes**, escolha **Configurar** > **Identidade Visual do Portal da Empresa** e defina as configurações necessárias.  

> [!Note]       
> Se você estiver usando o Azure Governamental, os logs do aplicativo serão oferecidos ao usuário final para decidir como eles compartilharão ao iniciar o processo para obter ajuda com um problema. No entanto, se você não estiver usando o Azure Governamental, o Portal da Empresa para Windows 10 enviará logs do aplicativo diretamente para a Microsoft quando o usuário iniciar o processo para obter ajuda com um problema. Enviar os logs do aplicativo para a Microsoft facilitará a solução de problemas. 

## <a name="company-information-and-privacy-statement"></a>Política de privacidade e informações da empresa        
O nome da empresa é exibido como o título do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

Os campos marcados com um asterisco (*) são obrigatórios.       


| Nome do campo | Comprimento máx. | Mais informações |
|---|---|---|
|**Nome da empresa**| 40 | Esse nome é exibido como o título do Portal da Empresa e exibido como texto em toda a experiência do usuário do Intune. |
| **URL da política de privacidade** |     79     | Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve inserir uma URL válida no formato `<https://www.contoso.com>`. |

## <a name="support-information"></a>Informações de suporte      
Insira as informações de suporte da sua empresa para fornecer ao seu funcionário um contato para questões relacionadas ao Intune.       

|Nome do campo|Comprimento máx.|Mais informações|
|---|---|---|
|**Nome de contato** | 40 | Esse nome é exibido na página **Contatar TI**. |
|**Número do telefone** | 20 | Esse número de contato é exibido na página **Contate a TI** para habilitar os funcionários a contatarem o suporte. |
|**Endereço de email**| 40 | Este endereço de contato é exibido na página **Contatar TI**. Você deve inserir um endereço de email válido no formato `alias@domainname.com`. |
|**Nome do site**| 40 | Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, Ir para o site da TI será exibido na página **Contatar IT** do Portal da Empresa. |
|**URL do Site**| 150 | Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato `https://www.contoso.com`. Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa. |
| **Informações adicionais**| 120 | Exibido na página **Contatar TI**. |


## <a name="company-branding-customization"></a>Personalização da identidade visual da empresa       
Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano. Para visualizar rapidamente a configuração de identidade visual sem um dispositivo de teste, você pode ir para [portal.manage.microsoft.com](https://portal.manage.microsoft.com). Observe que o logotipo que você carregou será usado para modelos de email.      

### <a name="theme-color"></a>Cores do tema
Aplique uma cor de tema ao Portal da Empresa. Selecione uma cor padrão ou insira um código hexadecimal de seis dígitos para uma cor personalizada.

|Nome do campo|Mais informações|
|---|---|
|**Tipo de cor**| Selecione uma cor de tema para aplicar ao Portal da Empresa. Você pode escolher uma cor padrão ou inserir um código hexadecimal específico. |
|**Escolher cor** ou **código de cor hexadecimal**| Selecione uma cor de tema para aplicar ao Portal da Empresa. Você pode escolher uma cor padrão ou inserir um código hexadecimal específico. Essas opções são fornecidas com base no **Tipo de cor** que você selecionar.  |

### <a name="company-logo"></a>Logotipo da empresa
Carregue o logotipo da empresa para torná-lo visível em toda a experiência do usuário do Intune.

|Nome do campo|Mais informações|
|---|---|
|**Mostrar logotipo da empresa**|Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa. Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada. |
|**Carregar um logotipo para usar em planos de fundo de cor de tema**| Essa opção estará disponível se você tiver escolhido mostrar o logotipo da empresa. O logotipo deve ser um tipo de arquivo .png ou .jpg, ter uma resolução máxima de 400 x 400 pixels e ter um tamanho de 750 KB ou menos. |
|**Carregar logotipo a ser usado em telas de fundo claras**| Essa opção estará disponível se você tiver escolhido mostrar o logotipo da empresa. O logotipo deve ser um tipo de arquivo .png ou .jpg, ter uma resolução máxima de 400 x 400 pixels e ter um tamanho de 750 KB ou menos. |
|**Mostrar o nome da empresa ao lado do logotipo**| Selecione essa opção para mostrar o nome da empresa inserido ao lado do logotipo carregado. |

Depois de salvar suas alterações, você pode escolher **Visualizar as configurações no Portal da Web do Intune** na parte superior da folha para ver a aparência de suas configurações.

## <a name="windows-company-portal-keyboard-shortcuts"></a>Atalhos de teclado do Portal da Empresa do Windows

Os usuários finais podem disparar ações de navegação, aplicativo e dispositivo no Portal da Empresa do Windows usando atalhos de teclado (aceleradores).

Os atalhos de teclado a seguir estão disponíveis no aplicativo do Portal da Empresa do Windows.

| Área | Descrição | Atalho de teclado |
|:------------------:|:--------------:|:-----------------:|
| Menu de navegação | Navegação | Alt+M |
|  | Início | Alt+H |
|  | Todos os aplicativos | Alt+A |
|  | Aplicativos instalados | Alt+I |
|  | Enviar comentários | Alt+F |
|  | Meu perfil | Alt+U |
|  | Configurações | Alt+T |
| Página inicial – Bloco do dispositivo | Renomear | F2 |
|  | Remover | Ctrl+D ou Excluir |
|  | Verificar acesso | Ctrl+M ou F9 |
| Detalhes do dispositivo | Renomear | F2 |
|  | Remover | Ctrl+D ou Excluir |
|  | Verificar acesso | Ctrl+M ou F9 |
| Detalhes do aplicativo | Instalar | Ctrl+I |

## <a name="next-steps"></a>Próximas etapas

- [Adicionar manualmente o aplicativo do Portal da Empresa ao Windows 10 usando o Microsoft Intune](store-apps-company-portal-app.md)