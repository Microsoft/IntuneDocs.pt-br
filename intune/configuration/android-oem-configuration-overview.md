---
title: Usar OEMConfig em dispositivos Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Use o Microsoft Intune para gerenciar e usar dispositivos que executam o Android Enterprise com OEMConfig. Veja todas as etapas, incluindo uma visão geral, confira os pré-requisitos, crie o perfil de configuração no Intune e veja uma lista de aplicativos OEMConfig com suporte.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9cc568cbadb683f632ffd2365ab7023cd796f231
ms.sourcegitcommit: 5ad0ce27a30ee3ef3beefc46d2ee49db6ec0cbe3
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76886699"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Usar e gerenciar dispositivos Android Enterprise com o OEMConfig no Microsoft Intune

No Microsoft Intune, você pode usar OEMConfig para adicionar, criar e personalizar configurações específicas do OEM para dispositivos Android Enterprise. Normalmente, OEMConfig é usado para definir configurações que não são internas do Intune. Diferentes OEMs (fabricantes de equipamento original) incluem diferentes configurações. As configurações disponíveis dependem do que o OEM inclui em seu aplicativo OEMConfig.

Esse recurso aplica-se a:  

- Android Enterprise

Este artigo descreve OEMConfig, lista os pré-requisitos, mostra como criar um perfil de configuração e lista os aplicativos OEMConfig com suporte no Intune.

## <a name="overview"></a>Visão geral

