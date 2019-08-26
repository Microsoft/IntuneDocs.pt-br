---
title: Usar linhas de base de segurança no Microsoft Intune – Azure | Microsoft Docs
description: Use as configurações de segurança recomendadas do Windows para proteger usuários e dados em dispositivos com o Microsoft Intune para gerenciamento de dispositivo móvel. Habilite a criptografia, configure a Proteção Avançada contra Ameaças do Microsoft Defender, controle o Internet Explorer, defina políticas de segurança local, exija uma senha, bloqueie downloads da Internet e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26ad26fedc6fe0e44328f5c77fa5f093c1230a28
ms.sourcegitcommit: 6f84e880411a202c5500eb460779b7ef63a7f430
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68978517"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Usar linhas de base de segurança para configurar dispositivos com Windows 10 no Intune

Use as linhas de base de segurança do Intune para proteger seus usuários e dispositivos. Linhas de base de segurança são grupos pré-configurados de configurações do Windows que ajudam você a aplicar um grupo conhecido de configurações e valores padrão recomendados pelas equipes de segurança relevantes. Quando você cria um perfil de linha de base de segurança no Intune, está criando um perfil de *configuração de dispositivo*.

Esse recurso aplica-se a:

- Windows 10 versão 1809 e posterior

Você implanta linhas de base de segurança em grupos de usuários ou dispositivos no Intune e as configurações se aplicam a dispositivos que executam o Windows 10 ou posterior. Por exemplo, a *Linha de Base de Segurança do MDM* habilita automaticamente o BitLocker para unidades removíveis, exige automaticamente uma senha para desbloquear um dispositivo, desabilita automaticamente a autenticação básica e muito mais. Quando um valor padrão não funcionar para o seu ambiente, personalize a linha de base para aplicar as configurações necessárias.  

Tipos de linha de base separados podem incluir as mesmas configurações, mas usar valores padrão diferentes para essas configurações. É importante entender os padrões nas linhas de base que você escolhe usar e modificar cada linha de base para atender às suas necessidades organizacionais.  

> [!NOTE]
> A Microsoft não recomenda o uso de versões prévias de linhas de base de segurança em um ambiente de produção. As configurações em uma linha de base prévia podem mudar ao longo da versão prévia. 

As linhas de base de segurança podem ajudar você a ter um fluxo de trabalho seguro de ponta a ponta ao trabalhar com o Microsoft 365. Alguns do benefícios incluem:

- Uma linha de base de segurança inclui as melhores práticas e recomendações de configurações que afetam a segurança. O Intune tem uma parceria com a mesma equipe de segurança do Windows que cria linhas de base de segurança de política grupo. Essas recomendações tem base em orientações e numa ampla experiência.
- Se você for um usuário novo do Intune e não souber por onde começar, as linhas de base de segurança oferecerão uma vantagem. Você pode criar e implantar rapidamente um perfil de seguro, sabendo que está ajudando a proteger os recursos e dados da sua organização.
- Se você estiver usando a politica de grupo, a migração para o Intune para gerenciamento é muito mais fácil com essas linhas de base. Essas linhas de base são criadas nativamente no Intune e incluem uma experiência de gerenciamento moderna.



[Linhas de base de segurança do Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) é uma excelente fonte para saber mais sobre esse recurso. [Gerenciamento de dispositivo móvel](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) é uma excelente fonte sobre MDM, e o que você pode fazer em dispositivos com Windows.

## <a name="about-baseline-versions-and-instances"></a>Sobre as versões e instâncias de linha de base de segurança

Cada nova instância de versão de uma linha de base pode adicionar ou remover configurações ou introduzir outras alterações. Por exemplo, à medida que novas configurações do Windows 10 são disponibilizadas com novas versões do Windows 10, a Linha de Base de Segurança do MDM pode receber uma nova instância da versão que inclui as configurações mais recentes.  

