---
title: Configurar configurações do Windows Update para Empresas no Microsoft Intune
titleSuffix: ''
description: Saiba como definir as configurações do Windows Update para Empresas no Microsoft Intune para controlar as atualizações em dispositivos Windows 10.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: ac26d0ac1855aa32ef0f00de6a4056bd57c07528
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="manage-software-updates"></a>Gerenciar atualizações de software

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Windows como serviço é a maneira de atualizar dispositivos Windows 10. Com o Windows 10, as novas Atualizações de Recursos e de Qualidade apresentam o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos Windows 10 estão atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e deixar que o Windows Update assegure que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam diretamente as atualizações do Windows Update. Use o Intune para configurar e gerenciar os **grupos de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Por exemplo, você pode configurar o seguinte:

- **Canal de Manutenção do Windows 10**: escolha se você deseja que grupos de dispositivos recebam atualizações do Canal Semestral (direcionado) ou do Canal Semestral.  
- **Configurações de Adiamento**: defina as configurações de adiamento da atualização para atrasar as instalações da atualização para os grupos de dispositivos. Use essas configurações para obter uma distribuição de atualizações em etapas para que você possa examinar o progresso ao longo do caminho.
- **Pausando**: adie a instalação das atualizações se você descobrir um problema em algum ponto durante a distribuição de atualização.
- **Janela de manutenção**: configure o horário em que as atualizações podem ser instaladas.
- **Tipo de atualização**: escolha os tipos de atualizações instaladas. Por exemplo, Atualizações de Qualidade, Atualizações de Recursos ou drivers.
- **Comportamento da instalação**: isso configura como a atualização é instalada. Por exemplo, o dispositivo reinicia automaticamente após a instalação?
- **Download de ponto a ponto**: você pode especificar se deseja configurar o download de ponto a ponto. Se configurado, quando um dispositivo tiver terminado o download de uma atualização, outros dispositivos poderão baixar a atualização desse dispositivo. Isso acelera o processo de download.

