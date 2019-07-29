---
title: Usar a ATP do Microsoft Defender no Microsoft Intune – Azure | Microsoft Docs
description: 'Veja como habilitar a Proteção Avançada contra Ameaças do Microsoft Defender (ATP do Microsoft Defender) em um cenário de ponta a ponta, incluindo: ativar a ATP do Microsoft Defender no Intune e no Centro de Segurança do Microsoft Defender, integrar dispositivos usando a ATP do Microsoft Defender, criar uma política de conformidade com o dispositivo no Intune, criar uma política de Acesso Condicional do Azure AD e monitorar a conformidade do dispositivo.'
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af27a9b07434346a5425d0539759cb90ebf1ee6f
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427082"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Impor a conformidade da ATP do Microsoft Defender com Acesso Condicional no Intune  

Proteção Avançada contra Ameaças do Microsoft Defender (ATP do Microsoft Defender) e o Microsoft Intune funcionam em conjunto para ajudar a evitar violações de segurança e a limitar o impacto de violações de dentro de uma organização.

Esse recurso aplica-se a: Dispositivos com Windows 10

Por exemplo, alguém envia um anexo do Word com código mal-intencionado incorporado para um usuário dentro de sua organização. O usuário abre o anexo e habilita o conteúdo. Inicia um ataque de privilégio elevado e um invasor de um computador remoto tem direitos de administrador no dispositivo da vítima. O invasor então remotamente acessa outros dispositivos do usuário.

Essa violação de segurança pode afetar toda a organização.

A ATP do Microsoft Defender pode resolver eventos de segurança como o deste cenário. A Central de Segurança do Microsoft Defender reporta os dispositivos como "alto risco" e inclui um relatório detalhado de atividade suspeita. Em nosso exemplo, a ATP do Microsoft Defender detecta que o dispositivo executou código anormal, apresentou uma elevação de privilégios de processo, injetou código mal-intencionado e emitiu um shell remoto suspeito. A ATP do Microsoft Defender, em seguida, fornece opções para atenuar a ameaça.

Usando o Intune, você pode criar uma política de conformidade que determina um nível aceitável de risco. Se um dispositivo excede esse risco, o dispositivo se tornará incompatível. Quando combinado com acesso condicional do Azure Active Directory (AD), o usuário tem o acesso bloqueado de recursos corporativos.

Este artigo mostra como:

- Habilite o Intune na Central de Segurança do Microsoft Defender e a ATP do Microsoft Defender no Intune. Essas tarefas criam uma conexão de serviço a serviço entre o Intune e a ATP do Microsoft Defender. Esta conexão permite que a ATP do Microsoft Defender grave o risco de máquina para seus dispositivos do Intune.
- Criar política de conformidade no Intune.
- Habilite o Acesso Condicional no Azure Active Directory (AD) em dispositivos com base em seu nível de ameaça.

## <a name="prerequisites"></a>Pré-requisitos

Para usar a ATP do Microsoft com o Intune, verifique se você tem a seguinte configuração e está pronto para usar:

- Locatário licenciado para Enterprise Mobility + Security E3 e Windows E5 (ou Microsoft 365 Enterprise E5)
- Ambiente do Microsoft Intune, com dispositivos Windows 10 [gerenciados para Intune](windows-enroll.md) que também façam parte do Azure AD
- [ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e acesso à Central de Segurança do Microsoft Defender (portal ATP)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Habilitar a ATP do Microsoft Defender no Intune

Quando você integra um novo aplicativo à Defesa contra Ameaças Móveis do Intune e habilita a conexão, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma política de acesso condicional clássica.  Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas ou desabilitadas.

As políticas de acesso condicional clássicas para aplicativos MTD: 

- São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma identificação do dispositivo. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.  
- São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD.
- Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.  

Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.

### <a name="to-enable-defender-atp"></a>Para habilitar o Defender ATP
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo** > **ATP do Microsoft Defender** e, em seguida, escolha *Configurações do Conector* e **Abrir a Central de Segurança do Microsoft Defender**.

    ![Selecione para abrir a Central de Segurança do Microsoft Defender](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. Na **Central de Segurança do Microsoft Defender**:
    1. Selecione **Configurações** > **Recursos avançados**.
    2. Para **Conexão do Microsoft Intune**, escolha **Ativado**:

        ![Habilitar a conexão com o Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Selecione **Salvar preferências**.

4. Volte para o Intune, **Conformidade do dispositivo** > **ATP do Microsoft Defender**. Defina **Conectar dispositivos Windows versão 10.0.15063 e superiores ao Microsoft Defender ATP** como **Ligado**.
5. Selecione **Salvar**.

Você normalmente realiza essa tarefa uma vez. Se a ATP do Microsoft Defender já estiver habilitada em seu recurso Intune, você não precisará ativá-la novamente.

## <a name="onboard-devices-using-a-configuration-profile"></a>Integrar dispositivos usando um perfil de configuração

Quando um usuário final é registrado no Intune, você pode enviar por push diferentes configurações para o dispositivo usando um perfil de configuração. Isso também se aplica à ATP do Microsoft Defender.

A ATP do Microsoft Defender inclui um pacote de configuração de integração que se comunica com os [serviços da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar arquivos, detectar ameaças e relatar o risco para a ATP do Microsoft Defender.

Quando você faz a integração, o Intune obtém um pacote de configuração gerado automaticamente da ATP do Microsoft Defender. O Intune envia por push o pacote de configuração para o dispositivo quando o perfil de configuração é enviado, o que permite que a ATP do Microsoft Defender monitore o dispositivo em busca de ameaças.

Quando você carregar um dispositivo usando o pacote de configuração, não precisará fazê-lo novamente. Você também pode integrar dispositivos usando uma [política de grupo ou System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-configuration-profile"></a>Criar o perfil de configuração

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do Dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição**.
4. Em **Plataforma**, selecione **Windows 10 e posterior**
5. Para **Tipo de perfil**, selecione **ATP do Microsoft Defender (Windows 10 Desktop)** .
6. Configure as definições:

    - **Tipo de pacote de configuração de cliente da ATP do Microsoft Defender**: selecione **Carregar** para adicionar o pacote de configuração no perfil. Selecione **Remover** para remover o pacote de configuração do perfil.
  
    > [!NOTE]  
    > Se você estabeleceu corretamente uma conexão com a ATP do Microsoft Defender, o Intune vai **Integrar** automaticamente o perfil de configuração e a configuração **Tipo de pacote de configuração de cliente da ATP do Microsoft Defender** não estará disponível.
  
    - **Compartilhamento de exemplo para todos os arquivos**: **Habilitar** permite que os exemplos sejam coletados e compartilhados com a ATP do Microsoft Defender. Por exemplo, se você vir um arquivo suspeito, poderá enviá-lo para a ATP do Microsoft Defender para uma análise profunda. **Não configurado** não compartilha nenhum exemplo com o a ATP do Microsoft Defender.
    - **Acelerar a frequência do relatório de telemetria**: Para dispositivos que estão em risco alto, **Habilitar** essa configuração para relatar a telemetria ao serviço da ATP do Microsoft Defender com maior frequência.

    [Integrar computadores do Windows 10 usando o System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) tem mais detalhes sobre essas configurações da ATP do Microsoft Defender.

7. Selecione **OK** e **Criar** para salvar suas alterações, o que cria o perfil.

## <a name="create-the-compliance-policy"></a>Criar a política de conformidade
A política de conformidade determina um nível aceitável de risco em um dispositivo.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
3. Insira um **Nome** e uma **Descrição**.
4. Em **plataforma**, selecione **Windows 10 e posterior**.
5. Nas configurações da **ATP do Microsoft Defender**, defina **Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo** como o seu nível preferencial. As classificações de nível de ameaça são [determinadas pela ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Limpar**: este é o nível mais seguro. O dispositivo não pode ter ameaças existentes e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível. A ATP do Microsoft Defender usa o valor *Seguro*.
   - **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo existirem. Dispositivos com níveis de ameaça média ou alta não são compatíveis.
   - **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.
   - **Alto**: este nível é o menos seguro e permite todos os níveis de ameaça. Sendo assim, os dispositivos com níveis de ameaça alta, média ou baixa são considerados compatíveis.

6. Selecione **OK** e **Criar** para salvar suas alterações (e criar a política).

## <a name="assign-the-policy"></a>Atribuir a política

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo** > **Políticas**> selecione a política de conformidade da ATP do Microsoft Defender.
3. Selecione **Atribuições**.
4. Incluir ou excluir seus grupos do Azure AD para atribuir a eles a política.
5. Para implantar a política aos grupos, selecione **Salvar**. Os dispositivos de usuário direcionados pela política são avaliados quanto à conformidade.

## <a name="create-a-conditional-access-policy"></a>Criar política de Acesso Condicional
A política de Acesso Condicional bloqueará o acesso a recursos *se* o dispositivo não for incompatível. Então se um dispositivo excede o nível de ameaça, você pode bloquear o acesso a recursos corporativos, como o SharePoint ou Exchange Online.  

> [!TIP]  
> O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*.  

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecione **Acesso Condicional** > **Nova política**.
2. Insira **Nome** da política e selecione **Usuários e grupos**. Use as opções Incluir ou Excluir para adicionar os grupos para a política e selecione **Concluído**.
3. Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger. Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Exchange Online do Office 365**.

    Selecione **Concluído** para salvar suas alterações.

4. Selecione **Condições** > **Aplicativos do cliente** para aplicar a política para aplicativos e navegadores. Por exemplo, selecione **Sim** e, em seguida, habilitar **Navegador** e **Aplicativos móveis e clientes de área de trabalho**.

    Selecione **Concluído** para salvar suas alterações.

5. Selecione **Conceder** para aplicar Acesso Condicional baseado na conformidade do dispositivo. Por exemplo, selecione **Conceder acesso** > **Exigir que o dispositivo seja marcado como compatível**.

    Marque **Selecionar** para salvar suas alterações.

6. Selecione **Habilitar política** e, em seguida, **Criar** para salvar suas alterações.

[O que é o Acesso Condicional? ](conditional-access.md) é um bom recurso.

## <a name="monitor-device-compliance"></a>Monitorar a conformidade do dispositivo
Em seguida, monitore o estado de dispositivos com a política de conformidade da ATP do Microsoft Defender.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo** > **Conformidade com a política**.
3. Localize sua política da ATP do Microsoft Defender na lista e veja quais dispositivos são compatíveis ou não.

## <a name="more-good-stuff"></a>Mais coisas legais
[Acesso Condicional da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)  
[Painel de risco da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  

[Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md)  
[Acesso Condicional no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)