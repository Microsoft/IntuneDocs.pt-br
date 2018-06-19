---
title: Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung
titlesuffix: Microsoft Intune
description: Saiba como inscrever dispositivos Android usando o Samsung KME
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88cb733c688019b2fc5455a0184e968d91e77806
ms.sourcegitcommit: b0ad42fe5b5627e5555b2f9e5bb81bb44dbff078
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2018
ms.locfileid: "33915804"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung

Este tópico ajuda você a configurar o Intune para a inscrição de dispositivos Android com suporte usando o KME (Samsung Knox Mobile) da Samsung. Usando o Intune com o Samsung KME, você pode inscrever muitos dispositivos Android da empresa quando os usuários finais ligarem seus dispositivos pela primeira vez e se conectarem a uma rede celular ou Wi-Fi. Além disso, os dispositivos podem ser inscritos usando Bluetooth ou NFC, ao usar o Aplicativo de Implantação do Knox.

Para habilitar a inscrição do Intune usando o Samsung KME, use os portais do Intune e do Samsung Knox nesta ordem:

1. No portal do Knox:
    1. [Criar um perfil de MDM](#create-mdm-profile)
    2. [Adicionar dispositivos](#add-devices)
    3. [Atribuir um perfil de MDM aos dispositivos](#assign-an-mdm-profile-to-devices)
2. No Portal do Azure, [identifique os dispositivos como corporativos](#identify-devices-as-corporate-owned).
3. No portal do Knox, [configure a entrada do usuário final](#configure-how-end-users-sign-in).
4. [Distribuir os dispositivos](#distribute-devices).


Uma lista de identificadores de dispositivo (números de série e IMEIs) é adicionada automaticamente ao Portal do Knox, ao comprar os dispositivos de revendedores autorizados que participam do Programa de Implantação do Knox.


## <a name="prerequisites"></a>Pré-requisitos

Para inscrever no Intune usando KME, primeiro você precisa registrar a sua empresa no Portal do Samsung Knox executando estas etapas:
1.  [Verifique se o KME está disponível em sua região](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): o KME está disponível em mais de 55 países. Verifique se o seu país de implantação tem suporte.

2.  [Dispositivos com suporte](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): o KME está disponível em todos os dispositivos Samsung com o Knox 2.4, no mínimo.

3.  [Requisitos de rede](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): verifique se as regras de acesso de rede e de firewall necessárias têm permissão em sua rede.

4.  [Registrar uma conta da Samsung](https://www2.samsungknox.com/en/user/register): é necessário ter uma conta da Samsung a fim de registrar e habilitar o KME, e gerenciar todos os direitos de empresa da Knox Enterprise em um único lugar.

5.  Análise do registro: após o preenchimento e envio de seu perfil, a Samsung fará uma revisão de sua inscrição e poderá aprová-la imediatamente ou colocá-la em um estado de análise pendente, para mais acompanhamento. Após a aprovação da sua conta, você poderá prosseguir com as etapas.

## <a name="create-mdm-profile"></a>Criar um perfil de MDM

Após o registro bem-sucedido da sua empresa, você pode criar seu perfil de MDM para o Microsoft Intune no Portal do Knox usando as informações a seguir. Para obter orientação passo a passo, consulte as instruções no [Assistente de instalação de Perfil do Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm).

| Campos do perfil de MDM| Necessário? | Valores |
|-------------------|-----------|-------|
|URI do servidor MDM     | Não        |Deixe em branco.
|Nome do perfil       | Sim       |Insira um nome de perfil de sua escolha.
|descrição        | Não        |Insira um texto que descreva o perfil.
|APK do Agente MDM      | Sim       |https://aka.ms/intune_kme
|Ignorar Assistente de Configuração  | Não        |Escolha essa opção para ignorar os avisos de instalação de dispositivo padrão em nome do usuário final.
|Permitir que o usuário final cancele o registro | Não | Escolha essa opção para permitir que os usuários cancelem o KME.
|JSON Personalizado        | Não        |Deixe em branco.
| EULAs, Termos de Serviço e Contratos de Usuário| Não | Escolha essa opção para mostrar contratos relacionados ao Knox para aceitação do usuário.
Associar uma licença do Knox a este perfil | Não | Deixe essa opção desmarcada. Não é necessário ter uma licença Knox para se registrar no Intune usando o KME.

## <a name="add-devices"></a>Adicionar Dispositivos

Para atribuir perfis de MDM aos dispositivos, é necessário adicionar os dispositivos Samsung Knox com suporte ao Portal do Knox usando um dos métodos a seguir:
- **Usando revendedores aprovados pela Samsung:** use esse método se você estiver adquirindo dispositivos de um dos revendedores aprovados pela Samsung. Os revendedores podem carregar automaticamente dispositivos para você após a aprovação. [Confira o Guia de Usuário de Inscrição do Samsung Knox para aprender a adicionar revendedores](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Usar o KDA (Aplicativo de Implantação do Knox):** use este método se você já tiver dispositivos que precisam de registro usando o KME. Você pode usar o Bluetooth ou o NFC para adicionar dispositivos ao Portal do Knox usando esse método. [Confira o Guia de Usuário de Inscrição do Samsung Knox para saber como usar o KDA](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Atribuir um perfil de MDM a dispositivos
Você deve atribuir um perfil de MDM aos dispositivos adicionados no Portal do Knox antes de poder inscrevê-los. [Confira o Guia de Usuário de Inscrição do Samsung Knox para aprender sobre a configuração de dispositivo](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="identify-devices-as-corporate-owned"></a>Identificar dispositivos como corporativos
Você pode identificar os dispositivos que foram inscritos usando o KME como corporativos. Isso deve ser feito antes da inscrição dos dispositivos. Isso permite que você execute tarefas de gerenciamento adicionais e colete informações adicionais, como o número de telefone completo e um inventário de aplicativos.

Execute estas etapas para identificar dispositivos como corporativos:

1. Exporte a lista de dispositivos do Portal Knox como um arquivo CSV.

2. Formate o arquivo CSV usando IMEI ou número de série, conforme indicado [aqui](https://docs.microsoft.com/en-us/intune/corporate-identifiers-add#identify-corporate-owned-devices-with-imei-or-serial-number).

3. No Portal do Azure, carregue o arquivo CSV em **Registro de dispositivo** > **Identificadores de dispositivo corporativo** > **Adicionar**.

Agora, os identificados dispositivos inscritos serão marcados como corporativos.

> [!NOTE]
>O Intune atribui automaticamente o status de corporativo a dispositivos inscritos com a conta do [Gerenciador de Registros do Dispositivo](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll).

## <a name="configure-how-end-users-sign-in"></a>Configurar como os usuários finais entram

Para dispositivos inscritos no Intune usando KME, você pode configurar como um usuário final faz logon da seguinte maneira:

- **Sem associação de nome de usuário:** no Portal do Knox, em **Detalhes do dispositivo**, deixe os campos **ID de Usuário** e **Senha** em branco para os dispositivos adicionados. Isso exige que o usuário final insira o nome de usuário e a senha ao se inscrever no Intune.

- **Com associação de nome de usuário:** no Portal do Knox em **Detalhes do dispositivo**, forneça uma **ID de Usuário** (como um nome de usuário para o usuário atribuído ou uma conta do [Gerenciador de Registro de Dispositivo](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll)) para os dispositivos adicionados. Isso preenche previamente o nome de usuário e exige que o usuário final insira uma senha ao se inscrever no Intune.

> [!NOTE]
>
>Quando a associação do usuário é definida, somente o usuário associado pode registrar o dispositivo usando KME. Isso é verdadeiro mesmo após uma redefinição de fábrica do dispositivo. Quando nenhuma associação de usuário for definida no Portal do Knox, qualquer usuário com uma licença válida do Intune poderá registrar o dispositivo usando KME.
>

## <a name="distribute-devices"></a>Distribuir dispositivos

Depois de criar e atribuir um perfil de MDM, associar um nome de usuário e identificar os dispositivos como corporativos no Intune, você pode distribuir dispositivos para os usuários.

Ainda precisa de ajuda? Confira o [Guia de Usuário completo de Inscrição Móvel do Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Perguntas frequentes
- **Conta do Google Play:** não é necessário ter uma conta do Google Play para registrar o dispositivo no Microsoft Intune. Porém, atualizações futuras ao aplicativo Portal da Empresa do Intune podem exigir uma conta do Google Play no dispositivo.

- **Modo Proprietário de Dispositivo Google:** não há suporte para a inscrição no modo Proprietário de Dispositivo Google com o KME nesta Versão prévia. Esse cenário está sendo investigado.

- **O campo "Senha" é ignorado:** se o campo **Senha** estiver preenchido em **Detalhes do dispositivo** no Portal do Knox, ele será ignorado pelo aplicativo Portal da Empresa do Intune. O usuário final deve inserir uma senha no dispositivo para concluir o registro.

## <a name="getting-support"></a>Como obter suporte
Saiba mais sobre [como obter suporte para o Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


