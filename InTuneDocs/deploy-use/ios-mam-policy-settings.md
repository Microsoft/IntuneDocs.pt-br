---
title: "Configurações de política MAM iOS | Microsoft Intune"
description: "Este tópico descreve as configurações de política de gerenciamento de aplicativo móvel para dispositivos iOS."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 126974152c638fc4bc69ef92b5fa79beeb0eed0c


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Configurações de política de gerenciamento de aplicativo móvel iOS
As configurações de política descritas neste tópico podem ser [configuradas](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para uma política de MAM (gerenciamento de aplicativo móvel) na folha **Configurações** no portal do Azure.

Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo *aplicativos gerenciados pela política* faz referência a aplicativos configurados com políticas de MAM.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

- **Evitar backups do iTunes e iCloud**: escolha **Sim** para desabilitar ou **Não** para permitir o backup de dados da empresa de aplicativos gerenciados por política.

  Valor padrão = **Sim**.

- **Permitir que o aplicativo transfira dados para outros aplicativos**: escolha uma das opções para indicar os aplicativos que podem receber dados de aplicativos gerenciados por política:
  - **Aplicativos gerenciados por política**: permitir a transferência somente para aplicativos com a política MAM.
  - **Todos os aplicativos**: permitir a transferência para qualquer aplicativo.
  - **Nenhum**: não permitir a transferência de dados para nenhum aplicativo, incluindo outros aplicativos gerenciados por política.

  Além disso, se você definir essa opção como **Aplicativos gerenciados pela política** ou **Nenhum**, o recurso do iOS 9 que permite que a Busca do Spotlight pesquise dados em aplicativos será bloqueado.

  >[!NOTE]
  >Essa configuração não controla o uso do recurso "Abrir em" nos dispositivos móveis. Para gerenciar o “Abrir em”, consulte [Gerenciar transferência de dados entre aplicativos iOS com Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Valor padrão = **Aplicativos gerenciados por política**.

- **Permitir que o aplicativo receba dados de outros aplicativos**: especificar aplicativos com permissão para transferir dados para os aplicativos gerenciados pela política:
  -  **Aplicativos gerenciados pela política**: permitir a transferência de dados somente de outros aplicativos gerenciados pela política.
  -  **Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo.
  -  **Nenhum**: não permitir a transferência de dados de nenhum aplicativo.

  Valor padrão = **Todos os aplicativos**.

- **Impedir Salvar como**: escolha **Sim** para desabilitar o uso da opção Salvar Como em qualquer aplicativo que use essa política. Escolha **Não** se quiser permitir o uso de Salvar Como.

  Valor padrão = **Sim**.

- **Restringir recortar, copiar e colar com outros aplicativos**: especifique quando recortar, copiar e colar operações deve ser restrito. Escolha:
  -   **Bloqueado**: não permite as operações recortar, copiar e colar entre aplicativos gerenciados por políticas.
  -   **Aplicativos gerenciados por política**: permite as ações de recortar, copiar e colar apenas entre aplicativos gerenciados pela política.
  -   **Aplicativos gerenciados pela política com colar em**: permite recortar ou copiar entre aplicativos gerenciados pela política. Permite que dados recortados ou copiados de qualquer aplicativo sejam colados neste aplicativo.
  - **Qualquer aplicativo**: não há restrições para ações de recortar, copiar e colar entre nenhum aplicativo.

  Valor padrão = **Aplicativos gerenciados pela política com colar em**.

- **Restringir conteúdo da web para exibir no Managed Browser**: quando essa configuração é habilitada, todos os links no aplicativo serão abertos no aplicativo Managed Browser.

  Para dispositivos que não estão registrados no Intune, os links da Web em aplicativos gerenciados pela política abrirão apenas no aplicativo Managed Browser.

  Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Valor padrão = **Sim**.

- **Criptografar dados do aplicativo:** para aplicativos associados a uma política de MAM do Intune, os dados são criptografados em repouso usando a criptografia no nível do dispositivo fornecida pelo SO. Quando um PIN for necessário, os dados serão criptografados segundo as configurações na política de MAM. Conforme indicado na documentação da Apple, [os módulos usados pelo iOS 7 têm a certificação FIPS 140-2](http://support.apple.com/en-us/HT202739).

  Nas configurações da política, você pode especificar valores de PIN de criptografia. Esses valores determinam quando os dados são criptografados. As opções são:
  -   **Quando o dispositivo estiver bloqueado**: todos os dados de aplicativo associados a essa política ficam criptografados enquanto o dispositivo está bloqueado.
  -   **Quando o dispositivo estiver bloqueado (exceto arquivos abertos)**: todos os dados de aplicativo associados a essa política ficam criptografados enquanto o dispositivo está bloqueado, exceto pelos dados nos arquivos que estão abertos no aplicativo.
  -   **Após a reinicialização do dispositivo**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo é reiniciado, até que o dispositivo seja desbloqueado pela primeira vez.
  -   **Usar configurações do dispositivo**: os dados do aplicativo são criptografados com base nas configurações padrão do dispositivo.
  Quando você habilita essa configuração, é obrigatório que o usuário configure e use um PIN para acessar o dispositivo.  Se não houver um PIN, os aplicativos não abrirão e o usuário será solicitado a definir um PIN com a mensagem: “Sua empresa exige que, para acessar este aplicativo, primeiro você deve habilitar um PIN de dispositivo.”

  Valor padrão = A opção de criptografia não está selecionada.
- **Desabilitar sincronização do contato**: escolha **Sim** para impedir que as informações de contato sincronizem com o aplicativo de catálogo de endereço nativo no dispositivo. Se você escolher **Não**, o aplicativo salvará as informações de contato no aplicativo de catálogo de endereço nativo no dispositivo.

  Ao fazer um apagamento seletivo para remover dados da empresa, contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.

  Valor padrão = **Sim**.

- **Desabilitar a impressão**: escolha **Sim** para evitar a impressão de dados da empresa dos aplicativos associados à política de MAM.

    Valor padrão = **Sim**.

##  <a name="access-settings"></a>Configurações de acesso

- **Solicitar PIN para acesso**: escolha **Sim** para exigir que um PIN use aplicativos gerenciados pela política. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo no contexto corporativo.

  Valor padrão = **Sim**.
    -  **Permitir PIN simples**: especifique se deseja permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Valor padrão = **Sim**.
    - **Comprimento do PIN**: especifique o número mínimo de dígitos em um PIN. Valor padrão = **4**.
    - **Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas de entrada de PIN que podem ser feitas antes que o usuário precise redefinir o PIN. Não há valor padrão para esta configuração.

- **Exigir a impressão digital em vez de PIN (iOS 8.0 +):** escolha **Sim** para exigir uma identidade de impressão digital, em vez de um PIN, para acesso ao aplicativo.
Em dispositivos iOS, você pode permitir que o usuário se identifique usando a impressão digital em dispositivos iOS, em vez de um PIN. Quando o usuário tenta acessar o aplicativo usando sua conta corporativa, é solicitado que ele forneça a identidade de impressão digital em vez de inserir um PIN.

  Valor padrão = **Sim**.
- **Exigir credenciais corporativas para acesso**: escolha **Sim** para exigir credenciais corporativas, em vez de um PIN, para acesso ao aplicativo. Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque. O usuário deverá fornecer suas credenciais corporativas.

  Valor padrão = **Não**.
- **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou com raiz**: escolha **Sim** para bloquear a execução de aplicativos em dispositivos com jailbreak ou com raiz. O usuário continuará a ser capaz de usar os aplicativos para tarefas pessoais, mas terá que usar um dispositivo diferente para o trabalho.

  Valor padrão = **Sim**.
- **Verificar novamente os requisitos de acesso após (minutos)**
  -   **Tempo limite**: especifique o tempo (em minutos) antes que os requisitos de acesso ao aplicativo sejam verificados novamente.
  -   **Período de carência offline**: se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.

  Valor padrão = tempo limite de **30** minutos e período de carência offline de **720** minutos.
- **Intervalo offline antes do apagamento dos dados do aplicativo (dias)**: você pode optar por apagar os dados da empresa se um dispositivo ficar offline por um determinado período. Especifique o número de dias que um dispositivo pode ficar offline antes que os dados da empresa sejam removidos do dispositivo.

  >[!TIP]
  >Inserir um valor de **0** desativa essa configuração.

  Valor padrão = **90** dias.



<!--HONumber=Dec16_HO2-->


