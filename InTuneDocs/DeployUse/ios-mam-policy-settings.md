---
# required metadata

title: Configurações de política MAM iOS | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#  Configurações de política de gerenciamento de aplicativo móvel iOS
As configurações de política descritas abaixo podem ser [configuradas](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para uma política de MAM na folha **Configurações** no portal do Azure.

Há duas categorias de configurações de política, Realocação dos dados e Configurações de acesso:

##  Configurações de realocação de dados
O termo **Aplicativos gerenciados por política** é usado para fazer referência a aplicativos configurados com políticas de MAM.

- **Impedir backups do iTunes e iCloud:**
  Escolha **Sim** para desabilitar ou **não** para permitir o backup dos dados da empresa de aplicativos gerenciados por política.

  **Valor padrão = sim**

- **Permitir que o aplicativo transfira dados para outros aplicativos:** escolha uma das opções para indicar os aplicativos que podem receber dados de aplicativos gerenciados por política:
  - **Aplicativos gerenciados por política**: permitir a transferência somente para aplicativos com a política MAM.
  - **Todos os aplicativos**: permitir a transferência para qualquer aplicativo
  - **Nenhum**: não permitir a transferência de dados para qualquer aplicativo, incluindo outros aplicativos gerenciados por política.

  Além disso, se você definir essa opção como **Aplicativos Gerenciados por Política** ou **Nenhum**, o recurso do iOS 9 que permite a Pesquisa de Destaque pesquise dados em aplicativos será bloqueado.

  **Valor padrão = aplicativos gerenciados por política**

- **Permitir que o aplicativo receba dados de outros aplicativos:** especifique aplicativos com permissão para transferir dados para a política de aplicativos gerenciados:
  -  **Aplicativos gerenciados por política**: permitir a transferência de dados somente de outros aplicativos gerenciados por política.
  -  **Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo
  -  **Nenhum**: não permitir a transferência de dados de nenhum aplicativo.

  **Valor padrão = todos os aplicativos**

- **Impedir Salvar como:**
  Escolha **Sim** para desabilitar o uso da opção Salvar Como em qualquer aplicativo que use essa política. Escolha **Não** se quiser permitir o uso de Salvar Como.

  **Valor padrão = sim**

- **Restringir recortar, copiar e colar com outros aplicativos:**
Especifique quando as operações de recortar, copiar e colar devem ser restringidas. Escolha:
  -   **Bloqueado:** não permite as operações recortar, copiar e colar entre aplicativos gerenciados por políticas.
  -   **Aplicativos Gerenciados pela Política:** permite operações de recortar, copiar e colar apenas entre aplicativos gerenciados pela política.
  -   **Aplicativos Gerenciados pela Política com Colar Em**: permite recortar ou copiar entre aplicativos gerenciados pela política. Permite que dados recortados ou copiados de qualquer aplicativo sejam colados neste aplicativo.
  - **Qualquer Aplicativo**: sem restrições para operações de recortar, copiar e colar entre quaisquer aplicativos.

  **Valor padrão = aplicativos gerenciados por política com colagem em**

- **Restringir conteúdo da web para exibir no Managed Browser:** quando essa configuração é habilitada, todos os links no aplicativo serão abertos no Navegador Gerenciado.

  Para dispositivos que não estão registrados no Intune, é possível abrir os links da Web somente no aplicativo Navegador Gerenciado usando a política de gerenciamento de aplicativo móvel.

  Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md) (Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune).

    **Valor padrão = sim**

