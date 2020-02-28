---
title: Solucionar problemas de instalação do aplicativo
titleSuffix: Microsoft Intune
description: Use o painel de solução de problemas do Microsoft Intune para resolver problemas com a instalação do aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 13aea23f58c69d5c7e38f77ae7dfa19bd12edd35
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511644"
---
# <a name="troubleshoot-app-installation-issues"></a>Solucionar problemas de instalação do aplicativo

Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. O Microsoft Intune fornece detalhes sobre falha na instalação do aplicativo, com os quais os operadores de suporte técnico e os administradores dessa plataforma podem exibir informações do aplicativo para atender às solicitações de ajuda dos usuários. O painel de solução de problemas do Intune fornece os detalhes da falha, inclusive sobre aplicativos gerenciados no dispositivo do usuário. Fornecemos detalhes sobre o ciclo de vida de ponta a ponta de um aplicativo em cada dispositivo individual, no painel **Aplicativos Gerenciados**. Você pode exibir problemas de instalação, por exemplo, quando o aplicativo for criado, modificado, direcionado e baixado em um dispositivo. 

> [!NOTE]
> Para obter informações sobre o código de erro de instalação de aplicativos específico, confira [Referência de erros de instalação de aplicativos do Intune](~/apps/app-install-error-codes.md).

## <a name="app-troubleshooting-details"></a>Detalhes da solução de problemas do aplicativo

