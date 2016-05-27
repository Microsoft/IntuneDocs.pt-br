---
# required metadata

title: Resolver conflitos de política do GPO e do Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Resolver conflitos de política do Microsoft Intune e GPO (Objetos de Política de Grupo)
O Intune usa políticas que ajudam a gerenciar as configurações nos computadores que você gerencia. Por exemplo, é possível usar uma política para controlar as configurações do Firewall do Windows nos computadores. Muitas das configurações do Intune são semelhantes às configurações que podem ser feitas com a Política de Grupo do Windows. No entanto, é possível que, às vezes, os dois métodos entrem em conflito.

Quando ocorrem conflitos, a Política de Grupo de nível de domínio tem precedência sobre a política do Intune, a menos que o computador não possa fazer logon no domínio. Nesse caso, a política do Intune é aplicada ao computador cliente.

## O que fazer se você estiver usando a política de grupo
Verifique se todas as políticas aplicadas não estão sendo gerenciadas pela política de grupo. Para evitar conflitos, é possível usar um ou mais dos seguintes métodos:

-   Mova seus computadores para uma OU (unidade organizacional) do Active Directory que não tenha configurações de Política de Grupo aplicadas antes de instalar o cliente do Intune. Você também pode bloquear a herança da Política de Grupo nas OUs que contenham computadores inscritos no Intune, aos quais você não deseja aplicar as configurações de Política de Grupo.

-   Use um filtro WMI ou um filtro de segurança para restringir somente GPOs (Objetos de Política de Grupo) para computadores não gerenciados pelo Intune. Para obter mais informações e exemplos de como fazer isso, consulte a seção [Como filtrar os Objetos de Política de Grupo existentes para evitar conflitos com a política do Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) abaixo.

-   Desabilite ou remova os Objetos da Política de Grupo que entram em conflito com as políticas do Intune.

Para obter mais informações sobre o Active Directory e a Política de Grupo do Windows, consulte a documentação do Windows Server.

## Como filtrar os GPOs (Objetos da Política de Grupo) existentes para evitar conflitos com a política do Intune
Identifique os GPOs (Objetos de Política de Grupo) com configurações que possam entrar em conflito com as políticas do Intune; use um dos métodos de filtragem a seguir para restringir esses GPOs somente aos computadores não gerenciados pelo Intune.

### Use filtros WMI
Os filtros WMI aplicam GPOs seletivamente a computadores que atendem às condições de uma consulta. Para aplicar um filtro WMI, implante uma instância da classe WMI em todos os computadores da empresa antes de inscrever qualquer um deles no serviço do Intune.

#### Para aplicar filtros WMI em um GPO

1.  Crie um arquivo de objeto de gerenciamento copiando e colando o seguinte em um arquivo de texto e, em seguida, salvando o conteúdo em um local apropriado, como **WIT.mof**. O arquivo contém a instância da classe WMI a ser implantada em computadores que deseja inscrever no serviço do Intune.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use um script de inicialização ou uma Política de Grupo para implantar o arquivo. Abaixo, segue o comando de implantação para o script de inicialização. A instância da classe WMI deve ser implantada antes da inscrição dos computadores cliente no serviço do Intune.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;caminho para o arquivo MOF&gt;\wit.mof**

3.  Execute um dos comandos a seguir para criar os filtros WMI, dependendo se o GPO que você deseja filtrar se aplica a computadores que são gerenciados usando o Intune ou a computadores que não são gerenciados usando o Intune.

    -   Para GPOs que se aplicam aos computadores que não são gerenciados com o Intune, use o seguinte:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Para GPOs que se aplicam aos computadores que são gerenciados com o Intune, use o seguinte:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edite o GPO no console do Gerenciamento de Política de Grupo para aplicar o filtro WMI que você criou na etapa anterior.

    -   Para GPOs que devem ser aplicados apenas a computadores que você deseja gerenciar usando o Intune, aplique o filtro **WindowsIntunePolicyEnabled=1**.

    -   Para GPOs que devem ser aplicados apenas a computadores que você não deseja gerenciar usando o Intune, aplique o filtro **WindowsIntunePolicyEnabled=0**.

Para obter mais informações sobre como aplicar filtros WMI na Política de Grupo, consulte a publicação do blog [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences (Filtragem de segurança, filtragem WMI e direcionamento no nível de item nas Preferências de Política de Grupo)](http://go.microsoft.com/fwlink/?LinkId=177883).

### Use filtros de grupo de segurança
A política de Grupo permite aplicar GPOs apenas aos grupos de segurança especificados na área **Filtragem de Segurança** do console do Gerenciamento de política de Grupo de um GPO selecionado. Por padrão, os GPOs aplicam-se aos **Usuários Autenticados**.

-   No snap-in **Usuários e Computadores do Active Directory**, crie uma novo grupo de segurança que contenha computadores e contas de usuário que você não deseja gerenciar usando o Intune. Por exemplo, você pode nomear o grupo **Fora do Microsoft Intune**.

-   No console de Gerenciamento de Política de Grupo, na guia **Delegação** do GPO selecionado, clique com o botão direito do mouse no novo grupo de segurança para delegar as permissões **Leitura** e **Aplicar Política de Grupo** a usuários e computadores no grupo de segurança. (As permissões para**Aplicar Política de Grupo** estão disponíveis na caixa de diálogo **Avançado** .)

-   Em seguida, aplique o filtro do novo grupo de segurança a um GPO selecionado e remova o filtro padrão **Usuários Autenticados** .

O novo grupo de segurança deve ser mantido como registro nas alterações de serviço do Intune.

### Consulte também
[Gerenciar PCs com Windows com o Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


