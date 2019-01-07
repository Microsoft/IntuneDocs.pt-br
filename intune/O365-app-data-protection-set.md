---
title: Gerenciamento de dados de aplicativos do Office 365 no Microsoft Intune
titlesuffix: ''
description: Saiba mais sobre gerenciamento e proteção de dados de aplicativos do Office 365 no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 05af4625c06975e4eb7b2566ce676c4610500bdf
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642466"
---
# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps-in-microsoft-intune"></a>Como seus usuários receberão a proteção básica nos aplicativos gerenciados do Office 365 no Microsoft Intune

O assistente **Gerenciar aplicativos Office 365** cria uma política de proteção de aplicativo para cada plataforma de dispositivo.

O assistente ativa as políticas a seguir:

**iOS**
* Criptografar dados do aplicativo

**Android**
* Criptografar dados do aplicativo
* Solicitar PIN simples para acesso

Essas políticas garantem que você possa gerenciar os aplicativos do Office 365, oferecendo a capacidade de apagar os dados de trabalho nos aplicativos do Office quando necessário. Eles também garantem a proteção básica em caso de perda ou de roubo de um dispositivo, assegurando que os dados de trabalho estejam criptografados e que um PIN deva ser inserido para exibir os dados em aplicativos do Office 365.


Este artigo usa o OneDrive for Business como exemplo para demonstrar a experiência do usuário em um aplicativo gerenciado pelo Intune.


>[!NOTE]
>Em um dispositivo pessoal, normalmente o usuário final deve baixar o aplicativo. Se o dispositivo for gerenciado por uma solução MDM (gerenciamento de dispositivo móvel), você poderá implantar o aplicativo no dispositivo.

## <a name="user-experience-on-an-ios-device"></a>Experiência do usuário em um dispositivo iOS

1. Inicie o aplicativo OneDrive for Business para abrir a página de entrada.  
2. Digite seu nome de usuário da conta corporativa. Você será redirecionado para a página de autenticação do Office 365 para inserir suas credenciais de trabalho. 
3. Depois que as credenciais forem autenticadas com êxito pelo Azure Active Directory, as políticas de proteção de aplicativo serão aplicadas e você deverá será solicitado a reiniciar o aplicativo OneDrive for Business. 

   > [!NOTE]
   > A mensagem de reinicialização necessária é exibida somente em dispositivos que não estão registrados no Intune.

4. Inicie novamente o aplicativo OneDrive for Business. O aplicativo é iniciado com as políticas de proteção de aplicativo e será solicitado que você defina um PIN para o dispositivo (se ainda não o tiver configurado).  

   > [!NOTE]
   > A maioria dos usuários não verá esse prompt. Somente os usuários que não habilitaram um PIN no dispositivo iOS verão esse aviso.

5. Depois de definir o PIN e confirmá-lo, retorne ao aplicativo do OneDrive for Business. Você verá um aviso único que seu administrador de TI agora está protegendo os dados de trabalho no OneDrive. 
6. Clique após este aviso para acessar os arquivos em seu OneDrive for Business. 

>[!NOTE]
>Quando você altera uma política implantada, as alterações serão aplicadas da próxima vez que abrir o aplicativo.

## <a name="user-experience-on-an-android-device"></a>Experiência do usuário em um dispositivo Android

1. Inicie o aplicativo OneDrive for Business para abrir a página de entrada.  <br/> ![Imagem da tela de boas-vindas do aplicativo do OneDrive](./media/onedrive-android-welcome.png)
2. Digite seu nome de usuário da conta corporativa. Você será redirecionado para a página de autenticação do Office 365 para inserir suas credenciais de trabalho. <br/> ![Imagem da entrada do O365 no Android](./media/o365-sign-in-android.png)
3. Depois que suas credenciais forem autenticadas com êxito pelo Azure Active Directory, você verá uma mensagem solicitando a instalação do aplicativo do Portal da Empresa, se ele já não estiver instalado no dispositivo. Toque em **Ir para a loja** para continuar. <br/> ![Imagem de mensagem para obter o aplicativo de Portal da Empresa](./media/get-company-portal-android.png) <br/>Se já tiver o aplicativo de Portal da Empresa instalado no seu telefone, o OneDrive for Business será iniciado automaticamente e você poderá pular para a nota final.   

   > [!IMPORTANT]
   > No Android, após definir aplicativos do Office para serem gerenciados pela política de proteção de aplicativo, o usuário do dispositivo **deve** instalar o aplicativo de Portal da Empresa para acessar emails e documentos de trabalho, mesmo que o usuário final não precise abrir ou entrar no aplicativo para realmente ler emails ou documentos.

