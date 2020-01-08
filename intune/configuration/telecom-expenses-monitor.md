---
title: Configurar um serviço de gerenciamento de despesas de telecomunicações no Microsoft Intune – Azure| Microsoft Docs
titleSuffix: ''
description: Integre o Microsoft Intune ao serviço de gerenciamento de despesas de telecomunicações do Saaswedo para monitorar o uso de dados e definir limites em dispositivos Android e iOS.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c97a3ad329ce0e431c6dc8ef318306e4e002f36
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207104"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Configurar um serviço de gerenciamento de despesas de telecomunicações no Intune



O Intune permite que você gerencie as despesas de telecomunicações decorrentes da utilização de dados em dispositivos móveis da empresa. O Intune se integra ao [Gerenciamento de despesas de telecomunicações do Datalert](http://datalert.biz/get-started) da Saaswedo. O Datalert é uma solução de gerenciamento de despesas de telecomunicações em tempo real que gerencia o uso de dados de telecomunicações. Ele pode ajudar a evitar preços elevados e inesperados de dados e roaming para seus dispositivos gerenciados pelo Intune.

A integração com o Datalert permite definir, monitorar e impor limites de uso de dados de roaming e doméstico. Quando os limites excedem o que foi definido, alertas automatizados são disparados. Você também pode configurar o serviço para aplicar diferentes ações a indivíduos ou grupos de usuários finais, como desabilitar roaming ou exceder o limite. O console de gerenciamento do Datalert inclui relatórios do uso de dados e informações de monitoramento.

A seguinte imagem mostra como o Intune se integra ao Datalert:

  ![Diagrama de integração do Intune e Datalert](./media/telecom-expenses-monitor/tem-datalert-intune-solution-diagram.png)

Para usar o serviço Datalert com o Intune, há algumas definições de configuração no Datalert e no Intune. Este artigo mostra como:

- Definir as configurações no console do Datalert para conectar o serviço Datalert ao Intune.
- Confirmar se essa conexão está ativa e habilitada no Intune.
- Usar o Intune para adicionar o aplicativo Datalert a seus dispositivos.
- Desligar o serviço Datalert e para o Intune (opcional).

## <a name="supported-platforms"></a>Plataformas com Suporte

- Android 4.4 e dispositivos mais recentes compatíveis com Knox (Samsung)

  [Versões do Android que dão suporte a Knox](https://seap.samsung.com/faq/what-versions-android-support-knox-standard-and-knox-premium-sdks-0) (abre o site da Samsung) lista as versões com suporte a Knox.

- iOS 8.0 e posterior

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura para Microsoft Intune e acesso ao [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431)
- Uma assinatura do [Datalert](http://www.datalert.biz/) (abre o site do Datalert)

## <a name="telecom-expense-management-providers"></a>Provedores de gerenciamento de despesas de telecomunicações

O Intune se integra aos seguintes provedores de gerenciamento de despesas de telecomunicações:

- [Serviço de gerenciamento de despesas de telecomunicações do Saaswedo Datalert](http://www.datalert.biz/) (abre o site do Datalert)

## <a name="deploy-the-intune-and-datalert-solution"></a>Implantar a solução do Intune e do Datalert

### <a name="step-1-connect-the-datalert-service-to-intune"></a>Etapa 1: Conectar o serviço Datalert ao Intune

1. Entre no console de gerenciamento do Datalert com suas credenciais de administrador.

2. No console, acesse a guia **Configurações** > **Configuração MDM**.

3. Escolha **Desbloquear**. **Desbloquear** permite alterar ou atualizar as configurações na página.

4. Em **Conexão do Datalert/Intune** > **Servidor MDM**, escolha **Microsoft Intune**.

5. Como **Domínio do Azure AD**, insira sua ID de locatário do Azure. Escolha **Conexão**.

    Quando você escolhe **Conexão**, o serviço Datalert faz check-in no Intune. E confirma se não há conexões Datalert existentes. Depois de alguns segundos, uma página de entrada do Microsoft será exibida, seguida da autenticação do Datalert Azure.

6. Na página de autenticação da Microsoft, selecione **Aceitar**.

    Você será redirecionado para uma página de **agradecimento** do Datalert, que se fechará depois de alguns segundos. O Datalert valida a conexão e exibe uma marca de seleção verde ao lado de itens validados. Se a validação falhar, você verá uma mensagem em vermelho. Entre em contato com o suporte do Datalert para obter ajuda.

    A imagem a seguir mostra as marcas de seleção verdes quando a conexão é realizada com êxito:

      ![Página do Datalert mostrando a conexão bem-sucedida](./media/telecom-expenses-monitor/tem-datalert-connection.png)

7. Em **Consentimento ADAL/Aplicativo Datalert**, defina a opção como **Ligada**. Na página de autenticação da Microsoft, selecione **Aceitar**.

    Você será redirecionado para uma página de **agradecimento** do Datalert, que se fechará depois de alguns segundos. O Datalert valida a conexão e exibe uma marca de seleção verde ao lado de itens validados. Se a validação falhar, você verá uma mensagem em vermelho. Entre em contato com o suporte do Datalert para obter ajuda.

    A imagem a seguir mostra as marcas de seleção verdes quando a conexão é realizada com êxito:

      ![Página do Datalert mostrando a conexão bem-sucedida](./media/telecom-expenses-monitor/tem-datalert-adal-consent.png)

8. Em **Gerenciamento de perfis MDM (opcional)** , defina a opção como **Ligado**. Essa configuração permite que o Datalert leia os perfis disponíveis no Intune para ajudar você a configurar políticas. 

    Na página de autenticação da Microsoft, selecione **Aceitar**.

    Você será redirecionado para uma página de **agradecimento** do Datalert, que se fechará depois de alguns segundos. O Datalert valida a conexão e exibe uma marca de seleção verde ao lado de itens validados. Se a validação falhar, você verá uma mensagem em vermelho. Entre em contato com o suporte do Datalert para obter ajuda.

    A imagem a seguir mostra as marcas de seleção verdes quando a conexão é realizada com êxito:

   ![Página do Datalert mostrando a conexão bem-sucedida](./media/telecom-expenses-monitor/tem-datalert-mdm-profiles.png)

### <a name="step-2-confirm-telecom-expense-management-is-active-in-intune"></a>Etapa 2: Confirmar se o gerenciamento de despesas de telecomunicações está ativo no Intune

Depois de concluir a Etapa 1, sua conexão será habilitada automaticamente. No Intune, o status da conexão mostra **Ativo**. Para confirmar se o status está ativo, use as seguintes etapas:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatário** > **Conectores e tokens** > **Gerenciamento de despesas de telecomunicações**. Procure o status de conexão **Ativo**:

   ![Página do Intune mostrando o status da conexão do Datalert Ativa](./media/telecom-expenses-monitor/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-devices"></a>Etapa 3: implantar o aplicativo Datalert nos dispositivos

Para confirmar que o uso de dados será coletado apenas de linhas pertencentes à organização, não deixe de:

- Criar categorias de dispositivo no Intune.
- Direcionar o aplicativo Datalert apenas para telefones corporativos.

Esta seção lista essas etapas.

#### <a name="create-device-categories-and-device-groups-mapped-to-your-categories"></a>Criar grupos e categorias de dispositivos mapeados para suas categorias

Dependendo das necessidades da sua organização, crie pelo menos duas categorias de dispositivo, por exemplo, Corporativo e Pessoal. Em seguida, crie grupos de dispositivos dinâmicos para cada categoria. Você pode criar mais categorias para sua organização, conforme necessário.

Para criar categorias de dispositivo no Intune, confira [Mapear dispositivos para grupos](../enrollment/device-group-mapping.md).

Essas categorias são mostradas aos usuários durante o registro ([registrar dispositivos Android](../enrollment/android-enroll.md)). Dependendo de qual categoria os usuários escolherem, o dispositivo registrado será movido para o grupo de dispositivo correspondente.

  ![Captura de tela do painel Adicionar uma política](./media/telecom-expenses-monitor/tem-dynamic-membership-rules.png)

#### <a name="add-the-datalert-app-to-intune"></a>Adicionar o aplicativo Datalert ao Intune

As etapas a seguir adicionam o aplicativo Datalert. O iOS é usado como exemplo. [Adicionar aplicativos](../apps/apps-add.md) e [Usar marcas de escopo](../fundamentals/scope-tags.md) oferecem informações mais específicas sobre essas etapas.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.

2. Escolha seu **Tipo de aplicativo**. Por exemplo, para o iOS, escolha **iOS – App Store**.

3. Em **Pesquisar na App Store**, digite **Datalert** para localizar o aplicativo Datalert.

4. Escolha o aplicativo **Datalert** > **Escolher**:

   ![Adicionar o aplicativo Datalert da App Store aos aplicativos cliente do Intune](./media/telecom-expenses-monitor/tem-select-app-from-apple-app-store.png)

5. Insira todas as propriedades adicionais, como as informações do aplicativo e as marcas de escopo:

   ![Insira as propriedades do aplicativo, incluindo o nome e a descrição e escolha o sistema operacional e outras configurações para o aplicativo no Intune](./media/telecom-expenses-monitor/tem-steps-to-create-the-app.png)

6. Escolha **OK** > **Adicionar** para salvar suas alterações. O aplicativo Datalert é mostrado na lista.

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Atribuir o aplicativo Datalert ao grupo de dispositivos corporativos

1. Em **Aplicativos** > **Todos os aplicativos**, escolha o aplicativo Datalert que você adicionou na etapa anterior.

2. Escolha **Atribuições** > **Adicionar grupo**. Escolha como o aplicativo é atribuído. O documento [Atribuir aplicativos a grupos no Intune](../apps/apps-deploy.md) tem mais detalhes sobre essas configurações.

    Nestas etapas, você escolherá se deseja tornar a instalação do aplicativo obrigatória ou opcional para o grupo. O exemplo a seguir mostra a instalação como obrigatória. Quando necessário, os usuários deverão instalar o aplicativo Datalert depois de registrar seu dispositivo.

   ![Captura de tela do painel Adicionar uma política](./media/telecom-expenses-monitor/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-organization-phone-lines-to-the-datalert-console"></a>Etapa 4: adicionar linhas telefônicas corporativas ao console do Datalert

Agora os serviços Intune e Datalert estão configurados para se comunicarem entre si. A seguir, adicione linhas telefônicas corporativas pagas ao console do Datalert. E insira limites e ações para violações de uso de celular ou roaming. É possível adicionar manualmente linhas telefônicas corporativas pagas ao console do Datalert ou adicioná-las automaticamente depois que o dispositivo é registrado no Intune.

Para definir esses itens, vá para a [Configuração do Datalert para Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (abre o site do Datalert). Na guia **Configurações**, siga as etapas no assistente de instalação.

  ![Captura de tela do painel Adicionar uma política](./media/telecom-expenses-monitor/tem-add-phone-lines-to-datalert-console.png)

O serviço Datalert já está ativo. Ele começará a monitorar o uso de dados e a desabilitar os dados em roaming em dispositivos que excederam os limites de uso configurados.

## <a name="end-user-enrollment"></a>Registro de usuários finais

Para a experiência de usuários finais, os seguintes artigos podem ajudar:

- [Registrar seu dispositivo iOS no gerenciamento de despesas de telecomunicações](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
- [Registrar seu dispositivo Android no gerenciamento de despesas de telecomunicações](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turn-off-the-datalert-service"></a>Desligar o serviço Datalert

1. Na [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Administração de locatário** > **Conectores e tokens** > **Gerenciamento de despesas de telecomunicações**.
2. Defina **Habilitar o Gerenciamento de Despesas de Telecomunicações e bloquear dados de celular ou roaming em dispositivos que excederem cotas de uso configuradas** como **Desabilitar**.
3. **Salve** suas alterações.

> [!IMPORTANT]
> Se você desabilitar o serviço Datalert no Intune:
>
> - Todas as ações aplicadas aos dispositivos devido a violações passadas dos limites de uso serão desfeitas.
> - Os usuários não são impedidos de acessar os dados e roaming.
> - O Intune ainda receberá os sinais proveniente do serviço, mas o Intune os ignora.

## <a name="next-steps"></a>Próximas etapas

Os relatórios de dados de uso estão disponíveis no console de gerenciamento do Datalert da Saaswedo.
