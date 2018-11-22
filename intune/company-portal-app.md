---
title: Como configurar o aplicativo do Portal da Empresa
titleSuffix: Microsoft Intune
description: Saiba como você pode aplicar a identidade visual específica à empresa ao aplicativo do Portal da Empresa do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a249962c4ac75e51be082112b884a5825d4ef2a
ms.sourcegitcommit: 490f68479af814fbea1d9bd222011736fcbb1dd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51811505"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Como configurar o aplicativo Portal da Empresa do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Portal da Empresa do Microsoft Intune é o local em que os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivos, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.        

> [!Tip]        
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa. Observe que os usuários devem ter uma licença do Intune atribuída para acessar o site do Portal da Empresa.

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


## <a name="company-identity-branding-customization"></a>Personalização de marca de identidade da empresa      
Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano.     

### <a name="theme-color-and-logo-in-the-company-portal"></a>Cor do tema e logotipo no Portal da Empresa
Aplique uma cor de tema ao Portal da Empresa. Selecione uma cor padrão ou insira um código hexadecimal de seis dígitos para uma cor personalizada.

|Nome do campo|Mais informações|
|---|---|
|**Selecione uma cor padrão ou insira um código hexadecimal de seis dígitos**| Escolha **Padrão** para selecionar visualmente uma cor. Escolha **Personalizado** para selecionar uma cor específica com base em um valor de código hexadecimal.|
|**Escolher cor do tema**| Selecione uma cor de tema para aplicar ao Portal da Empresa. Você pode escolher uma cor padrão ou inserir um código hexadecimal específico. |
|**Exibir**| Selecione se deseja exibir o **Logotipo e o nome da empresa**, **Apenas o logotipo da empresa** ou **Apenas o nome de empresa**. |
|**Fazer upload do logotipo da empresa**|Você pode fazer upload do logotipo da empresa para mostrar no Portal da Empresa. Observe que a cor do texto será escolhida automaticamente para fornecer o mais alto nível de contraste. Para melhorar a aparência, faça upload de um logotipo com uma tela de fundo transparente.<p><ul><li>Tamanho máximo da imagem: 400 px x 400 px</li><li>Tamanho máximo do arquivo: 750 KB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

Depois de fazer upload do logotipo, a área de visualização mostrará o logotipo com a cor de tema. Se você optar por exibir o nome da sua empresa, ele será mostrado em preto ou branco no Portal da Empresa e escolhido automaticamente para fornecer o mais alto nível de contraste com base na cor do seu tema. A área de visualização na tela não mostrará o nome da empresa. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logotipo a ser usado em planos de fundo claro ou brancos
Escolha um logotipo que tenha a melhor aparência em telas de fundo claras ou brancas.

|Nome do campo|Mais informações|
|---|---|
|**Fazer upload do seu logotipo**| Essa opção estará disponível se você tiver escolhido mostrar o logotipo da empresa. Para melhorar a aparência, faça upload de um logotipo com uma tela de fundo transparente.<p><ul><li>Tamanho máximo da imagem: 400 px x 400 px</li><li>Tamanho máximo do arquivo: 750 KB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Imagem de marca para o Portal da Empresa

Exiba uma imagem de marca que reflita a marca da empresa. Depois de salvar suas alterações, você pode escolher **Visualizar as configurações** no Portal da Web do Intune na parte superior da folha para ver a aparência de suas configurações. Observe que você só poderá visualizar a imagem de marca em um dispositivo iOS, e não no Portal da Web do Intune. 

|Nome do campo|Mais informações|
|---|---|
|**Fazer upload de sua imagem de marca**| Essa opção está disponível para que você possa exibir uma imagem de tela de fundo na página de perfil do usuário no aplicativo Portal da Empresa.<p>*Observação*: a imagem pode ser exibida de forma diferente para diversas plataformas.<p><ul><li>Largura de imagem recomendada: superior a 1.125 px, mas não inferior a 640 px</li><li>Tamanho máximo da imagem: 1,3 MB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

A imagem de marca certa pode melhorar a confiança do usuário no Portal da Empresa, apresentando um forte senso de marca da sua empresa. Aqui estão algumas dicas que você talvez queira considerar para adquirir, escolher e otimizar a imagem do Portal da Empresa. 

- Fale com seu departamento de marketing ou arte. Talvez já exista um conjunto aprovado de imagens da marca. Ele também poderá ajudá-lo a otimizar imagens conforme necessário. 

- Considere as composições em orientação de retrato e paisagem. A imagem deve ter suficientes segundo plano suficiente envolvendo o ponto focal. A imagem pode ser cortada de modo diferente, conforme o tamanho e a orientação do dispositivo e a plataforma. 

- Evite usar uma imagem genérica de banco de imagens. A imagem deve refletir a marca da sua empresa e ser familiar para os usuários. Se você não tiver uma, será melhor não usar nenhuma do que usar uma genérica que não tenha significado para o usuário. 

- Remova metadados desnecessários. O arquivo de imagem pode vir com metadados, como o perfil de câmera, localização geográfica, título, legenda e assim por diante. Use uma ferramenta de otimização de imagem remover essas informações para manter a qualidade enquanto cumpre o limite de tamanho do arquivo. 

Depois que uma imagem de marca é adicionada ou alterada no Intune, pode ser que o usuário final não veja a alteração em dispositivos iOS até que o Portal da Empresa reconheça a alteração na inicialização e reinicie para exibir a imagem de marca. 

### <a name="brand-image-examples"></a>Exemplos de imagem de marca

A imagem a seguir mostra um exemplo de imagem da marca iPad:

![Captura de tela de exemplo da imagem da marca iPhone](media/company-portal-app/company-portal-app-03.png)

A imagem a seguir mostra um exemplo de imagem da marca iPhone:

![Captura de tela de exemplo da imagem da marca iPad](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>Atalhos de teclado do Portal da Empresa do Windows

Os usuários finais podem disparar ações de navegação, aplicativos e dispositivos no Portal da Empresa do Windows, usando atalhos de teclado (aceleradores).

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

Os usuários finais também poderão ver os atalhos disponíveis no aplicativo do Portal da Empresa do Windows.

![Captura de tela dos atalhos disponíveis no aplicativo do Portal da Empresa do Windows](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Próximas etapas

- [Adicionar manualmente o aplicativo do Portal da Empresa ao Windows 10 usando o Microsoft Intune](store-apps-company-portal-app.md)
