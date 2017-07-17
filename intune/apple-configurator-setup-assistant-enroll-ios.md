---
title: "Registrar dispositivos iOS – Apple Configurator – Assistente de Configuração"
titleSuffix: Intune on Azure
description: "Saiba como usar o Apple Configurator para registrar dispositivos iOS de propriedade corporativa com o Assistente de Configuração."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Registrar dispositivos iOS com o Apple Configurador
<a id="enroll-ios-devices-with-apple-configurator" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em execução em um computador Mac. O registro com o Apple Configurator exige que você conecte por USB cada dispositivo iOS a um computador Mac para configurar o registro corporativo. Você pode registrar dispositivos no Intune com o Apple Configurator de duas maneiras:
- **Registro do Assistente de Configuração** – restaura o dispositivo para as configurações de fábrica, prepara-o para executar o Assistente de Configuração e instala as políticas da empresa para o novo usuário do dispositivo. A maioria dos cenários exige que a política aplicada ao dispositivo iOS inclua afinidade do usuário para habilitar o aplicativo no Portal da Empresa do Intune.
- **Registro direto** – não redefinir o dispositivo para as configurações de fábrica e registra o dispositivo com uma política predefinida. Esse método é destinado a dispositivos **sem afinidade de usuário**.

>[!NOTE]
>Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).

Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](enrollment-method-choose-ios.md).

## Pré-requisitos
<a id="prerequisites" class="xliff"></a>

Preencha os seguintes pré-requisitos antes de configurar o registro do dispositivo iOS:

- [Um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Acesso físico aos dispositivos iOS
- Números de série do dispositivo (consulte [Como obter um número de série do iOS](https://support.apple.com//HT204308))
- Cabos de conexão USB
- Computador Mac com o [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Adicionar números de série do Apple Configurator](apple-configurator-serial-numbers-add.md)

## Registro pelo Assistente de Configuração
<a id="setup-assistant-enrollment" class="xliff"></a>

### Criar um perfil do Apple Configurator para dispositivos
<a id="create-an-apple-configurator-profile-for-devices" class="xliff"></a>

Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos. As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o Apple Configurator.

1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Perfis de CA**.
3. Na folha **Perfis de registro do Apple Configurator**, selecione **Criar**.
4. Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.
5. Para **Afinidade do Usuário**, escolha se os dispositivos com esse perfil serão registrados com ou sem afinidade do usuário.

   - **Inscrever com afinidade do utilizador** – O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. A afinidade do usuário deve ser configurada para dispositivos gerenciados que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.
   - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

6. Selecione **Criar** para salvar o perfil.

### Adicionar números de série do Apple Configurator
<a id="add-apple-configurator-serial-numbers" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use estas etapas para adicionar números de série ao Intune quando quiser [registrar dispositivos iOS corporativos usando o Apple Configurator com o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md). Você pode adicionar números de série um por vez ou carregar um arquivo de valores de separados por vírgula (CSV) dos números de série. Depois de adicionar os números de série, você poderá atribuir um perfil para eles. O perfil contém as configurações de gerenciamento específicas que você deseja aplicar aos dispositivos.

Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](enrollment-method-choose-ios.md).

**Para adicionar números de série do Apple Configurator ao Intune**

1. Crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita. O máximo atual para a lista é de 500 linhas. Em um editor de texto, a lista .csv é semelhante a:

    F7TLWCLBX196, detalhes do dispositivo</br>
    DLXQPCWVGHMJ, detalhes do dispositivo

2. No portal do Azure, escolha **Registrar dispositivos** e, depois, **Registro da Apple**.
3. Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Números de Série do Apple Configurator**.
4. Na folha **Números de Série do Apple Configurator**, selecione **Adicionar**.
5. Na folha **Adicionar números de série**, selecione um perfil para aplicar a números de série que você está importando. Se você estiver importando um arquivo com novos detalhes que substituirão os existentes, selecione Substituir os detalhes para os identificadores existentes para que os novos detalhes substituam os existentes.
6. Navegue até o arquivo .csv de números de série e selecione **Adicionar**.

### Atribuir um perfil números de série específicos
<a id="assign-a-profile-to-specific-serial-numbers" class="xliff"></a>

O Intune permite atribuir perfis de dois locais diferentes no Portal do Azure. É possível atribuir por perfil do Apple Configurator ou por dispositivos.

#### Atribuir por dispositivos
<a id="assign-by-devices" class="xliff"></a>
1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
3. Na folha **Dispositivos do Apple Configurator**, selecione os números de série que você deseja atribuir a um perfil e, em seguida, selecione **Atribuir Perfil**.
4. Na folha **Atribuir Perfil**, selecione o perfil que você deseja atribuir e selecione **Atribuir**.

#### Atribuir por perfis
<a id="assign-by-profiles" class="xliff"></a>
1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Escolha **Perfis de CA** e selecione o perfil ao qual você deseja atribuir números de série.
3. Na folha nomeada para o perfil, selecione **Números de Série** > **Atribuir**.
4. Selecione os números de série para os quais você deseja atribuir o perfil e selecione o botão **Atribuir**.

### Exportar o perfil para dispositivos iOS
<a id="export-the-profile-to-ios-devices" class="xliff"></a>
Depois de criar o perfil e atribuir os números de série, você precisará exportar o perfil do Intune como uma URL ou um arquivo no formato descrito abaixo. Em seguida, você deverá importá-lo manualmente para o programa Apple Configurator em um Mac, quando então o programa Apple Configurator o implantará nos dispositivos.

1. No portal do Intune, escolha a folha **Perfis de Registro do Apple Configurator** e escolha o perfil a ser exportado.
2. Na folha do perfil, selecione **Exportar Perfil**.
3. Copie a URL do perfil para o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) com o dispositivo iOS anexado. Você fará o upload no Apple Configurator posteriormente para definir o perfil do Intune utilizado pelos dispositivos iOS.

  Você carregará essa URL do perfil para o serviço Apple usando o Apple Configurator no procedimento a seguir para definir o perfil do Intune utilizado pelos dispositivos iOS.
4. Carregue essa URL do perfil para o serviço Apple usando o Apple Configurator para definir o perfil do Intune utilizado pelos dispositivos iOS.
 1.  Em um computador Mac, abra o **Apple Configurator 2**. Na barra de menus, selecione **Apple Configurator 2** e clique em **Preferências**.
  > [!WARNING]
  > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você conectar o dispositivo.
  2. No painel de **preferências**, selecione **Servidores** e escolha o símbolo de mais (+) para inicializar o assistente do Servidor MDM. Escolha **Avançar**.
  3. Insira o **Nome de Host ou a URL** e a **URL do Registro** para o servidor MDM em Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune. Para URL de Registro, insira a URL do perfil de registro exportada do Intune. Escolha **Avançar**.  

    Você pode desconsiderar com segurança um aviso indicando "URL do servidor não verificada". Para continuar, clique em **Avançar** até que o assistente seja concluído.
  4.  Conecte os dispositivos móveis iOS ao computador Mac com um adaptador USB.
  > [!WARNING]
  > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você iniciar o Assistente de Configuração.
  5.  Selecione **Preparar**. No painel **Preparar o Dispositivo iOS**, selecione **Manual** e, em seguida, selecione **Avançar**.
  6. No painel **Registrar no Servidor MDM**, selecione o nome do servidor que você criou e escolha **Avançar**.
  7. No painel **Supervisionar Dispositivos**, selecione o nível de supervisão e, em seguida, selecione **Avançar**.
  8. No painel **Criar uma Organização**, escolha **Organização** ou crie uma nova organização e escolha **Avançar**.
  9. No painel **Configurar o Assistente de Instalação do iOS**, escolha as etapas que serão apresentadas ao usuário e escolha **Preparar**. Se solicitado, autentique para atualizar as configurações de confiança.  
  10. Quando o dispositivo iOS concluir a preparação, desconecte o cabo USB.  
6.  **Distribuir dispositivos**.
    Os dispositivos agora estão prontos para registro corporativo. Desligue os dispositivos e distribua-os para os usuários. Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.

## Registro direto
<a id="direct-enrollment" class="xliff"></a>
Ao registrar dispositivos iOS diretamente com o Apple Configurator, é possível registrar um dispositivo sem adquirir o número de série do dispositivo. Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro. Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente. Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.

1. No portal do Intune, escolha **Registro de dispositivo**, **Registro da Apple** e, em seguida, selecione **Perfis de CA**.
2. Na folha **Perfis de registro do Apple Configurator**, selecione **Criar**.
3. Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.
4. Para **Afinidade de Usuário**, escolha **Registrar sem afinidade de usuário** para garantir que o dispositivo não esteja afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.
5. Selecione **Criar** para salvar o perfil.

### Exporte um perfil como .mobileconfig para implantar em dispositivos iOS
<a id="export-the-profile-as-mobileconfig-to-ios-devices" class="xliff"></a>

1. Na folha **Exportar Perfil**, baixe o perfil de registro para o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) para envio por push diretamente como um perfil de gerenciamento para um dispositivo iOS conectado. Esse método não faz uma redefinição de fábrica do dispositivo.
2. Prepare o dispositivo com o Apple Configurator usando as etapas a seguir.
  1. Em um computador Mac, abra o Apple Configurator 2.0.
  2. Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as Fotos, iTunes e outros aplicativos que são abertos com o dispositivo quando ele é detectado.
  3. No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Escolha **Perfis**.
  4. Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**. O perfil é adicionado ao dispositivo. Se o dispositivo for Sem supervisão, a instalação necessitará da aceitação no dispositivo.
3. Use as etapas a seguir para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso. Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.
   1. Desbloquear o dispositivo iOS.
   2. Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.
   3. Forneça a Senha do Dispositivo ou a ID da Apple, se necessário.
   4. Aceite o **Aviso** e escolha **Instalar**.
   5. Aceite o **Aviso Remoto** e escolha **Confiar**.
   6. Quando a caixa **Perfil Instalado** confirmar que o perfil foi Instalado, escolha **Concluído**.

    4. No dispositivo iOS, abra **Configurações** e vá para **Geral** > **Gerenciamento de Dispositivo** > **Perfil de Gerenciamento**. Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

    5. Distribuir dispositivos. O dispositivo iOS agora está registrado com o Intune e é gerenciado.


## Como os usuários instalam e usam o Portal da Empresa em seus dispositivos
<a id="how-users-install-and-use-the-company-portal-on-their-devices" class="xliff"></a>

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão realizar várias etapas adicionais descritas abaixo para concluir o Assistente de Configuração e instalar o aplicativo do Portal da Empresa.