As políticas de OEMConfig são um tipo especial de política de configuração do dispositivo, semelhante à [política de configuração do aplicativo](../apps/app-configuration-policies-overview.md). OEMConfig é um padrão definido pelo Google que usa a configuração do aplicativo no Android para enviar configurações de dispositivo para aplicativos escritos por OEMs (fabricantes de equipamento original). Esse padrão permite que OEMs e EMMs (gerenciamento de mobilidade empresarial) criem e deem suporte a recursos específicos dos OEMs de forma padronizada. [Saiba mais sobre OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

Historicamente, os EMMs, como o Intune, criam manualmente o suporte para recursos específicos do OEM depois que eles são introduzidos. Essa abordagem gera esforços duplicados e lentidão na adoção.

Com OEMConfig, o OEM cria um esquema que define os recursos de gerenciamento específicos a ele. O OEM insere o esquema em um aplicativo e, em seguida, coloca esse aplicativo no Google Play. O EMM lê o esquema do aplicativo e o expõe no console do administrador do EMM. O console permite que os administradores do Intune definam as configurações no esquema.

Quando o aplicativo OEMConfig é instalado em um dispositivo, ele usa as configurações definidas no administrador do EMM para gerenciar o dispositivo. As configurações do dispositivo são executadas pelo aplicativo OEMConfig em vez de um agente de MDM criado pelo EMM.

Quando adiciona e aprimora recursos de gerenciamento, o OEM também atualiza o aplicativo no Google Play. Como administrador, você obtém esses novos recursos e atualizações (incluindo correções) sem esperar que o EMMs os incluam.

> [!TIP]
> Só é possível usar OEMConfig com dispositivos que são suporte a esse recurso e têm um aplicativo OEMConfig correspondente. Consulte seu OEM para obter detalhes específicos.

## <a name="before-you-begin"></a>Antes de começar

Ao usar OEMConfig, esteja ciente das seguintes informações:

- O Intune expõe o esquema do aplicativo OEMConfig para que você possa configurá-lo. O Intune não valida nem altera o esquema fornecido pelo aplicativo. Portanto, se o esquema estiver incorreto ou tiver dados imprecisos, esses dados ainda serão enviados aos dispositivos. Se encontrar um problema originado no esquema, entre em contato com o OEM para obter orientações.
- O Intune não influencia nem controla o conteúdo do esquema do aplicativo. Por exemplo, o Intune não tem controle sobre cadeias de caracteres, linguagem, as ações permitidas e assim por diante. Recomendamos entrar em contato com o OEM para obter mais informações sobre como gerenciar seus dispositivos com OEMConfig.
- A qualquer momento, os OEMs podem atualizar os recursos e esquemas com suporte e carregar um novo aplicativo no Google Play. O Intune sempre sincroniza a versão mais recente do aplicativo OEMConfig do Google Play. O Intune não mantém versões antigas do esquema nem do aplicativo. Se encontrar conflitos de versão, recomendamos entrar em contato com o OEM para obter mais informações.
- Atribua um perfil de OEMConfig a um dispositivo. Se vários perfis forem atribuídos ao mesmo dispositivo, você poderá ver um comportamento inconsistente. O modelo de OEMConfig dá suporte apenas a uma política por dispositivo.

## <a name="prerequisites"></a>Pré-requisitos

Para usar OEMConfig em seus dispositivos, tenha em vigor os seguintes requisitos:

- Um dispositivo Android Enterprise registrado no Intune.
- Um aplicativo OEMConfig criado pelo OEM e carregado para o Google Play. Se ele não estiver no Google Play, entre em contato com o OEM para obter mais informações.
- O administrador do Intune tem permissões de RBAC (controle de acesso baseado em função) para **Aplicativos móveis**, **Configurações de Dispositivo** e a permissão de "leitura" no **Android for Work**. Essas permissões são necessárias porque os perfis de OEMConfig usam configurações de aplicativo gerenciado para gerenciar as configurações do dispositivo.

## <a name="prepare-the-oemconfig-app"></a>Preparar o aplicativo OEMConfig

Verifique se o dispositivo dá suporte a OEMConfig, se o aplicativo OEMConfig correto foi adicionado ao Intune e se o aplicativo está instalado no dispositivo. Entre em contato com o OEM para obter essas informações.

> [!TIP] 
> Os aplicativos OEMConfig são específicos do OEM. Por exemplo, instalar um aplicativo OEMConfig da Sony em um dispositivo Zebra Technologies não surte nenhum efeito.

1. Obtenha o aplicativo OEMConfig da Managed Google Play Store. [Adicionar aplicativos do Google Play gerenciados a dispositivos Android Enterprise](../apps/apps-add-android-for-work.md) relaciona as etapas.
2. Alguns OEMs podem fornecer dispositivos com o aplicativo OEMConfig pré-instalado. Se o aplicativo não estiver pré-instalado, use o Intune para [adicionar e implantar o aplicativo nos dispositivos](../apps/apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Criar um perfil de OEMConfig

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Plataforma**: selecione **Android Enterprise**.
    - **Tipo de perfil**: selecione **OEMConfig**.

4. Selecione **Criar**.
5. Em **Básico**, insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Aplicativo OEMConfig**: escolha **Selecionar um aplicativo OEMConfig**.

6. Em **Aplicativo associado**, selecione um aplicativo OEMConfig existente que você adicionou anteriormente > **Selecionar**. Escolha o aplicativo OEMConfig correto para os dispositivos a que você está atribuindo a política.

    Se não vir nenhum aplicativo listado, configure a Managed Google Play e obtenha aplicativos da Managed Google Play Store. [Adicionar aplicativos da Managed Google Play a dispositivos Android Enterprise](../apps/apps-add-android-for-work.md) relaciona as etapas.

    > [!IMPORTANT]
    > Se você adicionou um aplicativo OEMConfig e o sincronizou com a Google Play, mas ele não está listado como um **Aplicativo associado**, talvez seja necessário entrar em contato com o Intune para integrar o aplicativo. Consulte [adicionando um novo aplicativo](#supported-oemconfig-apps) (neste artigo).

7. Selecione **Avançar**.
8. Em **Definir configurações**, selecione o **Designer de Configuração** ou o **Editor de JSON**:

    > [!TIP]
    > Leia a documentação do OEM para garantir que você esteja configurando as propriedades corretamente. Essas propriedades do aplicativo são incluídas pelo OEM, não pelo Intune. O Intune faz a validação mínima das propriedades ou do que você insere. Por exemplo, se você inserir `abcd` como número da porta, o perfil salvará essa informação no estado em que se encontra e implantará em seus dispositivos os valores que você configurar. Certifique-se de inserir as informações corretas.

    - **Designer de Configuração**: quando você seleciona essa opção, as propriedades disponíveis no esquema do aplicativo são mostradas para que você as configure.

      - Menus de contexto no Designer de Configuração indicam que mais opções estão disponíveis. Por exemplo, o menu de contexto pode permitir que você adicione, exclua e reordene as configurações. Essas opções são incluídas pelo OEM. Leia a documentação do aplicativo do OEM para saber como essas opções devem ser usadas para criar perfis.

      - Muitas configurações têm valores padrão fornecidos pelo OEM. Para ver se há um valor padrão, focalize o ícone de informações ao lado da configuração. Uma dica de ferramenta mostra os valores padrão da configuração (se aplicável) e mais detalhes fornecidos pelo OEM.

      - Clicar em **Limpar** exclui uma configuração do perfil. Se uma configuração não estiver no perfil, seu valor no dispositivo não será alterado quando o perfil for aplicado.

      - Se você criar um pacote vazio (não configurado) no Designer de Configuração, ele será excluído ao alternar para o Editor de JSON.

    - **Editor de JSON**: quando você seleciona essa opção, um Editor de JSON é aberto com um modelo do esquema de configuração completo inserido no aplicativo. No editor, personalize o modelo com os valores das diferentes configurações. Se você usar o **Designer de Configuração** para alterar os valores, o Editor de JSON substituirá no modelo os valores do Designer de Configuração.

      - Se você estiver atualizando um perfil existente, o Editor de JSON mostrará as configurações que foram salvas pela última vez com o perfil.

      - Os esquemas de OEMConfig podem ser grandes e complexos. Se preferir atualizar essas configurações usando um editor diferente, selecione o botão **Baixar modelo de JSON**. Use um editor de sua escolha para adicionar seus valores de configuração ao modelo. Em seguida, copie e cole o JSON atualizado na propriedade do **Editor de JSON**.

      - Você pode usar o Editor de JSON para criar um backup de sua configuração. Depois de definir as configurações, use esse recurso para inserir seus valores nas configurações do JSON. Copie e cole o JSON em um arquivo e salve-o. Agora, você tem um arquivo de backup.

    As alterações feitas no Designer de Configuração também são feitas automaticamente no Editor de JSON. Da mesma forma, as alterações feitas no Editor de JSON são feitas automaticamente no Designer de Configuração. Se sua entrada contiver valores inválidos, você não poderá alternar entre o Designer de Configuração e o Editor de JSON até corrigir os problemas.

9. Selecione **Avançar**.
10. Em **Marcas de escopo** (opcional), atribua uma marca para filtrar o perfil para grupos de TI específicos, como `US-NC IT Team` ou `JohnGlenn_ITDepartment`. Para obter mais informações sobre as marcas de escopo, confira [Usar o RBAC e as marcas de escopo para TI distribuída](../fundamentals/scope-tags.md).

    Selecione **Avançar**.

11. Em **Atribuições**, selecione os usuários ou grupos que receberão o perfil. Atribua um perfil a cada dispositivo. O modelo de OEMConfig dá suporte apenas a uma política por dispositivo.

    Para obter mais informações sobre a atribuição de perfis, confira [Atribuir perfis de usuário e dispositivo](device-profile-assign.md).

    Selecione **Avançar**.

12. Em **Examinar + criar**, examine as configurações. Quando você seleciona **Criar**, suas alterações são salvas e o perfil é atribuído. A política também é mostrada na lista de perfis.

Na próxima vez que o dispositivo verificar se há atualizações de configuração, as configurações específicas do OEM que você definiu serão aplicadas ao aplicativo OEMConfig.

> [!NOTE]
> Atualmente, o padrão OEMConfig não inclui relatórios de status. Portanto, por padrão, os perfis mostram o status **Pendente**.

## <a name="supported-oemconfig-apps"></a>Aplicativos OEMConfig com suporte

Em comparação com os aplicativos padrão, os aplicativos OEMConfig expandem os privilégios de configurações gerenciadas concedidos pelo Google para dar suporte a esquemas mais complexos. Atualmente, o Intune dá suporte aos seguintes aplicativos OEMConfig:

-----------------

| OEM | ID do Pacote | Documentação do OEM (se disponível) |
| --- | --- | ---|
| Samsung | com.samsung.android.knox.kpu | [Guia do Administrador de Plug-in do Knox Service](https://docs.samsungknox.com/knox-service-plugin/admin-guide/index.htm) |
| Zebra Technologies | com.zebra.oemconfig.common | [Visão geral do OEMConfig da Zebra](http://techdocs.zebra.com/oemconfig ) |
| Datalogic | com.datalogic.oemconfig | [Documentação do usuário do OEMConfig da Datalogic](https://datalogic.github.io/oemconfig/) |
| Honeywell | com.honeywell.oemconfig |  |
| Kyocera | jp.kyocera.enterprisedeviceconfig |  |
| Spectralink – Códigos de barra | com.spectralink.barcode.service |  |
| Spectralink – Botões | com.spectralink.buttons |  |
| Spectralink – Dispositivo | com.spectralink.slnkdevicesettings  |  |
| Spectralink – Registro em log | com.spectralink.slnklogger |  |
| Spectralink – VQO | com.spectralink.slnkvqo |  |
| HMD Global | com.hmdglobal.app.oemconfig.ironman |  |

-----------------

Se houver um aplicativo OEMConfig para seu dispositivo que não se encontra na tabela acima ou não aparece no console do Intune, envie um email para `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> Os aplicativos OEMConfig precisam ser integrados pelo Intune para que possam ser configurados com perfis de OEMConfig. Quando um aplicativo tem suporte, você não precisa entrar em contato com a Microsoft para saber como configurá-lo em seu locatário. Basta seguir as instruções nesta página.

## <a name="next-steps"></a>Próximas etapas

[Monitorar o status do perfil](device-profile-monitor.md).
