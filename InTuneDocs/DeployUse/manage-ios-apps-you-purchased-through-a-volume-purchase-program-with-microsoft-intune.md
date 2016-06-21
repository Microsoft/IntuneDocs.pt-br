---
# required metadata

title: Gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune
Algumas lojas de aplicativos oferecem a possibilidade de comprar várias licenças para um aplicativo que você deseja executar na empresa. Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda a gerenciar aplicativos comprados por meio de tal programa, importando as informações de licença da Windows Store e acompanhando quantas licenças você usou, além de evitar a instalação de mais cópias do seu aplicativo.

> [!Important]
> Atualmente, o Intune atribui licenças de aplicativo VPP do iOS para usuários, e não dispositivos. Por isso, os usuários finais devem digitar sua senha de ID da Apple para instalar o aplicativo.

## Gerenciar aplicativos adquiridos por volume para dispositivos iOS
Você adquire várias licenças para aplicativos iOS por meio do [VPP (Apple Volume Purchase Program) para Empresas](http://www.apple.com/business/vpp/). Isso envolve configurar uma conta de VPP da Apple no site da Apple e carregar o token de VPP da Apple no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## Antes de começar
Antes de começar, você precisará obter um token de VPP da Apple e carregá-lo na sua conta do Intune. Além disso, você deve compreender o seguinte:

* Cada organização pode ter apenas uma conta VPP e um token.
* Depois de associar uma conta de VPP da Apple ao Intune, não é possível associar posteriormente uma conta diferente. Por esse motivo, é muito importante que mais de uma pessoa tenha os detalhes da conta que você usa.
* Se você já tiver usado um token de VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. No entanto, você pode iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o VPP do iOS com o Intune, remova as contas de usuário VPP existentes criadas com outros fornecedores MDM. O Intune não sincronizará essas contas de usuário no Intune como medida de segurança. O Intune somente sincronizará os dados do serviço VPP da Apple que foram criados pelo Intune. 
* Não é possível implantar aplicativos VPP do iOS em dispositivos que tenham sido registrados usando o DEP (Protocolo de Registro de Dispositivo).

## Obter e carregar um token de VPP da Apple

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador** &gt; **iOS e Mac OS X** &gt;  **Volume Purchase Program**.

2.  Selecione o link **Conta da Apple VPP** e, se você ainda não fez isso, inscreva-se no Volume Purchase Program para Empresas. Depois de se inscrever, baixe o token de VPP da Apple para sua conta.

3.  Na página **Gerenciar VPP (Apple Volume Purchase Program)** do console do Intune, selecione **Carregar o token VPP**.

4.  Na caixa de diálogo **Carregar Token VPP**, digite ou cole o nome do token VPP e sua ID da Apple e selecione **Carregar**.

5.  Na caixa de diálogo de aviso, selecione a caixa de seleção para indicar que você entende que não é possível mudar para uma conta de VPP diferente posteriormente e selecione **Sim**.

Na página **Volume Purchase Program**, agora você pode exibir informações sobre o token de VPP da Apple, inclusive quando foi a última atualização, quando ela expirará e quando foi sincronizada pela última vez com o Intune.

Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## Implantar um aplicativo comprado por volume

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Software Gerenciado** &gt; **Aplicativos de Compra de Volume**. Esta lista mostra todos os aplicativos que foram sincronizados do serviço VPP da Apple.

2.  Escolha o aplicativo que deseja implantar, selecione **Gerenciar Implantação** e use as instruções no tópico [Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md) para concluir o carregamento, criação e implantação do aplicativo.

Quando você implantar o aplicativo como uma instalação **Obrigatória**, uma licença será usada por cada usuário que instalar o aplicativo.

Para recuperar uma licença, você deve alterar a ação de implantação para **Desinstalar**. A licença será recuperada quando o aplicativo for desinstalado.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. Eles devem fazer isso antes que a instalação do aplicativo prossiga.

> [!TIP] Examine a coluna **Status de Termos do VPP** para ver o status de aceitação para cada usuário ao qual o aplicativo foi implantado.

Se não houver nenhuma licença adicional disponível, a implantação falhará.

## Para monitorar aplicativos de VPP da Apple
Você pode monitorar quais aplicativos de VPP foram implantados e quantas licenças são usadas do espaço de trabalho **Aplicativos**, no nó **Software Gerenciado** &gt; **Aplicativos Adquiridos por Volume**.

> [!TIP] Você também pode usar o aplicativo **Filtros** para examinar o status de cada instalação do aplicativo.

### Consulte também
[Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=Jun16_HO2-->


