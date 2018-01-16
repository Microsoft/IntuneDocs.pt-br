---
title: Registro em massa no Windows 10
titlesuffix: Azure portal
description: Criar um pacote de registro em massa para o Microsoft Intune
keywords: 
author: Erikje
ms.author: erikje
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: f24bf5f8767763c3ca56d51127ab1d3f484e51d8
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2018
---
# <a name="bulk-enrollment-for-windows-devices"></a>Registro em massa para dispositivos Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador, você pode ingressar muitos dispositivos novos com Windows ao Azure Active Directory e ao Intune. Para registrar em massa os dispositivos em seu locatário do Azure AD, você cria um pacote de provisionamento com o aplicativo WCD (Windows Configuration Designer). A aplicação do pacote de provisionamento em dispositivos corporativos ingressa os dispositivos ao seu locatário do Azure AD e os registra no gerenciamento do Intune. Após a aplicação do pacote, ele estará pronto para logon de seus usuários do Azure AD.

Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas do Intune atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da empresa.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Pré-requisitos para registro em massa de dispositivos Windows

- Dispositivos com Atualização do Windows 10 para Criadores ou posteriores
- [Registro automático do Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Criar um pacote de provisionamento

1. Baixe o [WCD (Windows Configuration Designer)](https://www.microsoft.com/store/apps/9nblggh4tx22) na Microsoft Store.
![Capturas de tela e descrição do Windows Configuration Designer](media/bulk-enroll-store.png)

2. Abra o aplicativo **Windows Configuration Designer** e selecione **Provisionar dispositivos de área de trabalho**.
![Captura de tela da seleção de Provisionar dispositivos de área de trabalho no aplicativo Windows Configuration Designer](media/bulk-enroll-select.png)

3. A janela **Novo projeto** é aberta, e nela é possível especificar as seguintes informações:
  - **Nome** - um nome para seu projeto
  - **Pasta do projeto** – local de gravação do projeto
  - **Descrição** - uma descrição opcional do projeto ![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-name.png)

4.  Insira um nome exclusivo para seus dispositivos. Os nomes podem incluir um número de série (%%SERIAL%%) ou um conjunto aleatório de caracteres. Como opção, também é possível inserir uma chave do produto, se você estiver atualizando a edição do Windows, configurá-lo para uso compartilhado e remover o software pré-instalado.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-device.png)

5.  Como opção, você pode configurar a rede Wi-Fi à qual os dispositivos se conectem na primeira inicialização.  Se os dispositivos de rede não estiverem configurados, uma conexão de rede com fio será exigida quando o dispositivo for iniciado pela primeira vez.
![Captura de tela da habilitação de Wi-Fi, incluindo as opções de SSID da Rede e o Tipo da rede, no aplicativo Windows Configuration Designer](media/bulk-enroll-network.png)

6.  Selecione **Registrar no Azure AD**, insira uma data de **Expiração do Token em Massa** e selecione **Obter Token em Massa** .
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-account.png)

7. Forneça suas credenciais do Azure AD para obter um token em massa.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-cred.png)

8.  Clique em **Avançar** quando o **Token em Massa** for obtido com êxito.

9. Como opção, você pode **Adicionar aplicativos** e **Adicionar certificados**. Esses aplicativos e certificados são provisionados no dispositivo.

10. Como opção, você pode proteger com senha seu pacote de provisionamento.  Clique em **Criar**.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Provisionar dispositivos

1. Acesse o pacote de provisionamento no local especificado, na **Pasta do projeto** especificada no aplicativo.

2. Escolha como você pretende aplicar o pacote de provisionamento ao dispositivo.  Um pacote de provisionamento pode ser aplicado a um dispositivo usando uma das seguintes maneiras:
 - Coloque o pacote de provisionamento em uma unidade USB, insira a unidade USB no dispositivo que você deseja registrar em massa, e aplique-o durante a instalação inicial
 - Coloque o pacote de provisionamento em uma pasta de rede e aplique-o no dispositivo que você deseja registrar em massa após a instalação inicial

 Para obter instruções passo a passo sobre como aplicar um pacote de provisionamento, confira [Aplicar um pacote de provisionamento](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Depois de aplicar o pacote, o dispositivo será reiniciado automaticamente em um minuto.
 ![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-add.png)

4. Quando o dispositivo for reiniciado, ele se conectará ao Azure Active Directory e registrará no Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Solução de problemas de registro em massa do Windows

### <a name="provisioning-issues"></a>Problemas de provisionamento
O provisionamento deve ser usado em novos dispositivos com Windows. As falhas de provisionamento podem exigir a redefinição de fábrica do dispositivo ou a recuperação do dispositivo a partir de uma imagem de inicialização. Estes exemplos descrevem alguns dos motivos para falhas de provisionamento:

- Um pacote de provisionamento que tenta ingressar em um domínio do Active Directory ou locatário do Azure Active Directory que não cria uma conta local poderia tornar o dispositivo inacessível se o processo de ingresso no domínio falhar devido à falta de conectividade de rede.
- Scripts executados pelo pacote de provisionamento são executados no contexto do sistema. Os scripts são capazes de fazer alterações aleatórias no sistema de arquivos e nas configurações do dispositivo. Um script mal-intencionado ou incorreto pode colocar o dispositivo em um estado que só pode ser recuperado refazendo a imagem ou redefinindo o dispositivo para as configurações de fábrica.

### <a name="problems-with-bulk-enrollment-and-company-portal"></a>Problemas com o Portal da Empresa e registro em massa
Se um usuário tenta registrar um dispositivo previamente registrado em massa usando o Portal da Empresa, eles receberão um aviso de que seu dispositivo precisa de outras ações, seja instalação ou registro. O dispositivo é registrado, mas o registro não é reconhecido pelo aplicativo de Portal da Empresa ou site.

### <a name="bulk-enrollment-with-wi-fi"></a>Registro em massa com Wi-Fi 

Dispositivos registrados em massa não podem usar os certificados destinados ao usuário e a implantação de Wi-Fi. É necessário usar [certificados no nível do dispositivo](certificates-configure.md) para gerenciar essas conexões. 

### <a name="conditional-access"></a>Acesso condicional
O acesso condicional não está disponível para dispositivos Windows registrados em massa.
