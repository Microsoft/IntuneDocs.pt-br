---
title: Registrar dispositivos iOS – Apple Configurator – Assistente de Configuração
titleSuffix: Microsoft Intune
description: Saiba como usar o Apple Configurator para registrar dispositivos iOS de propriedade corporativa com o Assistente de Configuração.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7cff6c777de4a35aa6825d1d37fdd0c2f2d0b72
ms.sourcegitcommit: 165c1e48891e386f9f75b0ef7a6826b67695dbb7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2018
ms.locfileid: "42751710"
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Registrar dispositivos iOS com o Apple Configurador

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune dá suporte ao registro de dispositivos iOS por meio do [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344) em execução em um computador Mac. O registro com o Apple Configurator exige que você conecte por USB cada dispositivo iOS a um computador Mac para configurar o registro corporativo. Você pode registrar dispositivos no Intune com o Apple Configurator de duas maneiras:
- **Registro pelo Assistente de Configuração** – redefine o dispositivo para os padrões de fábrica e o prepara para o registro pelo Assistente de Configuração.
- **Registro direto** – não redefine o dispositivo para as configurações de fábrica e registra o dispositivo por meio das configurações do iOS. Apenas dispositivos **sem afinidade de usuário** têm suporte nesse método.

Os métodos de registro do Apple Configurator não podem ser utilizados com o [gerenciados de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Pré-requisitos

- Acesso físico aos dispositivos iOS
- [Configurar a autoridade MDM](mdm-authority-set.md)
- [Um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Números de série do dispositivo (somente para registro pelo Assistente de Configuração)
- Cabos de conexão USB
- Computador macOS com o [Apple Configurator 2.0](https://itunes.apple.com/app/apple-configurator-2/id1037126344)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Criar um perfil do Apple Configurator para dispositivos

Um perfil de registro do dispositivo define as configurações aplicadas durante o registro. Essas configurações são aplicadas apenas uma vez. Siga estas etapas para criar um perfil de registro a fim de registrar dispositivos iOS com o Apple Configurator.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Perfis** > **Criar**.

    ![Criar um perfil para o Apple Configurator](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. Em **Criar Perfil de Registro**, digite um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. É possível usar o campo Nome para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os grupos dinâmicos do Azure Active Directory.

    ![Captura de tela da tela Criar perfil com o Registro com afinidade de usuário selecionado](./media/apple-configurator-profile-create.png)

3. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.

    - **Registrar com afinidade do usuário** – escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o portal da empresa para serviços como a instalação de aplicativos. O dispositivo deve ser afiliado a um usuário com o Assistente de Configuração e, depois, pode acessar dados e email da empresa. Com suporte apenas para o registro do Assistente de Configuração. A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Registrar sem afinidade do usuário** – escolha esta opção para dispositivos não afiliados com um único usuário. Use-a para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão. Necessário para o registro direto.

4. Se você tiver escolhido **Registrar com Afinidade do Usuário**, terá a opção de permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    > [!NOTE]
    > Quando quiser fazer algum dos seguintes procedimentos, defina **Autenticar com o Portal da Empresa em vez de usar o Assistente de Configuração** como **Sim**.
    >    - Usar autenticação multifator
    >    - Solicitar aos usuários que precisam alterar a senha quando entram pela primeira vez
    >    - solicitar que os usuários redefinam suas senhas expiradas durante o registro
    >
    > Essas opções não têm suporte na autenticação com o Assistente de Configuração da Apple.


6. Escolha **Criar** para salvar o perfil.

## <a name="setup-assistant-enrollment"></a>Registro pelo Assistente de Configuração

### <a name="add-apple-configurator-serial-numbers"></a>Adicionar números de série do Apple Configurator

1. Crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione os números de série na coluna esquerda e os detalhes na coluna direita. O máximo atual para a lista é de 5.000 linhas. Em um editor de texto, a lista .csv é semelhante a isto:

    F7TLWCLBX196, detalhes do dispositivo</br>
    DLXQPCWVGHMJ, detalhes do dispositivo

   Saiba [como localizar o número de série de um dispositivo iOS](https://support.apple.com/HT204073).
2. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Dispositivos** > **Adicionar**.

5. Selecione um **Perfil de registro** para aplicar aos números de série que você está importando. Se quiser que os novos detalhes do número de série substituam os detalhes existentes, escolha **Substituir detalhes para identificadores existentes**.
6. Em **Importar dispositivos**, navegue para o arquivo csv dos números de série e selecione **Adicionar**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Reatribuir um perfil novamente aos números de série do dispositivo

Você pode atribuir um perfil de registro quando importar os números de série do iOS para o registro do Apple Configurator. Você também pode atribuir perfis de dois locais no Portal do Azure:
- **Dispositivos do Apple Configurator**
- **Perfis do AC**

#### <a name="assign-from-apple-configurator-devices"></a>Atribuir dos dispositivos do Apple Configurator
1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Dispositivos** > escolha os números de série > **Atribuir perfil**.
2. Em **Atribuir Perfil**, escolha o **Novo perfil** que você deseja atribuir e, em seguida, escolha **Atribuir**.

#### <a name="assign-from-profiles"></a>Atribuir de perfis
1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Perfis** > escolha um perfil.
2. No perfil, escolha **Dispositivos Atribuídos** e, em seguida, escolha **Atribuir**.
3. Filtre para localizar os números de série do dispositivo que você deseja atribuir ao perfil, selecione os dispositivos e, em seguida, escolha **Atribuir**.

### <a name="export-the-profile"></a>Exportar o perfil
Depois de criar o perfil e atribuir números de série, é necessário exportar o perfil do Intune como uma URL. Em seguida, importe-o para o Apple Configurator em um computador Mac para implantação em dispositivos.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Perfis** > escolha o perfil para exportar.
2. No perfil, selecione **Exportar Perfil**.
3. Copie a **URL do Perfil**. Então, será possível adicioná-la ao Apple Configurator para definir o perfil do Intune utilizado pelos dispositivos iOS.

   Depois, esse perfil será importado para o Apple Configurator no próximo procedimento, a fim de definir o perfil do Intune usado pelos dispositivos iOS.

### <a name="enroll-devices-with-setup-assistant"></a>Registrar dispositivos com o Assistente de Configuração

1. Em um computador Mac, abra o **Apple Configurator 2**. Na barra de menus, selecione **Apple Configurator 2** e clique em **Preferências**.
    > [!WARNING]
    > Os dispositivos são redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você conectar o dispositivo.

2. No painel de **preferências**, selecione **Servidores** e escolha o símbolo de mais (+) para inicializar o assistente do Servidor MDM. Escolha **Avançar**.
3. Insira o **Nome de Host ou a URL** e a **URL do Registro** para o servidor MDM em Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune. Para URL de Registro, insira a URL do perfil de registro exportada do Intune. Escolha **Avançar**.  
    Você pode desconsiderar com segurança um aviso indicando "URL do servidor não verificada". Para continuar, clique em **Avançar** até que o assistente seja concluído.
4.  Conecte os dispositivos móveis iOS ao computador Mac com um adaptador USB.
5.  Selecione os dispositivos iOS que deseja gerenciar e escolha **Preparar**. No painel **Preparar o Dispositivo iOS**, selecione **Manual** e, em seguida, escolha **Avançar**.
6. No painel **Registrar no Servidor MDM**, selecione o nome do servidor que você criou e escolha **Avançar**.
7. No painel **Supervisionar Dispositivos**, selecione o nível de supervisão e, em seguida, selecione **Avançar**.
8. No painel **Criar uma Organização**, escolha **Organização** ou crie uma nova organização e escolha **Avançar**.
9. No painel **Configurar o Assistente de Instalação do iOS**, escolha as etapas que serão apresentadas ao usuário e escolha **Preparar**. Se solicitado, autentique para atualizar as configurações de confiança.  
10. Quando o dispositivo iOS concluir a preparação, desconecte o cabo USB.  

### <a name="distribute-devices"></a>Distribuir dispositivos
Os dispositivos agora estão prontos para registro corporativo. Desligue os dispositivos e distribua-os para os usuários. Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.

Depois de receberem seus dispositivos, eles devem concluir o Assistente de Configuração. Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos.

## <a name="direct-enrollment"></a>Registro direto
Ao registrar dispositivos iOS diretamente com o Apple Configurator, é possível registrar um dispositivo sem adquirir o número de série do dispositivo. Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro. Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente. Esse método não faz uma redefinição de fábrica do dispositivo.

Aplicativos que exigem afiliação do usuário (inclusive o aplicativo do Portal da Empresa usado para instalar aplicativos LOB) não podem ser instalados.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exporte um perfil como .mobileconfig para implantar em dispositivos iOS

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple Configurator** > **Perfis** > escolha o perfil para exportar > **Exportar Perfil**.
2. Em **Registro Direto**, escolha **Baixar Perfil** e salve o arquivo. Um arquivo de perfil de registro só é válido por duas semanas, momento em que você deve recriá-lo.
3. Transferir o arquivo para um computador Mac executando [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) para enviar por push diretamente como um perfil de gerenciamento para dispositivos iOS.
4. Prepare o dispositivo com o Apple Configurator usando as etapas a seguir:
    1. Em um computador Mac, abra o Apple Configurator 2.0.
    2. Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as Fotos, iTunes e outros aplicativos que são abertos com o dispositivo quando ele é detectado.
    3. No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Escolha **Perfis**.

        ![Perfil de exportação de captura de tela para registro do assistente de instalação com a URL do perfil realçada](./media/ios-apple-configurator-add-profile.png)

    4. Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**. O perfil é adicionado ao dispositivo. Se o dispositivo for Sem supervisão, a instalação necessitará da aceitação no dispositivo.
5. Use as etapas a seguir para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso. Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID da Apple configurada, pois a implantação de aplicativo exige que você tenha uma ID da Apple conectada na App Store.
    1. Desbloquear o dispositivo iOS.
    2. Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.
    3. Forneça a Senha do Dispositivo ou ID da Apple, se necessário.
    4. Aceite o **Aviso** e escolha **Instalar**.
    5. Aceite o **Aviso Remoto** e escolha **Confiar**.
    6. Quando a caixa **Perfil Instalado** confirmar que o perfil foi Instalado, escolha **Concluído**.

6. No dispositivo iOS, abra **Configurações** e vá para **Geral** > **Gerenciamento de Dispositivo** > **Perfil de Gerenciamento**. Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

7. Distribuir dispositivos. O dispositivo iOS agora está registrado no Intune e é gerenciado.





