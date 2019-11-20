---
title: Configurar uma Página de status de registro
titleSuffix: Microsoft Intune
description: Configure uma página de saudação para usuários que estão registrando dispositivos com Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: ericor
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e453002493e95bd5147cca115075a17a6e7a298
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709321"
---
# <a name="set-up-an-enrollment-status-page"></a>Configurar uma Página de status de registro
 
[!INCLUDE [azure_portal](../includes/azure_portal.md)]
 
A Página de status de registro (ESP) exibe informações de instalação sobre dispositivos Windows 10 (versão 1803 e posterior) durante o registro inicial do dispositivo. Por exemplo:
- ao usar o [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/) 
- ou sempre que um dispositivo gerenciado for iniciado pela primeira vez depois que uma política de Página de status de registro tiver sido aplicada. 

Uma Página de status de registro pode ajudar os usuários a entender o status do dispositivo durante sua configuração. Você pode criar vários perfis de Página de status de registro e aplicá-los a diferentes grupos que contêm usuários. Os perfis podem ser definidos como:
- Mostrar progresso da instalação.
- Bloquear uso até a instalação ser concluída.
- Especificar o que um usuário pode fazer se a configuração do dispositivo falhar.

Também é possível definir a ordem de prioridade de cada perfil, de modo a levar em conta atribuições de perfil conflitantes do mesmo usuário.

> [!NOTE]
> A Página de status de registro destina-se apenas a um usuário que pertence a um grupo atribuído, e a política é definida no dispositivo no momento do registro para todos os usuários que usam o dispositivo.  

## <a name="available-settings"></a>Configurações disponíveis

 As seguintes configurações podem ser definidas para personalizar o comportamento da Página de status de registro:

<table>
<th align="left">Setting<th align="left">Sim<th align="left">Não
<tr><td>Mostrar o andamento da instalação do perfil e do aplicativo<td>A Página de status de registro é exibida.<td>A Página de status de registro não é exibida.
<tr><td>Bloquear o uso do dispositivo até que todos os perfis e aplicativos estejam instalados<td>As configurações nessa tabela são disponibilizadas para personalizar o comportamento da Página de status de registro para que o usuário seja capaz de resolver possíveis problemas de instalação.
<td>A Página de status de registro é exibida sem opções adicionais para tratar de falhas de instalação.
<tr><td>Permitir que os usuários redefinam o dispositivo se ocorrer um erro de instalação<td>Um botão <b>Redefinir dispositivo</b> é exibido em caso de falha na instalação.<td>O botão <b>Redefinir dispositivo</b> não é exibido em caso de falha na instalação.
<tr><td>Permitir que os usuários usem o dispositivo se ocorrer um erro de instalação<td>Um botão <b>Continuar mesmo assim</b> é exibido em caso de falha na instalação.<td>O botão <b>Continuar mesmo assim</b> não é exibido em caso de falha na instalação.
<tr><td>Mostrar erro de tempo limite quando a instalação demorar mais do que os minutos especificados<td colspan="2">Especifique o número de minutos a aguardar para a conclusão da instalação. Um valor padrão de 60 minutos está inserido.
<tr><td>Mostrar mensagem personalizada quando ocorrer um erro<td>Uma caixa de texto é fornecida, na qual é possível especificar uma mensagem personalizada que será exibida se ocorrer um erro de instalação.<td>A mensagem padrão é exibida: <br><b>A instalação excedeu o tempo limite definido por sua organização. Tente novamente ou entre em contato com a equipe de suporte de TI para obter ajuda.<b>
<tr><td>Permitir que os usuários coletem logs sobre erros de instalação<td>Se houver um erro de instalação, um botão <b>Coletar logs</b> será exibido. <br>Se o usuário clicar nesse botão, deverá escolher um local para salvar o arquivo de log <b>MDMDiagReport.cab</b><td>O botão <b>Coletar logs</b> não é exibido em caso de falha na instalação.
<tr><td>Bloquear o uso do dispositivo até que os aplicativos necessários sejam instalados, caso estejam atribuídos ao usuário/dispositivo<td colspan="2">Escolha <b>Todos</b> ou <b>Selecionados</b>. <br><br>Se <b>Selecionados</b> for escolhido, um botão <b>Selecionar aplicativos</b> é exibido, possibilitando escolher quais aplicativos devem ser instalados antes de habilitar o dispositivo.
</table>

## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Ativar a Página de status de registro padrão para todos os usuários

Para ativar a Página de status de registro, siga as etapas abaixo.
 
1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro do Windows** > **Página de status de registro**.
2. Na folha **Página de Status de Registro**, escolha **Padrão** > **Configurações**.
3. Para **Mostrar o progresso da instalação do aplicativo e do perfil**, escolha **Sim**.
4. Escolha as outras configurações que você deseja ativar e, em seguida, escolha **Salvar**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Criar perfil da Página de status de registro e atribuir a um grupo

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro do Windows** > **Página de status de registro** > **Criar perfil**.
2. Forneça um **Nome** e uma **Descrição**.
3. Escolha **Criar**.
4. Escolha o novo perfil na lista **Página de status de registro**.
5. Escolha **Atribuições** > **Selecionar grupos** > escolha os grupos para os quais você deseja adotar esse perfil > **Selecionar** > **Salvar**.
6. Escolha **Configurações** > escolha as configurações que você deseja aplicar a este perfil > **Salvar**.

## <a name="set-the-enrollment-status-page-priority"></a>Definir a prioridade da página de status do registro

Os usuários podem estar em vários grupos e ter vários perfis da Página de status de registro. Para lidar com esses conflitos, defina as prioridades de cada perfil. Durante o registro, se alguém tiver mais de um perfil da Página de status de registro, apenas o perfil com a prioridade mais alta será aplicado ao dispositivo que está sendo registrado.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro do Windows** > **Página de status de registro**.
2. Focalize o perfil na lista.
3. Usando os três pontos verticais, arraste o perfil para a posição desejada na lista.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Bloquear o acesso a um dispositivo até que um aplicativo específico seja instalado

Você pode especificar quais aplicativos precisam ser instalados antes de o usuário poder acessar a área de trabalho.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro do Windows** > **Página de status de registro**.
2. Escolha um perfil > **Configurações**.
3. Escolha **Sim** para **Mostrar o andamento da instalação do perfil e de aplicativos**.
4. Escolha **Sim** para **Bloquear o uso do dispositivo até que todos os perfis e aplicativos estejam instalados**.
5. Escolha **Selecionados** para **Bloquear o uso do dispositivo até que os aplicativos necessários sejam instalados, caso estejam atribuídos ao usuário/dispositivo**.
6. Escolha **Selecionar aplicativos** > escolha os aplicativos > **Selecionar** > **Salvar**.

## <a name="enrollment-status-page-tracking-information"></a>Informações de acompanhamento da Página de status de registro

Há três fases para as quais a Página de status de registro rastreia informações: preparação do dispositivo, configuração do dispositivo e configuração da conta.

### <a name="device-preparation"></a>Preparação do dispositivo

Para a preparação do dispositivo, a Página de status de registro rastreia:
- Atestados de chave TPM (Trusted Platform Module, quando aplicável)
- Andamento do ingresso no Azure Active Directory
- Registro no Intune
- Instalação de extensões de gerenciamento do Intune

### <a name="device-setup"></a>Configuração do dispositivo

A Página de status de registro rastreia os seguintes itens de configuração do dispositivo (se eles estão atribuídos a todos os dispositivos ou a um grupo de dispositivos do qual o dispositivo de registro faz parte):
- Diretivas de segurança
  - Um CSP (provedor de serviço de configuração) para todos os registros.
  - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
  - Aplicativos MSI de LoB (linha de negócios) por computador.
  - Aplicativos de repositório de LoB com contexto de instalação = Dispositivo.
  - Aplicativos de repositório de LoB e repositório offline com contexto de instalação = Dispositivo.
  - Aplicativos Win32 (somente Windows 10 versão 1903 e mais recentes) 
