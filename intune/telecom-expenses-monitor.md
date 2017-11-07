---
title: "Configurar um serviço de gestão de despesas de telecomunicações"
titleSuffix: Azure portal
description: "Configure o serviço de gerenciamento de despesas de telecomunicações da Saaswedo para integração com o Intune."
keywords: Saaswedo
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3f97cebe411b191f2bf0b13fb756c705613c46a
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Configurar um serviço de gerenciamento de despesas de telecomunicações no Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune permite que você gerencie as despesas de telecomunicações decorrentes da utilização de dados em dispositivos móveis corporativos. Para permitir este recurso, o Intune integrou-se à solução de gerenciamento de despesas de telecomunicações Datalert da desenvolvedora de software Saaswedo. O Datalert é um software de gerenciamento de despesas de telecomunicações em tempo real que permite que você gerencie o uso de dados de telecomunicações e evitar excedentes de dados móveis e roaming inesperados e dispendiosos para os dispositivos gerenciados pelo Intune.

A integração do Intune com o Datalert permite definir, monitorar centralmente e impor limites de uso de dados de roaming e doméstico usando alertas automatizados quando excederem os limites definidos. Você pode configurar o serviço para aplicar diferentes ações a indivíduos ou grupos de usuários finais, incluindo desabilitar roaming quando os usuários excederem o limite. Relatórios que fornecem o uso de dados e informações de monitoramento estão disponíveis no console de gerenciamento Datalert.

O diagrama a seguir mostra como o Intune se integra ao Datalert.

  ![Diagrama de integração do Intune e Datalert](./media/tem-datalert-intune-solution-diagram.png)

Antes de usar o serviço de Datalert com o Intune, você precisa definir as configurações no console de Datalert e no Intune. A conexão deve estar ativada para o serviço Datalert e para o Intune. Se o lado do Datalert da conexão estiver habilitado, mas não o lado do Intune, o Intune receberá a comunicação, mas a ignorará.

## <a name="supported-platforms"></a>Plataformas com suporte

- Samsung Knox
- iOS 8.0 e posterior

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do Microsoft Intune e acesso ao portal do Azure.
- Uma assinatura para o serviço de gerenciamento de despesas de telecomunicações do Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Lista de provedores de gerenciamento de despesas de telecomunicações

O Intune atualmente se integra com os seguintes provedores de gerenciamento de despesas de telecomunicações:

