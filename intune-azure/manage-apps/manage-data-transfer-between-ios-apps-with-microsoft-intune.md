---
title: "Gerenciar a transferência de dados entre aplicativos iOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: use este tópico para entender como você pode usar o recurso Open in do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Como gerenciar a transferência de dados entre aplicativos iOS 
## <a name="manage-ios-apps"></a>Gerenciar aplicativos iOS
Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.  Você pode gerenciar aplicativos iOS das seguintes maneiras:

-   Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos.

-   Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.  Isso requer que os dispositivos sejam registrados na solução MDM. Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.  Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.
##  <a name="using-app-protection-with-ios-apps"></a>Usando a proteção do aplicativo com aplicativos iOS
Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:

-   **Dispositivos de propriedade do funcionário não gerenciados por nenhuma solução de MDM:** você pode definir as configurações de política de proteção de aplicativo para **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Quando o usuário final abrir um arquivo protegido em um aplicativo não gerenciado por política, o arquivo ficará ilegível.

-   **Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente. Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.   

-   **Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.
Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting).  Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.

> [!IMPORTANT]
> A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.  Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.

## <a name="configure-user-upn-setting"></a>Definir configuração de UPN do usuário
Essa configuração é necessária para dispositivos gerenciados por uma solução MDM de terceiro. O procedimento descrito a seguir é um fluxo geral de como implementar a configuração de UPN e experiência do usuário final resultante:


1.  No portal do Azure, [configure uma política de gerenciamento de aplicativo móvel](app-protection-policies.md) para a plataforma iOS. Defina as configurações de política conforme os requisitos da sua empresa e selecione os aplicativos que devem ter essa política.

2.  Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando a configuração descrita nas etapas 3 e 4.

3.  Implante o aplicativo com as seguintes configurações do aplicativo: key=IntuneMAMUPN, Value=<username@company.com> [exemplo: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implantar a política de Gerenciamento Aberto nos dispositivos registrados.

### <a name="example-end-user-experience"></a>Experiência do usuário final de exemplo

1.  O usuário final instala um aplicativo Microsoft Word no dispositivo.

2.  O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3.  O usuário final tenta abrir o documento do email nativo no Microsoft Word.

4.  Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.  Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.

5.  Quando o logon for bem-sucedido, as configurações da política de aplicativo são aplicadas ao aplicativo Word.

6.  Agora a transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo. Além disso, os dados são tratados em um contexto de trabalho e as configurações da política são aplicadas de acordo.

### <a name="see-also"></a>Consulte também
[O que é a política de proteção de aplicativo do Intune](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


