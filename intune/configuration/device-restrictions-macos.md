---
title: Configurações de dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, defina ou crie configurações em dispositivos macOS para restringir recursos, incluindo definir os requisitos de senha, controlar a tela bloqueada, usar aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador da Web Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3d26c4c6cd05a411555f7824ad21b72431eb569c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511165"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo macOS para permitir ou restringir recursos usando o Intune



Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos macOS. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, permitir ou restringir aplicativos específicos e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos macOS.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de configuração de restrições de dispositivo](../device-restrictions-configure.md).

> [!NOTE]
> Essas configurações se aplicam a diferentes tipos de registro. Para obter mais informações sobre os diferentes tipos de registro, confira [Registro do macOS](../macos-enroll.md).

## <a name="general"></a>Geral

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Pesquisa de Definição**: A opção **Bloquear** impede o usuário de realçar uma palavra e, em seguida, pesquisar sua definição no dispositivo. **Não configurado** (padrão): permite o acesso ao recurso de pesquisa de definição.
- **Ditado**: A opção **Bloquear** impede o usuário de usar a entrada de voz para inserir um texto. **Não configurado** (padrão) permite que o usuário use a entrada por ditado.
- **Cache de conteúdo**: escolha **Não configurado** (padrão) para habilitar o cache de conteúdo. Cache de conteúdo armazena dados de aplicativo, dados de navegador da Web, downloads e muito mais localmente no dispositivo. Selecione **Bloquear** para impedir que esses dados sejam armazenados no cache.

  Para obter mais informações sobre o cache de conteúdo no macOS, veja [Gerenciar cache de conteúdo em Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (abre outro site).

  Esse recurso aplica-se a:  
  - macOS 10.13 e versões mais recentes

- **Adiar atualizações de software**: quando definido como **Não configurado** (padrão), as atualizações de software são exibidas no dispositivo conforme a Apple as libera. Por exemplo, se uma atualização do macOS é lançada pela Apple em uma data específica, essa atualização naturalmente aparece no dispositivo perto da data de lançamento. Atualizações de build de semente são permitidas sem atraso.

  **Habilitar** permite que você atrase quando as atualizações de software são mostradas em dispositivos, de 0 a 90 dias. Essa configuração não controla quando as atualizações são ou não instaladas. 

  - **Atrasar a visibilidade das atualizações do software**: insira um valor de 0 a 90 dias. Quando o atraso expira, os usuários recebem uma notificação para atualizar para a versão mais antiga do sistema operacional que estava disponível quando o atraso foi disparado.

    Por exemplo, se uma atualização do macOS está disponível no dia **1º de janeiro** e **Atrasar a visibilidade** está definido como **5 dias**, a atualização não é mostrada como uma atualização disponível. No **sexto dia** após o lançamento, essa atualização está disponível e os usuários finais podem instalá-la.

    Esse recurso aplica-se a:  
    - macOS 10.13.4 e mais recente

- **Capturas de tela**: o dispositivo deve ser registrado no DEP (Registro de Dispositivo Automatizado) da Apple. Quando definido como **Bloquear**, os usuários não podem salvar uma captura de tela da exibição. Isso também impede que o aplicativo Classroom observe telas remotas. **Não configurado** (padrão) permite que os usuários capturem capturas de tela e que o aplicativo Classroom exiba telas remotas.

### <a name="settings-apply-to-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado

- **Observação de tela remota por meio do aplicativo Classroom**: **Desabilitar** impede que os professores usem o aplicativo Classroom para ver as telas dos alunos. **Não configurado** (padrão) permite que os professores vejam as telas dos alunos.

  Para usar essa configuração, defina a configuração **Capturas de tela** como **Não configurada** (capturas de tela são permitidas).

- **Observação de tela não solicitada pelo aplicativo Classroom**: **Permitir** permite que os professores vejam as telas dos alunos sem exigir que o aluno concorde. **Não configurado** (padrão) exige que o aluno concorde antes que o professor possa ver as telas.

  Para usar essa configuração, defina a configuração **Capturas de tela** como **Não configurada** (capturas de tela são permitidas).

- **Os alunos devem solicitar permissão para sair da classe do Classroom**: **Exigir** força alunos matriculados em um curso do Classroom não gerenciado a obter aprovação do professor para sair do curso. **Não configurado** (padrão) permite que o aluno saia do curso sempre que escolher.

- **Os professores podem bloquear automaticamente dispositivos ou aplicativos no aplicativo Classroom**: **Permitir** permite que os professores bloqueiem o dispositivo ou aplicativo de um aluno sem a aprovação dele. **Não configurado** (padrão) exige que o aluno concorde antes que o professor possa bloquear o dispositivo ou o aplicativo.

- **Os alunos podem entrar na classe do Classroom**: **Permitir** que os alunos entrem em uma classe sem avisar o professor. **Não configurado** (padrão) exige a aprovação do professor para entrar em uma classe.

## <a name="password"></a>Senha

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Senha**: a opção **Exigir** torna necessário que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** (padrão) não requer uma senha. Também não força nenhuma restrição, como o bloqueio de senhas simples ou a definição de um comprimento mínimo.
  - **Tipo de senha necessária**: especifique se a senha usada pode ser apenas Numérica ou se deve ser Alfanumérica (conter letras e números).

    Esse recurso aplica-se a:  
    - macOS 10.10.3 e mais recente

  - **Número de caracteres não alfanuméricos na senha**: Especifica o número de caracteres complexos necessários na senha (de **0** a **4**).<br>Um caractere complexo é um símbolo, por exemplo " **?** ".
  - **Comprimento mínimo da senha**: insira o tamanho mínimo da senha que um usuário deve configurar (entre **4** e **16** caracteres).
  - **Senhas simples**: Permita o uso de senhas simples como **0000** ou **1234**.
  - **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**: Especifique por quanto tempo o computador deverá ficar inativo antes que uma senha seja necessária para desbloqueá-lo.
  - **Máximo de minutos de inatividade até a tela ser bloqueada**: especifique o período de tempo pelo qual o computador deve permanecer ocioso antes que a tela seja bloqueada.
  - **Expiração da senha (dias)** : Especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).
  - **Evitar a reutilização de senhas anteriores**: insira o número de senhas usadas anteriormente e que não podem ser reutilizadas, de **1** a **24**.

