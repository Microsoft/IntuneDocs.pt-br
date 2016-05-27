---
# required metadata

title: Categorize os dispositivos com o mapeamento do grupo de dispositivos | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Categorize os dispositivos com o mapeamento do grupo de dispositivos no Microsoft Intune
Use o **mapeamento do grupo de dispositivos** do Microsoft Intune para agrupar dispositivos em categorias que você define para facilitar o gerenciamento desses dispositivos. 

O mapeamento do grupo de dispositivos usa o seguinte fluxo de trabalho:
1. Você cria grupos de dispositivos do Intune para cada categoria que você deseja usar.
2. Você configura regras de mapeamento do grupo de dispositivos que mapeiam a categoria escolhida para o grupo de dispositivos que você criou.
3. Quando os usuários finais registram seus dispositivos, eles devem escolher uma categoria entre as categorias configuradas. Depois que escolherem, o dispositivo será adicionado automaticamente ao grupo de dispositivos correspondente que você criou.
4. Você pode usar esses grupos de dispositivos ao implantar políticas e aplicativos.

Exemplos de categorias podem ser:
* Pessoal
* Dispositivo de ponto de venda
* Dispositivo de demonstração
* Vendas
* Contabilização
* Manager

No entanto, você pode configurar qualquer categoria que desejar.

## Como configurar o mapeamento do grupo de dispositivos
1. Para cada categoria de dispositivos que você deseja usar, crie um grupo de dispositivos do Intune. Para obter informações sobre como criar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).
2. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Administração**.
3. No espaço de trabalho **Administração**, expanda **Gerenciamento de Dispositivo Móvel** e clique em **Mapeamento do Grupo de Dispositivos**.
4. Na página **Mapeamento do Grupo de Dispositivos**, habilite o mapeamento do grupo de dispositivos.
5. Clique em **Adicionar** para criar uma nova regra de mapeamento.
6. Na caixa de diálogo **Add device group mapping rule** (Adicionar regra de mapeamento do grupo de dispositivos), digite o nome da categoria que você deseja criar e, na lista suspensa, escolha a coleção de dispositivos para a qual você deseja mapear essa categoria. Clique em **Adicionar** depois de concluir.
7. Quando terminar de adicionar categorias e grupos, clique em **Salvar**.

Agora, quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos que corresponde à categoria escolhida.

### Consulte também
[Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO1-->


