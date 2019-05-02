---
title: Configurações de dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, defina ou crie configurações em dispositivos macOS para restringir recursos, incluindo definir os requisitos de senha, controlar a tela bloqueada, usar aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador da Web Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5feec66e791da4038bd069cdad69a7ba573f27f3
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798370"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo macOS para permitir ou restringir recursos usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos macOS. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, permitir ou restringir aplicativos específicos e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos macOS.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de configuração de restrições de dispositivo](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Geral

- **Pesquisa de definição de bloqueio**: **Bloquear** impede que o usuário realce uma palavra e, em seguida, pesquise sua definição no dispositivo. **Não configurado** (padrão): permite o acesso ao recurso de pesquisa de definição.
- **Bloquear ditado**: **Bloquear** impede o usuário de usar a entrada de voz para inserir um texto. **Não configurado** (padrão) permite que o usuário use a entrada por ditado.
- **Bloquear o cache de conteúdo**: escolha **não configurado** (padrão) para habilitar o cache do conteúdo. Cache de conteúdo armazena dados de aplicativo, dados de navegador da web, downloads e muito mais localmente no dispositivo. Selecione **bloco** para impedir que esses dados sejam armazenados no cache.

  Para obter mais informações sobre o cache do conteúdo no macOS, consulte [gerenciar o cache do conteúdo no Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (abre outro site da Web).

  Esse recurso aplica-se a:  
  - macOS 10.13 e posterior

- **Adiar atualizações de software**: quando definido como **não configurado** (padrão), as atualizações de software são exibidas no dispositivo com Apple as libera. Por exemplo, se uma atualização do macOS obtém lançada pela Apple em uma data específica, em seguida, essa atualização naturalmente aparecerá no dispositivo em torno da data de lançamento. Atualizações de compilação de semente são permitidas sem atraso.

  **Habilitar** permite que você atrasar quando as atualizações de software são mostradas em dispositivos, de 0 a 90 dias. Essa configuração não controla quando as atualizações são ou não estão instaladas. 

  - **Atrasar a visibilidade de atualizações de software**: insira um valor de 0 a 90 dias. Quando o atraso expira, os usuários recebem uma notificação para atualizar para a versão mais antiga do sistema operacional que estava disponível quando o atraso foi disparado.

    Por exemplo, se uma atualização do macOS está disponível no **1 de janeiro**, e **atrasar a visibilidade** está definido como **5 dias**, em seguida, a atualização não é mostrada como uma atualização disponível em dispositivos. Sobre o **sexto dia** após o lançamento, o que a atualização estiver disponível, e os usuários finais podem instalá-lo.

    Esse recurso aplica-se a:  
    - macOS 10.13.4 e posterior

## <a name="password"></a>Senha

- **Senha**: **Exigir** que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** (padrão) não requer uma senha e não impõe restrições, como bloqueio de senhas simples ou definir um tamanho mínimo.
  - **Tipo de senha necessária**: especifique se a senha usada pode ser apenas Numérica ou se deve ser Alfanumérica (conter letras e números). Essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.
  - **Número de caracteres não alfanuméricos na senha**: especifique o número de caracteres complexos necessários na senha (**0** a **4**).<br>Um caractere complexo é um símbolo, por exemplo "**?**".
  - **Tamanho mínimo da senha**: insira o tamanho mínimo da senha que um usuário deve configurar (entre **4** e **16** caracteres).
  - **Senhas simples**: permita o uso de senhas simples como **0000** ou **1234**.
  - **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**: especifique quanto tempo o computador deverá ficar inativo antes da senha ser necessária para desbloqueá-lo.
  - **Máximo de minutos de inatividade até o bloqueio de tela**: especifique o período que um computador deve permanecer ocioso antes da tela ser bloqueada.
  - **Expiração de senha (dias)**: especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).
  - **Evite a reutilização de senhas anteriores**: insira o número de senhas usadas anteriormente que não podem ser utilizadas, de **1** a **24**.

- **Impedir que o usuário de modificação de senha**: escolha **bloco** para interromper a senha seja alterada, adicionada ou removida. **Não configurado** (padrão) permite a adição, alteração ou remoção das senhas.
- **Bloquear desbloqueio de impressão digital**: escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** (padrão) permite que o usuário desbloqueie o dispositivo usando uma impressão digital.