- **Bloquear a modificação da senha pelo usuário**: Escolha **Bloquear** para impedir que a senha seja alterada, adicionada ou removida. **Não configurado** (padrão) permite a adição, alteração ou remoção das senhas.
- **Bloquear o desbloqueio de impressão digital**: Escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** (padrão) permite que o usuário desbloqueie o dispositivo usando uma impressão digital.

- **Bloquear o Preenchimento Automático de senha**: escolha **Bloquear** para impedir o uso do recurso Preenchimento Automático de Senhas no macOS. Escolher **Bloquear** também tem o seguinte impacto:

  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** (padrão) permite esses recursos.

- **Bloquear solicitações de proximidade de senha**: Escolha **Bloquear** para que o dispositivo de um usuário não solicite senhas de dispositivos próximos. **Não configurado** (padrão) permite essas solicitações de senha.

- **Bloquear compartilhamento de senha**: A opção **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** (padrão) permite o compartilhamento das senhas.

## <a name="built-in-apps"></a>Aplicativos internos

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Bloquear o Preenchimento Automático do Safari**: A opção **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.
- **Bloquear câmera**: Escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** (padrão) permite o acesso à câmera do dispositivo.
- **Bloquear o Apple Music**: A opção **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o serviço de Música. **Não configurado** (padrão) permite o uso do aplicativo Apple Music.
- **Bloquear os resultados da pesquisa de Internet de destaque**: A opção **Bloquear** impede o Spotlight de retornar qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.
- **Bloquear a transferência de arquivo usando o iTunes**: **Bloquear** desabilita os serviços de compartilhamento de arquivos do aplicativo. **Não configurado** (padrão) permite os serviços de compartilhamento de arquivos do aplicativo.

  Esse recurso aplica-se a:  
  - macOS 10.13 e mais recente

## <a name="restricted-apps"></a>Aplicativos restritos

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Lista de tipos de aplicativos restritos**: crie uma lista de aplicativos que os usuários não têm permissão para instalar nem usar. Suas opções:

  - **Não configurado** (padrão): não há restrições do Intune. Os usuários têm acesso aos aplicativos que você atribui e aos aplicativos internos.
  - **Aplicativos proibidos**: aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Os usuários não são impedidos de instalar um aplicativo proibido. Porém, se um usuário instalar um aplicativo dessa lista, ele será relatado no Intune.
  - **Aplicativos aprovados**: aplicativos que os usuários têm permissão para instalar. Os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Os usuários não são impedidos de instalar um aplicativo que não esteja na lista aprovada. Porém, se eles fizerem isso, isso será relatado no Intune.
