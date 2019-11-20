---
title: Usar a ATP do Microsoft Defender no Microsoft Intune – Azure | Microsoft Docs
description: Use a Microsoft Defender ATP (Proteção Avançada contra Ameaças do Microsoft Defender) com o Intune, incluindo instalação, configuração e integração de seus dispositivos Intune com a ATP. Em seguida, use uma avaliação de risco da ATP nos dispositivos com as políticas de conformidade do dispositivo Intune e de acesso condicional para proteger os recursos de rede.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6026cf3ef8d044c92680cf4c4c88ba55c9777e0
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713258"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Impor a conformidade da ATP do Microsoft Defender com Acesso Condicional no Intune

Você pode integrar o Microsoft Defender ATP (Proteção Avançada contra Ameaças do Microsoft Defender) com o Microsoft Intune como uma solução de Defesa contra Ameaças Móveis. A integração pode ajudá-lo a evitar violações de segurança e limitar o impacto das violações dentro da organização. O Microsoft Defender ATP funciona com dispositivos que executam Windows 10 ou posterior.

Para ter êxito, use as seguintes configurações em conjunto:

- **Estabeleça uma conexão de serviço a serviço entre o Intune e o Microsoft Defender ATP**. Essa conexão permite que o Microsoft Defender ATP colete dados sobre os riscos da máquina em dispositivos Windows 10 gerenciados com o Intune.
- **Use um perfil de configuração de dispositivo para integrar dispositivos ao Microsoft Defender ATP**. Você integra dispositivos a fim de configurá-los para comunicação com o Microsoft Defender ATP e fornecer dados que ajudem a avaliar o nível de risco deles.
- **Use uma política de conformidade do dispositivo para definir o nível de risco que você deseja permitir**. Os níveis de risco são relatados pelo Microsoft Defender ATP.  Os dispositivos que excederem o nível de risco permitido serão identificados como fora de conformidade.
- **Use uma política de acesso condicional** para impedir que os usuários acessem recursos corporativos de dispositivos que não estão em conformidade.