O Intune fornece detalhes da solução de problemas do aplicativo, de acordo com os aplicativos instalados no dispositivo de um usuário específico.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Solução de problemas + suporte**.
4. Clique em **Selecionar usuário** para selecionar um usuário cujos problemas serão solucionados. O painel **Selecionar usuário** será exibido.
5. Selecione um usuário digitando o nome ou o endereço de email. Clique em **Selecionar**, na parte inferior do painel. As informações da solução de problemas do usuário são exibidas no painel **Solucionar problemas**. 
6. Selecione na lista **Dispositivos** o dispositivo para o qual você deseja solucionar problemas.
    ![Painel Solução de problemas do Microsoft Intune](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. Selecione **Aplicativos Gerenciados**, no painel do dispositivo selecionado. O programa exibirá os aplicativos gerenciados.
    ![Detalhes de um dispositivo específico gerenciado pelo Intune.](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. Selecione um aplicativo na lista, cujo **Status de Instalação** indica uma falha.
    ![Aplicativo selecionado que mostra os detalhes da falha de instalação.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > O mesmo aplicativo pode ser atribuído a vários grupos, mas com diferentes ações previstas (finalidades) para o aplicativo. Por exemplo, uma tentativa resolvida de um aplicativo mostrará **excluído**, se o aplicativo for excluído por um usuário, durante a respectiva atribuição. Para saber mais, confira [Como são resolvidos os conflitos entre as finalidades do aplicativo](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Se ocorrer uma falha de instalação para um aplicativo necessário, você ou o suporte técnico poderá sincronizar o dispositivo e tentar novamente a instalação do aplicativo.

Os detalhes do erro de instalação do aplicativo indicarão o problema. Use esses detalhes para determinar a ação adequada à resolução do problema. Para obter mais informações sobre como solucionar problemas de instalação do aplicativo, confira [Erros de instalação do aplicativo Android](app-install-error-codes.md#android-app-installation-errors) e [Erros de instalação do aplicativo iOS](app-install-error-codes.md#ios-and-ipados-app-installation-errors).

> [!Note]  
> Você também pode acessar o painel **solução de problemas** apontando o navegador para: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>A instalação do aplicativo de destino do grupo de usuários não acessa o dispositivo
As seguintes ações deverão ser consideradas quando você tiver problemas ao instalar aplicativos:
- Se o aplicativo não for exibido no Portal da Empresa, verifique se ele está implantado com a intenção **Disponível** e se o usuário está acessando o Portal da Empresa com o tipo de dispositivo compatível com o aplicativo.
- Em dispositivos Windows BYOD, o usuário precisa adicionar uma conta corporativa ao dispositivo.
- Verifique se o usuário está acima do limite de dispositivos do AAD:
  1. Navegue até [Configurações do Dispositivo do Azure Active Directory](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId).
  2. Anote o valor definido para **Máximo de dispositivos por usuário**.
  3. Navegue até [Usuários do Azure Active Directory](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers).
  4. Selecione o usuário afetado e clique em **Dispositivos**.
  5. Se o usuário estiver acima do limite definido, exclua os registros obsoletos que não são mais necessários.
- Para dispositivos DEP iOS/iPadOS, verifique se o usuário está listado como **Registrado pelo Usuário** no painel Visão Geral do Dispositivo do Intune. Se NA for exibido, implante uma política de configuração para o Portal da Empresa do Intune. Para obter mais informações, confira [Configurar o aplicativo do Portal da Empresa](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-and-ipados-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Solução de problemas de instalação de aplicativo Win32

Selecione o aplicativo Win32 implantado usando a extensão de gerenciamento do Intune. Você pode selecionar a opção **Coletar logs** quando a instalação do aplicativo Win32 falha. 

> [!IMPORTANT]
> A opção **Coletar logs** não será habilitada quando o aplicativo Win32 tiver sido instalado com êxito no dispositivo.<p>Antes de coletar informações de log de aplicativo do Win32, a extensão de gerenciamento do Intune deve ser instalada no cliente Windows. A extensão de gerenciamento do Intune é instalada quando um script do PowerShell ou um aplicativo Win32 é implantado em um grupo de segurança de usuários ou dispositivos. Para obter mais informações, veja [Extensão de Gerenciamento do Intune – pré-requisitos](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Coletar arquivo de log

Para coletar seus logs de instalação de aplicativos do Win32, primeiro siga as etapas apresentadas na seção [Detalhes de solução de problemas do aplicativo](troubleshoot-app-install.md#app-troubleshooting-details). Então continue com as etapas a seguir:

1. Clique na opção **Coletar logs** no painel **Detalhes da instalação**.

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Forneça caminhos de arquivo com nomes de arquivo de log para iniciar o processo de coleta de arquivo de log e clique em **OK**.

    > [!NOTE]
    > A coleta de log levará menos de duas horas. Tipos de arquivos compatíveis: *.log, .txt, .dmp, .cab, .zip, .XML, .evtx e .evtl*. É permitido um máximo de 25 caminhos de arquivo.

3. Depois que os arquivos de log foram coletados, você pode selecionar o link **logs** para baixar os arquivos de log.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Uma notificação será exibida indicando o êxito da coleção de log do aplicativo.

#### <a name="win32-log-collection-requirements"></a>Requisitos de coleção de log do Win32

Há requisitos específicos que devem ser seguidos para coletar arquivos de log:

- Você deve especificar o caminho completo do arquivo de log. 
- Você pode especificar variáveis de ambiente para a coleção de log, como o seguinte:<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- Somente extensões de arquivo exatas são permitidas, como:<br>
  *.log,.txt,.dmp,.cab,.zip,.xml*
- O arquivo de log máximo para upload é de 60 MB ou 25 arquivos, o que ocorrer primeiro. 
- A coleta de log de instalação de aplicativo do Win32 está habilitada para aplicativos que tenham a intenção de atribuição de aplicativo necessário, disponível e de desinstalação.
- Os logs armazenados são criptografados para proteger as informações de identificação pessoal contidas nos logs.
- Quando a abertura de tíquetes de suporte para aplicativo Win32 falha, anexe os logs de falha relacionados seguindo as etapas apresentadas acima.

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Solução de problemas dos aplicativos da Microsoft Store

As informações no tópico [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Microsoft Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) ajudam a solucionar problemas comuns que podem ocorrer ao instalar aplicativos da Microsoft Store, usando o Intune ou por outros meios.

## <a name="app-troubleshooting-resources"></a>Recursos para solucionar problemas
- [Como implantar o Visio e o Project como parte da implantação do Office Pro Plus](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Tomar medidas para garantir a implantação de aplicativos MSfB por meio da instalação do Intune no Windows 10 1903](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Solução de problemas de implantações de aplicativo MSI no Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Melhores práticas para distribuição de software no agente clássico do computador Windows do Intune](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre a solução de problemas do Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](../fundamentals/help-desk-operators.md). 
- Saiba mais sobre os problemas conhecidos do Microsoft Intune. Para obter mais informações, confira [Sucesso dos Clientes do Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](../fundamentals/get-support.md).