- **ID de Lote de Aplicativo**: insira a [ID de lote](bundle-ids-built-in-ios-apps.md) de aplicativos do aplicativo que você deseja. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple apresenta uma lista de [aplicativos internos da Apple](https://support.apple.com/HT208094).
- **Nome do aplicativo**: insira o nome do aplicativo que você deseja. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple apresenta uma lista de [aplicativos internos da Apple](https://support.apple.com/HT208094).
- **Editor**: insira o editor do aplicativo que você deseja.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar**: selecione essa opção para criar sua lista de aplicativos.
- **Importar** um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app bundle ID>, <app name>, <app publisher>`. Ou **Exportar** para criar uma lista de aplicativos que você adicionou, no mesmo formato.

## <a name="connected-devices"></a>Dispositivos conectados

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Bloquear AirDrop**: A opção **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** (padrão) permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Bloquear o desbloqueio automático do Apple Watch**: a opção **Bloquear** impede que os usuários desbloqueiem seu dispositivo macOS com o Apple Watch. **Não configurado** (padrão) permite aos usuários desbloquear o dispositivo macOS com o seu Apple Watch.

## <a name="cloud-and-storage"></a>Nuvem e armazenamento

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **Bloquear a sincronização do Conjunto de Chaves do iCloud**: Escolha **Bloquear** para desabilitar a sincronização das credenciais armazenadas no Conjunto de Chaves com o iCloud. **Não configurado** (padrão) permite que os usuários sincronizem essas credenciais.
- **Bloquear a sincronização de documentos do iCloud**: **Bloquear** impede o iCloud de sincronizar documentos e dados. A opção **Não configurado** (padrão) permite a sincronização de documento e chave-valor com o espaço de armazenamento do iCloud.
- **Bloquear o backup do Email do iCloud**: a opção **Bloquear** impede que o iCloud sincronize-se com o aplicativo de Email do macOS. **Não configurado** (padrão) permite a sincronização de Email com o iCloud.
- **Bloquear o backup dos contatos do iCloud**: a opção **Bloquear** impede que o iCloud sincronize os contatos de dispositivos. **Não configurado** (padrão) permite a sincronização de contatos usando o iCloud.
- **Bloquear o backup do Calendário do iCloud**: a opção **Bloquear** impede que o iCloud se sincronize com o aplicativo de Calendário do macOS. **Não configurado** (padrão) permite a sincronização de Calendário com o iCloud.
- **Bloquear o backup de lembrete do iCloud**: a opção **Bloquear** impede que o iCloud se sincronize com o aplicativo de Lembretes do macOS. **Não configurado** (padrão) permite a sincronização de Lembretes com o iCloud.
- **Bloquear o backup de indicadores do iCloud**: a opção **Bloquear** impede que o iCloud sincronize os indicadores de dispositivos. **Não configurado** (padrão) permite a sincronização de Indicador com o iCloud.
- **Bloquear o backup de observações do iCloud**: a opção **Bloquear** impede que o iCloud sincronize as observações de dispositivos. **Não configurado** (padrão) permite a sincronização de Notas com o iCloud.
- **Bloquear Biblioteca de Fotos do iCloud**: **Bloquear** desabilita a Biblioteca de Fotos do iCloud e impede que o iCloud sincronize as fotos dos dispositivos. As fotos que não forem totalmente baixadas da Biblioteca de Fotos do iCloud serão removidas do armazenamento local do dispositivo. **Não configurado** (padrão) permite a sincronização de fotos entre o dispositivo e a Biblioteca de Fotos do iCloud.
- **Entrega**: **Não configurado** (padrão) permite que os usuários iniciem o trabalho em um dispositivo iOS e, em seguida, continuem o trabalho iniciado em outro dispositivo iOS/iPadOS ou macOS. **Bloquear** impede o recurso Entrega no dispositivo. 

  Esse recurso aplica-se a:  
  - macOS 10.15 e mais recente

## <a name="domains"></a>Domínios

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>As configurações se aplicam a(o): Registro de dispositivos e registro automatizado de dispositivos

- **URL de domínio de email**: **adicione** uma ou mais URLs à lista. Quando os usuários recebem um email de um domínio diferente daquele configurado por você, o email é marcado como não confiável no aplicativo Email do macOS.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Você também pode restringir recursos e configurações de dispositivo em dispositivos [iOS/iPadOS](../device-restrictions-ios.md).