[Serviço de gerenciamento de despesas de telecomunicações do Saaswedo Datalert](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Implantar a solução integrada do Intune e Datalert

Antes de começar, verifique se você já possui uma assinatura do Intune e do serviço de gerenciamento de gastos de telecomunicações do Datalert.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Etapa 1: conectar o serviço Datalert ao Microsoft Intune

1. Entre no console de gerenciamento Datalert com suas credenciais de administrador.

2. No console de gerenciamento Datalert, vá para a guia **Configurações** e, em seguida, **Configuração MDM**.

3. Selecione **Desbloquear** para permitir que você insira as configurações na página.

4. Para **Servidor MDM**, escolha **Microsoft Intune**.

5. Para **domínio do Azure AD**, insira sua ID de locatário do Azure e, em seguida, selecione o botão **Conexão**.

    Selecionar **Conexão** faz o serviço do Datalert verificar com o Intune se não existem conexões Datalert já existentes com o Intune. Depois de alguns segundos, uma página de logon do Microsoft aparecerá, seguida da autenticação do Datalert Azure.

6. Na página de autenticação da Microsoft, selecione **Aceitar**. Você será redirecionado para uma página de agradecimento, que se fecha depois de alguns segundos. O Datalert valida a conexão e exibe marcas de seleção verde ao lado de uma lista de itens validados. Se a validação falhar, você verá uma mensagem vermelha. Nesse caso, contate o suporte de Datalert para obter ajuda.

    A captura de tela a seguir mostra as marcas de seleção verde que você pode esperar encontrar quando a conexão for bem-sucedida.

  ![Página do Datalert mostrando a conexão bem-sucedida](./media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Etapa 2: verificar se o recurso de gerenciamento de despesas de telecomunicações está ativo no Intune

Depois de concluir a etapa 1 acima, a conexão deverá ser habilitada automaticamente e o status de conexão **Ativo** deverá aparecer no portal do Azure. Estas etapas mostram como verificar o status **Ativo**.

1. Entre no Portal do Azure.

2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

3. Na folha **Intune**, escolha **Configuração do dispositivo**.

4. Na folha **Configuração do Dispositivo**, escolha **Instalação** > **Gerenciamento de Despesas de Telecomunicações**.

   Procure o status de conexão **Ativo** na parte superior da página.

  ![Portal do Azure mostrando o status de conexão do Datalert ativo](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Etapa 3: implantar o aplicativo Datalert em dispositivos corporativos registrados

Para garantir que o uso de dados somente de linhas de propriedade corporativas seja coletado, é necessário criar categorias de dispositivo no Intune e, em seguida, direcionar o aplicativo Datalert apenas para telefones corporativos. Conclua as etapas nas subseções a seguir.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Definir grupos e categorias de dispositivos mapeados para as categorias

Dependendo das suas necessidades organizacionais, você precisará criar ao menos duas categorias de dispositivos (por exemplo, Corporativo e Pessoal) e criar grupos de dispositivos dinâmicos para cada categoria. Você pode criar mais categorias para sua organização, conforme necessário.

Essas categorias serão mostradas aos usuários durante o registro. Dependendo de qual categoria o usuário escolher, o dispositivo registrado será movido para o grupo de dispositivo correspondente. Para obter etapas sobre como criar categorias de dispositivos, consulte [Mapear dispositivos para grupos](device-group-mapping.md).

  ![Captura de tela da folha Adicionar uma política](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Criar o aplicativo Datalert no Intune

Siga estas etapas para criar o aplicativo Datalert no Intune para cada plataforma. O iOS é usado como um exemplo nessas etapas.

1. Na folha **Intune** do portal do Azure, escolha **Aplicativos móveis**.

2. Na folha **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.

3. Selecione **Adicionar** para adicionar um aplicativo.

4. Selecione o tipo de aplicativo. Por exemplo, para iOS, você selecionaria **iOS App Store**.

5. Em **Pesquisar na App Store**, procure o aplicativo Datalert digitando **Datalert** na janela de pesquisa.

6. Selecione o aplicativo **Datalert** e selecione **Ok**.

  ![Captura de tela da folha Adicionar uma política](./media/tem-select-app-from-apple-app-store.png)

7. Conclua as etapas restantes para criar um aplicativo para iOS.

  ![Captura de tela da folha Adicionar uma política](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Atribuir o aplicativo Datalert ao grupo de dispositivos corporativos

1. Selecione o aplicativo Datalert para iOS que você criou na etapa anterior.

2. Na folha **Aplicativos**, vá para **Gerenciar** > **Atribuições**.

3. Escolha **Selecionar grupos** e siga as etapas para selecionar o grupo de dispositivos corporativos.

4. Escolha se deseja tornar a instalação do aplicativo obrigatória ou opcional para o grupo. A captura de tela de exemplo a seguir mostra a instalação conforme necessário, o que significa que os usuários devem instalar o aplicativo Datalert depois de registrar seu dispositivo.

  ![Captura de tela da folha Adicionar uma política](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Etapa 4: adicionar linhas telefônicas pagas corporativas ao console do Datalert

Agora você configurou os serviços Intune e Datalert para se comunicar entre si. Você agora precisa adicionar linhas telefônicas pagas corporativas ao console do Datalert e definir limites e ações para qualquer violação de uso de dados celulares ou roaming. Você pode adicionar manualmente linhas telefônicas corporativas pagas ao console do Datalert ou adicioná-las automaticamente após o registro do dispositivo no Intune.

Para definir esses itens, vá para [Configuração do Datalert para a página do Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup) e siga as etapas no assistente de instalação na guia **Configurações**.

  ![Captura de tela da folha Adicionar uma política](./media/tem-add-phone-lines-to-datalert-console.png)


O serviço Datalert agora estará ativo e começará a monitorar o uso de dados e a desabilitar os dados em roaming em dispositivos que excederam os limites de uso configurados.

## <a name="client-enrollment-experience"></a>Experiência de registro do cliente
Para a experiência de registro de cliente, confira o seguinte:
-   [Registrar seu dispositivo iOS no gerenciamento de despesas de telecomunicações](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Registrar seu dispositivo Android no gerenciamento de despesas de telecomunicações](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Desativar o serviço Datalert

Se você desabilitar o serviço Datalert no Portal do Azure:

- Todas as ações que foram aplicadas aos dispositivos devido a violações passadas dos limites de uso serão desfeitas.
- Os usuários não são impedidos de acessar os dados e roaming.
- O Intune ainda recebe os sinais proveniente do serviço, mas os ignora.

**Para desligar o serviço**

1. Na folha **Gerenciamento de Despesas de Telecomunicações** no Portal do Azure, selecione **Desabilitar**.

2. Selecione **Salvar**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Exibindo o uso de dados e relatórios de roaming

No momento, os relatórios de dados de uso estão disponíveis somente no console de gerenciamento do Saaswedo Datalert.

As instruções que os usuários finais seguem para instalar o aplicativo Datalert serão adicionadas em breve.