Depois de criar anéis de atualização, você poderá atribuí-los em grupos de dispositivos. Usando anéis de atualização, você pode criar uma estratégia de atualização que espelha suas necessidades de negócios. Para obter mais informações, consulte [Gerenciar as atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Antes de começar

- Para atualizar os PCs com Windows 10, eles devem estar executando pelo menos o Windows 10 Pro com a atualização de Aniversário do Windows.

- O Windows Update oferece suporte às seguintes versões do Windows 10:
    - Windows 10
    - Windows 10 Team (para dispositivos Surface Hub)
    - [Windows Holographic for Business](#windows-holographic-for-business-support)

 Dispositivos que executam o Windows 10 Mobile não são compatíveis.

- Nos dispositivos do Windows, **Comentários e diagnóstico** > **Dados de diagnóstico e uso** devem ser definidos para pelo menos o **Básico**.

    ![Configuração do Windows para dados de diagnóstico e uso](./media/telemetry-basic.png)

    Você pode definir essa configuração manualmente ou pode usar um perfil de restrição de dispositivo do Intune para o Windows 10 e posterior. Para tanto, defina a configuração **Geral** > **Envio dos dados de diagnóstico** para pelo menos o **Básico**. Para obter mais informações sobre os perfis do dispositivo, consulte [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md).

- No console de administração do Intune, há quatro configurações que controlam o comportamento das atualizações do software. Essas configurações fazem parte da política de configuração geral para os dispositivos do Windows 10 desktop e Mobile:
    - **Permitir atualizações automáticas**
    - **Permitir recursos de pré-lançamento**
    - **Dia de Instalação Agendado**
    - **Hora de Instalação Agendada**

  O Portal Clássico também tem um número limitado de outras configurações de atualização do Windows 10 no perfil de configuração do dispositivo. Se você tiver uma dessas definições configuradas no console de administração do Intune quando migrar para o Portal do Azure, será altamente recomendável que faça o seguinte:

1. crie anéis de atualização do Windows 10 no portal do Azure com as configurações necessárias. A configuração **Permitir recursos de pré-lançamento** não é suportada no portal do Azure porque não é mais aplicável às compilações mais recentes do Windows 10. Você poderá definir três outras configurações, bem como outras configurações de atualização do Windows 10, quando criar anéis de atualização.

  > [!NOTE]
  > As configurações de atualização do Windows 10 criadas no Portal Clássico não são exibidas no Portal do Azure após a migração. No entanto, essas configurações continuam a ser aplicadas. Se você migrar essas configurações e editar a política migrada do portal do Azure, essas configurações serão removidas da política.

2. Exclua as configurações de atualização no Portal Clássico. Depois de migrar para o portal do Azure e adicionar as mesmas configurações a um anel de atualização, você deve excluir as configurações no portal clássico para evitar possíveis conflitos de política. Por exemplo, quando a mesma configuração for definida com valores diferentes, haverá um conflito e não será fácil descobrir por que a configuração definida no Portal Clássico não é exibida no Portal do Azure.

## <a name="how-to-create-and-assign-update-rings"></a>Como criar e atribuir anéis de atualização

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Atualizações de software**.
4. No painel **Atualizações de software**, escolha **Gerenciar** > **Grupos de Atualização do Windows 10**.
5. No painel que mostra a lista de grupos de atualização, escolha **Criar**.
6. No painel **Criar Grupo de Atualização**, forneça um nome e uma descrição opcional para o grupo de atualização, em seguida, escolha **Definições – Configurar**.
7. No painel **Configurações**, defina as seguintes informações:
    - **Canal de manutenção**: defina o canal para o qual o dispositivo recebe atualizações do Windows (Canal Semestral (direcionado) ou Canal Semestral.
    - **Atualizações de produto da Microsoft**: escolha se as atualizações de aplicativo devem ser verificadas no Microsoft Update.
    - **Drivers do Windows**: escolha se é para excluir os drivers do Windows Update durante as atualizações.
    - **Comportamento da atualização automática**: escolha como gerenciar o comportamento da atualização automática para verificar, baixar e instalar as atualizações. Para obter detalhes, consulte [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Período de adiamento da atualização de qualidade (dias)** – especifique o número de dias em que as atualizações de qualidade serão adiadas. Você pode adiar recebendo essas Atualizações de Qualidade por um período de até 30 dias a partir de seu lançamento.  

    As Atualizações de Qualidade são, em geral, correções e aprimoramentos da funcionalidade existente do Windows e normalmente são publicadas na primeira terça-feira de cada mês, embora possam ser lançadas a qualquer momento pela Microsoft. Você pode definir se, e por quanto tempo, deseja adiar o recebimento das Atualizações de Qualidade após sua disponibilidade.

    - **Período de adiamento da atualização de recursos (dias)** – especifique o número de dias em que as Atualizações de Recursos serão adiadas. Você pode adiar o recebimento dessas Atualizações do Recurso por um período de 180 dias após seu lançamento.

    As Atualizações do Recurso são geralmente novos recursos para o Windows. Depois de definir a configuração **Canal de manutenção** (Canal Semestral (direcionado) ou Canal Semestral), será possível definir se, e por quanto tempo, você deseja adiar o recebimento das Atualizações do Recurso após sua disponibilidade no Windows Update pela Microsoft.

    Por exemplo: **se o Canal de manutenção estiver definido como Canal Semestral (direcionado) e o período de adiamento for 30 dias**: vamos supor que a Atualização do Recurso X está publicamente disponível no Windows Update como um Canal Semestral (direcionado) em janeiro. O dispositivo não receberá a atualização até fevereiro - 30 dias depois.

    **Se o Canal de manutenção estiver definido como Canal Semestral e o período de adiamento for 30 dias**: vamos supor que a Atualização do Recurso X está publicamente disponível no Windows Update como um Canal Semestral (direcionado) em janeiro. Quatro meses depois, em abril, a Atualização do Recurso X será lançada para o Canal Semestral. O dispositivo receberá a Atualização do Recurso 30 dias depois do lançamento do Canal Semestral e será atualizado em maio.

    - **Modo de download de otimização da entrega** – Escolha o método para o qual os dispositivos baixarão as atualizações do Windows. Para obter detalhes, consulte [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).
1. Quando terminar, clique em **OK**, depois no painel **Criar Grupo de Atualização** e em **Criar**.

O novo anel de atualização será exibido na lista de anéis de atualização.

1. Para atribuir o anel, na lista de anéis de atualização, selecione um anel, em seguida, na guia *nome do anel*>, escolha **Atribuições**.
2. Na próxima guia, selecione **Selecionar os grupos a serem incluídos** e escolha os grupos para os quais você deseja atribuir esse anel.
3. Quando terminar, escolha **Selecionar** para concluir a atribuição.

## <a name="update-compliance-reporting"></a>Relatório de conformidade da atualização
Você pode exibir a conformidade de atualizações no Intune ou usando uma solução gratuita no OMS (Operations Management Suite) chamada Conformidade de Atualizações.

### <a name="review-update-compliance-in-intune"></a>Examinar a conformidade de atualizações no Intune 
<!-- 1352223 -->
Examine um relatório de política para exibir o status da implantação dos grupos de atualização do Windows 10 que você configurou. 
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Atualizações de software**.
4. No painel **Atualizações de software**, escolha **Visão Geral**. Aqui você é possível ver informações gerais sobre o status de todos os grupos de atualização atribuídos.
5. Abra um dos seguintes relatórios: 
     
   **Para todos os grupos de implantação:**
   1. No painel **Atualizações de software** > **Grupos de Atualização do Windows 10**. 
   2. Na **seção Monitorar**, escolha **Por estado de implantação do grupo de atualização**.
                   
   **Para grupos de implantação específicos:** 
   1. No painel **Atualizações de software** > **Grupos de atualização do Windows 10**, escolha o grupo de implantação a ser examinado.
   2. Na seção **Monitorar**, escolha entre os seguintes relatórios para exibir informações mais detalhadas sobre o grupo de atualização:
      - **Status do dispositivo**
      - **Status do usuário**

### <a name="review-update-compliance-using-oms"></a>Examinar conformidade de atualizações usando o OMS
Você pode monitorar as distribuições de atualização do Windows 10 usando uma solução gratuita no Operations Management Suite (OMS) denominada Conformidade da Atualização. Para obter detalhes, consulte [Monitorar as Atualizações do Windows com a Conformidade da Atualização](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Quando você usa essa solução, pode implantar uma ID comercial para qualquer dispositivo do Windows 10 gerenciado pelo Intune para o qual deseja relatar a conformidade da atualização.

No console do Intune, você pode usar as configurações OMA-URI de uma política personalizada para configurar a ID comercial. Para obter detalhes, consulte [Configurações da política do Intune para os dispositivos do Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

O caminho OMA-URI (com letras maiúsculas e minúsculas) para configurar a ID comercial é: ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

Por exemplo, você pode usar os seguintes valores em **Adicionar ou editar a configuração OMA-URI**:

- **Nome da Configuração**: ID comercial do Windows Analytics
- **Descrição da Configuração**: configurando a ID comercial para soluções Windows Analytics
- **OMA-URI** (com letras maiúsculas e minúsculas): ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID
- **Tipo de Dados**: cadeia de caracteres
- **Valor**: *use o GUID mostrado na guia Telemetria do Windows em seu espaço de trabalho OMS*>

![Configuração OMA-URI – Adicionar linha](./media/commID.png)

## <a name="how-to-pause-updates"></a>Como pausar as atualizações
Você pode pausar o recebimento pelo dispositivo das Atualizações do Recurso ou Atualizações de Qualidade por um período de até 35 dias a partir da pausa das atualizações. Depois do máximo de dias transcorrido, a funcionalidade de pausa irá expirar automaticamente e o dispositivo verificará as Atualizações do Windows em relação às atualizações aplicáveis. Após essa verificação, você pode pausar as atualizações novamente.
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Atualizações de software**.
4. No painel **Atualizações de software**, escolha **Gerenciar** > **Grupos de Atualização do Windows 10**.
5. No painel que mostra a lista de grupos de atualização, escolha o grupo que você deseja pausar e **...** > **Pausar Qualidade** > ou **Pausar Recurso**, dependendo do tipo de atualização que você deseja pausar.

> [!IMPORTANT]
> Ao emitir um comando para pausar, os dispositivos receberão esse comando quando eles verificarem o serviço na próxima vez. É possível que antes de verificarem, eles possam instalar uma atualização agendada.
> Além disso, se um dispositivo de destino estiver desativado quando você emitir o comando para pausar, quando você o ativar, ele poderá baixar e instalar as atualizações agendadas antes de verificar com o Intune.

## <a name="windows-holographic-for-business-support"></a>Compatibilidade do Windows Holographic for Business

O Windows Holographic for Business é compatível com as seguintes configurações:

- **Comportamento de atualização automática**
- **Atualizações de produto da Microsoft**
- **Canal de manutenção**