- **Criptografar dados do aplicativo:** para aplicativos associados a uma política de gerenciamento de aplicativo móvel [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], os dados são criptografada em repouso usando a criptografia no nível do dispositivo fornecida pelo sistema operacional. Quando um PIN for solicitado, os dados serão criptografados segundo as configurações na política de gerenciamento de aplicativos móveis. Conforme indicado na documentação da Apple, [os módulos usados pelo iOS 7 têm a certificação FIPS 140-2](http://support.apple.com/en-us/HT202739).

  Nas configurações da política, você pode especificar valores de PIN de criptografia.  Esses valores determinam quando os dados são criptografados. As opções são:
  - **Quando o dispositivo está bloqueado:** todos os dados de aplicativo associados a essa política ficam criptografados enquanto o dispositivo está bloqueado.
  -   **Quando o dispositivo está bloqueado (exceto arquivos abertos):** todos os dados de aplicativo associados a essa política ficam criptografados enquanto o dispositivo está bloqueado, exceto para dados nos arquivos que estão abertos no aplicativo no momento.
  -   **Após o dispositivo reiniciar:** todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo é reiniciado, até que o dispositivo seja desbloqueado pela primeira vez.
  -   **Usar configurações do dispositivo:** os dados do aplicativo são criptografados com base nas configurações padrão do dispositivo.
  Quando você habilita essa configuração, é obrigatório que o usuário final configure e use PIN para acessar seu dispositivo.  Se não houver configuração de PIN, os aplicativos não serão inicializados e o usuário final será solicitado a definir um PIN com uma mensagem: "A empresa exigiu que você habilite primeiro um dispositivo PIN para acessar este aplicativo".

  **Valor padrão - a opção de criptografia não está selecionada.**
- **ContactSyncDisabled:** escolha **Sim** para impedir que as informações de contato sincronizem com o aplicativo de catálogo de endereço nativo no dispositivo. Se você escolher **Não**, o aplicativo salvará as informações de contato no aplicativo de catálogo de endereço nativo no dispositivo.

  Ao fazer um apagamento seletivo para remover dados da empresa, contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso é aplicável somente ao aplicativo **Microsoft Outlook**.

  **Valor padrão = sim**
##  Configurações de política de acesso ao iOS
O termo **Aplicativos gerenciados por política** é usado para fazer referência a aplicativos configurados com políticas de MAM.
- **Exigir PIN simples para acesso:** escolha **Sim** para exigir um PIN para usar a política de aplicativos gerenciados. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo no contexto corporativo.

  **Valor padrão = sim**
- **Número de tentativas antes da redefinição do PIN:** especifique o número de tentativas de entrada de PIN que podem ser feitas antes que o usuário precise redefinir o PIN.

  **Não há valor padrão para esta configuração.**.
- **Exigir a impressão digital em vez de PIN (iOS 8.0 +):** escolha **Sim** para exigir uma identidade de impressão digital, em vez de um PIN numerado, para acesso ao aplicativo.
Em dispositivos iOS, você pode permitir que o usuário se identifique usando a impressão digital em dispositivos iOS, em vez de um PIN numerado. Quando o usuário final tenta acessar esse aplicativo usando sua conta corporativa, ele é solicitado a fornecer a identidade de impressão digital, em vez de inserir um número de PIN.

  **Valor padrão = sim**
- **Exigir credenciais corporativas para acesso:** escolha **Sim** para exigir credenciais corporativas, em vez de um PIN, para acesso ao aplicativo. **Se você tiver definido isto como Sim, ele substituirá os requisitos de PIN ou da ID de Toque.** O usuário deverá fornecer suas credenciais corporativas.

  **Valor padrão = Não**
- **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou com raiz:** escolha **Sim** para bloquear a execução de aplicativos em dispositivos com jailbreak ou com raiz. O usuário continuará a ser capaz de usar os aplicativos para tarefas pessoais, mas terá que usar um dispositivo diferente para o trabalho.

  **Valor padrão = sim**
- **Verificar novamente os requisitos de acesso após (minutos)**|-   **Tempo limite:** tempo (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.
  -   **Período de carência offline:** se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente.

  **Valor padrão = tempo limite de 30 minutos com período de carência offline de 720 minutos**
  - **Intervalo offline antes do apagamento dos dados do aplicativo (dias):** você pode optar por apagar os dados da empresa se um dispositivo ficar offline por um determinado período.  Especifique o número de dias que um dispositivo pode ficar offline antes que os dados da empresa sejam removidos do dispositivo. **A entrada de um valor 0 desativa essa configuração**.

  **Valor padrão = 90 dias**


<!--HONumber=May16_HO1-->


