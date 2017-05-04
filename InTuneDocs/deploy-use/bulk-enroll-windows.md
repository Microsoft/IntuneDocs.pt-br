---
title: Registro em massa para Windows 10 | Microsoft Docs
description: Criar um pacote de registro em massa para o Microsoft Intune
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0053e37a-f26e-452f-9524-5039a635b52e
ms.reviewer: damionw
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: dfe63ba7e1825db8d8b6b1e74c442b125ccafd46
ms.lasthandoff: 04/19/2017

---
# <a name="bulk-enrollment-for-windows-devices"></a>Registro em massa para dispositivos Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Como administrador, você pode ingressar muitos dispositivos novos com Windows ao Azure Active Directory e ao Intune. Para registrar em massa os dispositivos em seu locatário do Azure AD, você cria um pacote de provisionamento com o aplicativo WCD (Windows Configuration Designer). A aplicação do pacote de provisionamento em dispositivos corporativos ingressa os dispositivos ao seu locatário do Azure AD e os registra no gerenciamento do Intune. Após a aplicação do pacote, ele estará pronto para logon de seus usuários do Azure AD.

Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas do Intune atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da empresa.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Pré-requisitos para registro em massa de dispositivos Windows

O registro em massa para dispositivos Windows exige o seguinte:

- Dispositivos com Atualização do Windows 10 para Criadores ou posteriores
- [Registro automático do Windows](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Criar um pacote de provisionamento

1. Baixe o [WCD (Windows Configuration Designer)](https://www.microsoft.com/store/apps/9nblggh4tx22) da Windows Store.
![Capturas de tela e descrição do Windows Configuration Designer](../media/bulk-enroll-store.png)

2. Abra o aplicativo **Windows Configuration Designer** e selecione **Provisionar dispositivos de área de trabalho**.
![Captura de tela da seleção de Provisionar dispositivos de área de trabalho no aplicativo Windows Configuration Designer](../media/bulk-enroll-select.png)

3. A janela **Novo projeto** é aberta e é possível especificar o seguinte:
  - **Nome** - um nome para seu projeto
  - **Pasta do projeto** - onde seu novo projeto será salvo
  - **Descrição** - uma descrição opcional do projeto ![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-name.png)

4.    Insira um nome exclusivo para seus dispositivos. Os nomes podem incluir um número de série (%%SERIAL%%) ou um conjunto aleatório de caracteres. Como opção, também é possível inserir uma chave do produto, se você estiver atualizando a edição do Windows, configurá-lo para uso compartilhado e remover o software pré-instalado.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-device.png)

5.    Como opção, você pode configurar a rede Wi-Fi à qual os dispositivos se conectem na primeira inicialização.  Se isso não estiver configurado, uma conexão de rede com fio será exigida quando o dispositivo for iniciado pela primeira vez.
![Captura de tela da habilitação de Wi-Fi, incluindo as opções de SSID da Rede e o Tipo da rede, no aplicativo Windows Configuration Designer](../media/bulk-enroll-network.png)

6.    Selecione **Registrar no Azure AD**, insira uma data de **Expiração do Token em Massa** e selecione **Obter Token em Massa** .
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-account.png)

7. Forneça suas credenciais do Azure AD para obter um token em massa.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-cred.png)

8.    Clique em **Avançar** quando o **Token em Massa** for obtido com êxito.

9. Como opção, você pode **Adicionar aplicativos** e **Adicionar certificados**. Esses aplicativos e certificados são provisionados no dispositivo.

10. Como opção, você pode proteger com senha seu pacote de provisionamento.  Clique em **Criar**.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Provisionar dispositivos

1. Acesse o pacote de provisionamento no local especificado, na **Pasta do projeto** especificada no aplicativo.

2. Escolha como você pretende aplicar o pacote de provisionamento ao dispositivo.  Um pacote de provisionamento pode ser aplicado a um dispositivo usando uma das seguintes maneiras:
 - Coloque o pacote de provisionamento em uma unidade USB, insira a unidade USB no dispositivo que você deseja registrar em massa, e aplique-o durante a instalação inicial
 - Coloque o pacote de provisionamento em uma pasta de rede e aplique-o no dispositivo que você deseja registrar em massa após a instalação inicial

 Para obter instruções passo a passo sobre como aplicar um pacote de provisionamento, confira [Aplicar um pacote de provisionamento](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Depois de aplicar o pacote, o dispositivo será reiniciado automaticamente em um minuto.
 ![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](../media/bulk-enroll-add.png)

4. Quando o dispositivo for reiniciado, ele se conectará ao Azure Active Directory e registrará no Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Solução de problemas de registro em massa do Windows

O provisionamento deve ser usado em novos dispositivos com Windows. As falhas de provisionamento podem exigir a redefinição de fábrica do dispositivo ou a recuperação do dispositivo a partir de uma imagem de inicialização. Estes exemplos descrevem alguns dos motivos para falhas de provisionamento:

- Um pacote de provisionamento que tenta ingressar em um domínio do Active Directory ou locatário do Azure Active Directory que não cria uma conta local poderia tornar o dispositivo inacessível se o processo de ingresso no domínio falhar devido à falta de conectividade de rede.
- Os scripts executados pelo pacote de provisionamento são executados no contexto do sistema e podem fazer alterações aleatórias no sistema de arquivos e configurações do dispositivo. Um script mal-intencionado ou incorreto pode colocar o dispositivo em um estado que só pode ser recuperado refazendo a imagem ou redefinindo o dispositivo para as configurações de fábrica.