- Perfis de conectividade
  - Perfis de Wi-Fi ou VPN atribuídos a **Todos os Dispositivos** ou um grupo de dispositivos do qual o dispositivo de registro é um membro, mas somente para dispositivos do Autopilot
- Perfis de certificado atribuídos a **Todos os Dispositivos** ou a um grupo de dispositivos do qual o dispositivo de registro é um membro, mas somente para dispositivos do Autopilot

### <a name="account-setup"></a>Configuração da conta
Para a configuração da conta, a Página de status de registro rastreia os seguintes itens se eles estão atribuídos ao usuário conectado no momento:
- Diretivas de segurança
  - Um CSP para todos os registros.
  - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
  - Aplicativos MSI de LoB por usuário atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro.
  - Aplicativos MSI de LoB por computador atribuídos a Todos os Usuários ou a um grupo de usuários do qual o dispositivo de registro de usuário é membro.
  - Aplicativos de linha de negócios, online e offline que estão atribuídos a qualquer um dos seguintes objetos:
    - Todos os Dispositivos
    - Todos os Usuários
    - Um grupo de usuários do qual o usuário que está registrando o dispositivo faz parte com contexto de instalação definido como Usuário.
  - Aplicativos Win32 (somente Windows 10 versão 1903 e mais recentes) 
- Perfis de conectividade
  - Perfis de Wi-Fi ou VPN atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.
- Certificados
  - Perfis de certificado atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.

### <a name="troubleshooting"></a>Solução de problemas
Principais perguntas sobre a solução de problemas.

- Por que meus aplicativos não foram instalados durante a fase de configuração do dispositivo na implantação do Autopilot que está usando a Página de status de registro?
  - Para garantir que os aplicativos sejam instalados durante uma fase de configuração do dispositivo do Autopilot, verifique se: 
        1. O aplicativo está selecionado para bloquear o acesso na lista de aplicativos escolhidos
        2. Você está direcionando os aplicativos para o mesmo grupo de dispositivos do Azure Active Directory ao qual seu perfil do Autopilot está atribuído. 

- Por que a Página de status de registro é mostrada para implantações que não são do Autopilot, por exemplo, quando um usuário faz logon pela primeira vez em um dispositivo registrado de cogerenciamento do Configuration Manager?  
  - A Página de status de registro lista o status da instalação para todos os métodos de registro, incluindo:
      - Autopilot
      - Cogerenciamento do Configuration Manager
      - Quando um novo usuário faz logon no dispositivo que tem a política da Página de status de registro aplicada pela primeira vez

- Como posso desabilitar a Página de status de registro se ela está configurada no dispositivo?
  - A política da Página de status de registro é definida em um dispositivo no momento do registro. Para desabilitar a Página de status de registro, você deve desabilitar as seções da Página de status de registro do usuário e do dispositivo. Para desabilitar as seções, crie configurações personalizadas de OMA-URI com as definições a seguir.

      Desabilite a Página de status de registro do usuário:

      ```
      Name:  Disable User ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipUserStatusPage
      Data type:  Boolean
      Value:  True 
      ```
      Desabilite a Página de status de registro do dispositivo:

      ```
      Name:  Disable Device ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipDeviceStatusPage
      Data type:  Boolean
      Value:  True 
      ```
- Como faço para coletar arquivos de log?
  - Há duas maneiras de coletar os arquivos de log da Página de status de registro:
      - Habilite a capacidade dos usuários de coletar logs na política ESP. Quando ocorre um tempo limite na Página de status de registro, o usuário final pode escolher a opção **Coletar logs**. Os arquivos de log podem ser copiados para uma unidade USB
      - Abra um prompt de comando usando a sequência de teclas Shift+F10 e, em seguida, insira a seguinte linha de comando para gerar os arquivos de log: 

      ```
      mdmdiagnosticstool.exe -area Autopilot -cab <pathToOutputCabFile>.cab 
      ```

