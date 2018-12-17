---
title: Use o Windows Defender ATP no Microsoft Intune – Azure | Microsoft Docs
description: 'Veja como habilitar a Proteção Avançada contra Ameaças (ATP) do Windows Defender em um cenário de ponta a ponta, incluindo: ativar o ATP no Intune e o Centro de Segurança do Windows Defender (portal ATP), integrar dispositivos usando um perfil de configuração do ATP, criar uma política de conformidade com o dispositivo no Intune, criar uma política de acesso condicional do Azure AD e monitorar a conformidade do dispositivo.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1b8d08e60b9cd656eb9467fd5289b9dfc428d183
ms.sourcegitcommit: 67666682935c44ff6ad003c0da220a79cc42c9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53167987"
---
# <a name="enable-windows-defender-atp-with-conditional-access-in-intune"></a>Habilitar o Windows Defender ATP com acesso condicional no Intune

Proteção Avançada contra Ameaças da Proteção Avançada contra Ameaças (ATP) do Windows Defender e o Microsoft Intune funcionam em conjunto para ajudar a evitar violações de segurança e ajudam a limitar o impacto de violações de dentro de uma organização.

Esse recurso aplica-se a: Dispositivos com Windows 10

Por exemplo, alguém envia um anexo do Word com código mal-intencionado incorporado para um usuário dentro de sua organização. O usuário abre o anexo e habilita o conteúdo. Inicia um ataque de privilégio elevado e um invasor de um computador remoto tem direitos de administrador no dispositivo da vítima. O invasor então remotamente acessa outros dispositivos do usuário.

Essa violação de segurança pode afetar toda a organização.

O Windows Defender ATP pode resolver eventos de segurança como este cenário. A Central de Segurança do Windows Defender (console ATP) reporta os dispositivos como "alto risco" e inclui um relatório detalhado de atividade suspeita. Em nosso exemplo, o Windows Defender ATP detecta que o dispositivo executou código anormal, apresentou uma elevação de privilégios de processo, injetou código mal-intencionado e emitiu um shell remoto suspeito. O Windows Defender ATP, em seguida, fornece opções para atenuar a ameaça.

Usando o Intune, você pode criar uma política de conformidade que determina um nível aceitável de risco. Se um dispositivo excede esse risco, o dispositivo se tornará incompatível. Quando combinado com acesso condicional do Azure Active Directory (AD), o usuário tem o acesso bloqueado de recursos corporativos.

Este artigo mostra como:

- Habilitar o Intune no ATP e habilitar o ATP no Intune. Essas tarefas criam uma conexão de serviço a serviço entre o Intune e o Windows Defender ATP. Esta conexão permite que o Windows Defender ATP grave o risco de máquina para seus dispositivos do Intune.
- Criar política de conformidade no Intune.
- Habilite o acesso condicional no Azure Active Directory (AD) em dispositivos com base em seu nível de ameaça.

## <a name="prerequisites"></a>Pré-requisitos

Para usar ATP com o Intune, verifique se você tem a seguinte configuração e está pronto para usar:

- Locatário licenciado para Enterprise Mobility + Security E3 e Windows E5 (ou Microsoft 365 Enterprise E5)
- Ambiente do Microsoft Intune, com dispositivos Windows 10 [gerenciados para Intune](windows-enroll.md) que também façam parte do Azure AD
- [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) e acesso à Central de Segurança do Windows Defender (portal ATP)

## <a name="enable-windows-defender-atp-in-intune"></a>Habilitar o Windows Defender ATP no Intune

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Conformidade do dispositivo** > **Windows Defender ATP** > **Abrir a Central de Segurança do Windows Defender**.

    ![Selecione para abrir a Central de Segurança do Windows Defender](./media/atp-device-compliance-open-windows-defender.png)

4. No **Central de Segurança do Windows Defender**:
    1. Selecione **Configurações** > **Recursos avançados**.
    2. Para **Conexão do Microsoft Intune**, escolha **Ativado**:

        ![Habilitar a conexão com o Intune](./media/atp-security-center-intune-toggle.png)

    3. Selecione **Salvar preferências**.

5. Volte para o Intune, **Conformidade do dispositivo** > **Windows Defender ATP**. Defina **Conectar dispositivos Windows versão 10.0.15063 e superiores ao Windows Defender ATP** como **Ligado**.
6. Selecione **Salvar**.

Você normalmente realiza essa tarefa uma vez. Então, se o ATP já está habilitado em seu recurso Intune, você não precisa fazê-lo novamente.

## <a name="onboard-devices-using-a-configuration-profile"></a>Integrar dispositivos usando um perfil de configuração

Quando um usuário final é registrado no Intune, você pode enviar por push diferentes configurações para o dispositivo usando um perfil de configuração. Isso também se aplica ao Windows Defender ATP.

O Windows Defender inclui um pacote de configuração de integração que se comunica com os [serviços do Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) para examinar arquivos, detectar ameaças e relatar o risco para o Windows Defender ATP.

Quando você faz a integração, o Intune obtém um pacote de configuração gerado automaticamente do Windows Defender ATP. Quando o perfil é enviado por push ou implantado no dispositivo, esse pacote de configuração também é enviado por push para o dispositivo. Isso permite que o Windows Defender ATP monitore o dispositivo em busca de ameaças.

