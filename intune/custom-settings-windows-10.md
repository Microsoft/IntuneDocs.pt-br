---
title: "Configurações personalizadas do Intune para dispositivos Windows 10"
titlesuffix: Azure portal
description: "Conheça as configurações que você pode usar em um perfil personalizado do Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0758aed9672c4d1279c5deb24e23beea728df81d
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Configurações personalizadas do dispositivo para dispositivos Windows 10 no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias configurações de CSP, por exemplo o [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Se você estiver procurando uma determinada configuração, lembre-se de que o [perfil de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md) contém várias configurações que são integradas ao Intune e não exigem que você especifique valores personalizados.

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Configurações personalizadas do OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
4. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Use a lista neste tópico para saber mais sobre as configurações que você pode usar:
    - **Nome da configuração** - insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição da configuração** - opcionalmente, insira uma descrição para a configuração.
    - **Tipo de dados** - escolha dentre:
        - **Cadeia de caracteres**
        - **Cadeia de caracteres (XML)**
        - **Data e hora**
        - **Inteiro**
        - **Ponto flutuante**
        - **Booliano**
    - **OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Valor** - especifique o valor para associar ao OMA-URI que você inseriu.
5. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.
O perfil será criado e aparecerá na folha da lista de perfis.

## <a name="example"></a>Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Como localizar as políticas que você pode configurar

Você encontrará uma lista completa de todos os provedores de serviço de configuração (CSP) a que o Windows 10 dá suporte na [Referência do provedor do serviço de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) na biblioteca de documentação do Windows.

Nem todas as configurações são compatíveis com todas as versões do Windows 10. A tabela no tópico do Windows informa quais versões têm suporte para cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas no tópico. Para saber se o Intune oferece suporte à configuração desejada, abra o tópico para essa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.


