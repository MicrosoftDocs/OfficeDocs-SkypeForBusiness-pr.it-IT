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
description: Informazioni su come abilitare il routing Location-Based per il routing diretto, incluso l'abilitazione per utenti, siti di rete, configurazioni di gateway e criteri di chiamata.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822916"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Abilitare l'instradamento basato sulla posizione per Instradamento diretto

Prima di eseguire i passaggi descritti in questo articolo, assicurarsi di aver letto Pianificare il [routing Location-Based](location-based-routing-plan.md) per il routing diretto e di aver completato la procedura descritta in Configurare le impostazioni di rete per il [routing Location-Based.](location-based-routing-configure-network-settings.md)

Questo articolo descrive come abilitare il routing Location-Based per il routing diretto. Dopo aver distribuito l'instradamento diretto del sistema telefonico e aver configurato le aree geografiche, i siti e le subnet di rete, sei pronto per abilitare il routing Location-Based rete. Per completare i passaggi descritti in questo articolo, è necessaria una certa familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere [Panoramica di Teams su PowerShell.](teams-powershell-overview.md)

 È necessario abilitare il routing Location-Based per le operazioni seguenti:
- Utenti
- Siti di rete
- Configurazioni di gateway
- Criteri di chiamata

È possibile usare [l'interfaccia di amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare Location-Based distribuzione.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

### <a name="enable-location-based-routing-for-users"></a>Abilitare il Location-Based distribuzione per gli utenti

1. Creare criteri di routing vocale e assegnare utilizzi PSTN al criterio. Quando si assegnano utilizzi PSTN a un criterio, assicurarsi di eseguire una delle operazioni seguenti:

    - Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN locale nel sito.
    - Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN situato in un'area geografica Location-Based non sono necessarie limitazioni di routing.
2. Assegnare il criterio di routing vocale agli utenti che richiedono l'applicazione di restrizioni di routing.

Per altre informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere Gestire i criteri [di routing vocale in Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing Location-Based per i siti di rete

Abilitare Location-Based routing dei siti che devono applicare restrizioni di routing. A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a Topologia rete posizioni, selezionare un sito di rete, fare clic su Modifica e quindi attivare il routing basato sulla  >   **posizione.**   

Per altre informazioni, vedere [Gestire la topologia della rete.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based per i gateway

Abilitare Location-Based routing ai gateway che instradino le chiamate a gateway PSTN che instradino le chiamate alla rete PSTN e associno il sito di rete in cui si trova il gateway. 

1. Nella barra di spostamento sinistra passare a **Voice** Direct Routing e quindi fare  >  clic sulla **scheda SBCs.**
2. Selezionare l'oggetto SBC e quindi fare clic su **Modifica.** 
3. In **Routing basato sulla posizione e ottimizzazione multimediale** attivare Abilita routing basato sulla **posizione.**
4. Specificare l'ID del sito del gateway e quindi impostare la modalità bypass.
5. Fare clic su **Salva**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare il routing Location-Based chiamate per i criteri di chiamata

Per applicare Location-Based routing dei messaggi a utenti specifici, configurare il criterio di chiamata dell'utente per evitare il bypass a numero verde PSTN. A tale scopo, attivare **l'impostazione Impedisci il bypass** a numero verde nel criterio di chiamata.

Per ulteriori informazioni, consulta [Criteri per le chiamate in Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>Utilizzo di PowerShell

### <a name="enable-location-based-routing-for-users"></a>Abilitare il Location-Based distribuzione per gli utenti

1. Usa il [cmdlet Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare l'utilizzo di PSTN. Per più utilizzi, separare ogni utilizzo con una virgola.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Ad esempio:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Usare il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli utilizzi appropriati di PSTN.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando si assegnano utilizzi PSTN a un criterio di routing vocale, assicurarsi di eseguire una delle operazioni seguenti:
    - Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN locale per il sito
    - Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN situato in un'area geografica Location-Based non sono necessarie limitazioni di routing.

    In questo esempio vengono creati due nuovi criteri di routing vocale a cui vengono assegnati utilizzi di PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    La tabella seguente mostra i criteri di routing vocale definiti in questo esempio. 
    
    ||Criteri di routing vocale 1|Criteri di routing vocale 2|
    |---------|---------|---------|
    |ID criteri vocali online   |Criteri di routing vocale online di Delhi   |Criteri per l'instradamento vocale online di enorabad    |
    |Utilizzi di PSTN online  |Long Distance  |Long Distance, Local, Internal  |

3. Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono l'applicazione di restrizioni di routing.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing Location-Based per i siti di rete

1.  Usare il cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing Location-Based e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In questo esempio viene abilitato il routing Location-Based per il sito di Delhi e per il sito di Arabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    La tabella seguente mostra i siti abilitati per il routing Location-Based distribuzione in questo esempio.

    ||Sito 1 (Delhi)  |Sito 2 (Arabad)  |
    |---------|---------|---------|
|Nome sito    |Sito 1 (Delhi)    |Sito 2 (Arabad)   
    |EnableLocationBasedRouting    |Vero    |Vero    |
    |Subnet     |Subnet 1 (Delhi)     |Subnet 2 (Arabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare Location-Based per i gateway

1. Usare il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni gateway o sito di rete. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Se a un sistema sono associati più gateway, ad esempio Gateway o PBX, modificare ogni gateway per abilitare Location-Based di routing. 

    In questo esempio viene creata una configurazione del gateway per ogni gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)
    
2. Usare il cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing Location-Based per i gateway che devono applicare restrizioni di routing. 

    Abilitare Location-Based routing ai gateway che instradino le chiamate a gateway PSTN che instradino le chiamate alla rete PSTN e associno il sito di rete in cui si trova il gateway.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In questo esempio viene abilitato il routing Location-Based per ogni gateway associato ai gateway PSTN nei siti di Delhi e Delrabad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Non abilitare il routing Location-Based per i gateway che non instradno le chiamate alla rete PSTN. Tuttavia, è comunque necessario associare il gateway al sito di rete in cui si trova il sistema. Questo è dovuto Location-Based che sia necessario applicare restrizioni di routing per le chiamate PSTN che raggiungono gli endpoint connessi tramite questo gateway. In questo esempio, Location-Based routing non è abilitato per ogni gateway associato ai sistemi PBX nei siti del Delhi e di Pbxrabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare il routing Location-Based chiamate per i criteri di chiamata

Per applicare Location-Based routing a utenti specifici, configurare i criteri vocali degli utenti in modo da evitare il bypass a pedaggio PTSN. 

Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare Location-Based routing evitando il bypass a pedaggio PSTN.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In questo esempio evitiamo il bypass a numero verde PSTN per i criteri di chiamata dell'Utente1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