4. Agora você estará na Google Play Store, na qual poderá baixar e instalar o aplicativo do Portal da Empresa. O aplicativo ajuda a manter os dados seguros e protegidos. <br/> ![Imagem do aplicativo na Google Play Store](./media/google-play-get-app-android.png)
5. Depois de concluir a instalação de aplicativo, escolha **Aceitar** para aceitar os termos. O aplicativo OneDrive for Business é iniciado automaticamente.


>[!NOTE]
>Na próxima vez que você abrir o OneDrive for Business, poderá ser solicitado que você defina um PIN se seu departamento de TI exigir um. Depois de definir e confirmar o PIN, você poderá prosseguir para o OneDrive for Business.

![Imagem da solicitação de PIN](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a>Quais políticas são definidas por este assistente?

|     |       | |
|----|--------|-|
|**Nome**|Gerenciar aplicativos do Office 365| |
| **Descrição**|Criado pelo Assistente de aplicativos para gerenciar o Office 365| |
| |  | |
| **Nome da configuração** |**valor da política de iOS** | **Valor da política do Android** |
|Impedir backups do iTunes e iCloud| Não | N/D |
|Impedir backups do Android |N/D | Não|
|Permitir que o aplicativo transfira dados para outros aplicativos | Todos os aplicativos | Todos os aplicativos|
|Permitir que o aplicativo receba dados de outros aplicativos| Todos os aplicativos | Todos os aplicativos|
|Impedir "Salvar como" | Não | Não|
|Restringir recortar, copiar e colar com outros aplicativos | Qualquer aplicativo | Qualquer aplicativo |
|Restringir o conteúdo da web a ser exibido em um navegador gerenciado corporativo | Não| Não|
|Criptografar dados do aplicativo | Quando o dispositivo está bloqueado | Sim|
|Desabilitar a sincronização de contatos | Não| Não|
|Desabilitar a impressão | Não | Não|
|Solicitar PIN para acesso | Não | Sim|
|Número de tentativas antes da redefinição do PIN | N/D |5|
|Permitir PIN simples | N/D |Sim|
|Tamanho do PIN | N/D | 4|
|Permitir a impressão digital em vez do PIN | N/D | Sim |
|Exigir credenciais corporativas para acesso | Não | Não|
|Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root | Não | Não|
|Verificar novamente os requisitos de acesso após (minutos) – Tempo limite excedido | 30 | 30|
|Verificar novamente os requisitos de acesso após (minutos) – Período de cortesia offline | 720 |720|
|Intervalo offline (dias) antes do apagamento dos dados do aplicativo | 90 | 90|
|Bloquear captura de tela (somente para dispositivos Android) | N/D | Não |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a>Por que uma política de PIN de aplicativo está configurada somente para dispositivos Android?
A criptografia funciona de forma diferente no iOS e no Android.

No iOS, para aplicativos associados a uma política de proteção de aplicativo do Intune, os dados são criptografados em repouso por meio da criptografia no nível do dispositivo fornecida pelo sistema operacional. Portanto, quando você ativa a política de criptografia do aplicativo, também é automaticamente exigido que o usuário tenha e digite um PIN no dispositivo para acessar os dados de trabalho. Os usuários que ainda não tiverem um PIN configurado no dispositivo precisarão criar um PIN do dispositivo.

No Android, para aplicativos que estão associados a uma política de proteção de aplicativo do Intune, os dados são criptografados de forma síncrona durante as tarefas de E/S de arquivo. O conteúdo no armazenamento do dispositivo sempre é criptografado. Em dispositivos que não são gerenciados pelo MDM, a política de proteção de aplicativo não pode forçar a necessidade de um PIN do dispositivo. Para garantir que os usuários sejam obrigados a usar algum PIN para acessar os dados de trabalho, o assistente habilita a política de PIN de aplicativo.

Você sempre poderá editar essas configurações de política para atender às necessidades da sua organização.

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a>Como posso exibir e editar as políticas criadas pelo assistente?
Para ver ou atualizar essas políticas ou as políticas que você criar no portal do Intune no Azure, no painel, escolha **Gerenciar aplicativos** > **Políticas de Proteção de Aplicativo**. A lista de políticas será aberta à direita. Escolha a política que você deseja exibir para ver e editar as configurações. <br/>
![Imagem do caminho da interface do usuário para exibir políticas](./media/image-for-faq.png)

## <a name="next-steps"></a>Próximas etapas
- Saiba mais sobre as [políticas de proteção de aplicativo](app-protection-policy.md).