Quando você carregar um dispositivo usando o pacote de configuração, não precisará fazê-lo novamente. Você também pode integrar dispositivos usando uma [política de grupo ou System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection).

### <a name="create-the-configuration-profile"></a>Criar o perfil de configuração

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do Dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição**.
4. Em **Plataforma**, selecione **Windows 10 e posterior**
5. Para **Tipo de perfil**, selecione  **Windows Defender ATP (Windows 10 Desktop)**.
6. Configure as definições:

  - **Tipo de pacote de configuração de cliente do Windows Defender ATP**: selecione **Carregar** para adicionar o pacote de configuração no perfil. Selecione **Remover** para remover o pacote de configuração do perfil.
  
    > [!NOTE] 
    > Se você estabeleceu corretamente uma conexão com o Windows Defender ATP, o Intune vai **Integrar** automaticamente o perfil de configuração e a configuração **Tipo de pacote de configuração de cliente do Windows Defender ATP** não estará disponível.
  
  - **Compartilhamento de exemplo para todos os arquivos**: **Habilitar** permite que os exemplos sejam coletados e compartilhados com o Windows Defender ATP. Por exemplo, se você vir um arquivo suspeito, poderá enviá-lo para o Windows Defender ATP para uma análise profunda. **Não configurado** não compartilha nenhum exemplo com o Windows Defender ATP.
  - **Acelerar a frequência do relatório de telemetria**: para dispositivos que estão em risco alto, **Habilitar** essa configuração para relatar a telemetria ao serviço do Windows Defender ATP com maior frequência.

    [Integrar computadores do Windows 10 usando o System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection) tem mais detalhes sobre essas configurações do Windows Defender ATP.

7. Selecione **OK** e **Criar** para salvar suas alterações, o que cria o perfil.

## <a name="create-the-compliance-policy"></a>Criar a política de conformidade
A política de conformidade determina um nível aceitável de risco em um dispositivo.

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
3. Insira um **Nome** e uma **Descrição**.
4. Em **plataforma**, selecione **Windows 10 e posterior**.
5. Nas configurações do **Windows Defender ATP**, defina **Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo** para o seu nível preferido:

  - **Limpar**: este é o nível mais seguro. O dispositivo não pode ter ameaças existentes e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível.
  - **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo existirem. Dispositivos com níveis de ameaça média ou alta não são compatíveis.
  - **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.
  - **Alto**: este nível é o menos seguro e permite todos os níveis de ameaça. Sendo assim, os dispositivos com níveis de ameaça alta, média ou baixa são considerados compatíveis.

6. Selecione **OK** e **Criar** para salvar suas alterações (e criar a política).

## <a name="assign-the-policy"></a>Atribuir a política

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Conformidade do dispositivo** > **Políticas**> selecione sua política de conformidade do Windows Defender ATP.
3. Selecione **Atribuições**.
4. Incluir ou excluir seus grupos do Azure AD para atribuir a eles a política.
5. Para implantar a política aos grupos, selecione **Salvar**. Os dispositivos de usuário direcionados pela política são avaliados quanto à conformidade.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Criar uma política de acesso condicional do Azure AD
A política de acesso condicional bloqueará o acesso a recursos *se* o dispositivo não for incompatível. Então se um dispositivo excede o nível de ameaça, você pode bloquear o acesso a recursos corporativos, como o SharePoint ou Exchange Online.

1. No [Portal do Azure](https://portal.azure.com), abra **Azure Active Directory** > **Acesso condicional** > **Nova política**.
2. Insira **Nome** da política e selecione **Usuários e grupos**. Use as opções Incluir ou Excluir para adicionar os grupos para a política e selecione **Concluído**.
3. Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger. Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Exchange Online do Office 365**.

    Selecione **Concluído** para salvar suas alterações.

4. Selecione **Condições** > **Aplicativos do cliente** para aplicar a política para aplicativos e navegadores. Por exemplo, selecione **Sim** e, em seguida, habilitar **Navegador** e **Aplicativos móveis e clientes de área de trabalho**.

    Selecione **Concluído** para salvar suas alterações.

5. Selecione **Conceder** para aplicar acesso condicional baseado na conformidade do dispositivo. Por exemplo, selecione **Conceder acesso** > **Exigir que o dispositivo seja marcado como compatível**.

    Marque **Selecionar** para salvar suas alterações.

6. Selecione **Habilitar política** e, em seguida, **Criar** para salvar suas alterações.

[O que é o acesso condicional? ](conditional-access.md) é um bom recurso.

## <a name="monitor-device-compliance"></a>Monitorar a conformidade do dispositivo
Em seguida, monitore o estado de dispositivos com a política de conformidade do Windows Defender ATP.

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Conformidade do dispositivo** > **Conformidade com a política**.
3. Localize sua política do Windows Defender ATP na lista e veja quais dispositivos são compatíveis ou não.

## <a name="more-good-stuff"></a>Mais coisas legais
[Acesso condicional do Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/conditional-access-windows-defender-advanced-threat-protection)  
[Painel de risco do Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection)  
[Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md)  
[Acesso condicional no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
