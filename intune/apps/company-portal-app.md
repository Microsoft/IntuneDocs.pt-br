---
title: Como configurar o aplicativo do Portal da Empresa
titleSuffix: Microsoft Intune
description: Saiba como é possível aplicar a identidade visual específica da empresa ao aplicativo Portal da Empresa do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b750c09207b1950aa27a5f2cae1267503537b6e7
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199206"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Como configurar o aplicativo Portal da Empresa do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Portal da Empresa do Microsoft Intune é o local em que os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivos, a instalação de aplicativos e a localização de informações de assistência do departamento de TI. Além disso, o aplicativo Portal da Empresa permite que o usuário acesse os recursos da empresa com segurança. O aplicativo Portal da Empresa proporciona diversas páginas, como Página Inicial, Aplicativos, Detalhes do aplicativo, Dispositivos e Detalhes do dispositivo. Para localizar rapidamente os aplicativos no Portal da Empresa, você pode filtrá-los na página Aplicativos.

> [!IMPORTANT]
> Para oferecer compatibilidade com o FCM (Firebase Cloud Messaging) do Google, é preciso atualizar seu aplicativo Android do Portal da Empresa para a versão mais recente.  

> [!Tip]
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa. Observe que os usuários devem ter uma licença do Intune atribuída para acessar o site do Portal da Empresa.

Ao personalizar o Portal da Empresa, você ajudará a fornecer uma experiência familiar e útil para os usuários finais. Para fazer isso, no portal do Intune, selecione **Aplicativos de cliente** > **Identidade visual e personalização** e, em seguida, defina as configurações necessárias.

Quando um usuário instala um aplicativo iOS a partir do Portal da Empresa, ele recebe um aviso. Isso ocorre quando o aplicativo iOS está vinculado à loja de aplicativos, a um VPP (programa de compra por volume) ou a um aplicativo de linha de negócios. O aviso permite que os usuários aceitem a ação ou permitam o gerenciamento do aplicativo. O aviso exibe o nome da empresa ou, quando o nome da sua empresa está indisponível, o **Portal da Empresa**. 

> [!Note]
> Se você estiver usando o Azure Governamental, os logs do aplicativo serão oferecidos ao usuário final para decidir como eles compartilharão ao iniciar o processo para obter ajuda com um problema. No entanto, se você não estiver usando o Azure Governamental, o Portal da Empresa para Windows 10 enviará logs do aplicativo diretamente para a Microsoft quando o usuário iniciar o processo para obter ajuda com um problema. Enviar os logs do aplicativo para a Microsoft facilitará a solução de problemas. 

## <a name="company-information-and-privacy-statement"></a>Política de privacidade e informações da empresa
O nome da empresa é exibido como o título do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

| Nome do campo | Comprimento máx. | Mais informações |
|---|---|---|
|**Nome da empresa**| 40 | Esse nome é exibido como o título do Portal da Empresa e exibido como texto em toda a experiência do usuário do Intune. |
| **URL da política de privacidade** |     79     | Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve inserir uma URL válida no formato `<https://www.contoso.com>`. |

> [!NOTE]
> Consistente com a política da Apple e da Microsoft, não vendemos dados coletados pelo nosso serviço a terceiros por qualquer motivo.

## <a name="support-information"></a>Informações de suporte
Insira as informações de suporte da sua empresa para fornecer ao seu funcionário um contato para questões relacionadas ao Intune.

|Nome do campo|Comprimento máx.|Mais informações|
|---|---|---|
|**Nome de contato** | 40 | Esse nome é exibido na página **Ajuda e Suporte**. |
|**Número do telefone** | 20 | Esse número de contato é exibido na página **Ajuda e Suporte** para permitir que os funcionários entrem em contato com o suporte. |
|**Endereço de email**| 40 | Este endereço de contato é exibido na página **Ajuda e Suporte**. Você deve inserir um endereço de email válido no formato `alias@domainname.com`. |
|**Nome do site**| 40 | Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, Ir para o site da TI será exibido na página **Ajuda e Suporte** do Portal da Empresa. |
|**URL do Site**| 150 | Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato `https://www.contoso.com`. Se você não especificar uma URL, nada será exibido para o site de suporte na página **Ajuda e Suporte** do Portal da Empresa. |
| **Informações adicionais**| 120 | Exibidas na página **Ajuda e Suporte**. |


