---
title: Habilitar conexões de dados do eSIM no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou use o eSIM para obter acesso a dados e à Internet usando planos de dados diferentes. No Intune, adicione ou importe códigos de ativação e, em seguida, atribua esses códigos de ativação usando um perfil de configuração. Você também pode monitorar os perfis do eSIM e verificar o status dos dispositivos habilitados para eSIM.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8b3078769428e5ba2679b141476293cb6df6813
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723938"
---
# <a name="configure-esim-cellular-profiles-in-intune---public-preview"></a>Configurar perfis de celular eSIM no Intune – versão prévia pública

eSIM é um chip SIM inserido e permite que você se conecte à Internet em uma conexão de dados da rede celular em um dispositivo compatível com eSIM, como o [Surface LTE Pro](https://www.microsoft.com/surface/business/surface-pro). Com um eSIM, você não precisa obter um cartão SIM da operadora móvel. Como viajante global, você também pode alternar entre os planos de dados da operadora móvel para permanecer sempre conectado.

Por exemplo, você tem um plano de dados da rede celular para o trabalho e outro plano de dados com uma operadora móvel diferente para uso pessoal. Durante uma viagem, você pode obter acesso à Internet localizando as operadoras móveis com planos de dados nessa área.

No Intune, você pode importar códigos de ativação de uso avulso fornecidos pela operadora móvel. Para configurar planos de dados da rede celular no módulo do eSIM, implante esses códigos de ativação em dispositivos compatíveis com eSIM. Quando o Intune instala o código de ativação, o módulo de hardware do eSIM usa os dados no código de ativação para contatar a operadora móvel. Depois de concluído, o perfil do eSIM é baixado no dispositivo e configurado para a ativação de celular.

Para implantar o eSIM em dispositivos usando o Intune, os seguintes itens são necessários:

- **Dispositivos compatíveis com eSIM**, tais como o Surface LTE: Confira [se o dispositivo dá suporte a eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data). Se preferir, veja uma lista de [alguns dos dispositivos compatíveis com eSIM conhecidos](#esim-capable-devices) (neste artigo).
- **Um computador com o Windows 10 Fall Creators Update** (1709 ou posterior) que esteja registrado e com o MDM gerenciado pelo Intune
- **Códigos de ativação** fornecidos pela operadora móvel. Esses códigos de ativação de uso avulso são adicionados ao Intune e implantados nos dispositivos compatíveis com eSIM. Contate a operadora móvel para adquirir os códigos de ativação do eSIM.

## <a name="deploy-esim-to-devices---overview"></a>Implantar o eSIM em dispositivos – visão geral

Para implantar o eSIM em dispositivos, um Administrador conclui as seguintes tarefas:

1. Importar códigos de ativação fornecidos pela operadora móvel
2. Criar um grupo de dispositivos do Azure AD (Azure Active Directory) que inclui os dispositivos compatíveis com eSIM
3. Atribuir o grupo do Azure AD ao pool de assinaturas importado
4. Monitorar a implantação

Este artigo orienta você por essas etapas.

## <a name="esim-capable-devices"></a>Dispositivos compatíveis com eSIM

Os dispositivos a seguir foram anunciados como compatíveis com eSIM ou estão no mercado hoje. Além disso, verifique se [o dispositivo dá suporte ao eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

- Acer Swift 7
- Asus NovoGo TP370QL
- Asus TP401
- Asus Transformer Mini T103
- HP Elitebook G5
- HP Envy x2
- HP Probook G5
- Lenovo Miix 630
- Lenovo T480
- Samsung Galaxy Book
- Surface Pro LTE
- HP Spectre Folio 13
- Lenovo Yoga C630

## <a name="step-1-add-cellular-activation-codes"></a>Etapa 1: Adicionar códigos de ativação de celular

Os códigos de ativação de celular são fornecidos pela operadora móvel em um arquivo separado por vírgula (CSV). Quando você tiver esse arquivo, adicione-o ao Intune usando as seguintes etapas:

1. Entre no [Portal do Azure](https://portal.azure.com/).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis de celular eSIM** > **Adicionar**.
4. Selecione o arquivo CSV que tem os códigos de ativação.
5. Selecione **OK** para salvar suas alterações.

### <a name="csv-file-requirements"></a>Requisitos do arquivo CSV

Ao trabalhar com o arquivo CSV com os códigos de ativação, verifique se você ou a operadora móvel segue os requisitos:

- O arquivo precisa estar no formato CSV (filename.csv).
- A estrutura do arquivo precisa atender a um formato estrito. Caso contrário, a importação falhará. O Intune verifica o arquivo na importação e gera uma falha se são encontrados erros.
- Os códigos de ativação são usados uma única vez. Não é recomendável importar os códigos de ativação importados anteriormente, porque isso poderá causar problemas quando você fizer a implantação no mesmo dispositivo ou em outro dispositivo.
- Cada arquivo deve ser específico para uma única operadora móvel e todos os códigos de ativação específicos para o mesmo plano de cobrança. O Intune distribui aleatoriamente códigos de ativação para dispositivos de destino. Não há nenhuma garantia de qual dispositivo obtém um código de ativação específico.
- Um máximo de 1.000 códigos de ativação pode ser importado em um arquivo CSV.

### <a name="csv-file-example"></a>Exemplo de arquivo CSV

1. A primeira linha e a primeira célula do CSV são a URL do serviço de ativação do eSIM da operadora móvel, que é chamado de SM-DP+ (servidor de Preparação de Dados do Gerenciador de Assinaturas). A URL deve ser um FQDN (nome de domínio totalmente qualificado) sem vírgulas.
2. A segunda linha e todas as linhas posteriores são códigos de ativação de uso avulso exclusivos que incluem dois valores:

    1. A primeira coluna é a ICCID exclusiva (o identificador do chip SIM)
    2. A segunda coluna é a ID de Correspondência com apenas uma vírgula separando-as (sem vírgula no final). Veja o exemplo a seguir:

        ![Arquivo CSV de exemplo de código de ativação da operadora móvel](./media/esim-device-configuration/url-activation-code-examples.png)

3. O nome do arquivo CSV torna-se o nome do pool de assinaturas de celular no portal do Azure. Na imagem anterior, o nome de arquivo é `UnlimitedDataSkynet.csv`. Portanto, o Intune nomeia o pool de assinaturas `UnlimitedDataSkynet.csv`:

    ![O pool de assinaturas de celular tem o nome do arquivo CSV de exemplo de código de ativação](./media/esim-device-configuration/subscription-pool-name-csv-file.png)

## <a name="step-2-create-an-azure-ad-device-group"></a>Etapa 2: Criar um grupo de dispositivos do Azure AD

Crie um grupo de dispositivos que inclui os dispositivos compatíveis com eSIM. [Adicionar grupos](../fundamentals/groups-add.md) lista as etapas.

> [!NOTE]
> - Somente os dispositivos são direcionados; os usuários não.
> - Recomendamos criar um grupo de dispositivos estáticos do Azure AD que inclui os dispositivos eSIM. O uso de um grupo de confirma que você está direcionando somente dispositivos eSIM.

## <a name="step-3-assign-esim-activation-codes-to-devices"></a>Etapa 3: Atribuir códigos de ativação eSIM em dispositivos

Atribua o perfil ao grupo do Azure AD que inclui os dispositivos eSIM.

1. No [portal do Azure](https://portal.azure.com/), selecione **Todos os Serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Celular eSIM** > **Perfis**.
3. Na lista de perfis, selecione o pool de assinaturas de celular eSIM que deseja atribuir e, em seguida, selecione **Atribuições**.
4. Escolha **Incluir** ou **Excluir** grupos e, em seguida, selecione os grupos.

    ![Incluir o grupo de dispositivos para atribuir o perfil](./media/esim-device-configuration/include-exclude-groups.png)

5. Ao selecionar os grupos, você está escolhendo um grupo do Azure AD. Para selecionar vários grupos, use a tecla **Ctrl** e, em seguida, selecione os grupos.
6. Quando terminar, **Salve** as alterações.

Os códigos de ativação do eSIM são usados uma única vez. Depois que o Intune instala um código de ativação em um dispositivo, o módulo do eSIM contata a operadora móvel para baixar o perfil de celular. Esse contato conclui o registro do dispositivo na rede da operadora móvel.

## <a name="step-4-monitor-deployment"></a>Etapa 4: Monitorar a implantação

### <a name="review-the-deployment-status"></a>Examinar o status da implantação

Depois de atribuir o perfil, você pode monitorar o status da implantação de um pool de assinaturas.

1. Entre no [Portal do Azure](https://portal.azure.com/).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis de celular eSIM**. Todos os pools de assinaturas de celular eSIM existentes são listados.
4. Selecione uma assinatura e examine o **Status de Implantação**.

### <a name="check-the-profile-status"></a>Verificar o status do perfil
Depois de criar o perfil do seu dispositivo, o Intune fornece gráficos. Esses gráficos exibem o status de um perfil como sendo atribuído com êxito a dispositivos, ou se o perfil mostra um conflito.

1. Selecione **Configuração do dispositivo** > **Perfis de celular eSIM** > Selecionar uma assinatura existente.
2. Na guia **Visão Geral**, o gráfico superior mostra o número de dispositivos atribuídos à implantação de pool de assinaturas de celular eSIM específica.

    Ele também mostra o número de dispositivos para outras plataformas que recebem o mesmo perfil de dispositivo.

    O Intune mostra o status de entrega e de instalação para o código de ativação destinado aos dispositivos.

    - **Dispositivo não sincronizado**: O dispositivo de destino não contatou o Intune desde que a política de implantação do eSIM foi criada
    - **Ativação pendente**: Um estado transitório quando o Intune está instalando ativamente o código de ativação no dispositivo
    - **Ativo**: Instalação de código de ativação bem-sucedida
    - **Falha de ativação**: Instalação de código de ativação com falha – confira o guia de solução de problemas.

#### <a name="view-the-detailed-device-status"></a>Exibir o status detalhado do dispositivo

Monitore e exiba uma lista detalhada de dispositivos que podem ser exibidos no Status do Dispositivo.**

1. Selecione **Configuração do dispositivo** > **Perfis de celular eSIM** > Selecionar uma assinatura existente.
2. Selecione **Status do Dispositivo**. O Intune mostra detalhes adicionais sobre o dispositivo:

    - **Nome do Dispositivo**: Nome do dispositivo de destino
    - **Usuário**: Usuário do dispositivo registrado
    - **ICCID**: Código exclusivo fornecido pela operadora móvel no código de ativação instalado no dispositivo
    - **Status de Ativação**: Status de entrega e instalação do Intune do código de ativação no dispositivo
    - **Status do celular**: Estado fornecido pela operadora móvel. Faça um acompanhamento com a operadora móvel para solucionar problemas.
    - **Último check-in**: Data da última comunicação do dispositivo com o Intune

### <a name="monitor-esim-profile-details-on-the-actual-device"></a>Monitorar os detalhes do perfil do eSIM no dispositivo real

1. No dispositivo, abra **Configurações** > acesse **Rede e Internet**.
2. Selecione **Celular** > **Gerenciar perfis do eSIM**
3. Os perfis do eSIM são listados:

    ![Exibir os perfis do eSIM nas configurações do dispositivo](./media/esim-device-configuration/device-settings-cellular-profiles.png)

## <a name="remove-the-esim-profile-from-device"></a>Remover o perfil do eSIM do dispositivo

Quando você remove o dispositivo do grupo do Azure AD, o perfil do eSIM também é removido. Não se esqueça de:

1. Confirme se você está usando o grupo do Azure AD de dispositivos do eSIM.
2. Acesse o grupo do Azure AD e remova o dispositivo do grupo.
3. Quando o dispositivo removido contata o Intune, a política atualizada é avaliada e o perfil do eSIM é removido.

O perfil do eSIM também é removido quando o dispositivo é [desativado](../remote-actions/devices-wipe.md#retire), quando seu registro é cancelado pelo usuário ou quando a [ação remota para redefinir dispositivo](../remote-actions/devices-wipe.md#wipe) é executada no dispositivo.

> [!NOTE]
> A remoção do perfil pode não interromper a cobrança. Contate a operadora móvel para verificar o status de cobrança do dispositivo.

## <a name="best-practices--troubleshooting"></a>Melhores práticas e solução de problemas

- Verifique se o arquivo CSV está formatado corretamente. Confirme se o arquivo não inclui códigos duplicados, não inclui várias operadoras móveis ou não inclui planos de dados diferentes. Lembre-se de que cada arquivo precisa ser exclusivo para uma operadora móvel e um plano de dados da rede celular.
- Crie um grupo de dispositivos estáticos do Azure AD que inclui apenas os dispositivos do eSIM de destino.
- Se houver um problema com o status da implantação, verifique o seguinte:
  - **Formato de arquivo não adequado**: Confira a **Etapa 1: Adicionar códigos de ativação de celular** (neste artigo) para saber como formatar o arquivo corretamente.
  - **Falha de ativação de celular, entre em contato com operador móvel**: O código de ativação não pode ser ativado em sua rede. Ou o download do perfil e a ativação de celular falhou.

## <a name="next-steps"></a>Próximas etapas
[Configurar perfis do dispositivo](../device-profiles.md)
