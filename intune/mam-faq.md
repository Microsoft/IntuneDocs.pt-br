---
title: Perguntas frequentes sobre o MAM e a proteção do aplicativo
description: Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ab616c373482109ccd402199f7b0de69fe27348
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Perguntas frequentes sobre o MAM e a proteção do aplicativo

Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune.

## <a name="mam-basics"></a>Noções básicas sobre o MAM


**O que é o MAM?** [Gerenciamento de aplicativo móvel do Intune](/intune/app-lifecycle) refere-se ao pacote de recursos de gerenciamento do Intune que permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para os usuários.

**Quais são os benefícios da proteção do aplicativo do MAM?** O MAM protege os dados de uma organização em um aplicativo. Com o MAM sem registro (MAM-WE), um aplicativo relacionado ao trabalho ou à escola que contém dados confidenciais pode ser gerenciado em quase todos os dispositivos, incluindo dispositivos pessoais em cenários de BYOD (traga seu próprio dispositivo). Vários aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo Intune MAM. Consulte a lista oficial de [aplicativos gerenciados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais configurações de dispositivo têm suporte no MAM?** O Intune MAM dá suporte a duas configurações:
- **Intune MDM + MAM**: os administradores de TI apenas podem gerenciar aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel). Para gerenciar aplicativos usando o MDM + MAM, os clientes devem usar o console do Intune no portal do Azure em https://portal.azure.com.

- **MAM sem registro de dispositivo**: o MAM sem registro de dispositivo, ou MAM-WE, permite que os administradores de TI gerenciem aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos não registrados no Intune MDM. Isso significa que os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados em provedores de EMM de terceiros. Para gerenciar aplicativos usando o MAM-WE, os clientes devem usar o console do Intune no portal do Azure em http://portal.azure.com. Além disso, os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados com provedores de Gerenciamento de Mobilidade Empresarial (EMM) de terceiros ou não registrados com um MDM.


## <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

**O que são políticas de proteção do aplicativo**? Políticas de proteção do aplicativo são regras que garantem que os dados de uma organização permanecem seguros ou contidos em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados “corporativos” ou um conjunto de ações proibidas ou monitoradas quando o usuário está no aplicativo.

**Quais são exemplos de políticas de proteção do aplicativo?** Consulte [Android app protection policy settings](app-protection-policy-settings-android.md) (Configurações da política de proteção de aplicativo Android) e [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Configurações da política de proteção de aplicativo iOS) para obter informações detalhadas sobre cada configuração da política de proteção do aplicativo.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplicativos que podem ser gerenciados com políticas de proteção do aplicativo