## <a name="company-identity-branding-customization"></a>Personalização de marca de identidade da empresa
Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano.

### <a name="theme-color-and-logo-in-the-company-portal"></a>Cor do tema e logotipo no Portal da Empresa
Aplique uma cor de tema ao Portal da Empresa. Selecione uma cor padrão ou insira um código hexadecimal de seis dígitos para uma cor personalizada.

|Nome do campo|Mais informações|
|---|---|
|**Selecione uma cor padrão ou insira um código hexadecimal de seis dígitos**| Escolha **Padrão** para selecionar visualmente uma cor. Escolha **Personalizado** para selecionar uma cor específica com base em um valor de código hexadecimal.|
|**Escolher cor do tema**| Selecione uma cor de tema para aplicar ao Portal da Empresa. Você pode escolher uma cor padrão ou inserir um código hexadecimal específico. |
|**Exibir**| Selecione se deseja exibir o **Logotipo e o nome da empresa**, **Apenas o logotipo da empresa** ou **Apenas o nome de empresa**. |
|**Fazer upload do logotipo da empresa**|Você pode fazer upload do logotipo da empresa para mostrar no Portal da Empresa. Observe que a cor do texto será escolhida automaticamente para fornecer o mais alto nível de contraste. Para melhorar a aparência, faça upload de um logotipo com uma tela de fundo transparente.<p><ul><li>Tamanho máximo da imagem: 400px x 400px</li><li>Tamanho máximo do arquivo: 750 KB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

Depois de fazer upload do logotipo, a área de visualização mostrará o logotipo com a cor de tema. Se você optar por exibir o nome da sua empresa, ele será mostrado em preto ou branco no Portal da Empresa e escolhido automaticamente para fornecer o mais alto nível de contraste com base na cor do seu tema. A área de visualização na tela não mostrará o nome da empresa. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logotipo a ser usado em planos de fundo claro ou brancos
Escolha um logotipo que tenha a melhor aparência em telas de fundo claras ou brancas.

|Nome do campo|Mais informações|
|---|---|
|**Fazer upload do seu logotipo**| Essa opção estará disponível se você tiver escolhido mostrar o logotipo da empresa. Para melhorar a aparência, faça upload de um logotipo com uma tela de fundo transparente.<p><ul><li>Tamanho máximo da imagem: 400px x 400px</li><li>Tamanho máximo do arquivo: 750 KB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Imagem de marca para o Portal da Empresa

Exiba uma imagem de marca que reflita a marca da empresa. Depois de salvar suas alterações, você pode escolher **Visualizar as configurações** no Portal da Web do Intune na parte superior da folha para ver a aparência de suas configurações. Observe que você só poderá visualizar a imagem de marca em um dispositivo iOS, e não no Portal da Web do Intune. 

|Nome do campo|Mais informações|
|---|---|
|**Fazer upload de sua imagem de marca**| Essa opção permite que você exiba uma imagem de marca. No Portal da Empresa para iOS, isso aparece como uma imagem de plano de fundo na página de perfil do usuário.<p><ul><li>Largura da imagem recomendada: Mais de 1125 px (necessário pelo menos 650 px)</li><li>Tamanho máximo da imagem: 1,3 MB</li><li>Tipo de arquivo: PNG, JPG ou JPEG</li></ul>|

A imagem de marca certa pode melhorar a confiança do usuário no Portal da Empresa, apresentando um forte senso de marca da sua empresa. Aqui estão algumas dicas que você talvez queira considerar para adquirir, escolher e otimizar a imagem do Portal da Empresa. 

- Fale com seu departamento de marketing ou arte. Talvez já exista um conjunto aprovado de imagens da marca. Ele também poderá ajudá-lo a otimizar imagens conforme necessário. 

