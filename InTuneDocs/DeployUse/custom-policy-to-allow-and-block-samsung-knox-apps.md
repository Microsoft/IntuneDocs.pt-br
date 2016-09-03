---
title: Aplicativos permitidos e bloqueados para KNOX | Microsoft Intune
description: Perfil personalizado para criar uma lista de aplicativos permitidos e bloqueados para KNOX.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65d2c9c1f5d81dae33422bd4bf7c0e2e21bb96e4
ms.openlocfilehash: 937e291f193f61329598395baa63c24d7fefa25f



---
# Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX

Use os procedimentos neste tópico para criar uma política personalizada do Microsoft Intune que cria um destes procedimentos:

- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Nenhum outro aplicativo poderá ser executado. Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Apenas os aplicativos listados podem ser instalados. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.

## Para criar uma lista de aplicativos permitidos ou bloqueados

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política** &gt; **Políticas de Configuração** &gt; **Adicionar**.
2. Na caixa de diálogo **Criar Nova política**, expanda **Android**, escolha **Configuração Personalizada** e escolha **Criar Política**.
3. Forneça um nome e uma descrição opcional para a política e, na seção **Configurações do OMA-URI**, escolha **Adicionar**.
4. Na caixa de diálogo **Adicionar ou editar a Configuração do OMA-URI**, especifique o seguinte: para obter uma lista dos aplicativos que são impedidos de serem executados no dispositivo:
    
    - **Nome da configuração.** Digite **PreventStartPackages**.
    - **Descrição da configuração.** Insira uma descrição opcional, como "Lista de aplicativos impedidos de serem executados".
    -   **Tipo de dados.** Na lista suspensa, escolha **Cadeia de caracteres**.
    -   **OMA-URI.** Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -   **Valor.** Insira uma lista dos nomes de pacotes do aplicativo que deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

    Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:

    - **Nome da configuração.** Digite **AllowInstallPackages**.
    - **Descrição da configuração.** Insira uma descrição opcional, como "Lista de aplicativos que os usuários podem instalar do Google Play".
    - **Tipo de dados.** Na lista suspensa, escolha **Cadeia de caracteres**.
    - **OMA-URI.** Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Valor.** Insira uma lista dos nomes de pacotes do aplicativo que deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

4. Clique em **OK** e em **Salvar Política**. 

>[DICA] Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.


## Implantar a política

1.  No espaço de trabalho **Política** , selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar Implantação**, selecione um ou mais grupos para os quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.

 
Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.

### Consulte também
[Configurações de política do Android e Samsung KNOX no Microsoft Intune](android-policy-settings-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->

