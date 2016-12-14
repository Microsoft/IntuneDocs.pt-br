---
title: "Configurações de política de MAM do Android | Microsoft Intune"
description: "Este tópico descreve as configurações de política de gerenciamento de aplicativo móvel para dispositivos Android."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d0a1a2b3f4e5dbac8b333db3a5cc4bb32c0d61ef


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Configurações de política de gerenciamento de aplicativo móvel de Android no Microsoft Intune
As configurações de política descritas neste tópico podem ser [configuradas](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para uma política de MAM (gerenciamento de aplicativo móvel) na folha **Configurações** no portal do Azure.
Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo *aplicativos gerenciados pela política* faz referência a aplicativos configurados com políticas de MAM.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

- **Evitar backups do Android:** escolha **Sim** para desabilitar ou **Não** para habilitar o backup dos dados da empresa de aplicativos gerenciados pela política.

  Valor padrão = **Sim**
- **Permitir que o aplicativo transfira dados para outros aplicativos**: escolha uma das opções para indicar quais tipos de aplicativos podem receber dados da empresa de aplicativos gerenciados por política:
  -   **Aplicativos gerenciados por política**: habilita a transferência para aplicativos com a política MAM.
  -   **Todos os aplicativos**: habilita a transferência para qualquer aplicativo.
  -   **Nenhum**: não permite a transferência de dados para nenhum aplicativo.

 Valor padrão = **Aplicativos gerenciados por política**.
- **Permitir que o aplicativo receba dados de outros aplicativos**: especifique quais aplicativos podem transferir dados para os aplicativos gerenciados por política:
  -   **Aplicativos gerenciados por política**: habilita transferências de dados somente de outros aplicativos gerenciados por política.
  -   **Todos os aplicativos**: habilita a transferência de dados de qualquer aplicativo.
  -   **Nenhum**: não permite a transferência de dados de nenhum aplicativo.

  Valor padrão = **Todos os aplicativos**

-   **Impedir Salvar como**: escolha **Sim** para desabilitar o uso da opção Salvar Como em qualquer aplicativo que use essa política. Escolha **Não** se quiser habilitar o uso de Salvar Como.

  Valor padrão = **Sim**
- **Restringir recortar, copiar e colar com outros aplicativos**: especifique quando as ações de recortar, copiar e colar devem ser restritas. Escolha:
  -   **Bloqueado**: não permite as ações de recortar, copiar e colar entre aplicativos gerenciados pela política.
  -   **Aplicativos Gerenciados pela Política**: habilita as ações de recortar, copiar e colar apenas entre aplicativos gerenciados pela política.
  -   **Aplicativos gerenciados pela política com colar em**: habilita recortar ou copiar entre aplicativos gerenciados pela política. Permite que dados recortados ou copiados de qualquer aplicativo sejam colados neste aplicativo.
  -   **Qualquer aplicativo**: não há restrições para ações de recortar, copiar e colar entre nenhum aplicativo.

  Valor padrão = **Aplicativos gerenciados pela política com colar em**
-   **Restringir conteúdo da web a exibir no Managed Browser**: escolha **sim** para especificar que todos os links no aplicativo serão abertos no aplicativo Managed Browser.

  Para dispositivos que não estão registrados no Intune, os links em aplicativos gerenciados pela política poderão ser abertos apenas no aplicativo Managed Browser se você usar a política de MAM.

  Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Valor padrão = **Sim**
- **Criptografar dados de aplicativo**: escolha **Sim** para habilitar a criptografia. Quando essa configuração está habilitada, a Microsoft fornece criptografia para aplicativos associados a uma política de MAM. Os dados são criptografados de forma síncrona durante tarefas de E/S de arquivo. O conteúdo no armazenamento do dispositivo é Always Encrypted.
  >[!NOTE]
  >O método de criptografia não tem certificação FIPS 140-2.

  Valor padrão = **Sim**

- **Desabilitar sincronização do contato**: escolha **Sim** para impedir que as informações de contato sincronizem com o aplicativo de catálogo de endereço nativo no dispositivo. Se você escolher **Não**, o aplicativo salvará as informações de contato no aplicativo de catálogo de endereço nativo no dispositivo.

  Ao realizar um apagamento seletivo para remover dados da empresa, os contatos sincronizados diretamente entre o aplicativo e o catálogo de endereços nativos são removidos. Os contatos sincronizados entre o catálogo de endereços nativo e outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.

  Valor padrão = **Sim**
- **Desabilitar a impressão**: escolha **Sim** para evitar a impressão de dados da empresa dos aplicativos associados à política de MAM.

  Valor padrão = **Sim**

##  <a name="access-settings"></a>Configurações de acesso

- **Solicitar PIN para acesso**: escolha **Sim** para exigir que um PIN use aplicativos gerenciados pela política. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo no contexto corporativo.

 Valor padrão = **Sim**

 -  **Permitir PIN simples**: especifique se deseja permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Valor padrão = **Sim**.
 - **Comprimento do PIN**: especifique o número mínimo de dígitos em um PIN. Valor padrão = **4**.
 - **Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas de entrada de PIN que podem ser feitas antes que o usuário precise redefinir o PIN. Não há valor padrão para esta configuração.
 - **Exigir a impressão digital em vez de PIN (Android 6.0 +):** escolha **Sim** para exigir uma identidade de impressão digital, em vez de um PIN numerado, para acesso ao aplicativo.
 Em dispositivos Android, você pode possibilitar que o usuário se identifique usando a impressão digital em vez de um PIN numerado. Quando o usuário tenta acessar o aplicativo usando sua conta corporativa, é solicitado que ele forneça a identidade de impressão digital em vez de inserir um PIN.
 - **Exigir credenciais corporativas para acesso**: escolha **Sim** para exigir credenciais corporativas, em vez de um PIN ou impressão digital, para acesso ao aplicativo. Se você definir como **Sim**, esta configuração substituirá os requisitos de PIN ou da ID de Toque. O usuário deverá fornecer suas credenciais corporativas. Valor padrão = **Não**.


- **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou com raiz**: escolha **Sim** para bloquear a execução de aplicativos em dispositivos com jailbreak ou com raiz. O usuário poderá continuar usando os aplicativos para tarefas pessoais, mas terá que usar um dispositivo diferente para o trabalho.

  Valor padrão = **Sim**
- **Verificar novamente os requisitos de acesso após (minutos)**
  -   **Tempo limite**: especifique o tempo (em minutos) antes que os requisitos de acesso ao aplicativo sejam verificados novamente.
  -   **Período de carência offline**: se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.

  Valor padrão = tempo limite de **30** minutos e período de carência offline de **720** minutos

-   **Intervalo offline antes do apagamento dos dados do aplicativo (dias)**: você pode optar por apagar os dados da empresa se um dispositivo ficar offline por um determinado período.  Especifique o número de dias que um dispositivo pode ficar offline antes que os dados da empresa sejam removidos do dispositivo.

    >[!TIP]
    >Inserir um valor de **0** desativa essa configuração.

  Valor padrão = **90** dias
- **Bloquear captura de tela e o Assistente do Android (Android 6 Marshmallow ou posterior)**: escolha **Sim** para bloquear a captura de tela e as funcionalidades do **Assistente do Android** do dispositivo ao usar este aplicativo.



<!--HONumber=Dec16_HO2-->