- Considere as composições em orientação de retrato e paisagem. A imagem deve ter suficientes segundo plano suficiente envolvendo o ponto focal. A imagem pode ser cortada de modo diferente, conforme o tamanho e a orientação do dispositivo e a plataforma. 

- Evite usar uma imagem genérica de banco de imagens. A imagem deve refletir a marca da sua empresa e ser familiar para os usuários. Se você não tiver uma, será melhor não usar nenhuma do que usar uma genérica que não tenha significado para o usuário. 

- Remova metadados desnecessários. O arquivo de imagem pode vir com metadados, como o perfil de câmera, localização geográfica, título, legenda e assim por diante. Use uma ferramenta de otimização de imagem remover essas informações para manter a qualidade enquanto cumpre o limite de tamanho do arquivo. 

Depois que uma imagem de marca é adicionada ou alterada no Intune, pode ser que o usuário final não veja a alteração em dispositivos iOS até que o Portal da Empresa reconheça a alteração na inicialização e reinicie para exibir a imagem de marca. 

### <a name="brand-image-examples"></a>Exemplos de imagem de marca

A imagem a seguir mostra um exemplo de imagem da marca iPad:

![Captura de tela de exemplo da imagem da marca iPhone](./media/company-portal-app/company-portal-app-03.png)

A imagem a seguir mostra um exemplo de imagem da marca iPhone:

