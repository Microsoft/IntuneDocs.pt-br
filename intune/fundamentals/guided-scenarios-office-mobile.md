---
title: Cenário guiado – Aplicativos móveis do Microsoft Office seguros
titleSuffix: Microsoft Intune
description: Saiba mais sobre o cenário guiado para implantar aplicativos móveis do Microsoft Office do portal de Gerenciamento de Dispositivos do Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0232855773626693d848f77e561c51d281739215
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514601"
---
# <a name="guided-scenario---secure-microsoft-office-mobile-apps"></a>Cenário guiado – Aplicativos móveis seguros do Microsoft Office 

Seguindo este cenário guiado no portal de Gerenciamento de Dispositivos, você pode habilitar a proteção básica de aplicativo do Intune em dispositivos iOS/iPadOS e Android.

A proteção de aplicativo que você habilita impõe as seguintes ações: 
- Criptografar arquivos de trabalho.
- Exigir um PIN para acessar os arquivos de trabalho.
- Exigir que o PIN seja redefinido após cinco tentativas com falha.
- Bloquear o backup de arquivos de trabalho nos serviços de backup do iTunes, iCloud ou Android.  
- Exigir que arquivos de trabalho apenas sejam salvos no OneDrive ou SharePoint.
- Impedir que aplicativos protegidos carreguem arquivos de trabalho em dispositivos com jailbreak ou desbloqueados por rooting.
- Bloquear o acesso a arquivos de trabalho se o dispositivo estiver offline por 720 minutos.
- Remover arquivos de trabalho se o dispositivo estiver offline por 90 dias. 

## <a name="background"></a>Tela de fundo

Os aplicativos móveis do Office, bem como o Microsoft Edge para Dispositivos Móveis, dão suporte à identidade dupla. A identidade dupla permite que os aplicativos gerenciem arquivos de trabalho separadamente de arquivos pessoais. 

![Imagem de dados corporativos versus dados pessoais](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-01.png)

As [políticas de proteção de aplicativo do Intune](~/apps/app-protection-policy.md) ajudam a proteger seus arquivos de trabalho nos dispositivos registrados no Intune. Use também as políticas de proteção de aplicativo em dispositivos dos funcionários que não estão registrados no gerenciamento do Intune. Nesse caso, mesmo que sua empresa não gerencie o dispositivo, ainda é necessário verificar se os arquivos de trabalho e recursos estão protegidos.

Você pode usar as Políticas de proteção de aplicativo para impedir que usuários salvem arquivos de trabalho em locais não protegidos. Você também pode restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção do aplicativo. As configurações de política de proteção de aplicativo incluem:
- Políticas de realocação de dados, como **Salvar cópias de dados da organização** e **Restringir recortar, copiar e colar**.
- Configurações de política de acesso para exigir PIN simples para acesso e bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou desbloqueados por rooting.

O acesso condicional baseado no aplicativo e o gerenciamento de aplicativo cliente adicionam uma camada de segurança, garantindo que apenas os aplicativos cliente que dão suporte às políticas de Proteção de Aplicativo do Intune podem acessar o Exchange Online e outros serviços do Office 365.

Você poderá bloquear os aplicativos de email internos no iOS/iPadOS e no Android quando permitir que apenas o aplicativo Microsoft Outlook acesse o Exchange Online. Além disso, bloqueie o acesso ao SharePoint Online por aplicativos que não têm as políticas de Proteção de Aplicativo do Intune aplicadas.

Neste exemplo, o administrador aplicou políticas de proteção de aplicativo ao aplicativo Outlook seguidas por uma regra de acesso condicional que adiciona o aplicativo Outlook a uma lista aprovada de aplicativos que podem ser usados ao acessar o email corporativo.

![Fluxo de processos de acesso condicional do aplicativo Outlook](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-02.png)

## <a name="prerequisites"></a>Pré-requisitos

Você precisará seguir as permissões de administrador do Intune:

   - Permissões de leitura, criação, exclusão e atribuição de aplicativos gerenciados
   - Permissões de leitura, criação e atribuição de conjuntos de políticas
   - Permissão de leitura da organização

## <a name="step-1---introduction"></a>Etapa 1 – Introdução

Seguindo o cenário guiado de **Proteção de Aplicativo do Intune**, você consegue impedir que dados da sua organização sejam vazados ou compartilhados externamente. 

Os usuários de iOS/iPadOS e Android atribuídos precisarão inserir um PIN ao abrir aplicativos do Office. Depois de 5 tentativas de PIN com falha, os usuários precisam redefinir o PIN. Se você já precisar de um PIN de dispositivo, os usuários não serão afetados.

### <a name="what-you-will-need-to-continue"></a>Do que você precisará para continuar

Nós perguntaremos sobre os aplicativos e usuários necessários e o que é preciso para acessá-los. Verifique se você tem as seguintes informações à disposição:
- Lista de aplicativos do Office aprovados para uso corporativo.
- Requisitos de PIN para iniciar aplicativos aprovados em dispositivos não gerenciados.

