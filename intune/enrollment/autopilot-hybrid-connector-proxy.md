---
title: Definir configurações de proxy para o conector do Intune para o Active Directory
description: Aborda como configurar o conector do Intune para o Active Directory trabalhar com os servidores proxy locais existentes.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11537902e8306d753d6c3e144e0ac15f90ab3b51
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503283"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Trabalhar com servidores proxy locais existentes

Este artigo explica como configurar o conector do Intune para o Active Directory trabalhar com servidores proxy de saída. Destina-se a clientes com ambientes de rede que já têm proxies.

Para saber mais sobre como funcionam os conectores, confira [Noções básicas sobre conectores de Proxy de Aplicativo do Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Ignorar proxies de saída

Os conectores têm componentes de sistema operacional subjacentes que fazem solicitações de saída. Esses componentes tentam localizar automaticamente um servidor proxy na rede usando a WPAD (Descoberta Automática de Proxy Web).

Os componentes do sistema operacional tentam localizar um servidor proxy realizando uma pesquisa de DNS para wpad.domainsuffix. Se a pesquisa for resolvida na DNS, uma solicitação HTTP será feita para o endereço IP para wpad.dat. Essa solicitação torna-se o script de configuração de proxy em seu ambiente. O conector usa esse script para selecionar um servidor proxy de saída. No entanto, o tráfego do conector não pode continuar ainda por causa das configurações adicionais necessárias no proxy.

É possível configurar o conector para ignorar o proxy local para que ele use a conectividade direta com os serviços do Azure. Recomendamos essa abordagem, desde que a política de rede a permita, porque isso significa que você tem uma configuração a menos para manter.

Para desabilitar o uso do proxy de saída para o conector, edite o arquivo :\Arquivos de Programas\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config e adicione o endereço e a porta do proxy à seção mostrada no exemplo de código:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```

Para verificar se o serviço do Atualizador do Conector também ignora o proxy, faça uma alteração semelhante em C:\Arquivos de Programas\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Faça cópias dos arquivos originais caso seja necessário reverter para os arquivos .config padrão.

Após a modificação dos arquivos de configuração, será necessário reiniciar o serviço do Conector do Intune. 

1. Abra **services.msc**.
2. Localize e selecione o **Serviço do Intune ODJConnector**.
3. Selecione **Reiniciar**.

![Captura de tela da reinicialização do serviço](./media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Próximas etapas

[Gerenciar seus dispositivos](../remote-actions/device-management.md)