### <a name="known-issues"></a>Problemas conhecidos
Veja os problemas conhecidos abaixo. 
- Desabilitar o perfil ESP não removerá a política ESP de dispositivos e os usuários ainda terão o ESP ao fazer logon no dispositivo pela primeira vez. A política não é removida quando o perfil ESP é desabilitado. É preciso implantar o OMA-URI para desabilitar o ESP. Confira os pontos acima para obter instruções sobre como desabilitar o ESP usando o OMA-URI. 
- Uma reinicialização pendente sempre causará um tempo limite. O tempo limite ocorre porque o dispositivo precisa ser reinicializado. A reinicialização é necessária para permitir que o item rastreado na Página de status de registro seja concluído. Uma reinicialização fará com que a Página de status de registro seja encerrada e o dispositivo não entrará durante a configuração da conta após a reinicialização.  Considere não exigir uma reinicialização com a instalação do aplicativo. 
- Uma reinicialização durante a configuração do dispositivo forçará o usuário a inserir suas credenciais antes de fazer a transição para a fase de configuração da conta. As credenciais do usuário não são preservadas durante a reinicialização. Faça com que o usuário insira suas credenciais para que a Página de status de registro prossiga. 
- A Página de status de registro sempre atingirá o tempo limite durante uma adição de registro de conta corporativa e de estudante em versões do Windows 10 inferiores à 1903. A Página de status de registro aguarda a conclusão do registro do Azure Active Directory. O problema foi corrigido no Windows 10 versão 1903 e mais recente.  
- A implantação do Autopilot do Azure Active Directory híbrido com ESP demora mais do que a duração do tempo limite definida no perfil ESP. Em implantações do Autopilot do Azure AD híbrido, o ESP levará 40 minutos a mais do que o valor definido no perfil ESP. Esse atraso dá tempo para que o conector local do AD crie o novo registro de dispositivo para o Azure Active Directory. 
- A página de logon do Windows não é preenchida previamente com o nome de usuário no Modo Controlado pelo Usuário do Autopilot. Se ocorre uma reinicialização durante a fase de configuração do dispositivo ESP:
    - As credenciais do usuário não são preservadas
    - O usuário deve inserir as credenciais novamente antes de prosseguir da fase de configuração do dispositivo para a fase de configuração da conta
- O ESP está parado há muito tempo ou nunca conclui a fase de "Identificação". O Intune analisa as políticas ESP durante a fase de identificação. Um dispositivo pode nunca concluir a análise das políticas de ESP se o usuário atual não tem um Intune licenciado atribuído.  
- A configuração do Controle de Aplicativos do Windows Defender faz com que ocorra a reinicialização de um prompt durante o Autopilot. A configuração do Aplicativo do Windows Defender (AppLocker CSP) requer uma reinicialização. Quando essa política é configurada, ela pode fazer com que um dispositivo seja reinicializado durante o Autopilot. Atualmente, não há como suprimir ou adiar a reinicialização.
- Quando a política DeviceLock (https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) ) é habilitada como parte de um perfil ESP, o logon automático de desktop para usuário ou OOBE pode falhar inesperadamente por dois motivos.
  - Se o dispositivo não for reinicializado antes de sair da fase de configuração do dispositivo ESP, o usuário poderá ser solicitado a inserir suas credenciais do Azure Active Directory. Esse prompt ocorre no lugar de um logon automático bem-sucedido em que o usuário vê a animação de primeiro logon do Windows.
  - O logon automático falhará se o dispositivo for reinicializado depois que o usuário inserir suas credenciais do Azure AD, mas antes de sair da fase de configuração do dispositivo ESP. Essa falha ocorre porque a fase de configuração do dispositivo ESP nunca foi concluída. A solução alternativa é redefinir o dispositivo.

## <a name="next-steps"></a>Próximas etapas
Depois de configurar páginas de registro do Windows, saiba como gerenciar dispositivos do Windows. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](../remote-actions/device-management.md)