## <a name="step-2---basics"></a>Etapa 2 – Conceitos básicos

Nesta etapa, você deverá inserir um **Prefixo** e uma **Descrição** para sua nova política de proteção de aplicativo. À medida que você adiciona o **Prefixo**, os detalhes relacionados aos recursos que o cenário guiado cria serão atualizados. Esses detalhes facilitarão a localização de suas políticas posteriormente se você precisar alterar as atribuições e a configuração. 

> [!TIP]
> Considere anotar os recursos que serão criados para poder consultá-los posteriormente.

## <a name="step-3---apps"></a>Etapa 3 – Aplicativos

Para ajudar você a começar, este cenário guiado seleciona previamente os seguintes aplicativos móveis para proteção em dispositivos iOS/iPadOS e Android:
- Microsoft Excel 
- Microsoft Word 
- Microsoft Teams 
- Microsoft Edge 
- Microsoft PowerPoint 
- Microsoft Outlook 
- Microsoft OneDrive 

Esse cenário guiado também configurará esses aplicativos para abrir links da Web no Microsoft Edge para garantir que os sites de trabalho sejam abertos em um navegador protegido.

Modifique a lista de aplicativos gerenciados por política que você deseja proteger. Adicione ou remova aplicativos desta lista. 

Quando você tiver selecionado os aplicativos, clique em **Avançar**.

## <a name="step-4---configuration"></a>Etapa 4 – Configuração

Nesta etapa, você deve configurar os requisitos para acessar e compartilhar os arquivos corporativos e emails nesses aplicativos. Por padrão, os usuários podem salvar dados nas contas do OneDrive e SharePoint de sua organização.

| Setting | Descrição | Valor padrão |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Tipo de PIN | Os PINs numéricos são compostos por todos os números. As senhas são compostas por caracteres alfanuméricos e caracteres especiais.  No iOS/iPadOS, para configurar o tipo de “Senha”, é necessário que o aplicativo tenha o SDK do Intune versão 7.1.12 ou superior. O tipo numérico não tem nenhuma restrição de versão do SDK do Intune. | Numérico |
| Selecionar tamanho mínimo do PIN | Especifique o número mínimo de dígitos em uma sequência de PIN. | 6 |
| Verificar novamente os requisitos de acesso após (minutos de inatividade) | Se o aplicativo gerenciado por política estiver inativo por mais tempo do que o número de minutos de inatividade especificado, o aplicativo solicitará que os requisitos de acesso (ou seja, PIN, configuração de inicialização condicional) sejam verificados novamente depois que o aplicativo for iniciado. | 30 |
| Imprimir dados da organização | Se bloqueado, o aplicativo não poderá imprimir dados protegidos. | Bloquear |
| Abrir links de aplicativos gerenciados por política em navegadores não gerenciados | Se bloqueados, os links de aplicativos gerenciados por política deverão ser abertos em um navegador gerenciado. | Bloquear |
| Copiar dados para aplicativos não gerenciados | Se bloqueados, os dados gerenciados permanecerão nos aplicativos gerenciados. | Allow |

## <a name="step-5---assignments"></a>Etapa 5 – Atribuições

Nesta etapa, você poderá escolher os grupos de usuários que deseja incluir para garantir que eles tenham acesso aos seus dados corporativos. A proteção de aplicativo é atribuída a usuários, e não a dispositivos; assim, seus dados corporativos serão protegidos, independentemente do dispositivo usado e do seu status de registro.

Os usuários sem políticas de proteção de aplicativo e configurações de acesso condicional atribuídas poderão salvar dados de seu perfil corporativo em aplicativos pessoais e armazenamento local não gerenciado em dispositivos móveis. Eles também podem se conectar a serviços de dados corporativos, como o Microsoft Exchange, com aplicativos pessoais.

## <a name="step-6---review--create"></a>Etapa 6 – Examinar + criar

A etapa final permite que você examine um resumo das configurações que você definiu. Após examinar suas escolhas, clique em **Criar** para concluir o cenário guiado. Depois que o cenário guiado estiver concluído, uma tabela de recursos será exibida. Você pode editar esses recursos posteriormente. No entanto, depois que você sair da exibição de resumo, a tabela não será salva.

> [!IMPORTANT]
> Depois que o cenário guiado estiver concluído, ele exibirá um resumo. Você pode modificar os recursos listados no resumo posteriormente. No entanto, a tabela que exibe esses recursos não será salva.
## <a name="next-steps"></a>Próximas etapas

- Aprimore a segurança de arquivos de trabalho atribuindo aos usuários uma política de acesso condicional baseada em aplicativo para proteger serviços de nuvem contra o envio de arquivos de trabalho a aplicativos não protegidos. Para obter mais informações, confira [Configurar políticas de Acesso Condicional baseadas em aplicativo com o Intune](~/protect/app-based-conditional-access-intune-create.md).

