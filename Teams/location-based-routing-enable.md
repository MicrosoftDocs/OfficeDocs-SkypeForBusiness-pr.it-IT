---
title: Abilitare l'instradamento basato sulla posizione per Instradamento diretto
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare Location-Based Routing per il routing diretto, inclusa l'abilitazione per utenti, siti di rete, configurazioni di gateway e criteri di chiamata.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562195"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Abilitare l'instradamento basato sulla posizione per Instradamento diretto

Questo articolo descrive come abilitare Location-Based Routing per il routing diretto. Prima di seguire i passaggi descritti in questo articolo, assicurarsi di aver letto [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) e aver completato i passaggi descritti in [Configurare le impostazioni di rete per Location-Based Routing](location-based-routing-configure-network-settings.md).

 Dopo aver distribuito il routing diretto e configurato aree di rete, siti e subnet, è possibile abilitare Location-Based Routing. Per completare i passaggi descritti in questo articolo, è necessaria una certa familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere [Panoramica di PowerShell di Teams](teams-powershell-overview.md)

 È necessario abilitare Location-Based Routing per quanto segue:

- Utenti
- Siti di rete
- Configurazioni dei gateway
- Criteri di chiamata

È possibile usare [l'interfaccia di amministrazione di Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) per abilitare Location-Based routing.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

### <a name="enable-location-based-routing-for-users"></a>Abilitare Location-Based Routing per gli utenti

1. Creare un criterio di routing vocale e assegnare gli utilizzi PSTN al criterio. Quando si assegnano gli utilizzi PSTN a un criterio, assicurarsi di eseguire una delle operazioni seguenti:

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale nel sito.

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui non sono necessarie restrizioni di routing Location-Based.

2. Assegnare i criteri di routing vocale agli utenti che richiedono l'applicazione di restrizioni di routing.

Per altre informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere [Gestire i criteri di routing vocale in Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare Location-Based Routing per i siti di rete

Abilitare Location-Based Routing per i siti che devono applicare restrizioni di routing. A questo scopo, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Topologia rete** **percorsi** > , selezionare un sito di rete, fare clic su **Modifica** e quindi attivare **routing basato sulla posizione**.  

Per altre informazioni, vedere [Gestire la topologia della rete](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based Routing per gateway

Abilitare Location-Based Routing a gateway che instradano le chiamate a gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito di rete in cui si trova il gateway. 

1. Nel riquadro di spostamento sinistro vai a **Routing diretto** **vocale** >  e quindi fai clic sulla scheda **SBCs**.

2. Selezionare la scheda SBC e quindi fare clic su **Modifica**. 

3. In **Routing basato sulla posizione e ottimizzazione multimediale** attiva **Abilita routing basato sulla posizione**.

4. Specificare l'ID del sito del gateway e quindi impostare la modalità di esclusione.

5. Fare clic su **Salva**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare Location-Based Routing per i criteri di chiamata

Per applicare Location-Based Routing per utenti specifici, configurare i criteri per le chiamate dell'utente in modo da evitare il bypass a pagamento PSTN. A tale scopo, attiva l'impostazione **Impedisci bypass a pagamento** nei criteri per le chiamate.

Per altre informazioni, vedi [Criteri per le chiamate in Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Utilizzo di PowerShell

### <a name="enable-location-based-routing-for-users"></a>Abilitare Location-Based Routing per gli utenti

1. Per impostare gli utilizzi PSTN, usa il cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Per più utilizzi, separare ogni utilizzo con una virgola.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Ad esempio:

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Per creare un criterio di routing vocale per associare l'utente all'utilizzo PSTN appropriato, utilizza il cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando si assegnano utilizzi PSTN a un criterio di routing vocale, assicurarsi di eseguire una delle operazioni seguenti:

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale nel sito.

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui non sono necessarie restrizioni di routing Location-Based.

    L'esempio seguente crea due nuovi criteri di routing vocale e assegna loro gli utilizzi PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    La tabella seguente mostra i criteri di routing vocale definiti in questo esempio. 
    
    |&nbsp;|Criteri di routing vocale 1|Criteri di routing vocale 2|
    |---------|---------|---------|
    |ID dei criteri vocali online   |Politica di routing vocale online di Delhi   |Criteri di routing vocale online di Hyderabad    |
    |Utilizzo di PSTN online  |Long Distance  |Long Distance, Local, Internal  |

3. Per associare i criteri di routing vocale online agli utenti che richiedono l'applicazione di restrizioni di routing, utilizzare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare Location-Based Routing per i siti di rete

1. Per abilitare Location-Based Routing e associare criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing, utilizzare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In questo esempio viene abilitato Location-Based Routing per il sito di Delhi e quello di Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    La tabella seguente mostra i siti abilitati per Location-Based Routing in questo esempio.

    |&nbsp;|Sito 1 (Delhi)  |Sito 2 (Hyderabad)  |
    |---------|---------|---------|
    |Nome sito    |Sito 1 (Delhi)    |Sito 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Vero    |Vero    |
    |Subnet     |Subnet 1 (Delhi)     |Subnet 2 (Hyderabad)     |


### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based Routing per gateway

1. Per creare una configurazione del gateway per ogni gateway o sito di rete, usa il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Se a un sistema sono associati più gateway (ad esempio Gateway o PBX), modificare ogni gateway per abilitare Location-Based restrizioni di routing. 

    L'esempio seguente crea una configurazione del gateway per ogni gateway. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md).
    
2. Per abilitare Location-Based Routing per i gateway che devono applicare restrizioni di routing, usare il cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    Abilitare Location-Based Routing a gateway che instradano le chiamate a gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito di rete in cui si trova il gateway.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   L'esempio seguente abilita Location-Based Routing per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    Non abilitare Location-Based Routing per gateway che non instradano le chiamate alla rete PSTN. Tuttavia, è comunque necessario associare il gateway al sito di rete in cui si trova il sistema. Ciò è dovuto al fatto che Location-Based restrizioni di routing devono essere applicate per le chiamate PSTN che raggiungono endpoint connessi tramite questo gateway. In questo esempio, Location-Based Routing non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare Location-Based Routing per i criteri di chiamata

Per applicare Location-Based Routing per utenti specifici, configura i criteri vocali degli utenti per evitare il bypass a pagamento PTSN. 

Per abilitare Location-Based routing impedendo il bypass a pagamento PSTN, utilizzare il cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

In questo esempio impediamo il bypass a pagamento PSTN ai criteri di chiamata dell'Utente1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità voce cloud in Teams](cloud-voice-network-settings.md)