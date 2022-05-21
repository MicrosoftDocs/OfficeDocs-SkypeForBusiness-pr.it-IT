---
title: Gestire i criteri di routing delle chiamate di emergenza per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Scopri come usare e gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare come instradare le chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624120"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Gestire i criteri di routing delle chiamate di emergenza per il routing diretto

Se hai distribuito il [routing diretto](direct-routing-landing-page.md) nella tua organizzazione, puoi usare i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare come instradare le chiamate di emergenza. Un criterio di routing delle chiamate di emergenza determina se i servizi di emergenza avanzati sono abilitati per gli utenti a cui sono stati assegnati i criteri, i numeri utilizzati per chiamare i servizi di emergenza (ad esempio 911 nella Stati Uniti) e la modalità di instradamento delle chiamate ai servizi di emergenza. 

> [!Note]
> **Tieni presente che questi criteri di routing delle chiamate si applicano solo al routing diretto, non ai Piani per chiamate o a Connessione con operatore.**

È possibile gestire i criteri di routing delle chiamate di emergenza tramite i **criteri di emergenza VoiceEmergency**  >  nell'interfaccia di amministrazione di Microsoft Teams o usando Windows PowerShell. I criteri possono essere assegnati agli utenti e ai [siti di rete](cloud-voice-network-settings.md).

Per gli utenti, è possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo. Per i siti di rete è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio di routing delle chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Creare criteri personalizzati per il routing delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di emergenza VoiceE** >  quindi fare clic sulla scheda **Criteri routing chiamate**.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Per abilitare le chiamate di emergenza dinamiche, attiva **Chiamate di emergenza dinamiche**. Quando è abilitata una chiamata di emergenza dinamica, Teams recupera le informazioni sui criteri e sulla posizione dal servizio e include tali informazioni nell'ambito della chiamata di emergenza.
5. Definisci uno o più numeri di emergenza. A tale scopo, in **Numeri di emergenza** fare clic su **Aggiungi** e quindi eseguire le operazioni seguenti:
    1. **Stringa di chiamata di emergenza**: immetti la stringa di chiamata di emergenza. Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza e il percorso deve corrispondere esattamente a questa stringa di chiamata. 
        > [!NOTE]
        > **Per il routing diretto, Teams client non inviano più chiamate di emergenza con un segno "+" davanti alla stringa di chiamata di emergenza. Assicurati che il modello del percorso vocale che corrisponde a una stringa di chiamata di emergenza rifletta questa modifica.**
    2. **Maschera di emergenza**: per ogni numero di emergenza, è possibile specificare zero o più maschere di chiamata di emergenza. Una maschera di chiamata è il numero che si desidera tradurre nel valore della stringa di chiamata di emergenza. In questo modo è possibile comporre numeri di emergenza alternativi e mantenere la portata dei servizi di emergenza per la chiamata. <br>Ad esempio, si aggiunge 112 come maschera di chiamata di emergenza, ovvero il numero del servizio di emergenza per la maggior parte dell'Europa, e 911 come stringa di chiamata di emergenza. Un utente Teams europeo che è in visita potrebbe non sapere che 911 è il numero di emergenza nel Stati Uniti e quando comporlo 112, la chiamata viene effettuata al 911. Per definire più maschere di chiamata, separare ogni valore con un punto e virgola. Ad esempio, 112;212.
    3. **Record di utilizzo PSTN**: selezionare il record di utilizzo PSTN (Public Switched Telephone Network). Il record di utilizzo PSTN viene usato per determinare quale route viene usata per instradare le chiamate di emergenza da parte di utenti autorizzati a usarle. Il percorso associato a questo utilizzo deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al più vicino punto di risposta per la sicurezza pubblica (PSAP).

    > [!NOTE]
    > Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio. Ciò significa che per un criterio è possibile definire più numeri di emergenza e impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata una sola volta.

6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modificare i criteri di routing delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di emergenza VoiceE** >  quindi fare clic sulla scheda **Criteri routing chiamate**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Assegnare criteri personalizzati di routing delle chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Assegnare criteri di routing delle chiamate di emergenza personalizzati a un sito di rete

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile assegnare i criteri globali o i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare alla **topologia LocationsNetwork** >  e fare clic sulla scheda **Siti di rete**.
2. Selezionare il sito facendo clic a sinistra del nome e quindi su **Modifica**.
3. In **Criteri di routing delle chiamate di emergenza** seleziona il criterio e quindi fai clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Utilizzare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.

In questo esempio viene illustrato come assegnare un criterio denominato Criteri di routing delle chiamate di emergenza 1 al sito Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
