---
title: Configurações de quiosque do Android no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos de quiosque Android Enterprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c4db49b6727a430696d6ade3bc8eb8f4600ebe3e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190278"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Configurações de quiosque Android Enterprise no Intune

Os perfis de quiosque do Android dão suporte às seguintes definições de configurações. Ao criar um perfil, essas configurações aparecem quando você escolhe **Tipo de perfil** > **Somente o Proprietário do Dispositivo** > **Restrições do dispositivo**. Para ver essas configurações, escolha **Propriedades** de um perfil de restrição de dispositivo do Android Enterprise e, em seguida, escolha **Configurar**.

## <a name="general-settings"></a>Configurações gerais

- **Captura de tela**: escolha **Bloquear** para impedir que os usuários capturem de tela do dispositivo.
- **Câmera**: escolha **Bloquear** para desabilitar a câmera do dispositivo.
- **Política de permissão padrão**: essa configuração define a política de permissão padrão para as solicitações de permissões do tempo de execução. Os valores possíveis incluem:
    - **Padrão do dispositivo**: usar a configuração padrão do dispositivo.
    - **Solicitar**: é solicitado que o usuário aprove a permissão.
    - **Concessão automática**: as permissões são concedidas automaticamente.
    - **Negação automática**: as permissões serão negadas automaticamente.
- **Alterações de volume**: escolha **Bloquear** para impedir que usuários alterem o volume do dispositivo.
- **Apagar**: escolha **Bloquear** para impedir que os usuários apaguem o dispositivo.
- **Inicialização segura**: escolha **Bloquear** para impedir que os usuários reiniciem o dispositivo no modo de segurança.
- **Barra de status**: escolha **Bloquear** para impedir que os usuários acessem a barra de status, incluindo notificações e configurações rápidas.
- **Alterações de configuração de Wi-Fi**: escolha **Bloquear** para impedir que os usuários alterem as configurações de Wi-Fi criadas pelo proprietário do dispositivo. Os usuários podem criar suas próprias configurações de Wi-Fi.
- **Configuração de ponto de acesso de Wi-Fi**: escolha **Bloquear** para impedir que os usuários criem ou editem as configurações de Wi-Fi.
- **Recursos de depuração**: escolha **Permitir** para que os usuários possam usar recursos de depuração.
- **Ajuste de microfone**: escolha **Bloquear** para impedir que os usuários ajustem o volume ou ativem o mudo do microfone.
- **Emails de proteção de apagamento**: escolha **Endereços de email de conta do Google** para definir endereços de email (separados por ponto e vírgula) que podem desbloquear o dispositivo após um apagamento. Se não for especificado nenhum email, qualquer pessoa poderá desbloquear o dispositivo após um apagamento.
- **Hachura de escape de rede**: escolha **Habilitar** para permitir que o recurso de hachura de escape de rede seja habilitado. Se uma conexão de rede não puder ser feita no momento da inicialização, a hachura de escape solicitará que o usuário se conecte temporariamente a uma rede para atualizar a política do dispositivo. Depois de aplicar a política, a rede temporária será esquecida e o dispositivo continuará com a inicialização. Isso impede que não seja possível se conectar a uma rede quando não houver nenhuma rede adequada na última política e o dispositivo for inicializado em um aplicativo no modo de tarefa de bloqueio ou quando o usuário não conseguir chegar às configurações do dispositivo.
- **Permitir instalação de fontes desconhecidas**: escolha **Permitir** para que os usuários possam instalar de fontes desconhecidas.
- **Atualização do sistema**: escolha uma opção para definir como o dispositivo trata as atualizações over-the-air:
    - **Padrão do dispositivo**: usar a configuração padrão do dispositivo.
    - **Automático**: as atualizações são instaladas automaticamente sem interação do usuário. A configuração dessa política instala imediatamente todas as atualizações pendentes.
    - **Adiado**: as atualizações são adiadas por 30 dias. No final do período de 30 dias, o Android solicitará que o usuário instale a atualização. É possível que os fabricantes de dispositivos ou operadoras impeçam que as atualizações de segurança importantes (isenção) sejam adiadas. Uma atualização isenta mostra uma notificação do sistema para o usuário no dispositivo. 
    - **Janela de manutenção**: instala as atualizações automaticamente durante uma janela de manutenção diária definida no Intune. A tentativa de instalação ocorre diariamente por 30 dias, podendo falhar devido a espaço insuficiente ou níveis de bateria. Após 30 dias, o Android solicitará que o usuário a instale. Essa janela também é usada para instalar atualizações de aplicativos do Play. Essa opção é recomendada para dispositivos dedicados, como quiosques, pois é possível atualizar aplicativos de primeiro plano em quiosques de aplicativo único. 

## <a name="kiosk-settings"></a>Configurações do quiosque

- **Modo de quiosque**: define se o dispositivo pode executar somente um único aplicativo ou vários aplicativos. Para obter mais informações, confira [Configurações de quiosque para dispositivos Android](android-kiosk-settings.md).
    - **Quiosque de um único aplicativo**: os usuários só podem acessar um único aplicativo.
    - **Quiosque de vários aplicativos**: os usuários podem acessar um conjunto limitado de aplicativos.

## <a name="device-password-settings"></a>Configurações de senha do dispositivo

- **Keyguard**: escolha **Desabilitar** para impedir que os usuários usem o Keyguard no dispositivo.
- **Tipo de senha necessária**: defina o tipo de senha necessária para o dispositivo.
- **Tamanho mínimo da senha**: defina o tamanho mínimo da senha necessário para o dispositivo.
- **Número de falhas de entrada antes de apagar o dispositivo**: defina o número de entradas com falha que precisam ocorrer para que o dispositivo seja apagado.

## <a name="power-settings"></a>Configurações da energia

- **Tempo para bloquear a tela**: defina a quantidade de tempo ocioso necessário para que o dispositivo seja bloqueado.
- **Tela ligada enquanto o dispositivo está conectado**: escolha quais fontes de alimentação fazem com que a tela do dispositivo permaneça ligada enquanto o dispositivo está conectado.

## <a name="users-and-accounts-settings"></a>Configurações de usuários e de contas

- **Adicionar novos usuários**: escolha **Bloquear** para impedir que os usuários adicionem novos usuários.
- **Remoção de usuário**: escolha **Bloquear** para impedir que os usuários removam usuários.
- **Alterações de conta**: escolha **Bloquear** para impedir que os usuários modifiquem as contas.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).



