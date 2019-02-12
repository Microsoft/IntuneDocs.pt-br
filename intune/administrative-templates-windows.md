---
title: Usar modelos para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Use Modelos Administrativos no Microsoft Intune para criar grupos de configurações para dispositivos Windows 10. Use essas configurações em um perfil de configuração do dispositivo para controlar programas do Office, proteger recursos no Internet Explorer, controlar o acesso ao OneDrive, usar recursos da área de trabalho remota, habilitar a Reprodução Automática, definir configurações de gerenciamento de energia, usar a impressão HTTP, usar diferentes opções de logon do usuário e controlar o tamanho do log de eventos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36076aab02f16937066cb3d47d573f7c74dd6277
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55833609"
---
# <a name="windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Modelos do Windows 10 para definir as configurações da Política de Grupo no Microsoft Intune

Ao gerenciar dispositivos em sua organização, você deseja criar um grupo de configurações que são aplicadas a diferentes grupos de dispositivos. Por exemplo, você tem vários grupos de dispositivos. Para o GroupA, você deseja atribuir um conjunto específico de configurações. Para o GroupB, você deseja atribuir um conjunto diferente de configurações. Você também deseja obter uma exibição simples das configurações definidas.

Realize essa tarefa usando **Modelos Administrativos** no Microsoft Intune. Os modelos administrativos incluem centenas de configurações que controlam recursos no Internet Explorer, programas do Microsoft Office, área de trabalho remota, acesso ao OneDrive, uso de uma senha com imagem ou um PIN para conexão, entre outros. Esses modelos são semelhantes às configurações de GPO (Política de Grupo) no AD (Active Directory) e são [configurações com suporte de ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) que usam XML. Porém, os modelos do Intune são 100% baseados em nuvem. Eles oferecem uma forma mais simples e direta para definir as configurações e encontrar as configurações desejadas.

Os **Modelos Administrativos** são internos ao Intune e não exigem personalizações, incluindo o uso de OMA-URI. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações de modelo como um ponto único centralizado para gerenciar seus dispositivos Windows 10.

Este artigo lista as etapas usadas para criar um modelo para dispositivos Windows 10 e mostra como filtrar todas as configurações disponíveis no Microsoft Intune. Quando você cria o modelo, ele cria um perfil de configuração do dispositivo. Em seguida, você pode atribuir ou implantar esse perfil a dispositivos Windows 10 em sua organização.

> [!NOTE]
> Há suporte para modelos administrativos em dispositivos autônomos. No momento, não há suporte para eles em dispositivos cogerenciados do SCCM (System Center Configuration Manager).

## <a name="create-a-template"></a>Criar um modelo

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome para o perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: Selecione **Modelos Administrativos (Versão Prévia)**.

4. Selecione **Criar**. Na nova janela, selecione **Configurações**. Cada configuração é listada e você poderá usar as setas Anterior e Próximo para ver mais configurações:

    ![Ver uma lista de exemplo de configurações e usar os botões Anterior e Próximo](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Selecione qualquer configuração. Por exemplo, selecione **Permitir downloads de arquivo**. Uma descrição detalhada da configuração é mostrada. Escolha **Habilitar**, **Desabilitar** ou mantenha a configuração como **Não configurado** (padrão). A descrição detalhada também explica o que acontece quando você escolhe **Habilitar**, **Desabilitar** ou **Não configurado**.
6. Selecione **OK** para salvar suas alterações.

Continue percorrendo a lista de configurações e defina as configurações desejadas no ambiente. Estes são alguns exemplos:

- Use a configuração **Configurações de Notificação de Macro VBA** para manipular macros VBA em diferentes programas do Microsoft Office, incluindo Word e Excel.
- Use a configuração **Permitir downloads de arquivo** para permitir ou impedir downloads no Internet Explorer.
- Use a configuração **Exigir uma senha quando um computador for ativado (conectado)** para solicitar aos usuários uma senha quando os dispositivos saírem do modo de suspensão.
- Use a configuração **Baixar controles ActiveX não assinados** para impedir que os usuários baixem controles ActiveX não assinados no Internet Explorer.
- Use a configuração **Desligar Restauração do Sistema** para permitir ou impedir que os usuários executem uma restauração do sistema no dispositivo.
- E muito mais!

## <a name="find-some-settings"></a>Encontrar algumas configurações

Há centenas de configurações disponíveis nesses modelos. Para facilitar a localização de configurações específicas, use os recursos internos:

- No modelo, selecione as colunas **Configurações**, **Estado** ou **Caminho** para classificar a lista. Por exemplo, selecione a coluna **Caminho** para ver todas as configurações no caminho `Microsoft Excel`:

  ![Clicar em Caminho para classificar em ordem alfabética](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- No modelo, use a caixa **Pesquisar** para encontrar configurações específicas. Por exemplo, procure `copy`. Todas as configurações com `copy` são mostradas:

  ![Clicar em Caminho para classificar em ordem alfabética](./media/administrative-templates-windows/search-copy-settings.png)

  Em outro exemplo, pesquise `microsoft word`. Você verá todas as configurações que podem ser definidas para o programa Microsoft Word. Pesquise `explorer` para ver todas as configurações do Internet Explorer que podem ser adicionadas ao modelo.

## <a name="next-steps"></a>Próximas etapas

O modelo foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o modelo, também chamado de perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