![Captura de tela de exemplo da imagem da marca iPad](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Personalização da política de privacidade

Você pode personalizar a política de privacidade que é exibida para sua organização em dispositivos iOS gerenciados. Essa mensagem lista os itens que sua organização não pode ver nem fazer em dispositivos iOS gerenciados.

Em **Personalização do Portal da Empresa** > **Gerenciamento de dispositivos e mensagem de privacidade**, você pode:

- Aceitar o **Padrão** para usar a lista conforme ela é mostrada ou
- Escolher **Personalizar** para personalizar a lista de itens que sua organização não pode ver nem fazer em dispositivos iOS gerenciados. Você pode usar [markdown](https://daringfireball.net/projects/markdown/) para adicionar marcadores, negrito, itálico e links.

## <a name="company-portal-derived-credentials-for-ios-devices"></a>Credenciais derivadas do Portal da Empresa para dispositivos iOS
O Intune dá suporte às Credenciais Derivadas de PIV (Verificação de Identidade Pessoal) e CAC (Cartão de Acesso Comum) em parceria com os provedores de credenciais DISA Purebred, Entrust Datacard e Intercede. Os usuários finais passarão por etapas adicionais após o registro de seu dispositivo iOS para verificar sua identidade no aplicativo do Portal da Empresa. As Credenciais Derivadas serão habilitadas para os usuários primeiro por meio da configuração de um provedor de credenciais para seu locatário e, em seguida, do direcionamento de um perfil que usa Credenciais Derivadas para usuários ou dispositivos.

> [!NOTE]
> O usuário verá instruções sobre as credenciais derivadas com base no link que você especificou por meio do Intune.

Para obter mais informações sobre credenciais derivadas para dispositivos iOS, confira [Usar credenciais derivadas no Microsoft Intune](~/protect/derived-credentials.md).

## <a name="dark-mode-for-ios-company-portal"></a>Modo escuro para Portal da Empresa no iOS

O Modo escuro está disponível para o Portal da Empresa no iOS. Os usuários podem baixar aplicativos da empresa, gerenciar seus dispositivos e obter suporte de TI no esquema de cores de sua escolha, com base nas configurações do dispositivo. O Portal da Empresa para iOS corresponderá automaticamente às configurações do dispositivo do usuário final para o modo escuro ou claro. 

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
| Dispositivos | Disponível | Ctrl+D |

Os usuários finais também poderão ver os atalhos disponíveis no aplicativo do Portal da Empresa do Windows.

![Captura de tela dos atalhos disponíveis no Portal da Empresa do Windows](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>Ações de dispositivo de autoatendimento do usuário no Portal da Empresa

Os usuários podem executar ações em seus dispositivos locais ou remotos por meio do aplicativo Portal da Empresa ou site. As ações que um usuário pode executar variam de acordo com a plataforma e a configuração do dispositivo. Em todos os casos, as ações de dispositivo remoto só podem ser executadas pelo Usuário primário do dispositivo.
- **Desativar**: remove o dispositivo do Gerenciamento do Intune. No aplicativo e site do Portal da Empresa, isso é mostrado como **Remover**.
- **Apagar**: esta ação inicia uma redefinição do dispositivo. No site do Portal da Empresa, isso é mostrado como **Redefinir** ou **Redefinir aos padrões de fábrica** no aplicativo iOS do Portal da Empresa.
- **Renomear**: esta ação altera o nome do dispositivo que o usuário pode ver no Portal da Empresa. Ela não altera o nome do dispositivo local, apenas a listagem no Portal da Empresa.
- **Sincronizar**: esta ação inicia um check-in do dispositivo com o serviço do Intune. Essa ação é exibida como **Verificar Status** no Portal da Empresa.
- **Bloqueio remoto**: bloqueia o dispositivo e exige um PIN para desbloqueá-lo.
- **Redefinir senha**: esta ação é usada para redefinir a senha do dispositivo. Em dispositivos iOS, a senha será removida e o usuário final será solicitado a inserir um novo código nas configurações. Em dispositivos Android compatíveis, uma nova senha é gerada pelo Intune e exibida temporariamente no Portal da Empresa.
- **Recuperação de chave**: esta ação é usada para encontrar uma chave de recuperação pessoal para dispositivos macOS criptografados no site do Portal da Empresa. 

### <a name="self-service-actions"></a>Ações de autoatendimento

Algumas plataformas e configurações não permitem ações de dispositivos de autoatendimento. Esta tabela abaixo fornece mais detalhes sobre as ações de autoatendimento:

|  | Windows 10<sup>(3)</sup> | iOS/iPadOS<sup>(3)</sup> | MacOS<sup>(3)</sup> | Android<sup>(3)</sup> |
|----------------------|--------------------------|-------------------|-----------------------------------|-------------------------|
| Desativar | Disponível<sup>(1)</sup> | Disponível | Disponível | Disponível<sup>(7)</sup> |
| Apagamento | Disponível | Disponível<sup>(5)</sup> | NA | Disponível<sup>(7)</sup> |
| Renomear<sup>(4)</sup> | Disponível | Disponível | Disponível | Disponível |
| Sincronização | Disponível | Disponível | Disponível | Disponível |
| Bloqueio remoto | Apenas Windows Phone | Disponível | Disponível | Disponível |
| Redefinir Senha | Apenas Windows Phone | Disponível <sup>(8)</sup> | NA | Disponível<sup>(6)</sup> |
| Recuperação de chave | NA | NA | Disponível<sup>(2)</sup> | NA |

<sup>(1)</sup> A ação **Desativar** está sempre bloqueada em dispositivos Windows ingressados no Azure AD.<br>
<sup>(2)</sup> A **Recuperação de Chave** para MacOS está disponível somente pelo Portal da Web.<br>
<sup>(3)</sup> Todas as ações remotas serão desabilitadas com o uso de um registro do Gerenciador de Registro do Dispositivo.<br>
<sup>(4)</sup> A ação **Renomear** muda apenas o nome do dispositivo no aplicativo do Portal da Empresa ou no Portal da Web, não no dispositivo.<br>
<sup>(5)</sup> A ação **Apagar** não está disponível nos dispositivos iOS registrados do usuário.<br>
<sup>(6)</sup> Não há suporte para a **Redefinição de Senha** em algumas configurações do Android e Android Enterprise. Para saber mais, confira [Redefinir ou remover uma senha de dispositivo no Intune](../remote-actions/device-passcode-reset.md).<br>
<sup>(7)</sup> As ações **Desativar** e **Apagar** não estão disponíveis em cenários de Proprietário de Dispositivo Android Enterprise (COPE, COBO, COSU).<br> 
<sup>(8)</sup> A ação **Redefinir Senha** não tem suporte nos dispositivos iOS registrados do usuário.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar manualmente o aplicativo do Portal da Empresa ao Windows 10 usando o Microsoft Intune](company-portal-app.md)
