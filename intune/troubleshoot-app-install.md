---
title: Solucionar problemas de instalação do aplicativo
titlesuffix: Microsoft Intune
description: Use o painel de solução de problemas do Microsoft Intune para resolver problemas com a instalação do aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd43bfda69b42fb81a72d520d169fe1785161f65
ms.sourcegitcommit: 0f19bc5c76b7c0835bfd180459f2bbd128eec1c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53266997"
---
# <a name="troubleshoot-app-installation-issues"></a>Solucionar problemas de instalação do aplicativo

Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. O Microsoft Intune fornece detalhes sobre falha na instalação do aplicativo, com os quais os operadores de suporte técnico e os administradores dessa plataforma podem exibir informações do aplicativo para atender às solicitações de ajuda dos usuários. O painel de solução de problemas do Intune fornece os detalhes da falha, inclusive sobre aplicativos gerenciados no dispositivo do usuário. Fornecemos detalhes sobre o ciclo de vida de ponta a ponta de um aplicativo em cada dispositivo individual, no painel **Aplicativos Gerenciados**. Você pode exibir problemas de instalação, por exemplo, quando o aplicativo for criado, modificado, direcionado e baixado em um dispositivo. 

## <a name="to-review-app-troubleshooting-details"></a>Para examinar os detalhes da solução de problemas do aplicativo

O Intune fornece detalhes da solução de problemas do aplicativo, de acordo com os aplicativos instalados no dispositivo de um usuário específico.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Solucionar problemas**.
4. Clique em **Selecionar usuário** para selecionar um usuário cujos problemas serão solucionados. O painel **Selecionar usuário** será exibido.
5. Selecione um usuário digitando o nome ou o endereço de email. Clique em **Selecionar**, na parte inferior do painel. As informações da solução de problemas do usuário são exibidas no painel **Solucionar problemas**. 
6. Selecione na lista **Dispositivos** o dispositivo para o qual você deseja solucionar problemas.
    ![Painel Solução de problemas do Microsoft Intune](media/troubleshoot-app-install-01.png)
7. Selecione **Aplicativos Gerenciados**, no painel do dispositivo selecionado. O programa exibirá os aplicativos gerenciados.
    ![Detalhes de um dispositivo específico gerenciado pelo Intune.](media/troubleshoot-app-install-02.png)
