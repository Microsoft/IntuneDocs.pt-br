---
title: "Configurações de política de MAM do Android | Microsoft Intune"
description: "Este tópico descreve as configurações de política de gerenciamento de aplicativo móvel para dispositivos Android."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: 7313854dc9cee26412ed4759e570f0aecc5f156b
ms.openlocfilehash: e8b1ccca0c905ccdefd5c4a97b78561c6edb7908


---

# Configurações de política de gerenciamento de aplicativo móvel de Android no Microsoft Intune
As configurações de política descritas abaixo podem ser [configuradas](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para uma política de MAM na folha **Configurações** no portal do Azure.
Há duas categorias de configurações de política, Realocação dos dados e Configurações de acesso:

##  Configurações de realocação de dados
O termo **Aplicativos gerenciados por política** é usado para fazer referência a aplicativos configurados com políticas de MAM.
- **Evitar backups do Android:** escolha **Sim** para desabilitar ou **Não** para permitir o backup dos dados da empresa de aplicativos gerenciados pela política.

  **Valor padrão = sim**
- **Permitir que o aplicativo transfira dados para outros aplicativos:** selecione uma das opções para indicar os aplicativos que podem receber dados da empresa de aplicativos gerenciados pela política:
  -   **Aplicativos gerenciados pela política**: permita a transferência somente para aplicativos com a política MAM
  -   **Todos os aplicativos**: permitir a transferência para qualquer aplicativo
  -   **Nenhum**: não permitir a transferência de dados para nenhum aplicativo

  **Valor padrão = aplicativos gerenciados por política**
- **Permitir que o aplicativo receba dados de outros aplicativos:** especifique aplicativos com permissão para transferir dados para os aplicativos gerenciados pela política:
  -   **Aplicativos gerenciados pela política**: permita a transferência de dados somente de outros aplicativos gerenciados pela política
  -   **Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo
  -   **Nenhum**: não permita a transferência de dados de nenhum aplicativo

      **Valor padrão = todos os aplicativos**

-   **Impedir Salvar como:** escolha **Sim** para desabilitar o uso da opção Salvar Como em qualquer aplicativo que use essa política. Escolha **Não** se quiser permitir o uso de Salvar Como.

  **Valor padrão = sim**
- **Restringir recortar, copiar e colar com outros aplicativos:** especifique quando recortar, copiar e colar operações deve ser restrito. Escolha:
  -   **Bloqueado:** não permite as operações recortar, copiar e colar entre aplicativos gerenciados por políticas.
  -   **Aplicativos Gerenciados pela Política:** permite operações de recortar, copiar e colar apenas entre aplicativos gerenciados pela política.
  -   **Aplicativos Gerenciados pela Política com Colar Em**: permite recortar ou copiar entre aplicativos gerenciados pela política. Permite que dados recortados ou copiados de qualquer aplicativo sejam colados neste aplicativo.
  -   **Qualquer Aplicativo**: sem restrições para operações de recortar, copiar e colar entre quaisquer aplicativos.

    **Valor padrão = Aplicativos gerenciados pela política com colar em**
-   **Restringir conteúdo da web para exibir no Managed Browser:** quando essa configuração é habilitada, todos os links no aplicativo serão abertos no Navegador Gerenciado.

  Para dispositivos que não estão registrados no Intune, os links da Web em aplicativos gerenciados pela política apenas abrirão no aplicativo Managed Browser usando a política de gerenciamento de aplicativos móveis.

  Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md) (Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune).

    **Valor padrão = sim**
- **Criptografar dados de aplicativo:** escolha **Sim** para habilitar a criptografia. Quando essa configuração está habilitada, para aplicativos associados a uma política de gerenciamento de aplicativos móveis, a criptografia é fornecida pela Microsoft. Os dados são criptografados de forma síncrona durante operações de E/S de arquivo. O conteúdo no armazenamento do dispositivo sempre será criptografado.
  >[!NOTE]
  >O método de criptografia não tem certificação FIPS 140-2

  **Valor padrão = sim**

- **Desabilitar sincronização do contato:** escolha **Sim** para impedir que as informações de contato sincronizem com o aplicativo de catálogo de endereço nativo no dispositivo. Se você escolher **Não**, o aplicativo salvará as informações de contato no aplicativo de catálogo de endereço nativo no dispositivo.<br/>Ao fazer um apagamento seletivo para remover dados da empresa, contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso é aplicável somente ao aplicativo **Microsoft Outlook**.

  **Valor padrão = sim**
- **Desabilitar a impressão:** escolha **Sim** para evitar dados de impressão da empresa dos aplicativos associados à política de MAM.

  **Valor padrão – Sim**

##  Configurações de política de acesso do Android
O termo **Aplicativos gerenciados pela política** é usado para fazer referência a aplicativos configurados com políticas de MAM

- **Solicitar PIN para acesso:** escolha **Sim** para exigir que um PIN use aplicativos gerenciados pela política. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo no contexto corporativo.

 **Valor padrão = sim**

 -  **Permitir PIN simples:** especifique se deseja permitir que os usuários usem sequências PIN simples como 1234 ou 1111. **Valor padrão = Sim**.
 - **Comprimento do PIN:** especifique o número mínimo de dígitos em um PIN. **Valor padrão = 4**
 - **Número de tentativas antes da redefinição do PIN:** especifique o número de tentativas de entrada de PIN que podem ser feitas antes que o usuário precise redefinir o PIN. **Não há valor padrão para esta configuração.**
- **Exigir credenciais corporativas para acesso:** escolha **Sim** para exigir credenciais corporativas, em vez de um PIN, para acesso ao aplicativo.  Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque.  O usuário deverá fornecer suas credenciais corporativas.

  **Valor padrão = Não**
- **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou com raiz:** escolha **Sim** para bloquear a execução de aplicativos em dispositivos com jailbreak ou com raiz. O usuário continuará a ser capaz de usar os aplicativos para tarefas pessoais, mas terá que usar um dispositivo diferente para o trabalho.

  **Valor padrão = sim**
- **Verificar novamente os requisitos de acesso após (minutos)**-   **Tempo limite:** tempo (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.
  -   **Período de carência offline:** se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.

    **Valor padrão = tempo limite de 30 minutos e período de carência offline de 720 minutos**

-   **Intervalo offline antes do apagamento dos dados do aplicativo (dias):** você pode optar por apagar os dados da empresa se um dispositivo ficar offline por um determinado período.  Especifique o número de dias que um dispositivo pode ficar offline antes que os dados da empresa sejam removidos do dispositivo. **Dica:** a entrada de um valor 0 desativa esta configuração.

  **Valor padrão = 90 dias**
- **Bloquear captura de tela e o Assistente do Android (Android 6 Marshmallow ou posterior):** escolha **Sim** para bloquear a captura de tela e as funcionalidades do **Assistente do Android** do dispositivo ao usar este aplicativo.



<!--HONumber=Oct16_HO2-->