No console do Intune, o título de cada linha de base exibe o nome do modelo da linha de base e informações básicas sobre ela. As informações incluem quantos perfis você usa que empregam esse tipo de linha de base, quantas instâncias separadas (versões) do tipo de linha de base estão disponíveis e uma data de *Última Publicação* identificando quando o modelo da linha de base foi adicionado a seu locatário. O exemplo a seguir mostra o bloco de uma linha de base de segurança do MDM bem usada:  

![Bloco de linha de base](./media/security-baselines/baseline-tile.png)

Para exibir mais informações sobre as versões de linha de base usadas, selecione um título de linha de base para abrir o painel *Visão Geral* dela e selecione **Versões**. O Intune exibe detalhes sobre as versões da linha de base que estão sendo usadas pelos seus perfis. No painel Versões, você pode selecionar uma única versão para exibir mais detalhes sobre os perfis que a utilizam. Também pode selecionar duas versões diferentes e, em seguida, escolher **Comparar linhas de base** para fazer o download de um arquivo CSV que detalha essas diferenças.  

![Comparar linhas de base](./media/security-baselines/compare-baselines.png)

Quando você cria um *perfil* ​​de linha de base de segurança, ele usa automaticamente a instância da linha de base de segurança liberada mais recentemente.  Você pode continuar a usar e editar perfis criados anteriormente que usam uma instância de versão de linha de base anterior, incluindo linhas de base criadas usando uma versão prévia. 

