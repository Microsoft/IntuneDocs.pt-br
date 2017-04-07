---
title: "Configurações de restrição de dispositivo do Intune para Windows 10"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do dispositivo e as funcionalidades dos dispositivos Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 74f99d5e2d4eef8d42ccd2c7bc34e0ed7b6f0d51
ms.lasthandoff: 02/18/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo do Windows 10 e posterior no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Geral
-     **Captura de tela** – Permite que o usuário capture a tela do dispositivo como uma imagem. (Somente Windows 10 Mobile)
-     **Copiar e colar (somente dispositivo móvel)** – Permitir utilizar ações de copiar e colar entre os aplicativos do dispositivo.
-     **Cancelamento de registro manual** – Permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
-     **Instalação manual de certificado raiz** -     
-     **Envio de dados de diagnóstico** – Os valores possíveis são:
    -         **Nenhum** Nenhum dado é enviado para a Microsoft
    -         **Básico** Informações limitadas são enviadas para a Microsoft
    -         **Avançado** Dados de diagnóstico avançados são enviados para a Microsoft
    -         **Completo** Envia os mesmos dados que Avançado, além de dados adicionais sobre o estado do dispositivo
-     **Câmera** – Permite ou bloqueia o uso da câmera do dispositivo.
-     **Armazenamento removível** – Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo.
-     **Geolocalização** – Especifica se o dispositivo pode usar informações de serviços de localização.
-     **Compartilhamento da Internet** – Permite o uso do compartilhamento de conexão com a Internet no dispositivo.
-     **Redefinição do telefone** – Controla se o usuário pode realizar uma redefinição de fábrica em seu dispositivo.
-     **Conexão USB** – Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.
-     **Modo AntiTheft** – Configure se o modo AntiTheft do Windows está habilitado.
-     **Notificações da central de ações** – Habilita ou desabilita as notificações da central de ações na tela de bloqueio do dispositivo (somente Windows 10 Mobile).
-     **Cortana** – Habilitar ou desabilitar a assistente de voz Cortana.
-     **Gravação de voz** – Permitir ou bloquear o uso do gravador de voz do dispositivo.

## <a name="password"></a>Senha
-     **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
-     **Tipo de senha exigida** – Especifica se a senha deve ser apenas numérica ou alfanumérica.
-     **Tamanho mínimo da senha** – Aplicável somente a Windows 10 Mobile.
-     **Número de falhas conexão antes de limpar o dispositivo** – Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a conexão falhar o número de vezes especificado. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.
Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar o número de vezes que você especificar, o dispositivo será apagado.
-     **Máximo de minutos de inatividade para o bloqueio de tela** – Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.
-     **Expiração de senha (dias)** – Especifica o período após o qual a senha do dispositivo deve ser alterada.
-     **Impedir a reutilização de senhas anteriores** – Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.
-     **Exigir senha quando o dispositivo retorna do estado inativo** – Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente Windows 10 Mobile).
-     **Criptografia** – Habilitar a criptografia em dispositivos de destino (somente Windows 10 Mobile).
## <a name="app-store"></a>Loja de aplicativos

