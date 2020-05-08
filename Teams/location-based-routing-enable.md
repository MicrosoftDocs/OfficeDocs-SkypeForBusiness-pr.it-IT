---
title: Abilitare l'instradamento basato sulla posizione per Instradamento diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare il routing basato sulla posizione per il routing diretto, incluso l'abilitazione per gli utenti, i siti di rete, le configurazioni dei gateway e i criteri di chiamata.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158993"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Abilitare l'instradamento basato sulla posizione per Instradamento diretto

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Prima di eseguire la procedura descritta in questo articolo, verificare di aver letto il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) ed è stata completata la procedura descritta in [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).

Questo articolo descrive come abilitare il routing basato sulla posizione per il routing diretto. Dopo aver distribuito il routing diretto del sistema telefonico e configurato le aree geografiche, i siti e le subnet della rete, è possibile abilitare il routing basato sulla posizione. Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

 È necessario abilitare il routing basato sulla posizione per gli elementi seguenti:
- Utenti
- Siti di rete
- Configurazioni gateway
- Criteri di chiamata

Puoi usare l'interfaccia di [amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare il routing basato sulla posizione.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

### <a name="enable-location-based-routing-for-users"></a>Abilitare il routing basato sulla posizione per gli utenti

1. Creare un criterio di routing vocale e assegnare gli usi PSTN al criterio. Quando si assegnano gli usi PSTN a un criterio, verificare di eseguire una delle operazioni seguenti:

    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito.
    - USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.
2. Assegnare i criteri di routing vocale agli utenti che richiedono restrizioni di routing per l'applicazione.

Per ulteriori informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere [gestire i criteri di routing vocale in Microsoft teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing basato sulla posizione per i siti di rete

Abilitare il routing basato sulla posizione per i siti che devono applicare restrizioni di routing. A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alla**topologia di rete** **locations** > , seleziona un sito di rete, fai clic su **modifica**e quindi attiva **routing basato sulla posizione**.  

Per altre informazioni, vedere [gestire la topologia di rete](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare il routing basato sulla posizione per i gateway

Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway. 

1. Nella barra di spostamento sinistra, passa a routing **vocale** > **diretto**e quindi fai clic sulla scheda **SBCS** .
2. Selezionare l'SBC e quindi fare clic su **modifica**. 
3. In **ottimizzazione di routing e media basato sulla posizione**attivare **Abilita routing basato sulla posizione**.
4. Specificare l'ID sito del gateway e quindi impostare la modalità di bypass.
5. Fare clic su **Salva**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare il routing basato sulla posizione per i criteri di chiamata

Per applicare il routing basato sulla posizione per utenti specifici, configurare i criteri di chiamata dell'utente per evitare il bypass PSTN. A questo scopo, attiva l'impostazione **Impedisci esclusione di pedaggio** nel criterio di chiamata.

Per altre informazioni, vedere [chiamare i criteri in teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Utilizzo di PowerShell

### <a name="enable-location-based-routing-for-users"></a>Abilitare il routing basato sulla posizione per gli utenti

1. Usa il cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli usi PSTN. Per più usi, separare ogni utilizzo con una virgola.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Ad esempio:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Usa il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli usi appropriati della rete PSTN.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando si assegnano gli usi PSTN a un criterio di routing vocale, verificare di eseguire una delle operazioni seguenti:
    - Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito
    - USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.

    In questo esempio creiamo due nuovi criteri di routing vocale e li assegniamo agli usi PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Nella tabella seguente sono illustrati i criteri di routing vocale definiti in questo esempio. 
    
    ||Criteri di routing vocale 1|Criteri di routing vocale 2|
    |---------|---------|---------|
    |ID criterio vocale online   |Politica di routing vocale Delhi online   |Criteri di routing vocale di Hyderabad online    |
    |Usi PSTN online  |Lunga distanza  |Lunga distanza, locale, interno  |

3. Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono restrizioni di routing per l'applicazione.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Abilitare il routing basato sulla posizione per i siti di rete

1.  Usa il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In questo esempio, consentiamo il routing basato sulla posizione per il sito Delhi e il sito Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    La tabella seguente mostra i siti abilitati per il routing basato sulla posizione in questo esempio.

    ||Sito 1 (Delhi)  |Sito 2 (Hyderabad)  |
    |---------|---------|---------|
|Nome sito    |Sito 1 (Delhi)    |Sito 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Vero    |Vero    |
    |Subnet     |Subnet 1 (Delhi)     |Subnet 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Abilitare il routing basato sulla posizione per i gateway

1. Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni sito di gateway o di rete. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Se più gateway sono associati a un sistema, ad esempio gateway o PBX, modifica ogni gateway per abilitare le restrizioni di routing basate sulla posizione. 

    In questo esempio creiamo una configurazione di gateway per ogni gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).
    
2. Usa il cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing basato sulla posizione per i gateway che devono applicare restrizioni di routing. 

    Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In questo esempio, consentiamo il routing basato sulla posizione per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Non abilitare il routing basato sulla posizione per i gateway che non instradano le chiamate alla rete PSTN. Tuttavia, devi comunque associare il gateway al sito di rete in cui si trova il sistema. Questo perché le restrizioni di routing basate sul percorso devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite il gateway. In questo esempio, il routing basato sulla posizione non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.

    ```PowerShell
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
    |PstnGateway: Gateway 1 DEL-GW    |    Vero     |   Sito 1 (Delhi)      |
    |PstnGateway: Gateway 2 HYD-GW     |   Vero      |      Sito 2 (Hyderabad)   |
    |PstnGateway: Gateway 3 DEL-PBX    |    Falso     |     Sito 1 (Delhi)    |
    |PstnGateway: Gateway 4 HYD-PBX    |    Falso     |    Sito 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-calling-policies"></a>Abilitare il routing basato sulla posizione per i criteri di chiamata

Per applicare il routing basato sulla posizione per gli utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione dei pedaggi di PTSN. 

Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare il routing basato sulla posizione impedendo l'esclusione di pedaggio PSTN.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In questo esempio viene impedito l'esclusione del pedaggio PSTN ai criteri di chiamata di Utente1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali di cloud in teams](cloud-voice-network-settings.md)