Você pode optar por [alterar a versão](#change-the-baseline-version-for-a-profile) de uma linha de base em uso com determinado perfil. Isso significa que, quando uma nova versão for lançada, você não precisará criar um novo perfil de linha de base para aproveitá-la. Em vez disso, quando estiver pronto, você poderá selecionar um perfil de linha de base e, em seguida, usar a opção interna para alterar a versão da instância desse perfil para um novo.  

## <a name="available-security-baselines"></a>Escopos de segurança disponíveis 

As instâncias de linhas de base de segurança a seguir estão disponíveis para uso com o Intune. Use os links para visualizar as configurações da instância mais recente de cada linha de base. 

- **Linha de Base de Segurança do MDM**
  - [Linha de Base de Segurança do MDM para maio de 2019](security-baseline-settings-mdm.md)
  - [Versão prévia: Linha de base de segurança do MDM para outubro de 2018](security-baseline-settings-mdm-archive.md)

- **Linha de base da ATP do Microsoft Defender**  
  *Para usar essa linha de base, seu ambiente precisa atender aos pré-requisitos para o uso da [Proteção Avançada contra Ameaças do Microsoft Defender](advanced-threat-protection.md#prerequisites)* .
  - [Versão prévia: Linha de base da ATP do Microsoft Defender](security-baseline-settings-defender-atp.md)  

  > [!NOTE]
  > A linha de base de segurança do Microsoft Defender ATP foi otimizada para dispositivos físicos e, atualmente, não é recomendada para uso em VMs (máquinas virtuais) ou pontos de extremidade VDI. Algumas configurações de linha de base podem afetar as sessões interativas remotas em ambientes virtualizados.  Para obter mais informações, confira [Aumentar a conformidade com a linha de base de segurança do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) na documentação do Windows.

Você pode continuar a usar e editar perfis criados anteriormente com base em um modelo de visualização, mesmo quando esse modelo de visualização não estiver mais disponível para criar novos perfis. 

## <a name="manage-baselines"></a>Gerenciar linhas de base  

As tarefas comuns ao trabalhar com linhas de base de segurança incluem:
- [Criar um perfil](#create-the-profile) – para definir as configurações que você deseja usar e atribuir a linha de base aos grupos.
- [Alterar a versão](#change-the-baseline-version-for-a-profile) – altere a versão da linha de base usada por um perfil.
- [Remover uma atribuição de linha de base](#remove-a-security-baseline-assignment) – Saiba o que acontece quando você para de gerenciar as configurações com uma linha de base de segurança.


### <a name="prerequisites"></a>Pré-requisitos
- Para gerenciar linhas de base no Intune, sua conta deve ter a função interna [Gerenciador de Perfis e de Política](role-based-access-control.md#built-in-roles).

- O uso de algumas linhas de base pode exigir que você tenha uma assinatura ativa para serviços adicionais, como o Microsoft Defender ATP.  


### <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecione **Segurança do dispositivo** > **Linhas de base de segurança** para visualizar a lista de linhas de base disponíveis.


    ![Selecione uma linha de base de segurança para configurar](./media/security-baselines/available-baselines.png)

2. Selecione a linha de base que você quer usar e selecione **Criar perfil**.  

3. Na guia **Básico**, especifique as seguintes propriedades:

    - **Nome**: Insira um nome para seu perfil de linhas de base de segurança. Por exemplo, digite *Perfil padrão para Defender ATP*.

    - **Descrição**: Insira algum texto que descreva a função dessa linha de base. A descrição serve para você inserir qualquer texto que quiser. Isso é opcional, mas recomendado.  

   Selecione **Avançar** para ir até a próxima guia. Depois de avançar para uma nova guia, você pode selecionar o nome da guia a fim de retornar a uma guia visualizada anteriormente.  

4. Na guia Configurações, visualize os grupos de **Configurações** disponíveis na linha de base selecionada. É possível expandir um grupo para ver as configurações dele e os valores padrão dessas configurações na linha de base. Para localizar configurações específicas:
   - Selecione um grupo para expandir e verificar as configurações disponíveis.  
   - Use a barra *Pesquisar* e especifique as palavras-chave que filtram a exibição para exibir apenas os grupos que contêm seus critérios de pesquisa.  
 
   Cada configuração em uma linha de base tem uma configuração padrão para essa versão de linha de base. Redefina as configurações padrão para atender às suas necessidades de negócios. Linhas de base diferentes podem conter a mesma configuração e usar valores padrão diferentes para a configuração, dependendo da intenção da linha de base. 

    ![Expanda um grupo para exibir as configurações dele](./media/security-baselines/sample-list-of-settings.png)

5. Na guia **Marcas de escopo**, selecione **Selecionar marcas de escopo** para abrir o painel *Selecionar marcas* e atribuir marcas de escopo ao perfil. 

6. Na guia **Atribuições**, selecione **Selecionar grupos para incluir** e atribua a linha de base a um ou mais grupos. Use **Selecionar grupos para excluir** a fim de ajustar a atribuição.  

   ![Atribuir um perfil](./media/security-baselines/assignments.png)
  
7. Quando estiver pronto para implantar a linha de base, avance até a guia **Revisar + criar** para examinar os detalhes da linha de base. Selecione **Criar** para salvar e implantar o perfil.  

   Assim que você criar o perfil, ele será enviado ao grupo atribuído e poderá ser aplicado imediatamente.

   > [!TIP]  
   > Se você salvar um perfil sem primeiro atribuí-lo aos grupos, poderá editar o perfil posteriormente para fazer isso.  

   ![Revisar a linha de base](./media/security-baselines/review.png) 

  
8. Depois de criar o perfil, edite-o acessando **Segurança do Dispositivo** > **Linhas de base de segurança**, depois selecione o tipo da linha de base que você configurou e selecione **Perfis**. Selecione o perfil na lista de perfis disponíveis e, em seguida, selecione **Propriedades**. Você pode editar as configurações de todas as guias de configuração disponíveis e selecionar **Revisar + salvar** para confirmar suas alterações.  

### <a name="change-the-baseline-version-for-a-profile"></a>Alterar a versão de linha de base para um perfil  

Você pode alterar a versão da instância de linha de base usada em um perfil.  Ao alterar a versão, você seleciona uma instância disponível da mesma linha de base. Não é possível alterar entre dois tipos de linhas de base diferentes, como alterar um perfil de uma linha de base do Defender ATP para usar a linha de base de segurança do MDM. 

Ao configurar uma alteração da versão de linha de base, você pode baixar um arquivo CSV que lista as alterações entre as duas versões de linha de base envolvidas. Você também tem a opção de manter todas as personalizações da versão da linha de base original ou implementar a nova versão usando todos os valores padrão. Você não tem a opção de alterar configurações individuais quando altera a versão de uma linha de base de um perfil. 

Depois de salvar, após a conclusão da conversão, a linha de base é reimplantada imediatamente nos grupos atribuídos.  

**Durante a conversão**:
- Novas configurações que não estavam na versão original que você estava usando são adicionadas e definidas para usar os valores padrão.  

- As configurações que não estão na nova versão de linha de base selecionada são removidas e não são mais aplicadas por esse perfil de linha de base de segurança.  

  Quando uma configuração não é mais gerenciada por um perfil de linha de base, essa configuração não é redefinida no dispositivo. Em vez disso, a configuração no dispositivo permanece definida para sua última configuração até que algum outro processo gerencie a configuração para alterá-la. Exemplos de processos que podem alterar uma configuração depois que você parar de gerenciá-la incluem um perfil de linha de base diferente, uma configuração de política de grupo ou configuração manual feita no dispositivo. 

#### <a name="to-change-the-baseline-version-for-a-profile"></a>Para alterar a versão da linha de base de um perfil  

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecione **Segurança do dispositivo** > **Linhas de base de segurança**, depois selecione o bloco para o tipo de linha de base que tem o perfil que você deseja alterar.  

2. Em seguida, selecione **Perfis**, marque a caixa de seleção do perfil que você quer editar e selecione **Alterar Versão**.  

   ![selecionar uma linha de base](./media/security-baselines/select-baseline.png)  

3. No painel **​​Alterar Versão**, use o menu suspenso **Selecionar uma linha de base de segurança para a qual atualizar** e selecione a instância da versão que você deseja usar.  

   ![selecionar uma versão](./media/security-baselines/select-instance.png)  
   
4. Selecione **Revisar atualização** para fazer o download de um arquivo CSV que exiba a diferença entre a versão da instância atual do perfil e a nova versão que você selecionou. Revise esse arquivo para entender quais configurações são novas ou foram removidas e quais são os valores padrão para essas configurações no perfil atualizado.  

   Quando estiver pronto, prossiga para a próxima etapa.  

5. Escolha uma das duas opções para **Selecionar um método para atualizar o perfil**: 
   - **Aceitar alterações de linha de base, mas manter minhas personalizações de configuração existentes** – Essa opção mantém as personalizações feitas no perfil da linha de base e as aplica à nova versão selecionada para uso.
   - **Aceitar alterações de linha de base e descartar personalizações de configurações existentes** – Esta opção substitui completamente o seu perfil original. O perfil atualizado usará os valores padrão para todas as configurações.  

6. Selecione **Enviar**. O perfil é atualizado para a versão de linha de base selecionada e, após a conclusão da conversão, a linha de base é imediatamente reimplementada aos grupos atribuídos.

### <a name="remove-a-security-baseline-assignment"></a>Remover uma atribuição de linha de base de segurança
Quando uma configuração de linha de base de segurança não se aplica mais a um dispositivo ou as configurações em uma linha de base estão definidas como *Não configurada*, essas configurações em um dispositivo não são revertidas para uma configuração pré-gerenciada. Em vez disso, as configurações gerenciadas anteriormente no dispositivo mantêm as últimas configurações recebidas da linha de base até que outro processo atualize essas configurações no dispositivo.  

Outros processos que podem alterar posteriormente as configurações no dispositivo incluem uma linha de base de segurança diferente ou nova, um perfil de configuração de dispositivo, configurações de Política de Grupo ou a edição manual da configuração no dispositivo.  

## <a name="co-managed-devices"></a>Dispositivos cogerenciado

Linhas de base de segurança em dispositivos gerenciados pelo Intune são semelhantes aos dispositivos cogerenciados com o Configuration Manager. Dispositivos cogerenciados usam o System Center Configuration Manager e o Microsoft Intune para gerenciar dispositivos com Windows 10 simultaneamente. Isso permite que você anexe à nuvem seu investimento existente do Configuration Manager para obter os benefícios do Intune. [Visão geral do cogerenciamento](https://docs.microsoft.com/sccm/comanage/overview) é um excelente recurso se você usa o Configuration Manager e também deseja os benefícios da nuvem.

Ao usar dispositivos cogerenciados, você deve alternar a carga de trabalho **Configuração do dispositivo** (suas configurações) para o Intune. [Cargas de trabalho de configuração de dispositivo](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) fornece mais informações.  

## <a name="q--a"></a>Perguntas e Respostas

### <a name="why-these-settings"></a>Por que essas configurações?

A equipe de segurança da Microsoft tem anos de experiência trabalhando diretamente com os desenvolvedores do Windows e com a comunidade de segurança para criar essas recomendações. As configurações nessa linha de base são consideradas as opções de configuração de segurança mais relevantes. Em cada novo build do Windows, a equipe ajusta suas recomendações com base em recursos lançados recentemente.

### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Há alguma diferença nas recomendações para linhas de base de segurança de Windows para política de grupo versus Intune?

A mesma equipe de segurança da Microsoft escolheu e organizou as configurações para cada linha de base. O Intune inclui todas as configurações relevantes na linha de base de segurança do Intune. Há algumas configurações na linha de base de política de grupo que são específicas a um controlador de domínio local. Essas configurações são excluídas das recomendações do Intune. Todas as outras configurações são iguais.

### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>As linhas de base de segurança do Intune são compatíveis com CIS ou NSIT?

Estritamente falando, não. A equipe de segurança da Microsoft consulta organizações, como a CIS, para compilar suas recomendações. Porém, não existe um mapeamento individual entre "compatível com CIS" e as linhas de base da Microsoft.

### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Quais certificações as linhas de base de segurança da Microsoft têm? 

- A Microsoft continua a publicar linhas de base de segurança para políticas de grupo (GPOs) e o [Kit de Ferramentas de Conformidade de Segurança](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), como faz há muitos anos. Essas linhas de base são usadas por muitas organizações. As recomendações nessas linhas de base são provenientes do envolvimento da equipe de segurança da Microsoft com clientes corporativos e órgãos externos, incluindo o Departamento de Defesa (DoD), Instituto Nacional de Padrões e Tecnologia (NIST) e muito mais. Compartilhamos nossas recomendações e linhas de base com essas organizações. Essas organizações também têm suas próprias recomendações que refletem com maior exatidão as recomendações da Microsoft. À medida que o MDM (gerenciamento de dispositivo móvel) continua a evoluir para a nuvem, a Microsoft criou recomendações de MDM equivalentes dessas linhas de base de política de grupo. Essas linhas de base adicionais são incorporadas ao Microsoft Intune e incluem relatórios de conformidade sobre usuários, grupos e dispositivos que seguem (ou não) a linha de base.

- Muitos clientes estão usando as recomendações de linha de base do Intune como um ponto de partida e, em seguida, personalizando-as para atender às demandas de TI e de segurança. A **Linha de Base de Segurança de MDM** do Windows 10 RS5 da Microsoft é a primeira linha de base lançada. Esta linha de base é compilada como uma infraestrutura genérica que permite aos clientes importar eventualmente outras linhas de base de segurança com base no CIS, NIST e outros padrões. Atualmente, ela está disponível para Windows e, eventualmente, incluirá o iOS e Android.

- A migração de políticas locais de grupo do Active Directory para uma solução de nuvem pura usando o Azure Active Directory (AD) com o Microsoft Intune é uma jornada. Para ajudar, há modelos de políticas de grupo incluídos no [Kit de Ferramentas de Conformidade de Segurança](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10) que podem ajudar a gerenciar dispositivos híbridos do AD e do Azure AD. Esses dispositivos podem obter as configurações de MDM da nuvem (Intune) e configurações de política de grupo de controladores de domínio locais conforme necessário.

## <a name="next-steps"></a>Próximas etapas
- Confira as configurações nas versões mais recentes das linhas de base disponíveis:  
  - [Linha de Base de Segurança do MDM](security-baseline-settings-mdm.md)  
  - [Linha de base da ATP do Microsoft Defender](security-baseline-settings-defender-atp.md)  

- Verifique o status e monitore a [linha de base e o perfil](security-baselines-monitor.md)

