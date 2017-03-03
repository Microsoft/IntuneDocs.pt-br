---
title: "Adicionar números de série do Apple Configurator"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como adicionar números de série aos dispositivos iOS corporativos usando o Apple Configurator."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26d253f013195cc18f9a97b8259c603d707d22bf
ms.lasthandoff: 02/18/2017


---

# <a name="add-apple-configurator-serial-numbers"></a>Adicionar números de série do Apple Configurator

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use estas etapas para adicionar números de série ao Intune quando quiser [registrar dispositivos iOS corporativos usando o Apple Configurator com o Assistente de Configuração](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Você pode adicionar números de série um por vez ou carregar um arquivo de valores de separados por vírgula (CSV) dos números de série. Depois de adicionar os números de série, você poderá atribuir um perfil para eles. O perfil contém as configurações de gerenciamento específicas que você deseja aplicar aos dispositivos.

Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](choose-ios-enrollment-method.md).

**Para adicionar números de série do Apple Configurator ao Intune**

1. Crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita. O máximo atual para a lista é de 500 linhas. Em um editor de texto, a lista .csv é semelhante a:

    F7TLWCLBX196, detalhes do dispositivo</br>
    DLXQPCWVGHMJ, detalhes do dispositivo

2. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

3.  Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.

4. Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Números de Série do Apple Configurator**.

5. Na folha **Números de Série do Apple Configurator**, selecione **Adicionar**.

6. Na folha **Adicionar números de série**, selecione um perfil para aplicar a números de série que você está importando. Se você estiver importando um arquivo com novos detalhes que substituirão os existentes, selecione Substituir os detalhes para os identificadores existentes para que os novos detalhes substituam os existentes.

7. Navegue até o arquivo .csv de números de série e selecione **Adicionar**.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Atribuir um perfil números de série específicos

O Intune permite atribuir perfis de dois locais diferentes no Portal do Azure. Você pode usar as etapas a seguir ou pode atribuir perfis na folha Perfis de Registro do Apple Configurator, na qual você cria o perfil (consulte [Registrar dispositivos iOS com Apple Configurator usando o Assistente de configuração](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Use as etapas a seguir para atribuir o perfil somente se você já o criou.

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.

3. Na folha **Números de série do Apple Configurator**, selecione os números de série que você deseja atribuir a um perfil e, em seguida, selecione **Atribuir Perfil**.

4. Na folha **Atribuir Perfil**, selecione o perfil que você deseja atribuir e selecione **Atribuir**.

## <a name="delete-serial-numbers"></a>Excluir números de série
Você pode excluir os números de série importados anteriormente. Você poderá excluir os números de série apenas se o registro do dispositivo for cancelado primeiro. Quando você remove um número de série, não é possível usar o Apple Configurator por meio do Assistente de configuração, a menos que você adicione novamente o número de série.

## <a name="view-the-state-of-a-device"></a>Exibir o estado de um dispositivo
Os números de série do dispositivo pode ter um dos dois estados:

- Registrado – o dispositivo é registrado e se conectou ao serviço do Intune
- Não Contatado – o dispositivo nunca se conectou ao serviço Intune.
- Redefinição pendente – o dispositivo foi registrado, mas uma alteração foi feita (por exemplo, configurações do registro ou o perfil DEP aplicado foi alterado). Se você alterar o perfil DEP de um dispositivo, as alterações não serão aplicadas até que o dispositivo seja cancelado e, em seguida, registrado novamente.

**Para exibir o estado de um número de série**

Na folha **Números de Série do Apple Configurator**, selecione o número de série cujo estado você deseja ver e procure o item **Estado**.

