---
title: Registrar dispositivos usando o Windows Autopilot
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Windows 10 usando o Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4f97c4c56073044e79b5251dc83c54decb5c9c55
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124836"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Registrar dispositivos Windows no Intune usando o Windows Autopilot  
O Windows Autopilot simplifica a inscrição de dispositivos no Intune. Compilar e manter imagens de sistema operacional personalizadas é um processo que consome muito tempo. Além disso, geralmente se gasta muito tempo para aplicar essas imagens personalizadas de sistema operacional aos novos dispositivos para prepará-los para o uso antes de fornecê-los aos usuários finais. Com o Microsoft Intune e o Autopilot, é possível dar novos dispositivos seus usuários finais sem precisar criar, manter e aplicar imagens personalizadas do sistema operacional para os dispositivos. Quando usa o Intune para gerenciar dispositivos do Autopilot, você pode gerenciar políticas, perfis, aplicativos e muito mais, depois de registrá-los. Para obter uma visão geral dos benefícios, cenários e pré-requisitos, confira [Visão geral do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

Há quatro tipos de implantação do Autopilot:
- [Modo de Autoimplantação](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) para quiosques, sinalização digital ou um dispositivo compartilhado
- A [Assistência Individual](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) permite que parceiros ou a equipe de TI pré-provisionem um computador Windows 10 para que ele esteja totalmente configurado e pronto para a empresa; o [Autopilot para dispositivos existentes](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) permite que você implante com facilidade a versão mais recente do Windows 10 em seus dispositivos existentes
- [Modo controlado pelo usuário](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) para usuários tradicionais. 


## <a name="prerequisites"></a>Pré-requisitos
- [Assinatura do Intune](../fundamentals/licenses.md)
- [Registro automático no Windows habilitado](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Assinatura do Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](https://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Como obter o CSV para Importação no Intune

Para obter mais informações, confira Entender o cmdlet do PowerShell.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Adicionar Dispositivos

É possível adicionar dispositivos Windows Autopilot importando um arquivo CSV com as respectivas informações.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot** > **Importar**.

    ![Captura de tela de dispositivos Windows Autopilot](./media/enrollment-autopilot/autopilot-import-device.png)

2. Em **Adicionar dispositivos do Windows Autopilot**, navegue até um arquivo CSV que inclui a listagem de dispositivos que você pretende adicionar. O arquivo CSV precisa listar números de série, IDs de produto do Windows, hashes de hardware, marcas de grupo opcionais e usuário atribuído opcional. Você pode ter até 500 linhas na lista. Para saber como obter informações sobre o dispositivo, confira [Adicionar dispositivos ao Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#device-identification). Use o cabeçalho e o formato de linha mostrados abaixo:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Captura de tela de adição de dispositivos Windows Autopilot](./media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > Ao usar o upload de CSV para atribuir um usuário, atribua UPNs válidos. Se você atribuir um UPN inválido (nome de usuário incorreto), seu dispositivo poderá ficar inacessível até que você remova a atribuição inválida. Durante o upload de CSV, a única validação que executamos na coluna **Usuário atribuído** é para verificar se o nome de domínio é válido. Não podemos executar validação individual de UPNs para garantir que você atribuiu um usuário existente ou correto.

3. Escolha **Importar** para iniciar a importação de informações do dispositivo. A importação pode demorar vários minutos.

4. Concluída a importação, escolha **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot** > **Sincronizar**. É exibida uma mensagem informando que a sincronização está em andamento. O processo poderá levar alguns minutos para ser concluído, dependendo de quantos dispositivos estiverem sendo sincronizados.

5. Atualize a exibição para ver os novos dispositivos.

## <a name="create-an-autopilot-device-group"></a>Criar um grupo de dispositivos do Autopilot

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Grupos** > **Novo grupo**.
2. Na folha **Grupo**:
    1. Em **Tipo de grupo**, escolha **Segurança**.
    2. Digite o **Nome do grupo** e a **Descrição do grupo**.
    3. Em **Tipo de associação**, escolha **Atribuído** ou **Dispositivo Dinâmico**.
3. Se escolheu **Atribuído** como **Tipo de associação** na etapa anterior, na folha **Grupo**, escolha **Membros** e adicione dispositivos do Autopilot ao grupo.
    Os dispositivos do Autopilot ainda não registrados são dispositivos cujos nomes são iguais aos respectivos números de série.
4. Se escolheu **Dispositivo Dinâmico** como **Tipo de associação** anteriormente, na folha **Grupo**, escolha **Membros de dispositivo dinâmico** e digite qualquer um dos códigos a seguir na caixa **Regra avançada**. Somente os dispositivos do AutoPilot são coletados por essas regras, pois elas visam atributos que apenas os dispositivos do AutoPilot têm. A criação de um grupo com base em atributos não Autopilot não garantirá que os dispositivos incluídos no grupo estejam de fato registrados no Autopilot.
    - Se você pretende criar um grupo que inclua todos os dispositivos do Autopilot, digite: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - O campo de marcação de grupo do Intune é mapeado para o atributo OrderID em dispositivos do Azure AD. Se você pretende criar um grupo que inclua todos os dispositivos do Autopilot com uma marca de grupo específica (a OrderID do dispositivo do Azure AD), digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot com a ID da Ordem de Compra específica, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Depois de adicionar o código de **Regra avançada**, escolha **Salvar**.
5. Escolha **Criar**.  

## <a name="create-an-autopilot-deployment-profile"></a>Criar um perfil de implantação do Autopilot
Os perfis de implantação do Autopilot são usados para configurar os dispositivos do Autopilot. Você pode criar até 350 perfis por locatário.
1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Perfis de implantação** > **Criar perfil**.
2. Na página **Básico**, digite um **Nome** e uma **Descrição** opcional.

    ![Captura de tela da página Básico](./media/enrollment-autopilot/create-profile-basics.png)

3. Se quiser que todos os dispositivos nos grupos atribuídos sejam convertidos automaticamente no Autopilot, defina **Converter todos os dispositivos direcionados em Autopilot** como **Sim**. Todos os dispositivos de propriedade corporativa que não sejam Autopilot em grupos atribuídos serão registrados com o serviço de implantação do Autopilot. Os dispositivos de propriedade pessoal não serão convertidos para o Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o registra. Após um dispositivo ser registrado dessa maneira, desabilitar essa opção ou remover a atribuição de perfis não removerá o dispositivo do serviço de implantação do Autopilot. Em vez disso, é necessário [remover o dispositivo diretamente](enrollment-autopilot.md#delete-autopilot-devices).
4. Selecione **Avançar**.
5. Na página **Experiência de configuração inicial do usuário (OOBE)** para o **Modo de implantação**, escolha uma destas duas opções:
    - **Controlada pelo usuário**: Dispositivos com este perfil são associados ao usuário que faz o registro do dispositivo. As credenciais do usuário são necessárias para registrar o dispositivo.
    - **Autoimplantação (versão prévia)** : (exige o Windows 10, versão 1809 ou posterior) Os dispositivos com esse perfil não são associados ao usuário que registrou o dispositivo. As credenciais do usuário não são necessárias para registrar o dispositivo. Quando um dispositivo não tem nenhum usuário associado, as políticas de conformidade baseadas no usuário não são aplicadas a ele. Ao usar o modo de autoimplantação, somente as políticas de conformidade direcionadas ao dispositivo serão aplicadas.

    ![Captura de tela da página OOBE](./media/enrollment-autopilot/create-profile-outofbox.png)

   > [!NOTE]
   > As opções que aparecem esmaecidas ou sombreadas não são compatíveis com o modo de implantação selecionado.

6. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD**.
7. Configure as seguintes opções:
    - **Contrato de licença de usuário final (EULA)** : (Windows 10, versão 1709 ou posterior) Escolha se deseja mostrar o EULA aos usuários.
    - **Configurações de privacidade**: Escolha se deseja mostrar as configurações de privacidade aos usuários.
    >[!IMPORTANT]
    >O valor padrão da configuração Dados de diagnóstico varia entre as versões do Windows. Para dispositivos que executam o Windows 10, versão 1903, o valor padrão é definido como Completo durante a experiência inicial de uso. Para obter mais informações, consulte [Dados de diagnóstico do Windows](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Ocultar opções de alteração de conta (exige o Windows 10, versão 1809 ou posterior)** : Escolha **Ocultar** para impedir que as opções de alteração de conta sejam exibidas nas páginas de entrada e de erro de domínio da empresa. Essa opção exige que a [identidade visual da empresa seja configurada no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Tipo de conta de usuário**: Escolha o tipo de conta do usuário (usuário **Administrador** ou **Padrão**). Permitimos que o usuário que ingressa no dispositivo seja um Administrador local, para tanto só é necessário adicioná-lo ao grupo de Administradores locais. Não habilitamos o usuários como administrador padrão no dispositivo.
    - **Permitir White Glove OOBE** (exige o Windows 10, versão 1903 ou posterior; [requisitos físicos adicionais](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): Escolha **Sim** para permitir suporte a OOBE com Assistência Individual.
    - **Aplicar o modelo do nome do dispositivo** (requer o Windows 10, versão 1809 ou posterior e o tipo de ingresso no Azure AD): Escolha **Sim** para criar um modelo a ser usado ao nomear um dispositivo durante o registro. Os nomes precisam ter 15 caracteres ou menos e podem ter letras, números e hifens. Os nomes não podem conter apenas números. Use a [macro %%SERIAL%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) para adicionar um número de série específico do hardware. Ou use a [macro %RAND:x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) para adicionar uma cadeia de números aleatória, em que x é igual ao número de dígitos a serem adicionados. Só é possível fornecer uma correção prévia para dispositivos híbridos em um [perfil de ingresso no domínio](windows-autopilot-hybrid.md#create-and-assign-a-domain-join-profile). 
    - **Idioma (região)** \*: Escolha o idioma que pretende usar no dispositivo. Esta opção está disponível apenas quando você escolhe **Implantação automática** como **Modo de implantação**.
    - **Configurar automaticamente o teclado**\*: Se um **Idioma (Região)** estiver selecionado, escolha **Sim** para ignorar a página de seleção de teclado. Esta opção está disponível apenas quando você escolhe **Implantação automática** como **Modo de implantação**.
8. Selecione **Avançar**.
9. Na página **Marcas do Escopo**, você tem a opção de adicionar as marcas de escopo que deseja aplicar ao perfil. Saiba mais sobre marcas de escopo em [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](../fundamentals/scope-tags.md).
10. Selecione **Avançar**.
11. Na página **Atribuições**, escolha **Grupos selecionados** em **Atribuir a**.

    ![Captura de tela da página Atribuições](./media/enrollment-autopilot/create-profile-assignments.png)

12. Escolha **Selecionar grupos para incluir** e escolha os grupos que deseja incluir no perfil.
13. Se quiser excluir todos os grupos, escolha **Selecionar grupos para excluir** e escolha os grupos que deseja excluir.
14. Selecione **Avançar**.
15. Na página **Revisar + Criar**, escolha **Criar** para criar o perfil.

    ![Captura de tela da página Revisar](./media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> O Intune verificará periodicamente se há novos dispositivos nos grupos atribuídos e, em seguida, iniciará o processo de atribuição de perfis a esses dispositivos. Esse processo poderá levar vários minutos para ser concluído. Antes de implantar um dispositivo, verifique se esse processo foi concluído.  Você pode verificar em**Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot**, em que você deverá ver o status do perfil mudar de "Não atribuído" para "Atribuindo" e, por fim, para "Atribuído".

## <a name="edit-an-autopilot-deployment-profile"></a>Editar um perfil de implantação do Autopilot
Depois de criar um perfil de implantação do Autopilot, será possível editar determinadas partes do perfil de implantação.   

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Perfis de implantação**.
2. Selecione o perfil que deseja editar.
3. Selecione **Propriedades** à esquerda para alterar o nome ou a descrição do perfil de implantação. Clique em **Salvar** depois de fazer as alterações.
5. Clique em **Configurações** para alterar as configurações de OOBE. Clique em **Salvar** depois de fazer as alterações.

> [!NOTE]
> As alterações feitas no perfil se aplicam aos dispositivos atribuídos a ele. No entanto, o perfil atualizado somente será aplicado a um dispositivo que já foi registrado no Intune depois que o dispositivo for redefinido e registrado novamente.

## <a name="edit-autopilot-device-attributes"></a>Editar atributos de dispositivo do Autopilot
Depois de carregar um dispositivo do Autopilot, você poderá editar determinados atributos desse dispositivo.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot**.
2. Selecione o dispositivo a editar.
3. No painel à direita da tela, você pode editar o nome do dispositivo, a marca do grupo ou o Nome Amigável do Usuário (se você tiver atribuído um usuário).
4. Selecione **Salvar**.

> [!NOTE]
> É possível configurar nomes dos dispositivos para todos os dispositivos, mas eles serão ignorados em implantações conjuntas do Azure AD híbrido. O nome do dispositivo ainda vem do perfil de ingresso no domínio para dispositivos do Azure AD híbrido.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alertas para dispositivos não atribuídos do Windows Autopilot  <!-- 163236 -->  

Os alertas mostrarão quantos dispositivos do programa Autopilot não têm os perfis de implantação do Autopilot. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows Autopilot e informações detalhadas sobre eles.

Para receber alertas sobre dispositivos não atribuídos, no [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Visão geral** > **Alertas de registro** > **Dispositivos não atribuídos**.  

## <a name="autopilot-deployments-report"></a>Relatório de implantações do Autopilot
É possível ver detalhes sobre cada dispositivo implantado usando o Windows Autopilot.
Para ver o relatório, vá ao [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Monitor** > **Implantações do Autopilot**.
Os dados ficam disponíveis por 30 dias após a implantação.

Este relatório está em versão prévia. Atualmente, os registros de implantação de dispositivo são acionados apenas por novos eventos de registro no Intune. Isso significa que qualquer implantação que não acionar um novo registro do Intune não será coletada por esse relatório. Isso inclui qualquer tipo de redefinição que mantém o registro e a parte do usuário da assistência individual do Autopilot.

## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Atribuir um usuário a um dispositivo específico do Autopilot

Você pode atribuir um usuário a um dispositivo específico do Autopilot. Essa atribuição preenche previamente um usuário do Azure Active Directory na página de entrada [com a identidade visual da empresa](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) durante a instalação do Windows. Ela também permite que você defina um nome de saudação personalizado. Ela não preenche previamente nem modifica a entrada do Windows. Somente os usuários licenciados do Intune podem ser atribuídos dessa maneira.

Pré-requisitos: O Portal da Empresa do Azure Active Directory foi configurado e o Windows 10, versão 1809 ou posterior.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot** > escolha o dispositivo > **Atribuir usuário**.

    ![Captura de tela de Atribuir usuário](./media/enrollment-autopilot/assign-user.png)

2. Selecione um usuário do Azure licenciado para usar o Intune e escolha **Selecionar**.

    ![Captura de tela de Selecionar usuário](./media/enrollment-autopilot/select-user.png)

3. Na caixa **Nome Amigável de Usuário**, digite um nome amigável ou simplesmente aceite o padrão. Essa cadeia de caracteres é o nome amigável que será exibido quando o usuário entrar durante a Instalação do Windows.

    ![Captura de tela do nome amigável](./media/enrollment-autopilot/friendly-name.png)

4. Escolha **OK**.


## <a name="delete-autopilot-devices"></a>Excluir dispositivos Autopilot

É possível excluir os dispositivos do Windows Autopilot não registrados no Intune:

- Exclua os dispositivos do Windows Autopilot em **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot**. Escolha os dispositivos que você deseja excluir e depois escolha **Excluir**. A exclusão de dispositivo do Windows Autopilot pode levar alguns minutos para ser concluída.

Remover completamente um dispositivo do seu locatário exige que você exclua o dispositivo do Intune, o dispositivo do Azure Active Directory e os registros de dispositivo do Windows Autopilot. Isso pode ser feito do Intune:

1. Se os dispositivos estiverem registrados no Intune, será necessário primeiro [excluí-los da folha Todos os dispositivos do Intune](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Exclua os dispositivos em dispositivos do Azure Active Directory, em **Dispositivos** > **Dispositivos do Azure AD**.

3. Exclua os dispositivos do Windows Autopilot em **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** (em **Programa de Implantação do Windows Autopilot** >. Escolha os dispositivos que você deseja excluir e depois escolha **Excluir**. A exclusão de dispositivo do Windows Autopilot pode levar alguns minutos para ser concluída.

## <a name="using-autopilot-in-other-portals"></a>Usando o Autopilot em outros portais
Caso não tenha interesse no gerenciamento de dispositivo móvel, é possível usar o Autopilot em outros portais. Embora haja a opção de usar outros portais, é recomendável usar somente o Intune para gerenciar suas implantações do Autopilot. Quando você usar o Intune e outro portal, o Intune não será capaz de:  

- Exibir as alterações dos perfis criados no Intune, mas editados em outro portal
- Sincronizar os perfis criados em outro portal
- Exibir alterações em atribuições de perfil feitas em outro portal
- Sincronizar as atribuições de perfil feitas em outro portal
- Exibir as alterações na lista de dispositivos que foram feitas em outro portal

## <a name="windows-autopilot-for-existing-devices"></a>Windows Autopilot para dispositivos existentes

Você pode agrupar dispositivos Windows por uma ID de correlação ao registrar usando o [Autopilot para dispositivos existentes](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) por meio do Configuration Manager. A ID de correlação é um parâmetro do arquivo de configuração do Autopilot. O [atributo enrollmentProfileName do dispositivo Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) é definido automaticamente para que seja igual a "OfflineAutopilotprofile-\<correlator ID\>". Isso permite que os grupos dinâmicos arbitrários do Azure AD sejam criados com base na ID de correlação usando o atributo enrollmentprofileName.

>[!WARNING] 
> Porque a ID de correlação não está previamente listada no Intune, o dispositivo pode relatar qualquer ID de correlação que você desejar. Se o usuário criar uma ID de correlação correspondente a um nome de perfil do Autopilot ou Apple DEP, o dispositivo será adicionado a qualquer grupo de dispositivos dinâmico do Azure AD com base no atributo enrollmentProfileName. Para evitar esse conflito:
> - Sempre crie regras de grupo dinâmico que correspondam com o valor enrollmentProfileName *inteiro*
> - Nunca nomeie perfis do Autopilot ou do Apple DEP começando com "OfflineAutopilotprofile-".

## <a name="next-steps"></a>Próximas etapas
Após configurar o Windows Autopilot para dispositivos Windows 10 registrados, saiba como gerenciar esses dispositivos. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](../remote-actions/device-management.md)
