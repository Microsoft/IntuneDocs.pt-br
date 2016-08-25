---
title: "Gerenciar transferência de dados entre aplicativos iOS | Microsoft Intune"
description: "Use este tópico para entender como você pode usar o recurso Open in do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 488ecb801eac2b591db87683bbe9f371879483c4


---

# Gerenciar transferência de dados entre aplicativos iOS com Microsoft Intune
## Gerenciar aplicativos iOS
Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.  Você pode gerenciar aplicativos iOS das seguintes maneiras:

-   Evite a perda de dados da empresa configurando uma política MAM para aplicativos, que chamaremos de aplicativos **gerenciados por política** aplicativos.

-   Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.  Isso requer que os dispositivos sejam registrados na solução MDM. Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.  Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.
##  Usando MAM com aplicativos do iOS
Políticas MAM (gerenciamento de aplicativo móvel) podem ser usadas com o recurso iOS **Abrir em gerenciamento** para proteger os dados da empresa das seguintes maneiras:

-   **Dispositivos de propriedade do funcionário não gerenciados por qualquer solução de MDM:** você pode definir as configurações de política MAM para **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Quando o usuário final abrir um arquivo protegido em um aplicativo não gerenciado por política, o arquivo ficará ilegível.

-   **Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de MAM e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente. Para permitir a transferência de dados entre aplicativos com as políticas de MAM, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.   

-   **Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.
Para certificar-se de que os aplicativos implantados usando a solução do MDM de terceiros também sejam associados às políticas MAM configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting).  Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas MAM serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta de trabalho.

> [!IMPORTANT]
> A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.  Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.

## Definir configuração de UPN do usuário
Essa configuração é necessária para dispositivos gerenciados por uma solução MDM de terceiro. O procedimento descrito a seguir é um fluxo geral de como implementar a configuração de UPN e experiência do usuário final resultante:


1.  No portal do Azure, [configure uma política de gerenciamento de aplicativo móvel](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para a plataforma iOS. Defina as configurações de política conforme os requisitos da sua empresa e selecione os aplicativos que devem ter essa política.

2.  Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando a configuração descrita nas etapas 3 e 4.

3.  Implante o aplicativo com as seguintes configurações do aplicativo: key=IntuneMAMUPN, Value=<username@company.com> [exemplo: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implantar a política de Gerenciamento Aberto nos dispositivos registrados.

### Experiência do usuário final de exemplo

1.  O usuário final instala um aplicativo Microsoft Word no dispositivo.

2.  O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3.  O usuário final tenta abrir o documento do email nativo no Microsoft Word.

4.  Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.  Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas MAM ao usar o aplicativo do Word em um contexto pessoal.

5.  Quando o logon for bem-sucedido, as configurações da política de aplicativo são aplicadas ao aplicativo Word.

6.  Agora a transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo. Além disso, os dados são tratados em um contexto de trabalho e as configurações da política são aplicadas de acordo.

### Consulte também
[Proteger dados de aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->


