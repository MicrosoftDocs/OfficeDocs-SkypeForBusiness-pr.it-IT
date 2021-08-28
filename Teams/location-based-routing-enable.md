---
title: Abilitare l'instradamento basato sulla posizione per Instradamento diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare Location-Based routing per il routing diretto, inclusa l'abilitazione per utenti, siti di rete, configurazioni di gateway e criteri di chiamata.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51a7aa95eb74e7baa199ac8d43dd5f89b352c95c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584500"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Abilitare l'instradamento basato sulla posizione per Instradamento diretto

Prima di seguire i passaggi descritti in questo articolo, verificare di aver letto Pianificare il routing [Location-Based per](location-based-routing-plan.md) il routing diretto e di aver completato i passaggi descritti in Configurare le impostazioni di rete per Location-Based [Routing](location-based-routing-configure-network-settings.md).

Questo articolo descrive come abilitare il routing Location-Based routing diretto. Dopo aver distribuito Sistema telefonico routing diretto e aver configurato aree di rete, siti e subnet, è possibile abilitare Location-Based routing. Per completare i passaggi descritti in questo articolo, è necessaria una certa familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere Teams [panoramica di PowerShell.](teams-powershell-overview.md)

 È necessario abilitare Location-Based routing per gli elementi seguenti:
- Utenti
- Siti di rete
- Configurazioni del gateway
- Criteri di chiamata

È possibile usare [l'interfaccia Microsoft Teams o](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l per abilitare Location-Based routing.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

### <a name="enable-location-based-routing-for-users"></a>Abilitare Location-Based routing per gli utenti

1. Creare un criterio di routing vocale e assegnare gli utilizzi PSTN al criterio. Quando si assegnano gli utilizzi PSTN a un criterio, assicurarsi di eseguire una delle operazioni seguenti:

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito.
    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area in cui Location-Based non sono necessarie restrizioni di routing.
2. Assegnare i criteri di routing vocale agli utenti che richiedono l'applicazione di restrizioni di routing.

Per altre informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere Gestire i criteri di routing vocale [in Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing Location-Based per i siti di rete

Abilitare Location-Based routing per i siti che devono applicare restrizioni di routing. A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a Topologia di rete percorsi, selezionare un sito di rete, fare clic su Modifica e quindi attivare il routing basato sulla   >   **posizione.**   

Per altre informazioni, vedere [Gestire la topologia di rete.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based routing per i gateway

Abilitare Location-Based routing ai gateway che instradare le chiamate a gateway PSTN che instradare le chiamate alla rete PSTN e associare il sito di rete in cui si trova il gateway. 

1. Nel riquadro di spostamento sinistro passare a **Routing**  >  **diretto vocale** e quindi fare clic sulla scheda **SBC.**
2. Selezionare il valore SBC e quindi fare clic su **Modifica.** 
3. In **Routing basato sulla posizione e ottimizzazione multimediale** attivare Abilita routing basato sulla **posizione.**
4. Specificare l'ID del sito gateway e quindi impostare la modalità di bypass.
5. Fare clic su **Salva**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare Location-Based routing per i criteri di chiamata

Per applicare Location-Based routing per utenti specifici, configurare i criteri di chiamata dell'utente per impedire il bypass a pedaggio PSTN. A questo scopo, attivare l'impostazione **Impedisci bypass** a pedaggio nel criterio di chiamata.

Per altre informazioni, vedere [Criteri di chiamata in Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Utilizzo di PowerShell

### <a name="enable-location-based-routing-for-users"></a>Abilitare Location-Based routing per gli utenti

1. Usare il cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli utilizzi PSTN. Per più utilizzi, separare ogni utilizzo con una virgola.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Ad esempio:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Usare il cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli utilizzi PSTN appropriati.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, assicurarsi di eseguire una delle operazioni seguenti:
    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito
    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area in cui Location-Based non sono necessarie restrizioni di routing.

    In questo esempio vengono creati due nuovi criteri di routing vocale e vengono assegnati gli utilizzi PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    La tabella seguente mostra i criteri di routing vocale definiti in questo esempio. 
    
    ||Criteri di routing vocale 1|Criteri di routing vocale 2|
    |---------|---------|---------|
    |ID dei criteri vocali online   |Criteri di routing vocale online di Delhi   |Criteri di routing vocale online di Hyderabad    |
    |Utilizzi PSTN online  |Lunga distanza  |Interurbana, Locale, Interna  |

3. Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono l'applicazione di restrizioni di routing.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing Location-Based per i siti di rete

1.  Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing Location-Based e associare criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In questo esempio viene abilitato Location-Based routing per il sito di Delhi e il sito di Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    La tabella seguente mostra i siti abilitati per Location-Based routing in questo esempio.

    ||Sito 1 (Delhi)  |Sito 2 (Hyderabad)  |
    |---------|---------|---------|
|Nome del sito    |Sito 1 (Delhi)    |Sito 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Vero    |Vero    |
    |Subnet     |Subnet 1 (Delhi)     |Subnet 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based routing per i gateway

1. Usare il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni gateway o sito di rete. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Se a un sistema sono associati più gateway, ad esempio Gateway o PBX, modificare ogni gateway per abilitare Location-Based di routing. 

    In questo esempio viene creata una configurazione del gateway per ogni gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Per altre informazioni, vedere [Configurare il routing diretto.](direct-routing-configure.md)
    
2. Usare il cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing Location-Based per i gateway che devono applicare restrizioni di routing. 

    Abilitare Location-Based routing ai gateway che instradare le chiamate a gateway PSTN che instradare le chiamate alla rete PSTN e associare il sito di rete in cui si trova il gateway.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In questo esempio viene abilitato Location-Based routing per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad.In this example, we enable Location-Based routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Non abilitare il routing Location-Based per i gateway che non instradare le chiamate alla rete PSTN. Tuttavia, è comunque necessario associare il gateway al sito di rete in cui si trova il sistema. Questo avviene perché Location-Based le restrizioni di routing devono essere applicate per le chiamate PSTN che raggiungono gli endpoint connessi tramite questo gateway. In questo esempio, Location-Based routing non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare Location-Based routing per i criteri di chiamata

Per applicare Location-Based routing per utenti specifici, configurare i criteri vocali degli utenti in modo da impedire il bypass a pedaggio PTSN. 

Usare il cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare Location-Based il routing dei messaggi impedendo il bypass a pedaggio PSTN.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In questo esempio viene impedito il bypass a pedaggio PSTN ai criteri di chiamata dell'utente1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)