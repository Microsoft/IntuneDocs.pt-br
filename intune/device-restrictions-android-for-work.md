---
title: Restrições de dispositivos para Android for Work no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos que executam o Android for Work, é possível restringir algumas configurações no dispositivo, incluindo ações de copiar e colar, de mostrar notificações, permissões de aplicativo, compartilhamento de dados, tamanho da senha, falhas de entrada, uso de impressão digital para desbloquear, reutilização de senhas e habilitação de compartilhamento de bluetooth para contatos de trabalho.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1db0e98318c05c7a1a854ed1af77d9d9654cc38
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="work-device-restriction-settings-in-intune"></a>Configurações de restrição de dispositivo de trabalho no Intune

Este artigo lista as configurações de restrições de dispositivo do Microsoft Intune que você pode definir para dispositivos que executam o Android for Work.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Configurações de perfil de trabalho

### <a name="general-settings"></a>Configurações Gerais

- **Copiar e colar entre os perfis de trabalho e pessoais**: controla as ações de copiar e colar entre aplicativos pessoais e de trabalho. Escolha **Bloquear** para habilitar o bloqueio. Escolha **Não configurado** para desabilitar o bloqueio.
- **Compartilhamento de dados entre perfis de trabalho e pessoais**: controle se os aplicativos no perfil de trabalho podem ser compartilhados com aplicativos no perfil pessoal. Essa configuração controla as ações de compartilhamento em aplicativos (por exemplo, a opção **Compartilhar...** no aplicativo de navegador Chrome) e não se aplica ao comportamento da área de transferência copiar/colar. Ao contrário das [configurações de política de proteção do aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), as configurações de restrição de dispositivos são gerenciadas no portal do Intune e usam a partição de perfil de trabalho do Android for Work para isolar os aplicativos gerenciados. Escolha:
  - **Restrições de compartilhamento padrão**: o comportamento de compartilhamento padrão do dispositivo, que varia dependendo da versão do Android. Por padrão, há permissão para o compartilhamento do perfil pessoal com o perfil de trabalho. Também por padrão, o compartilhamento do perfil de trabalho com o perfil pessoal é bloqueado. Essa configuração impede o compartilhamento de dados do perfil de trabalho com o perfil pessoal. O Google não oferece uma maneira de bloquear o compartilhamento do perfil pessoal com o perfil de trabalho em dispositivos que executam versões 6.0 e posterior.
  - **Os aplicativos no perfil de trabalho podem lidar com solicitações de compartilhamento do perfil pessoal**: habilita o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando habilitada, uma solicitação de compartilhamento de um aplicativo no perfil pessoal pode ser compartilhada com aplicativos no perfil de trabalho. Essa configuração é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
  - **Permitir compartilhamento entre limites**: habilita o compartilhamento no limite do perfil de trabalho em ambas as orientações. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos sem selo no perfil pessoal. Use essa configuração com cuidado, pois isso permite que os aplicativos gerenciados no perfil de trabalho sejam compartilhados com aplicativos no lado não gerenciado do dispositivo.

- **Notificações de perfil de trabalho enquanto o dispositivo estiver bloqueado**: controla se os aplicativos no perfil de trabalho podem exibir dados em notificações quando o dispositivo está bloqueado.
- **Permissões de aplicativo padrão**: define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, o usuário deve conceder determinadas permissões necessárias por aplicativos quando o aplicativo é iniciado. Essa configuração de política permite que você decida se os usuários deverão conceder permissões para todos os aplicativos no perfil de trabalho. Por exemplo, você atribui um aplicativo ao perfil de trabalho que exige o acesso à localização. Normalmente, esse aplicativo solicita que o usuário aprove ou negue o acesso à localização para o aplicativo. Essa política permite que você decida se todas as permissões devem ser concedidas automaticamente sem aviso, negadas automaticamente sem aviso ou permitir que o usuário final decida. Escolha:
  - **Padrão do dispositivo**
  - **Prompt**
  - **Concessão automática**
  - **Negação automática**

    O estado de concessão das permissões pode ser definido de forma mais detalhada para aplicativos específicos usando uma política de Configuração de Aplicativo para um aplicativo individual (em **Aplicativos Móveis** > **Políticas de configuração de aplicativo**).

