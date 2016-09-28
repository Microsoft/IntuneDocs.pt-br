---
title: Implantar o aplicativo Lookout for Work | Microsoft Intune
description: Configurar e implantar aplicativos Lookout for Work para Android.
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Configurar e implantar aplicativos Lookout for Work
Nesta versão, o aplicativo Lookout for Work em dispositivos Android que executam a versão 4.1 ou posterior tem suporte.
## Android
Esta seção discute como configurar e implantar o aplicativo Lookout for Work para dispositivos Android registrados no Intune.  
* Etapa 1: no [Console do administrador do Microsoft Intune](https://manage.microsoft.com), vá até **Aplicativos** e selecione **Adicionar Aplicativos**.   
* Etapa 2: na página **Configuração do Software** do editor, escolha **Link externo** e especifique a seguinte URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Não clique na caixa para exigir um navegador gerenciado.

* Etapa 3: na página **Descrição do software**, preencha as seguintes informações:
  * **Editor:** Lookout Mobile Security
  * **Nome:** Lookout for Work
  * **Descrição:** o Lookout oferece a melhor proteção contra ameaças móveis para manter seu dispositivo em segurança. Quando o aplicativo Lookout é instalado no dispositivo, ele o protege contra ameaças e alerta você e o administrador da empresa se alguma ameaça for encontrada.
  * **Categoria:** Gerenciamento de Computador
* Etapa 4: após a conclusão bem-sucedida, você verá uma mensagem **Upload de dados para o Microsoft Intune concluído com êxito**.

No Console do Intune, quando clicar em **Aplicativos**, agora você verá o aplicativo Lookout for Work na lista ![captura de tela da página de aplicativos do console do administrador do Intune mostrando os aplicativos Lookout for Work na lista](../media/mtp/lookout-app-listed-intune-console.png)

Etapa 5: neste ponto, o Intune sabe como implantar o aplicativo para Android Lookout for Work.   Você pode implantar o aplicativo para usuários, selecionando o aplicativo Lookout for Work mostrado na tela acima e selecionando **Gerenciar Implantação**.

Você precisa selecionar os mesmos usuários adicionados à opção de Gerenciamento de Registro no console da Consulta MTP.  Consulte a Etapa 3 na seção [Configurar sua assinatura da Consulta MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) para obter informações sobre como adicionar grupos de usuários à Consulta MTP.
>[!IMPORTANT]
> O assistente de implantação de aplicativo do Intune não está ciente dos grupos de usuários do Azure AD e usa os grupos de usuários do Intune em vez disso. Sendo assim, você precisa criar um grupo de usuários do Intune com base no grupo de usuários do Azure AD que está registrado no console da Consulta MTP, conforme descrito [neste](plan-your-user-and-device-groups.md) tópico.

Etapa 6: escolha a opção **Instalação Obrigatória** para exigir que o aplicativo Lookout seja instalado no dispositivo do usuário.

### Ativação do dispositivo
Com a opção **Instalação Obrigatória** selecionada para a implantação, o Intune enviará por push o aplicativo Lookout for Work para o dispositivo.   

Quando abrir o Lookout for Work no dispositivo, o usuário será solicitado a ativar o aplicativo e escolher a opção Entrar no Azure Active Directory. Uma explicação detalhada, com o fluxo do usuário final, pode ser encontrada nos tópicos a seguir:

* [Você é solicitado a instalar o Lookout for Work em seu dispositivo Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Próximas etapas
* [Habilitar a regra de proteção de dispositivo na política de conformidade](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


