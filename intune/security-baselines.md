---
title: Usar linhas de base de segurança no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou defina as configurações de segurança de grupo recomendadas para proteger usuário e dados em dispositivos usando o Microsoft Intune para gerenciamento de dispositivos móveis. Habilite o BitLocker, configure a Proteção Avançada contra Ameaças do Microsoft Defender, controle o Internet Explorer, use a Smart Screen, defina políticas de segurança local, exija uma senha, bloqueie downloads da Internet e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bb1ddcadcac1ec9b4730a5dcd66abca111d80196
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251211"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Criar uma linha de base de segurança do Windows 10 no Intune

Linhas de base de segurança é um recurso em versão prévia e disponível para dispositivos com Windows 10 e posterior. Esse recurso inclui várias configurações compatíveis com o Intune e que você pode usar para ajudar a proteger e os seus usuários e dispositivos. Ele também define automaticamente essas configurações para os valores recomendados por equipes de segurança. Por exemplo, a linha de base habilita automaticamente o BitLocker, exige automaticamente uma senha para desbloquear um dispositivo, desabilita automaticamente a autenticação básica e muito mais.

Esse recurso aplica-se a:

- Windows 10 versão 1809 e posterior

> [!NOTE]
> Enquanto as linhas de base de segurança estão em versão prévia, a Microsoft não recomendada o uso de perfis em um ambiente de produção porque as linhas de base podem ser alteradas durante a versão prévia. Quando as linhas de base de segurança estão disponíveis ao público em geral, os perfis existentes não serão convertidos para os perfis compatíveis mais recentes.

O objetivo de usar linhas de base de segurança é fornecer um fluxo de trabalho seguro de ponta a ponta ao trabalhar com o Microsoft 365. Alguns do benefícios incluem:

- Uma linha de base de segurança inclui as melhores práticas e recomendações de configurações que afetam a segurança. O Intune tem uma parceria com a mesma equipe de segurança do Windows que cria linhas de base de segurança de política grupo. Essas recomendações tem base em orientações e numa ampla experiência.
- Se você for um usuário totalmente novo do Intune e não souber onde começar, as linhas de base de segurança oferecem uma vantagem. Você pode criar e implantar rapidamente um perfil de seguro, sabendo que está ajudando a proteger os recursos e dados da sua organização.
- Se você estiver usando a politica de grupo, a migração para o Intune para gerenciamento é muito mais fácil com essas linhas de base. Essas linhas de base são criadas nativamente no Intune e incluem uma experiência de gerenciamento moderna.

Linhas de base de segurança criam um "perfil de configuração" no Intune. Esse perfil inclui todas as configurações na linha de base. Você aplica ou atribui esse perfil aos seus usuários, grupos e dispositivos.

Após a atribuição do perfil, você pode monitorar o perfil e monitorar a linha de base. Por exemplo, você pode ver quais dispositivos correspondem à linha de base ou não.

Este artigo pode ajudar a usar linhas de base de segurança para criar, atribuir e monitorar um perfil.

[Linhas de base de segurança do Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) é uma excelente fonte para saber mais sobre esse recurso. [Gerenciamento de dispositivo móvel](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) é uma excelente fonte sobre MDM, e o que você pode fazer em dispositivos com Windows.

## <a name="available-security-baselines"></a>Escopos de segurança disponíveis  

As linhas de base de segurança a seguir estão disponíveis para uso com o Intune.
- **Versão prévia: Linha de base de segurança do MDM para outubro de 2018**  
  [Exibir as configurações](security-baseline-settings-windows.md)

