---
title: Usar modelos para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Use Modelos Administrativos no Microsoft Intune para criar grupos de configurações para dispositivos Windows 10. Use essas configurações em um perfil de configuração do dispositivo para controlar programas do Office, o Microsoft Edge, proteger recursos no Internet Explorer, controlar o acesso ao OneDrive, usar recursos da área de trabalho remota, habilitar a Reprodução Automática, definir configurações de gerenciamento de energia, usar a impressão HTTP, usar diferentes opções de entrada do usuário e controlar o tamanho do log de eventos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca087ec67542102a0cd3111d27a860500b23d3c4
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547980"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Use modelos do Windows 10 para definir as configurações da política de grupo no Microsoft Intune

Ao gerenciar dispositivos em sua organização, você deseja criar grupos de configurações que se aplicam a diferentes grupos de dispositivos. Por exemplo, você tem vários grupos de dispositivos. Para o GroupA, você deseja atribuir um conjunto específico de configurações. Para o GroupB, você deseja atribuir um conjunto diferente de configurações. Você também deseja obter uma exibição simples das configurações definidas.

Realize essa tarefa usando **Modelos Administrativos** no Microsoft Intune. Os modelos administrativos incluem centenas de configurações que controlam recursos no Microsoft Edge versão 77 e posteriores, no Internet Explorer, em programas do Microsoft Office, na área de trabalho remota, no OneDrive, em senhas e PINs, entre outros. Essas configurações permitem que os administradores gerenciem políticas de grupo usando a nuvem.

As configurações do Windows são semelhantes às configurações de política de grupo (GPO) no Active Directory (AD). Essas configurações são internas do Windows e são [configurações com suporte de ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) que usam XML. As definições do Office e do Microsoft Edge são ingeridas pelo ADMX e usam as configurações do ADMX nos [arquivos de modelo administrativo do Office](https://www.microsoft.com/download/details.aspx?id=49030) e nos [arquivos de modelo administrativo do Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise). No entanto, os modelos do Intune são 100% baseados em nuvem. Eles oferecem uma forma simples e direta para definir e encontrar as configurações desejadas.

Os **Modelos Administrativos** são internos ao Intune e não exigem personalizações, incluindo o uso de OMA-URI. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações de modelo como um ponto único centralizado para gerenciar seus dispositivos Windows 10.

Este artigo lista as etapas usadas para criar um modelo para dispositivos Windows 10 e mostra como filtrar todas as configurações disponíveis no Intune. Quando você cria o modelo, ele cria um perfil de configuração do dispositivo. Em seguida, você pode atribuir ou implantar esse perfil a dispositivos Windows 10 em sua organização.

## <a name="before-you-begin"></a>Antes de começar

- Algumas dessas configurações estão disponíveis no Windows 10 versão 1703 (RS2). Algumas configurações não são incluídas em todas as edições do Windows. Para uma melhor experiência, recomendamos usar o Windows 10 Enterprise versão 1903 (19H1) e mais recente.

- As configurações do Windows usam [CSPs da política do Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies). Os CSPs funcionam em diferentes edições do Windows, como Home, Professional, Enterprise e assim por diante. Para ver se um CSP funciona em uma edição específica, acesse os [CSPs da política do Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies).

## <a name="create-a-template"></a>Criar um modelo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome para o perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: Selecione **Modelos Administrativos**.

4. Selecione **Criar**. Na nova janela, selecione **Configurações**. Cada configuração é listada e você poderá usar as setas Anterior e Próximo para ver mais configurações:

    ![Ver uma lista de exemplo de configurações e usar os botões Anterior e Próximo](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > As configurações do Windows no Intune se correlacionam ao caminho da política de grupo local que você vê no Editor de Política de Grupo Local (`gpedit`).

5. Na lista suspensa, selecione **Todos os Produtos**. Na lista, você também pode filtrar as configurações para mostrar apenas as configurações do **Windows**, do **Office** ou do **Microsoft Edge versão 77 ou posteriores**:

    ![filtre a lista para mostrar todas as configurações do Windows ou todas do Office em modelos administrativos no Intune](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > As configurações do Microsoft Edge aplicam-se ao:
    >
    > - Microsoft Edge versão 77 e posteriores. Para configurar o Microsoft Edge versão 45 e anteriores, confira as [Configurações de restrição de dispositivo do Navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).
    > - Windows 10 RS4 e mais recente com a [KB 4512509](https://support.microsoft.com/kb/4512509) instalada
    > - Windows 10 RS5 e mais recente com a [KB 4512534](https://support.microsoft.com/kb/4512534) instalada
    > - Windows 10 19H1 e mais recente com a [KB 4512941](https://support.microsoft.com/kb/4512941) instalada

6. Selecione qualquer configuração. Por exemplo, aplique o filtro no **Office** e selecione **Ativar Navegação Restrita**. Uma descrição detalhada da configuração é mostrada. Selecione **Habilitar**, **Desabilitar**, ou escolha a opção padrão **Não configurado**. A descrição detalhada também explica o que acontece quando você escolhe **Habilitado**, **Desabilitado** ou **Não configurado**.
7. Selecione **OK** para salvar suas alterações.

Continue percorrendo a lista de configurações e defina as configurações desejadas no ambiente. Estes são alguns exemplos:

- Use a configuração **Configurações de Notificação de Macro VBA** para manipular macros VBA em diferentes programas do Microsoft Office, incluindo Word e Excel.
- Use a configuração **Permitir downloads de arquivo** para permitir ou impedir downloads no Internet Explorer.
- Use a configuração **Exigir uma senha ao ativar o computador (conectado)** para solicitar aos usuários uma senha quando os dispositivos saírem do modo de suspensão.
- Use a configuração **Baixar controles ActiveX não assinados** para impedir que os usuários baixem controles ActiveX não assinados no Internet Explorer.
- Use a configuração **Desligar Restauração do Sistema** para permitir ou impedir que os usuários executem uma restauração do sistema no dispositivo.
- Use a configuração **Permitir importação de favoritos** para permitir ou impedir que os usuários importem favoritos de outro navegador para o Microsoft Edge.
- E muito mais!

## <a name="find-some-settings"></a>Encontrar algumas configurações

Há centenas de configurações disponíveis nesses modelos. Para facilitar a localização de configurações específicas, use os recursos internos:

- No modelo, selecione as colunas **Configurações**, **Estado**, **Tipo de configuração** ou **Caminho** para classificar a lista. Por exemplo, selecione a coluna **Caminho** para ver todas as configurações no caminho `Microsoft Excel`:

  ![Clique no caminho para mostrar todas as configurações agrupadas pela política de grupo ou pelo caminho do ADMX em modelos administrativos no Intune](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- No modelo, use a caixa **Pesquisar** para encontrar configurações específicas. Você pode pesquisar definindo o título ou o caminho. Por exemplo, procure `copy`. Todas as configurações com `copy` são mostradas:

  ![Procure a cópia para mostrar todas as configurações do Windows e do Office em modelos administrativos no Intune](./media/administrative-templates-windows/search-copy-settings.png) 

  Em outro exemplo, pesquise `microsoft word`. Você verá todas as configurações que podem ser definidas para o programa Microsoft Word. Pesquise `explorer` para ver todas as configurações do Internet Explorer que podem ser adicionadas ao modelo.

## <a name="next-steps"></a>Próximas etapas

O modelo foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o modelo, também chamado de perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

[Atualizar o Office 365 usando modelos administrativos](administrative-templates-update-office.md).