-     **Loja de aplicativos (somente dispositivo móvel)** – Habilitar ou bloquear o uso da loja de aplicativos em dispositivos Windows 10 Mobile.
## <a name="edge-browser"></a>Navegador Edge
-     **Navegador Microsoft Edge (somente dispositivo móvel)** – Permitir o uso do navegador da Web Edge no dispositivo.
-     **SmartScreen** – Habilita ou desabilita o SmartScreen, que bloqueia sites fraudulentos.
-     **Enviar cabeçalhos Do Not Track** – Configura o navegador Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.
-     **Cookies** – Permite que o navegador salve cookies da Internet no dispositivo.
-     **JavaScript** – Permite que scripts, como JavaScript, sejam executados no navegador Edge.
-     **Pop-ups** – Bloqueia janelas pop-up no navegador.<br>(Aplica-se somente ao Windows 10 desktop.)
-     **Sugestões de Pesquisa** – Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
-     **Enviar tráfego da intranet para o Internet Explorer** – Permite aos usuários abrir sites de intranet no Internet Explorer. <br>(Somente Windows 10 Desktop).
-     **Preenchimento automático** – Permite que os usuários possam alterar as configurações de preenchimento automático no navegador.<br>(Somente Windows 10 Desktop)
-     **Gerenciador de Senhas** – Habilitar ou desabilitar o recurso de Gerenciador de Senhas do Edge.
-     **Local da lista de sites do modo Empresarial** – Especifica onde encontrar a lista de sites que serão abertos no modo Empresarial. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop).
## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-     **Conta da Microsoft** – Permite que o usuário associe uma conta da Microsoft ao dispositivo.
-     **Conta não Microsoft** – Permite que o usuário adicione contas de email ao dispositivo que não estão associadas a uma conta da Microsoft.
-     **Sincronização de configurações para conta da Microsoft** – Permitir configurações de dispositivo e aplicativos associadas a uma conta da Microsoft para sincronização entre dispositivos.
## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade
-     **Roaming de dados** – Permitir roaming entre redes ao acessar os dados.
-     **VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.
-     **Roaming VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular em roaming.
-     **Bluetooth** – Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
-     **Descoberta de Bluetooth** – Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
-     **Anúncios por Bluetooth** – Permite que o dispositivo receba anúncios via Bluetooth.
-     **NFC** – Permite que o usuário habilite e configure recursos de comunicação a curta distância no dispositivo.
-     **Wi-Fi** – Permite que o usuário habilite e configure o Wi-Fi no dispositivo (somente Windows 10 Mobile).
-     **Conectar automaticamente a hotspots Wi-Fi** – Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
-     **Configuração manual de Wi-Fi** – Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi (somente Windows 10 Mobile).
## <a name="defender"></a>Defender

-     **Monitoramento em tempo real** – Habilita a verificação em tempo real de malware, de spyware e de outros tipos de software indesejados.
-     **Monitoramento de comportamento** – Permite que o Defender verifique se há certos padrões conhecidos de atividade suspeita nos dispositivos.
-     **Sistema de Inspeção de Rede (NIS)** – O Sistema de Inspeção de Rede (NIS) ajuda a proteger os dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado.
-     **Examinar todos os downloads** – Controla se o Defender examina todos os arquivos baixados da Internet.
-     **Examinar scripts carregados nos navegadores da Web da Microsoft** – Permite que o Defender verifique os scripts que são usados no Internet Explorer.
-     **Acesso do usuário final ao Defender** – Controla se a interface do usuário do Windows Defender está oculta para usuários finais.
Quando essa configuração é alterada, ela entrará em vigor na próxima vez em que o computador do usuário final for reiniciado.
-     **Intervalo de atualização de assinatura (em horas)** – Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.
-     **Monitorar a atividade de arquivos e programas** – Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
-     **Dias de espera antes de excluir malware em quarentena** – Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente.
-     **Limite de uso de CPU durante uma verificação** – Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**).
-     **Verificar arquivos mortos** – Permite que o Defender examine arquivos mortos, como os arquivos Zip ou Cab.
-     **Verificar mensagens de email recebidas** – Permite que o Defender verifique mensagens de email assim que elas chegarem ao dispositivo.
-     **Examinar unidades removíveis durante uma verificação completa** – Permite que o Defender examine unidades removíveis como pen drives.
-     **Examinar unidades de rede mapeadas durante uma verificação completa** – Permite que o Defender examine arquivos em unidades de rede mapeadas.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-     **Examinar arquivos abertos de pastas de rede** – Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC).
Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-     **Proteção de nuvem** – Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.
-     **Perguntar aos usuários antes de enviar amostras** – Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados são enviados automaticamente para a Microsoft.
-     **Hora para realizar uma verificação rápida diária** – Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.
-     **Tipo de verificação do sistema a ser executada** – Permite que você especifique o nível de verificação que será executado ao agendar uma verificação do sistema.
## <a name="defender-exclusions"></a>Exclusões do Defender

-     **Arquivos e pastas a serem excluídas da verificação e proteção em tempo real** – Adiciona um ou mais arquivos e pastas como **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
-     **Extensões de arquivos a serem excluídas de verificações e proteção em tempo real** – Adicione uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Qualquer arquivo com essas extensões não serão incluídos em verificações em tempo real ou programadas.
-     **Processos a serem excluídos de verificações e proteção em tempo real** – Adicionar um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.

