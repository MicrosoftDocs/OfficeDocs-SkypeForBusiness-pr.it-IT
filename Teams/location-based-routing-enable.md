---
title: Abilitare il routing basato sulla posizione per il routing diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a4646ba212c9e654ec06fca2fdd107b2671c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245129"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Abilitare il routing basato sulla posizione per il routing diretto

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Prima di eseguire la procedura descritta in questo articolo, verificare di aver letto il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) ed è stata completata la procedura descritta in [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).

Questo articolo descrive come abilitare il routing basato sulla posizione per il routing diretto. Dopo aver distribuito il routing diretto del sistema telefonico e configurato le aree geografiche, i siti e le subnet della rete, è possibile abilitare il routing basato sulla posizione. Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

 È necessario abilitare il routing basato sulla posizione per gli elementi seguenti:
- Utenti
- Siti di rete
- Configurazioni gateway
- Criteri di chiamata

## <a name="enable-location-based-routing-for-users"></a>Abilitare il routing basato sulla posizione per gli utenti

1. Usa il cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli usi PSTN. Per più usi, separare ogni utilizzo con una virgola.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Ad esempio:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Usa il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli usi appropriati della rete PSTN.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando si assegnano gli usi PSTN a un criterio di routing vocale, verificare di eseguire una delle operazioni seguenti:
    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito
    - USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.

    In questo esempio creiamo due nuovi criteri di routing vocale e li assegniamo agli usi PSTN. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Nella tabella seguente sono illustrati i criteri di routing vocale definiti in questo esempio. 
    
    ||Criteri di routing vocale 1|Criteri di routing vocale 2|
    |---------|---------|---------|
    |ID criterio vocale online   |Politica di routing vocale Delhi online   |Criteri di routing vocale di Hyderabad online    |
    |Usi PSTN online  |Lunga distanza  |Lunga distanza, locale, interno  |

3. Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono restrizioni di routing per l'applicazione.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing basato sulla posizione per i siti di rete
1.  Usa il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In questo esempio, consentiamo il routing basato sulla posizione per il sito Delhi e il sito Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    La tabella seguente mostra i siti abilitati per il routing basato sulla posizione in questo esempio.

    ||Sito 1 (Delhi)  |Sito 2 (Hyderabad)  |
    |---------|---------|---------|
|Nome sito    |Sito 1 (Delhi)    |Sito 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subnet     |Subnet 1 (Delhi)     |Subnet 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Abilitare il routing basato sulla posizione per i gateway
1. Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni sito di gateway o di rete. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Se più gateway sono associati a un sistema, ad esempio gateway o PBX, modifica ogni gateway per abilitare le restrizioni di routing basate sulla posizione. 

    In questo esempio creiamo una configurazione di gateway per ogni gateway. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).
    
2. Usa il cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing basato sulla posizione per i gateway che devono applicare restrizioni di routing. 

    Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In questo esempio, consentiamo il routing basato sulla posizione per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Non abilitare il routing basato sulla posizione per i gateway che non instradano le chiamate alla rete PSTN. Tuttavia, devi comunque associare il gateway al sito di rete in cui si trova il sistema. Questo perché le restrizioni di routing basate sul percorso devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite il gateway. In questo esempio, il routing basato sulla posizione non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ad esempio, un PBX) avranno restrizioni simili agli endpoint degli utenti di teams abilitati per il routing basato sulla posizione. Ciò significa che questi utenti possono effettuare e ricevere chiamate da e verso utenti di teams indipendentemente dalla posizione dell'utente. Possono anche effettuare e ricevere chiamate da e verso altri sistemi che non instradano le chiamate alla rete PSTN, ad esempio un endpoint connesso a un PBX diverso, indipendentemente dal sito di rete a cui è associato il sistema. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti delle chiamate e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti a imposte di routing basate sulla posizione. Queste chiamate devono usare solo gateway PSTN definiti come locali per tali sistemi. 

    La tabella seguente mostra la configurazione del gateway di quattro gateway in due diversi siti di rete: due collegati a gateway PSTN e due collegati a sistemi PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: Gateway 1 DEL-GW    |    True     |   Sito 1 (Delhi)      |
    |PstnGateway: Gateway 2 HYD-GW     |   True      |      Sito 2 (Hyderabad)   |
    |PstnGateway: Gateway 3 DEL-PBX    |    False     |     Sito 1 (Delhi)    |
    |PstnGateway: Gateway 4 HYD-PBX    |    False     |    Sito 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare il routing basato sulla posizione per i criteri di chiamata

Per applicare il routing basato sulla posizione per gli utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione dei pedaggi di PTSN. 

Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare il routing basato sulla posizione impedendo l'esclusione di pedaggio PSTN.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In questo esempio viene impedito l'esclusione del pedaggio PSTN ai criteri di chiamata di Utente1. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Argomenti correlati
- [Pianificare il routing basato sulla posizione per il routing diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Terminologia di routing basata sulla posizione](location-based-routing-terminology.md)