- **VERSÃO PRÉVIA: linha de base da ATP do Windows Defender**  
  [Exibir as configurações](security-baseline-settings-defender-atp.md)  
  *(Esta linha de base está disponível quando seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](advanced-threat-protection.md#prerequisites))* .


## <a name="prerequisites"></a>Pré-requisitos
Para gerenciar linhas de base no Intune, sua conta deve ter a função interna [Gerenciador de Perfis e de Política](role-based-access-control.md#built-in-roles).


## <a name="co-managed-devices"></a>Dispositivos cogerenciado

Linhas de base de segurança em dispositivos gerenciados pelo Intune são semelhantes aos dispositivos cogerenciados com o Configuration Manager. Dispositivos cogerenciados usam o System Center Configuration Manager e o Microsoft Intune para gerenciar dispositivos com Windows 10 simultaneamente. Isso permite que você anexe à nuvem seu investimento existente do Configuration Manager para obter os benefícios do Intune. [Visão geral do cogerenciamento](https://docs.microsoft.com/sccm/comanage/overview) é um excelente recurso se você usa o Configuration Manager e também deseja os benefícios da nuvem.

Ao usar dispositivos cogerenciados, você deve alternar a carga de trabalho **Configuração do dispositivo** (suas configurações) para o Intune. [Cargas de trabalho de configuração de dispositivo](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) fornece mais informações.

## <a name="create-the-profile"></a>Criar o perfil

1. Faça login no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecione **Segurança do Dispositivo** > **Linhas de base de segurança (versão prévia)** . Uma lista com as linhas de base disponíveis está disponível. 

    ![Selecione uma linha de base de segurança para configurar](./media/security-baselines/available-baselines.png)

   >[!TIP]  
   > A linha de base do Windows Defender ATP está disponível quando seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](advanced-threat-protection.md#prerequisites).
2. Selecione a linha de base que você quer usar e selecione **Criar perfil**.  

3. Na guia **Básico**, especifique as seguintes propriedades:

    - **Nome**: Insira um nome para seu perfil de linhas de base de segurança. Por exemplo, digite *Perfil padrão para ATP do Defender*
    - **Descrição**: Insira algum texto que descreva a função dessa linha de base. A descrição serve para você inserir qualquer texto que quiser. É opcional, mas definitivamente recomendado.

4. Selecione a guia **Configuração** para exibir os grupos de **Configurações** disponíveis nessa linha de base. Selecione um grupo para expandi-lo e exibir as configurações individuais que ele contém. As configurações possuem definições padrão para a linha de base de segurança. Redefina as configurações padrões para atender às suas necessidades de negócios.  

    ![Expanda um grupo para exibir as configurações dele](./media/security-baselines/sample-list-of-settings.png)

5. Selecione a guia **Atribuições** para atribuir a linha de base aos grupos. Atribua a linha de base a um grupo existente ou crie um novo grupo usando o processo padrão no console do Intune para concluir a configuração.  

   ![Atribuir um perfil](./media/security-baselines/assignments.png)
  
6. Quando estiver pronto para implantar a linha de base, selecione a guia **Revisar + Criar** para examinar os detalhes da linha de base. Depois, selecione **Salvar perfil** para salvar e implantar o perfil. 

   ![Revisar a linha de base](./media/security-baselines/review.png) 

   Assim que você salvar, o perfil será enviado por push para dispositivos ao fazer o check-in no Intune. Portanto, isso pode ocorrer imediatamente.

   > [!TIP]  
   > É possível salvar um perfil sem atribuí-lo a grupos primeiro. Você pode editar o perfil posteriormente para adicionar grupos. 

7. Depois de criar o perfil, você pode editá-lo acessando **Segurança do Dispositivo** > **Linhas de Base de Segurança**, em seguida, selecione a linha de base que você configurou e selecione **Perfis**.  Selecione o perfil e **Propriedades** para editar as configurações. Depois, selecione **Atribuições** para editar os grupos que recebem essa linha de base. 

## <a name="q--a"></a>Perguntas e Respostas

#### <a name="why-these-settings"></a>Por que essas configurações?

A equipe de segurança da Microsoft tem anos de experiência trabalhando diretamente com os desenvolvedores do Windows e com a comunidade de segurança para criar essas recomendações. As configurações nessa linha de base são consideradas as opções de configuração de segurança mais relevantes. Em cada novo build do Windows, a equipe ajusta suas recomendações com base em recursos lançados recentemente.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Há alguma diferença nas recomendações para linhas de base de segurança de Windows para política de grupo versus Intune?

A mesma equipe de segurança da Microsoft escolheu e organizou as configurações para cada linha de base. O Intune inclui todas as configurações relevantes na linha de base de segurança do Intune. Há algumas configurações na linha de base de política de grupo que são específicas a um controlador de domínio local. Essas configurações são excluídas das recomendações do Intune. Todas as outras configurações são iguais.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>As linhas de base de segurança do Intune são compatíveis com CIS ou NSIT?

Estritamente falando, não. A equipe de segurança da Microsoft consulta organizações, como a CIS, para compilar suas recomendações. Porém, não existe um mapeamento individual entre "compatível com CIS" e as linhas de base da Microsoft.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Quais certificações as linhas de base de segurança da Microsoft têm? 

- A Microsoft continua a publicar linhas de base de segurança para políticas de grupo (GPOs) e o [Kit de Ferramentas de Conformidade de Segurança](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), como faz há muitos anos. Essas linhas de base são usadas por muitas organizações. As recomendações nessas linhas de base são provenientes do envolvimento da equipe de segurança da Microsoft com clientes corporativos e órgãos externos, incluindo o Departamento de Defesa (DoD), Instituto Nacional de Padrões e Tecnologia (NIST) e muito mais. Compartilhamos nossas recomendações e linhas de base com essas organizações. Essas organizações também têm suas próprias recomendações que refletem com maior exatidão as recomendações da Microsoft. À medida que o MDM (gerenciamento de dispositivo móvel) continua a evoluir para a nuvem, a Microsoft criou recomendações de MDM equivalentes dessas linhas de base de política de grupo. Essas linhas de base adicionais são incorporadas ao Microsoft Intune e incluem relatórios de conformidade sobre usuários, grupos e dispositivos que seguem (ou não) a linha de base.

- Muitos clientes estão usando as recomendações de linha de base do Intune como um ponto de partida e, em seguida, personalizando-as para atender às demandas de TI e de segurança. A **Linha de Base de Segurança de MDM** do Windows 10 RS5 da Microsoft é a primeira linha de base lançada. Esta linha de base é compilada como uma infraestrutura genérica que permite aos clientes importar eventualmente outras linhas de base de segurança com base no CIS, NIST e outros padrões. Atualmente, ela está disponível para Windows e, eventualmente, incluirá o iOS e Android.

- A migração de políticas locais de grupo do Active Directory para uma solução de nuvem pura usando o Azure Active Directory (AD) com o Microsoft Intune é uma jornada. Para ajudar, há GPOs complementares publicados para AD híbrido e dispositivos ingressados no Azure AD. Esses dispositivos podem obter as configurações de MDM da nuvem (Intune) e configurações de política de grupo de controladores de domínio locais conforme necessário.

## <a name="next-steps"></a>Próximas etapas
- Exiba as [configurações de linha de base de segurança do Windows](security-baseline-settings-windows.md) compatíveis com o Intune.  
- Verifique o status e monitore a [linha de base e o perfil](security-baselines-monitor.md).