Quando você integra o Intune ao Microsoft Defender ATP, é possível utilizar o TVM (Gerenciamento de Ameaças e Vulnerabilidade) da ATP e [usar o Intune para corrigir a vulnerabilidade do ponto de extremidade identificada pelo TVM](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Exemplo de uso do Microsoft Defender ATP com o Intune

O exemplo a seguir explica como essas soluções funcionam em conjunto para ajudar a proteger sua organização. Neste exemplo, o Microsoft Defender ATP e o Intune já estão integrados.

Considere um evento em que alguém envia um anexo do Word com código mal-intencionado incorporado para um usuário dentro de sua organização.

- O usuário abre o anexo e habilita o conteúdo.
- Inicia um ataque de privilégio elevado e um invasor de um computador remoto tem direitos de administrador no dispositivo da vítima.
- O invasor então remotamente acessa outros dispositivos do usuário. Essa violação de segurança pode afetar toda a organização.

O Microsoft Defender ATP pode ajudar a resolver eventos de segurança como o deste cenário.

- Em nosso exemplo, a ATP do Microsoft Defender detecta que o dispositivo executou código anormal, apresentou uma elevação de privilégios de processo, injetou código mal-intencionado e emitiu um shell remoto suspeito.
- Com base nessas ações do dispositivo, o Microsoft Defender ATP [classifica o dispositivo como de alto risco](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) e inclui um relatório detalhado de atividades suspeitas no portal da Central de Segurança do Microsoft Defender.

Como você tem uma política de conformidade de dispositivos do Intune para classificar dispositivos com um nível de risco *Médio* ou *Alto* como fora de conformidade, o dispositivo comprometido é classificado dessa forma. Essa classificação permite que a política de acesso condicional entre em vigor e bloqueie o acesso desse dispositivo aos recursos corporativos.

## <a name="prerequisites"></a>Pré-requisitos

Para usar o Microsoft Defender ATP com o Intune, verifique se você tem a seguinte configuração e está pronto para o uso:

- Locatário licenciado para Enterprise Mobility + Security E3 e Windows E5 (ou Microsoft 365 Enterprise E5)
- Ambiente do Microsoft Intune, com dispositivos Windows 10 [gerenciados para Intune](../enrollment/windows-enroll.md) que também façam parte do Azure AD
- [ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e acesso à Central de Segurança do Microsoft Defender (portal ATP)

> [!NOTE]
> Não há suporte para o Microsoft Defender ATP com as políticas de proteção de aplicativo do Intune.

## <a name="enable-microsoft-defender-atp-in-intune"></a>Habilitar a ATP do Microsoft Defender no Intune

Esta primeira etapa destina-se à criação de uma conexão de serviço a serviço entre o Intune e o Microsoft Defender ATP. Isso requer acesso administrativo à Central de Segurança do Microsoft Defender e ao Intune.

### <a name="to-enable-defender-atp"></a>Para habilitar o Defender ATP

Você só precisa habilitar o Defender ATP uma única vez por locatário. 

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Segurança de ponto de extremidade** > **Microsoft Defender ATP** e **Abrir a Central de Segurança do Microsoft Defender**.

   ![Selecione para abrir a Central de Segurança do Microsoft Defender](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. Na **Central de Segurança do Microsoft Defender**:
    1. Selecione **Configurações** > **Recursos avançados**.
    2. Para **Conexão do Microsoft Intune**, escolha **Ativado**:

        ![Habilitar a conexão com o Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Selecione **Salvar preferências**.

4. Volte ao **Microsoft Defender ATP** no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft. Em **Configurações de política de conformidade do MDM**, defina **Conectar dispositivos Windows versão 10.0.15063 e posteriores ao Microsoft defender ATP** como **Ativado**.

5. Selecione **Salvar**.

> [!TIP]
> Quando você integra um novo aplicativo à Defesa contra Ameaças Móveis do Intune e habilita a conexão a essa plataforma, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma nova política de acesso condicional clássica. Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas ou desabilitadas.
>
> As políticas de acesso condicional clássicas para aplicativos MTD:
>
> - São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma ID de dispositivo, antes de se comunicarem com os parceiros de MTD. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.
> - Não afeta outros recursos ou aplicativos de nuvem.
> - São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD.
> - Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.
>
> Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Integrar dispositivos usando um perfil de configuração

Após estabelecer a conexão de serviço a serviço entre o Intune e o Microsoft Defender ATP, integre seus dispositivos gerenciados do Intune ao ATP para que os dados sobre o nível de risco possam ser coletados e usados. Para integrar serviços, use um perfil de configuração de dispositivo para o Microsoft Defender ATP.

Quando você estabeleceu a conexão com o Microsoft Defender ATP, o Intune recebeu dele um pacote de configuração da integração com o Microsoft Defender ATP. Esse pacote é implantado em dispositivos com o perfil de configuração do dispositivo. O pacote configura dispositivos para comunicação com os [serviços do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar arquivos, detectar ameaças e relatar os riscos ao Microsoft Defender ATP.

Após integrar um dispositivo usando o pacote de configuração, você não precisará fazer isso novamente. Você também pode integrar dispositivos usando uma [política de grupo ou System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-device-configuration-profile"></a>Criar o perfil de configuração do dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
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
8. [Atribua o perfil de configuração de dispositivo](../configuration/device-profile-assign.md) aos dispositivos que você deseja avaliar com o Microsoft Defender ATP.  

## <a name="create-and-assign-the-compliance-policy"></a>Criar e atribuir a política de conformidade

A política de conformidade determina o nível de risco considerado aceitável em um dispositivo.

### <a name="create-the-compliance-policy"></a>Criar a política de conformidade

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Políticas de conformidade** > **Criar política**.
3. Insira um **Nome** e uma **Descrição**.
4. Em **plataforma**, selecione **Windows 10 e posterior**.
5. Em **Configurações**, selecione **Microsoft Defender ATP**.
6. Defina **Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo** como o seu nível preferencial.

   As classificações de nível de ameaça são [determinadas pela ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Limpar**: este é o nível mais seguro. O dispositivo não pode ter ameaças existentes e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível. A ATP do Microsoft Defender usa o valor *Seguro*.
   - **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo existirem. Dispositivos com níveis de ameaça média ou alta não são compatíveis.
   - **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.
   - **Alto**: este nível é o menos seguro e permite todos os níveis de ameaças. Sendo assim, os dispositivos com níveis de ameaça alta, média ou baixa são considerados compatíveis.

7. Selecione **OK** e **Criar** para salvar suas alterações (e criar a política).
8. [Atribua a política de conformidade do dispositivo](create-compliance-policy.md#assign-the-policy) aos grupos aplicáveis.

## <a name="create-a-conditional-access-policy"></a>Criar política de Acesso Condicional

A política de Acesso Condicional bloqueia o acesso a recursos para dispositivos que excedam o nível de ameaça definido em sua política de conformidade. Você pode bloquear o acesso do dispositivo a recursos corporativos, como o SharePoint ou o Exchange Online.

> [!TIP]
> O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó Acesso Condicional acessado no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft é o mesmo nó acessado no *Azure AD*.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Segurança de ponto de extremidade** > **Acesso condicional** > **Nova política**.

3. Insira **Nome** da política e selecione **Usuários e grupos**. Use as opções Incluir ou Excluir para adicionar os grupos para a política e selecione **Concluído**.

4. Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger. Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Exchange Online do Office 365**.

   Selecione **Concluído** para salvar suas alterações.

5. Selecione **Condições** > **Aplicativos do cliente** para aplicar a política para aplicativos e navegadores. Por exemplo, selecione **Sim** e, em seguida, habilitar **Navegador** e **Aplicativos móveis e clientes de área de trabalho**.

   Selecione **Concluído** para salvar suas alterações.

6. Selecione **Conceder** para aplicar Acesso Condicional baseado na conformidade do dispositivo. Por exemplo, selecione **Conceder acesso** > **Exigir que o dispositivo seja marcado como compatível**.

    Marque **Selecionar** para salvar suas alterações.

7. Selecione **Habilitar política** e, em seguida, **Criar** para salvar suas alterações.

## <a name="monitor-device-compliance"></a>Monitorar a conformidade do dispositivo

Em seguida, monitore o estado de dispositivos com a política de conformidade da ATP do Microsoft Defender.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Monitor** > **Conformidade da política**.

3. Localize sua política da ATP do Microsoft Defender na lista e veja quais dispositivos são compatíveis ou não.

## <a name="view-onboarding-status"></a>Exibir o status da integração

Para exibir o status de integração de todos os dispositivos Windows 10 gerenciados pelo Intune, você pode ir para **Conformidade do dispositivo** > **Microsoft Defender ATP**. Nessa página, também é possível iniciar a criação de um perfil de configuração de dispositivo para integração de mais dispositivos ao Microsoft Defender ATP.

## <a name="next-steps"></a>Próximas etapas

[Acesso Condicional da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)

[Painel de risco da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)

[Use tarefas de segurança com o Gerenciamento de Vulnerabilidades da ATP para corrigir problemas em dispositivos](atp-manage-vulnerabilities.md).

[Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md)
