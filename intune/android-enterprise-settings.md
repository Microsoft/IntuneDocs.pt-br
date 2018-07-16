---
title: Configurações de quiosque do Android no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos de quiosque Android Enterprise.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28eca6fa3738519602ee5b2a778bc75bde487156
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909092"
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
- **Redefinição de fábrica**: escolha **Bloquear** para impedir que os usuários redefinam o dispositivo para as configurações de fábrica.
- **Inicialização segura**: escolha **Bloquear** para impedir que os usuários reiniciem o dispositivo no modo de segurança.
- **Barra de status**: escolha **Bloquear** para impedir que os usuários acessem a barra de status, incluindo notificações e configurações rápidas.
- **Alterações de configuração de Wi-Fi**: escolha **Bloquear** para impedir que os usuários alterem as configurações de Wi-Fi criadas pelo proprietário do dispositivo. Os usuários podem criar suas próprias configurações de Wi-Fi.
- **Configuração de ponto de acesso de Wi-Fi**: escolha **Bloquear** para impedir que os usuários criem ou editem as configurações de Wi-Fi.
- **Recursos de depuração**: escolha **Permitir** para que os usuários possam usar recursos de depuração.
- **Ajuste de microfone**: escolha **Bloquear** para impedir que os usuários ajustem o volume ou ativem o mudo do microfone.
- **Emails de proteção de redefinição de fábrica**: escolha **Endereços de email de conta do Google** para definir endereços de email (separados por ponto e vírgula) que podem desbloquear o dispositivo após a redefinição para as configurações de fábrica. Se não for especificado nenhum email, qualquer pessoa poderá desbloquear o dispositivo após uma redefinição de fábrica.
- **Hachura de escape de rede**: escolha **Habilitar** para permitir que o recurso de hachura de escape de rede seja habilitado. Se uma conexão de rede não puder ser feita no momento da inicialização, a hachura de escape solicitará que o usuário se conecte temporariamente a uma rede para atualizar a política do dispositivo. Depois de aplicar a política, a rede temporária será esquecida e o dispositivo continuará com a inicialização. Isso impede que não seja possível se conectar a uma rede quando não houver nenhuma rede adequada na última política e o dispositivo for inicializado em um aplicativo no modo de tarefa de bloqueio ou quando o usuário não conseguir chegar às configurações do dispositivo.
- **Permitir instalação de fontes desconhecidas**: escolha **Permitir** para que os usuários possam instalar de fontes desconhecidas.
- **Atualização do sistema**: escolha uma opção para definir como o dispositivo trata as atualizações over-the-air:
    - **Padrão do dispositivo**: usar a configuração padrão do dispositivo.
    - **Automático**: as atualizações são instaladas automaticamente.
    - **Adiado**: as atualizações são adiadas até uma data posterior.
    - **Janela de manutenção**: uma janela de manutenção solicita que os usuários aprovem a atualização.

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