- **Adicionar e remover contas**

   Impede que os usuários finais adicionem ou removam contas no perfil de trabalho.

   Por exemplo, quando você implanta o aplicativo Gmail em um perfil do Android for Work, é possível impedir que usuários finais adicionem ou removam contas neste perfil de trabalho.

- **Contato com compartilhamento via Bluetooth**: permite o acesso a contatos de trabalho de outro dispositivo, como um carro, emparelhado usando Bluetooth. Por padrão, essa configuração não está configurada e os contatos de perfil de trabalho não são mostrados. Selecione **Habilitar** para permitir esse compartilhamento e mostrar contatos de perfil de trabalho. Essa configuração aplica-se a dispositivos de perfil de trabalho Android no sistema operacional Android v6.0 e mais recentes. Habilitar essa opção pode permitir que determinados dispositivos Bluetooth armazene em cache os contatos do trabalho após a primeira conexão. Desabilitar essa política após um emparelhamento/uma sincronização inicial pode não remover os contatos de trabalho de um dispositivo Bluetooth.

- **Captura de tela**: bloqueia a captura de tela do dispositivo no perfil de trabalho. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura.

- **Exibir ID do chamador do contato de trabalho no perfil pessoal**: quando esta opção está habilitada (não configurada), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando bloqueada, o número de contato comercial do chamador não é exibido no perfil pessoal. Aplicável ao sistema operacional Android v6.0 e às versões mais recentes.

- **Câmera**: bloqueia a câmera do dispositivo no perfil de trabalho. A câmera no lado pessoal não é afetada pela configuração.

### <a name="work-profile-password"></a>Senha do perfil de trabalho

- **Exigir senha de perfil de trabalho**: aplica-se ao Android 7.0 e posterior com o perfil de trabalho habilitado. Defina uma política de senha que se aplica somente aos aplicativos no perfil de trabalho. Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou os usuários podem optar por combinar os PINs no mais forte entre eles.
- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve conter (de **4**-**16**)
- **Máximo de minutos de inatividade até o bloqueio do perfil de trabalho**: selecione a quantidade de tempo até o perfil de trabalho ser bloqueado. O usuário deve inserir suas credenciais para recuperar o acesso.
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que o perfil de trabalho seja apagado do dispositivo.
- **Expiração da senha (dias)**: insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**).
- **Tipo de senha necessária**: selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Numérico complexo**: números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio por impressão digital**: impede que usuários finais usem o scanner de impressão digital do dispositivo para desbloqueá-lo
- **Smart Lock e outros agentes de confiança**: controle o recurso Smart Lock em dispositivos compatíveis. Essa funcionalidade do telefone, às vezes conhecida como agente de confiança, permite desabilitar ou ignorar a senha do perfil de trabalho tela de bloqueio do dispositivo quando o dispositivo está em uma localização confiável. Por exemplo, quando está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marcação NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

## <a name="device-password"></a>Senha do dispositivo

- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve conter (de **4**-**14**)
- **Máximo de minutos de inatividade até a tela ser bloqueada**: selecione o tempo decorrido até um dispositivo inativo ser bloqueado automaticamente
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que todos os dados do dispositivo sejam apagados
- **Expiração da senha (dias)**: insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**)
- **Tipo de senha necessária**: selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Numérico complexo**: números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio por impressão digital**: impede que um usuário final use o scanner de impressão digital do dispositivo para desbloqueá-lo
- **Smart Lock e outros agentes de confiança**: controle o recurso Smart Lock em dispositivos compatíveis. Essa funcionalidade do telefone, às vezes conhecida como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo está em uma localização confiável. Por exemplo, quando está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marcação NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

## <a name="system-security"></a>Segurança do sistema

- **Verificação de ameaças em aplicativos**: garanta que a configuração **Verificar aplicativos** esteja habilitada para perfis pessoais e de trabalho.

   > [!Note]
   > Essa configuração só funciona para dispositivos Android O e superior.

## <a name="next-step"></a>Próxima etapa

Para salvar e atribuir o perfil a usuários e dispositivos, consulte [Configure device restriction settings](device-restrictions-configure.md) (Definir configurações de restrição de dispositivos).