8. Selecione um aplicativo na lista, cujo **Status de Instalação** indica uma falha.
    ![Aplicativo selecionado que mostra os detalhes da falha de instalação.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > O mesmo aplicativo pode ser atribuído a vários grupos, mas com diferentes ações previstas (finalidades) para o aplicativo. Por exemplo, uma tentativa resolvida de um aplicativo mostrará **excluído**, se o aplicativo for excluído por um usuário, durante a respectiva atribuição. Para saber mais, confira [Como são resolvidos os conflitos entre as finalidades do aplicativo](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Se ocorrer uma falha de instalação para um aplicativo necessário, você ou o suporte técnico poderá sincronizar o dispositivo e tentar novamente a instalação do aplicativo.

Os detalhes do erro de instalação do aplicativo indicarão o problema. Use esses detalhes para determinar a ação adequada à resolução do problema. Para saber mais sobre como solucionar problemas de instalação do aplicativo, confira [Códigos de erro da solução de problemas de instalação de aplicativos](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> Você também pode acessar o painel **solução de problemas** apontando o navegador para: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="app-installation-errors"></a>Erros de instalação do aplicativo

As seguintes mensagens de erro e descrições fornecem detalhes sobre os erros de instalação no Android e no iOS. 

### <a name="android-errors"></a>Erros no Android

|    Mensagem/código do erro    |    Descrição    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Falha ao instalar o aplicativo. (0xC7D14FB5)    |    Esta mensagem de erro é exibida quando o Intune não consegue determinar a causa do erro de instalação do aplicativo no Android. Não foi fornecida nenhuma informação pelo Android durante a falha.       Esse erro é retornado quando o download do APK é bem-sucedido, mas a instalação do aplicativo falha. Esse erro pode ocorrer com mais frequência devido a um arquivo APK inválido que não pode ser instalado no dispositivo. Uma possível causa pode ser quando o Google Play Protect bloqueia a instalação do aplicativo devido a questões de segurança. Outra possível causa desse erro é quando um dispositivo não dá suporte para o aplicativo. Por exemplo, se o aplicativo exigir a API versão 21 ou superior e o dispositivo tiver a versão 19 da API no momento.         O Intune retorna este erro para dispositivos DA e KNOX e, embora possa haver uma notificação de que os usuários podem clicar para tentar novamente, se houver um problema com o APK, ele nunca continuará a falhar. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.        |
|    A instalação do aplicativo foi cancelada porque o arquivo de instalação (APK) foi excluído após o download, mas antes da instalação. (0xC7D14FBA)    |    O download do APK foi bem-sucedido, mas antes do usuário instalar o aplicativo, o arquivo foi removido do dispositivo. Isso pode ocorrer quando há uma grande diferença de tempo entre o download e a instalação. Por exemplo, o usuário cancelou a instalação original, esperou e clicou na notificação para tentar novamente.         Essa mensagem de erro é retornada apenas para cenários de DA. Os cenários do KNOX podem ocorrer silenciosamente. Uma notificação para tentar novamente é apresentada para que o usuário possa aceitar em vez de cancelar. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.    |
|    A instalação do aplicativo foi cancelada pois o processo foi reiniciado durante a instalação. (0xC7D14FBB)    |    O dispositivo foi reiniciado durante o processo de instalação do APK, resultando no cancelamento da instalação.        Essa mensagem de erro é retornada para dispositivos DA e KNOX. O Intune apresenta uma notificação de que os usuários podem clicar para tentar novamente. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.    |
|    O aplicativo ainda não foi detectado depois que a desinstalação foi concluída com sucesso. (0x87D1041C)    |    O usuário desinstalou o aplicativo explicitamente. Esse erro não é retornado do cliente. É um erro produzido quando o aplicativo foi instalado em determinado momento, mas, em seguida, o usuário desinstalou-o. Esse erro só deve ocorrer para os aplicativos obrigatórios. Os usuários podem desinstalar aplicativos não obrigatórios. Esse erro só pode acontecer em DA. O KNOX bloqueia a desinstalação de aplicativos gerenciados.       A próxima sincronização postará novamente a notificação no dispositivo para o usuário instalar.   O usuário pode ignorar a notificação. Esse erro continuará a ser relatado até que o usuário instale o aplicativo.    |
|    O download falhou devido a um erro desconhecido. (0xC7D14FB2)    |    Esse erro ocorre quando o download falha. Normalmente, esse erro pode ocorrer devido a problemas de Wi-Fi ou a conexões lentas.       Esse erro é retornado apenas para cenários de DA. Para cenários do KNOX, não é solicitado que o usuário instale. Isso pode ocorrer silenciosamente. O Intune apresenta uma notificação de que os usuários podem clicar para tentar novamente. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.    |
|    O download falhou devido a um erro desconhecido. A política será repetida na próxima vez que o dispositivo for sincronizado. (0xC7D15078)    |    Esse erro ocorre quando o download falha. Normalmente, esse erro pode ocorrer devido a problemas de Wi-Fi ou a conexões lentas.       Esse erro é retornado apenas para cenários de DA. Para cenários do KNOX, não é solicitado que o usuário instale. Isso pode ocorrer silenciosamente.    |
|    O usuário final cancelou a instalação do aplicativo. (0xC7D14FB1)    |    O usuário desinstalou o aplicativo explicitamente. Esse erro é retornado quando a atividade de instalação do sistema operacional Android é cancelada pelo usuário. O usuário pressionou o botão Cancelar quando o prompt de instalação do sistema operacional foi apresentado ou clicou para sair do prompt.        Esse erro é retornado apenas para cenários de DA. Para cenários do KNOX, não é solicitado que o usuário instale. Isso pode ocorrer silenciosamente. O Intune apresenta uma notificação de que os usuários podem clicar para tentar novamente. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.    |
|    O processo de download do arquivo foi interrompido inesperadamente. (0xC7D15015)    |    O sistema operacional interrompeu o processo de download antes de sua conclusão. Esse erro pode ocorrer quando o dispositivo tem pouca bateria ou o download está demorando muito.       Esse erro é retornado apenas para cenários de DA. Para cenários do KNOX, não é solicitado que o usuário instale. Isso pode ocorrer silenciosamente. O Intune apresenta uma notificação de que os usuários podem clicar para tentar novamente. Se o aplicativo for um aplicativo disponível, a notificação poderá ser descartada. No entanto, se o aplicativo for obrigatório, ela não poderá ser descartada.    |
|    O serviço de download do arquivo foi interrompido inesperadamente. A política será repetida na próxima vez que o dispositivo for sincronizado. (0xC7D1507C)    |    O sistema operacional interrompeu o processo de download antes de sua conclusão. Esse erro pode ocorrer quando o dispositivo tem pouca bateria ou o download está demorando muito.       Esse erro é retornado apenas para cenários de DA. Para cenários do KNOX, não é solicitado que o usuário instale. Isso pode ocorrer silenciosamente.    |

### <a name="ios-errors"></a>Erros no iOS

|    Mensagem/código do erro    |    Descrição    |
|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    (0x87D12906)    |    Agente do Apple MDM retornou que o comando de instalação falhou.        |
|    (0x87D1313C)    |    A conexão de rede foi perdida enquanto a URL do serviço de download atualizada era enviada para o dispositivo. Especificamente, um servidor com o nome do host especificado não pôde ser encontrado.    |
|    O dispositivo iOS está ocupado no momento. (0x87D11388)    |    O dispositivo iOS estava ocupado, o que resultou em erro.    |
|    A instalação do aplicativo falhou. (0x87D13B64)    |    Ocorreu uma falha na instalação do aplicativo. Os logs do XCODE são necessários para solucionar esse erro.    |
|    O aplicativo é gerenciado, mas expirou ou foi removido pelo usuário. (0x87D13B66)    |    O usuário desinstalou o aplicativo explicitamente. O aplicativo expirou, mas seu download falhou, ou a detecção do aplicativo não corresponde à resposta do dispositivo.   Além disso, esse erro pode ocorrer com base em um bug da plataforma iOS 9.2.2.    |
|    O aplicativo está agendado para instalação, mas precisa de um código de resgate para que a transação seja concluída.   (0x87D13B60)    |    Esse erro normalmente ocorre com os aplicativos da iOS Store que são pagos.     |
|    O aplicativo ainda não foi detectado depois que a desinstalação foi concluída com sucesso. (0x87D1041C)    |    O processo de detecção do aplicativo não correspondeu à resposta do dispositivo.    |
|    O usuário rejeitou a oferta para instalar o aplicativo. (0x87D13B62)    |    Durante a instalação inicial do aplicativo, o usuário clicou em Cancelar.    |
|    O usuário rejeitou a oferta para atualizar o aplicativo. (0x87D13B63)    |    O usuário final clicou em Cancelar durante o processo de atualização.     |
|    Erro desconhecido (0x87D103E8)    |    Ocorreu um erro de instalação de aplicativo desconhecido. Esse é o erro resultante quando o outro erro não ocorre.    |

### <a name="other-installation-errors"></a>Outros erros de instalação

|    Mensagem/código do erro    |    Descrição    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF,   0x80CF201C (erro de cliente)    |    Para instalar esse aplicativo, você deve ter um sistema habilitado para carregamento. Verifique se o pacote do aplicativo foi assinado com uma assinatura confiável e instalado em um dispositivo com domínio associado que tenha a política **AllowAllTrustedApps** habilitada ou um dispositivo que tenha uma licença do Windows Sideloading com a política **AllowAllTrustedApps** habilitada. Para mais informações, veja [Solucionando empacotamento, implantação e consulta de aplicativos da Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    Não foi possível abrir o pacote. Possíveis causas:<ul><li> O pacote não está assinado.</li><li> O nome do publicador não corresponde ao assunto do certificado de assinatura.</li></ul> Consulte o log de eventos de **AppxPackagingOM** para obter mais informações. Para saber mais, veja [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    Falha na atualização do pacote, dependência ou validação de conflito. Possíveis causas:<ul><li> O pacote de entrada está em conflito com um pacote instalado.</li><li> Uma dependência de pacote especificada não foi encontrada.</li><li> O pacote não oferece suporte à arquitetura de processador correta.</li></ul> Consulte o log de eventos de **AppXDeployment-Server** para obter mais informações. Para saber mais, veja [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    O pacote fornecido já foi instalado e sua reinstalação está bloqueada. Talvez você receba esse erro se estiver instalando um pacote que não é idêntico ao pacote já instalado. Confirme se a assinatura digital também faz parte do pacote. Quando um pacote é recriado ou assinado novamente, ele não é mais idêntico bit a bit ao pacote instalado anteriormente. Duas opções possíveis para corrigir esse erro são as seguintes:<ul><li> Aumente o número de versão do aplicativo e recrie e assine novamente o pacote.</li><li> Remova o pacote antigo para cada usuário no sistema antes de instalar o novo pacote.</li></ul> Para saber mais, veja [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Êxito na instalação do aplicativo, mas o aplicativo não foi detectado. O aplicativo foi implantado com êxito pelo Intune e depois foi desinstalado. Os motivos para desinstalar o aplicativo incluem:<ul><li> O usuário final desinstalou o aplicativo.</li><li> As informações de identidade no pacote não correspondem ao que o dispositivo relata sobre aplicativos incorretos.</li><li>Para MSIs de atualização automática, a versão do produto não coincide com as informações do aplicativo após sua atualização fora do Intune.</li></ul> Instrua o usuário a reinstalar o aplicativo do portal da empresa. Observe que os aplicativos necessários serão reinstalados automaticamente na próxima vez em que o dispositivo fizer check-in.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Solução de problemas dos aplicativos da Microsoft Store

As informações no tópico [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Microsoft Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) ajudam a solucionar problemas comuns que podem ocorrer ao instalar aplicativos da Microsoft Store, usando o Intune ou por outros meios.

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre a solução de problemas do Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](help-desk-operators.md). 
- Saiba mais sobre os problemas conhecidos do Microsoft Intune. Para obter mais informações, consulte [Problemas conhecidos no Microsoft Intune](known-issues.md).
- Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](get-support.md).
