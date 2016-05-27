---
# required metadata

title: Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune
O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Ao conectar o armazenamento no Microsoft Intune, você pode gerenciar os aplicativos adquiridos por volume no console do Intune, por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode implantá-los como quaisquer outros aplicativos
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune
* O Intune bloqueará a implantação e a instalação de aplicativos se não houver licenças suficientes disponíveis

## Antes de começar
Examine as seguintes informações antes de iniciar a sincronização e a implantação de aplicativos da Windows Store for Business:
* Você deve configurar o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização. Para obter mais informações, consulte [Get ready to enroll devices in Microsoft Intune (Preparar-se para registrar dispositivos no Microsoft Intune)](get-ready-to-enroll-devices-in-microsoft-intune.md)
* Você deve se inscrever para uma conta na Windows Store for Business
* Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
* Aplicativos adquiridos da loja não poderão ser adicionados ao ou excluídos manualmente do Intune. Eles só poderão ser sincronizados com a Windows Store for Business.
* O Intune sincroniza apenas aplicativos online licenciados que você adquiriu da Windows Store for Business.

## Associe sua conta da Windows Store for Business ao Intune
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de fazer logon no repositório de negócios usando a mesma conta de locatário usada para fazer logon no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha Microsoft Intune.

Agora você pode continuar e configurar a sincronização no console do Intune.

## Configurar sincronização

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Administração**.
2. No espaço de trabalho **Administração**, expanda **Gerenciamento de Dispositivo Móvel** e clique em **Store for Business**.
3. Na página **Windows Store for Business**, faça o seguinte:
* Se você ainda tiver feito isso, clique no link para inscrever-se para a Windows Store for Business
* Quando você estiver inscrito, clique em **Configurar Sincronização**
4. Na caixa de diálogo **Configurar sincronização do aplicativo da Windows Store for Business**, selecione **Habilitar sincronização da Windows Store for Business**.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store for Business serão exibidos no console do Intune. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **OK**.

## Sincronizar aplicativos

1. Na página **Windows Store for Business**, clique em **Sincronizar agora** para sincronizar os aplicativos que você comprou da loja com o Intune.
2. No espaço de trabalho **Aplicativos**, clique em **Software Gerenciado** > **Software Licenciado** para exibir os aplicativos disponíveis e para verificar se seus aplicativos comprados foram importados corretamente.
Os aplicativos nesse nó são exibidos com o número total de licenças que você possui, junto com o número de licenças você tem disponível.

## Implantar aplicativos

Implante aplicativos da loja da mesma maneira que você implanta qualquer aplicativo do Intune. Para obter mais informações, consulte [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos no Microsoft Intune).
Quando você implanta um aplicativo da Windows Store for Business, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo implantado, você não poderá implantar mais cópias e deverá executar uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos
* Reduzir o escopo da implantação atual para o destino apenas os usuários para os quais você tiver licenças suficientes
* Comprar mais cópias do aplicativo da Windows Store for Business


### Consulte também
[Adicionar aplicativos a dispositivos móveis no Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=May16_HO1-->