**Quais aplicativos podem ser gerenciados por políticas de proteção do aplicativo?** Qualquer aplicativo que tenha sido integrado com o [SDK do Aplicativo do Intune](/intune/app-sdk) ou encapsulado pela [Ferramenta de Disposição do Aplicativo do Intune](/intune/apps-prepare-mobile-application-management) pode ser gerenciado por políticas de proteção do aplicativo do Intune. Consulte a lista oficial de [aplicativos gerenciados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais são os requisitos de linha de base para usar políticas de proteção do aplicativo em um aplicativo gerenciado pelo Intune?**
- O usuário final deve ter uma conta do AAD (Azure Active Directory). Consulte [Adicionar usuários e conceder permissão administrativa para o Intune](/intune/users-permissions-add) para saber como criar usuários do Intune no Azure Active Directory.

- O usuário final deve ter uma licença do Microsoft Intune atribuída à sua conta do Azure Active Directory. Confira [Gerenciar licenças do Intune](/intune/licenses-assign) para saber como atribuir licenças do Intune aos usuários finais.

- O usuário final deve pertencer a um grupo de segurança destinado a uma política de proteção do aplicativo. A mesma política de proteção do aplicativo deve ter como destino o aplicativo específico utilizado. Políticas de proteção do aplicativo podem ser criadas e implantadas no console do Intune no [portal do Azure](http://portal.azure.com). No momento, grupos de segurança podem ser criados no [portal do Office](http://portal.office.com).

- O usuário final deve se conectar ao aplicativo usando sua conta do AAD.

**Quais são os requisitos adicionais para usar o [aplicativo móvel do Outlook](https://products.office.com/outlook)?**

- O usuário final deve ter o aplicativo móvel do Outlook instalado em seu dispositivo.

- O usuário final deve ter uma caixa de correio do [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) e uma licença vinculada à sua conta do Azure Active Directory.

  >[!NOTE]
  > No momento, o aplicativo móvel do Outlook dá suporte apenas ao Microsoft Exchange Online e não dá suporte ao Exchange no Local nem ao Exchange no Office 365 Dedicated.

**Quais são os requisitos adicionais para usar os [aplicativos Word, Excel e PowerPoint](https://products.office.com/business/office)?**

- O usuário final deve ter uma licença do [Office 365 Business ou Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) vinculada à sua conta do Azure Active Directory. A assinatura deve incluir os aplicativos do Office em dispositivos móveis e pode incluir uma conta de armazenamento em nuvem com o [OneDrive for Business](https://onedrive.live.com/about/business/). As licenças do Office 365 podem ser atribuídas no [portal do Office](http://portal.office.com) seguindo estas [instruções](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- O usuário final deve configurar um local gerenciado usando o salvamento granular como funcionalidade, na configuração "Impedir Salvar como" da política de proteção do aplicativo. Por exemplo, se o local gerenciado for o OneDrive, será necessário configurar o aplicativo [OneDrive](https://onedrive.live.com/about/) no aplicativo Word, Excel ou PowerPoint do usuário final.

- Se o local gerenciado for o OneDrive, será necessário direcionar o aplicativo de acordo com a política de proteção do aplicativo implantada para o usuário final.

  >[!NOTE]
  > No momento, os aplicativos móveis do Office dão suporte apenas ao SharePoint Online e não ao SharePoint local.

**Por que o local gerenciado (ou seja, o OneDrive) é necessário para o Office?** O Intune marca todos os dados no aplicativo como “corporativos” ou “pessoais”. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas).

**Quais são os requisitos adicionais para usar o Skype for Business?** Consulte os requisitos de licença do [Skype for Business](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > No momento, o aplicativo móvel Skype for Business dá suporte apenas ao Skype for Business Online.

## <a name="app-protection-features"></a>Recursos de proteção do aplicativo

**O que é o suporte a várias identidades?** Suporte a várias identidades é a capacidade do SDK do Aplicativo do Intune de aplicar políticas de proteção do aplicativo apenas à conta corporativa ou de estudante conectada ao aplicativo. Se uma conta pessoal estiver conectada ao aplicativo, os dados permanecerão inalterados.

**Qual é a finalidade do suporte a várias identidades?** O suporte a várias identidades permite que aplicativos com público "corporativo" e de consumidor (ou seja, os aplicativos do Office) sejam liberados publicamente com as funcionalidades de proteção do aplicativo do Intune para as contas "corporativas".

**E o Outlook e as várias identidades?** Como o Outlook tem uma exibição de email combinada de emails pessoal e “corporativo”, o aplicativo Outlook solicita o PIN do Intune na inicialização.

**O que é o PIN do aplicativo do Intune?** O PIN (Número de Identificação Pessoal) é uma senha usada para verificar se o usuário correto está acessando os dados da organização em um aplicativo.

- **Quando o usuário deverá inserir seu PIN?** O Intune solicitará o PIN do aplicativo do usuário quando o usuário estiver prestes a acessar dados "corporativos". Em aplicativos de várias identidades, como o Word/Excel/PowerPoint, o usuário é solicitado a inserir seu PIN ao tentar abrir um arquivo ou documento “corporativo”. Em aplicativos de identidade única, como aplicativos de linha de negócios gerenciados com a Ferramenta de Disposição do Aplicativo do Intune, o PIN é solicitado na inicialização, pois o SDK do Aplicativo do Intune sabe que a experiência do usuário no aplicativo é sempre "corporativa".

- **Com que frequência o PIN do Intune será solicitado ao usuário?**
  O administrador de TI pode definir a política de proteção do aplicativo Intune configurando "Verificar novamente os requisitos de acesso após (minutos)" no console de administrador do Intune. Essa configuração especifica a quantidade de tempo até os requisitos de acesso serem verificados no dispositivo e a tela PIN do aplicativo ser exibida novamente. No entanto, detalhes importantes sobre o PIN que afetam a frequência com que o usuário será consultado são: 

    - **O PIN é compartilhado entre aplicativos do mesmo editor para aumentar a usabilidade:** no iOS, um PIN de aplicativo é compartilhado entre todos os aplicativos **do mesmo editor**. No Android, o PIN de um aplicativo é compartilhado com todos os aplicativos.
    - **A natureza constante do temporizador com o PIN:** uma vez que um PIN é inserido para acessar um aplicativo (aplicativo A) e o aplicativo deixa o segundo plano (foco de entrada principal) no dispositivo, o temporizador do PIN é redefinido para esse PIN. Qualquer aplicativo (aplicativo B) que compartilhe esse PIN não solicitará ao usuário para inserir o PIN porque o temporizador foi redefinido. A solicitação será exibida novamente quando o valor "Verificar novamente os requisitos de acesso após (minutos)" for atendido novamente. 

      >[!NOTE] 
      > Para verificar os requisitos de acesso do usuário com mais frequência (ou seja, solicitação do PIN), especialmente para um aplicativo usado com frequência, é recomendável reduzir o valor da configuração "Verificar novamente os requisitos de acesso após (minutos)". 

- **O PIN é seguro?** O PIN serve para permitir que somente o usuário correto acesse os dados de sua organização no aplicativo. Portanto, um usuário final deve entrar com sua conta corporativa ou de estudante antes de definir ou redefinir o PIN do aplicativo do Intune. Essa autenticação é manipulada pelo Azure Active Directory por meio da troca de tokens seguros e não é transparente para o SDK do Aplicativo do Intune. Sob a perspectiva de segurança, a melhor maneira de proteger dados corporativos ou de estudante é criptografá-los. A criptografia não está relacionada ao PIN do aplicativo, mas é sua própria política de proteção do aplicativo.

- **Como o Intune protege o PIN contra ataques de força bruta?** Como parte da política de PIN do aplicativo, o administrador de TI pode definir o número máximo de vezes que um usuário pode tentar autenticar seu PIN antes do bloqueio do aplicativo. Depois que o número de tentativas for atingido, o SDK do Aplicativo do Intune poderá apagar os dados “corporativos” no aplicativo.
  
- **Por que é necessário definir um PIN duas vezes em aplicativos do mesmo editor?**
  Atualmente, o MAM (no iOS) permite o PIN no nível de aplicativo com caracteres alfanuméricos e especiais (chamados de ''senha''), que exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser, Yammer) a fim de integrar o SDK do Aplicativo Intune para iOS. Sem isso, as configurações de senha não são aplicadas corretamente nos aplicativos de destino. Esse era um recurso lançado no SDK do Intune para iOS v. 7.1.12. <br><br> Para dar suporte a esse recurso e garantir a compatibilidade com versões anteriores do SDK do Intune para iOS, todos os PINs (numéricos ou de senha) na versão 7.1.12+ são tratados separadamente do PIN numérico das versões anteriores do SDK. Portanto, se um dispositivo tiver aplicativos com o SDK do Intune para versões do iOS anteriores a 7.1.12 E posteriores a 7.1.12 do mesmo editor, será necessário configurar dois PINs. <br><br> Dito isso, os dois PINs (para cada aplicativo) não estão relacionados de alguma forma, ou seja, devem aderir à política de proteção do aplicativo aplicada ao aplicativo. Como tal, *somente* se os aplicativos A e B tiverem as mesmas políticas aplicadas (com relação ao PIN), o usuário poderá configurar o mesmo PIN duas vezes. <br><br> Esse comportamento é específico ao PIN em aplicativos do iOS habilitados com o Gerenciamento de Aplicativo Móvel do Intune. Ao longo do tempo, à medida que os aplicativos adotam versões posteriores do SDK do Intune para iOS, a necessidade de definir um PIN duas vezes em aplicativos do mesmo editor se torna um problema menos significativo. Consulte a observação abaixo para obter um exemplo.

  >[!NOTE]
  > Por exemplo, se o aplicativo A for compilado com uma versão anterior à 7.1.12, e o aplicativo B for compilado com uma versão superior ou igual à 7.1.12 do mesmo editor, o usuário final precisará configurar PINs separadamente para A e B, se ambos forem instalados em um dispositivo iOS. <br><br> Se um aplicativo C que tenha o SDK versão 7.1.9 estiver instalado no dispositivo, ele compartilhará o mesmo PIN que o aplicativo A. <br><br> Um aplicativo D compilado com 7.1.14 compartilhará o mesmo PIN que o aplicativo B. <br><br> Se apenas os aplicativos A e C estiverem instalados em um dispositivo, será necessário definir um PIN. O mesmo se aplica se apenas os aplicativos B e D estiverem instalados em um dispositivo.

**E a criptografia?** Os administradores de TI podem implantar uma política de proteção do aplicativo que exige a criptografia dos dados do aplicativo. Como parte da política, o administrador de TI também pode especificar quando o conteúdo é criptografado.

- **Como o Intune criptografa os dados?** Consulte [Android app protection policy settings (Configurações da política de proteção do aplicativo Android)](app-protection-policy-settings-android.md) e [iOS app protection policy settings (Configurações da política de proteção do aplicativo iOS)](app-protection-policy-settings-ios.md) para obter informações detalhadas sobre a configuração da política de proteção do aplicativo para criptografia.

- **O que é criptografado?** Somente os dados marcados como “corporativos” são criptografados, de acordo com a política de proteção do aplicativo do administrador de TI. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas). Para aplicativos de linha de negócios gerenciados pela Ferramenta de Disposição do Aplicativo do Intune, todos os dados do aplicativo são considerados "corporativos".

**Como o Intune apaga os dados remotamente?** O Intune pode apagar os dados do aplicativo de três maneiras diferentes: apagamento completo do dispositivo, apagamento seletivo para MDM e apagamento seletivo de MAM. Para saber mais sobre o apagamento remoto para o MDM, confira [Remover dispositivos usando a redefinição de fábrica ou remover dados da empresa ](devices-wipe.md#factory-reset). Para saber mais sobre o apagamento seletivo usando o MAM, confira [Remover dados da empresa](devices-wipe.md#remove-company-data) e [Como apagar apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

- **O que é redefinição de fábrica?** A [redefinição de fábrica](devices-wipe.md) remove todos os dados e configurações do usuário **do dispositivo** restaurando o dispositivo para as configurações padrão de fábrica. O dispositivo é removido do Intune.
  >[!NOTE]
  > A redefinição de fábrica pode ser realizada apenas em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel).

- **O que é o apagamento seletivo para MDM?** Confira [Remover dispositivos - Remover dados da empresa](devices-wipe.md#remove-company-data) para ler sobre a remoção de dados da empresa.

- **O que é o apagamento seletivo para MAM?** O apagamento seletivo para MAM simplesmente remove dados de aplicativo da empresa de um aplicativo. A solicitação é iniciada usando o portal do Azure no Intune. Para saber como iniciar uma solicitação de apagamento, confira [Como remover apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

- **Com que rapidez o apagamento seletivo para MAM ocorre?** Se o usuário estiver usando o aplicativo quando o apagamento seletivo for iniciado, o SDK do Aplicativo do Intune verificará a cada 30 minutos uma solicitação de apagamento seletivo do serviço Intune MAM. Ele também verifica o apagamento seletivo quando o usuário inicia o aplicativo pela primeira vez e se conecta com sua conta corporativa ou de estudante.

**Por que os serviços Locais não funcionam com os aplicativos protegidos do Intune?** A proteção do aplicativo do Intune depende da consistência da identidade do usuário entre o aplicativo e o SDK do Aplicativo do Intune. A única maneira de assegurar isso é por meio da autenticação moderna. Existem cenários nos quais os aplicativos podem funcionar com uma configuração local, mas eles não são consistentes nem têm garantia.

**Existe uma maneira segura de abrir links da Web em aplicativos gerenciados?** Sim. O administrador de TI pode implantar e definir uma política de proteção do aplicativo para o [aplicativo Intune Managed Browser](app-configuration-managed-browser.md), um navegador da Web desenvolvido pelo Microsoft Intune que pode ser gerenciado facilmente com o Intune. O administrador de TI pode exigir que todos os links da Web em aplicativos gerenciados pelo Intune sejam abertos usando o aplicativo Managed Browser.

## <a name="app-experience-on-android"></a>Experiência do aplicativo no Android

**Por que o aplicativo Portal da Empresa é necessário para o funcionamento da proteção do aplicativo do Intune em dispositivos Android?** Grande parte da funcionalidade de proteção do aplicativo é interna ao aplicativo Portal da Empresa. O registro de dispositivo _não é necessário_, embora o aplicativo Portal da Empresa seja sempre obrigatório. Para o MAM-WE, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

**Como várias configurações de acesso de Proteção de Aplicativo do Intune definidas no mesmo conjunto de aplicativos e usuários funcionam no Android?** As políticas de Proteção de Aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos do usuário final à medida que eles tentarem acessar um aplicativo de destino da sua conta corporativa. Em geral, um bloqueio teria precedência e, em seguida, um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de versão de patch mínima do Android que avisa o usuário para fazer uma atualização de patch, que será aplicada após a configuração da versão de patch mínima do Android que bloqueia o acesso do usuário. Portanto, o cenário em que o administrador de TI configura a versão de patch de Android mínima 2018-03-01 e a versão de patch de Android mínima (somente Aviso) 2018-02-01, enquanto o dispositivo tentar acessar o aplicativo estava em uma versão de patch 2018-01-01, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de patch de Android mínima que resulta em acesso bloqueado. 

Ao lidar com diferentes tipos de configurações, um requisito de versão do aplicativo teria precedência, seguido por um requisito de versão do sistema operacional de versão de patch do Android. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados.

## <a name="app-experience-on-ios"></a>Experiência do aplicativo no iOS

**Consigo usar a extensão de compartilhamento do iOS para abrir dados corporativos ou de estudante em aplicativos não gerenciados, mesmo com a política de transferência de dados definida como “apenas aplicativos gerenciados” ou “nenhum aplicativo”. Isso não causa a perda de dados?** A política de proteção do aplicativo do Intune não pode controlar a extensão de compartilhamento do iOS sem gerenciar o dispositivo. Portanto, o _**Intune criptografa os dados “corporativos” antes que eles sejam compartilhados fora do aplicativo**_. É possível validar isso ao tentar abrir o arquivo “corporativo” fora do aplicativo gerenciado. O arquivo deve ser criptografado e não pode ser aberto fora do aplicativo gerenciado.

**Como várias configurações de acesso de Proteção de Aplicativo do Intune definidas no mesmo conjunto de aplicativos e usuários funcionam no iOS?** As políticas de Proteção de Aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos do usuário final à medida que eles tentarem acessar um aplicativo de destino da sua conta corporativa. Em geral, um apagamento teria precedência, seguido por um bloqueio e então um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de sistema operacional mínima do iOS que avisa o usuário para atualizar a versão de iOS, que será aplicada após a configuração de sistema operacional mínima do iOS que bloqueia o acesso do usuário. Portanto, no cenário em que o administrador de TI configura a versão de sistema operacional iOS mínima para 11.0.0.0 e do sistema operacional iOS mínima para 11.1.0.0, enquanto o dispositivo que tenta acessar o aplicativo estava em uma versão de iOS 10, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de sistema operacional iOS mínima que resulta em acesso bloqueado.

Ao lidar com diferentes tipos de configurações, um requisito de versão do SDK do Aplicativo Intune teria precedência, depois um requisito de versão do aplicativo, seguido pelo requisito de versão do sistema operacional iOS. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados. É recomendável que o requisito de versão do SDK do Aplicativo Intune seja configurado somente após a orientação da equipe de produto do Intune para cenários de bloqueio essenciais.

## <a name="see-also"></a>Consulte também
- [Implementar seu plano do Intune](planning-guide-onboarding.md)
- [Teste e validação do Intune](planning-guide-test-validation.md)
- [Configurações de política de gerenciamento de aplicativo móvel do Android no Microsoft Intune](app-protection-policy-settings-android.md)
- [Configurações de política de gerenciamento de aplicativo móvel iOS](app-protection-policy-settings-ios.md)
- [Validar políticas de proteção do aplicativo](app-protection-policies-validate.md)
- [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md)
- [Como obter suporte para o Microsoft Intune](get-support.md)