- **Bloquear o AutoPreenchimento de senha**: escolha **Bloquear** para evitar o uso do recurso de Preenchimento Automático de Senhas no macOS. Escolhendo **bloco** também tem o seguinte impacto:

  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** (padrão) permite esses recursos.

- **Bloquear solicitações de proximidade de senha**: escolha **Bloquear** para que um dispositivo de usuário não solicite senhas de dispositivos próximos. **Não configurado** (padrão) permite essas solicitações de senha.

- **Bloquear o compartilhamento de senha**: **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** (padrão) permite o compartilhamento das senhas.

## <a name="built-in-apps"></a>Aplicativos internos

- **Bloquear Preenchimento Automático do Safari**: **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.
- **Bloquear Câmera**: escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** (padrão) permite o acesso à câmera do dispositivo.
- **Bloquear Apple Music**: a opção **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o serviço de Música. **Não configurado** (padrão) permite o uso do aplicativo Apple Music.
- **Resultados de pesquisa de Internet de destaque do bloco**: **bloco** interrompe o destaque de retornar qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.
- **Transferência de arquivo do bloco usando o iTunes**: **bloco** desabilita serviços de compartilhamento de arquivos do aplicativo. Disponível no macOS 10.13 e posterior. **Não configurado** (padrão) permite que os serviços de compartilhamento de arquivos do aplicativo.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

- Uma lista de **Aplicativos proibidos**: listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar. Os usuários não são impedidos de instalar um aplicativo proibido, mas se isso ocorrer, ele será relatado para o administrador.
- Uma lista de **Aplicativos aprovados**: listar os aplicativos que os usuários têm permissão para instalar. Os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Os usuários não são impedidos de instalar um aplicativo que não esteja na lista aprovada. Mas, se Sim, ele será relatado para o administrador.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a ID do pacote do aplicativo (por exemplo *com.apple.calculator*).

## <a name="connected-devices"></a>Dispositivos conectados

- **Bloquear AirDrop**: a opção **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** (padrão) permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Bloco de Apple Watch automática desbloquear**: **bloco** impede que os usuários de desbloquear seu dispositivo macOS com o seu Apple Watch. **Não configurado** (padrão) permite aos usuários desbloquear seu dispositivo macOS com o seu Apple Watch.

## <a name="cloud-and-storage"></a>Nuvem e armazenamento

- **Bloquear a sincronização do Conjunto de Chaves no iCloud**: escolha **Bloquear** para desabilitar a sincronização de credenciais armazenadas no Keychain com o iCloud. **Não configurado** (padrão) permite que os usuários sincronizem essas credenciais.
- **Bloquear a sincronização de documento do iCloud**: **bloco** impede que o iCloud de sincronização de documentos e dados. A opção **Não configurado** (padrão) permite a sincronização de documento e chave-valor com o espaço de armazenamento do iCloud.
- **Bloquear o Backup de email do iCloud**: **bloco** impede que o iCloud de sincronização para o aplicativo de email do macOS. **Não configurado** (padrão) permite a sincronização de email com o iCloud.
- **Bloquear o contato de Backup do iCloud**: **bloco** impede que o iCloud sincronizando os contatos de dispositivos. **Não configurado** (padrão) permite que a sincronização de contatos usando o iCloud.
- **Bloquear o calendário de Backup do iCloud**: **bloco** impede iCloud da sincronização para o aplicativo de calendário do macOS. **Não configurado** (padrão) permite a sincronização de calendário com o iCloud.
- **Bloquear o lembrete de Backup do iCloud**: **bloco** impede iCloud da sincronização para o aplicativo de lembretes do macOS. **Não configurado** (padrão) permite a sincronização de lembretes para iCloud.
- **Bloquear o indicador de Backup do iCloud**: **bloco** impede que o iCloud sincronizando os indicadores de dispositivos. **Não configurado** (padrão) permite a sincronização do indicador com o iCloud.
- **Bloco de notas de Backup do iCloud**: **bloco** impede que o iCloud sincronizando os dispositivos de notas. **Não configurado** (padrão) permite a sincronização de notas com o iCloud.

## <a name="domains"></a>Domínios

- No campo **URL de Domínio de Email**, adicione uma ou mais URLs à lista. Quando os usuários recebem um email de um domínio diferente daquele configurado por você, o email é marcado como não confiável no aplicativo de Email do macOS.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você também pode restringir os recursos de dispositivo e as configurações no [iOS](device-restrictions-ios.md) dispositivos.
