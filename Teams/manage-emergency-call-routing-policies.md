---
title: Gestire i criteri del routing delle chiamate di emergenza
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di instradamento delle chiamate di emergenza in Microsoft Teams per impostare i numeri di emergenza e specificare come instradare le chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804676"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Gestire i criteri di instradamento delle chiamate di emergenza in Microsoft Teams

Se hai implementato [](direct-routing-landing-page.md) l'instradamento diretto del sistema telefonico nella tua organizzazione, puoi utilizzare i criteri di instradamento delle chiamate di emergenza in Microsoft Teams per impostare i numeri di emergenza e specificare come instradare le chiamate di emergenza. I criteri di instradamento delle chiamate di emergenza determinano se i servizi di emergenza avanzato sono abilitati per gli utenti a cui è assegnato il criterio, i numeri utilizzati per chiamare i servizi di emergenza (ad esempio il 911 negli Stati Uniti) e la modalità di instradamento delle chiamate ai servizi di emergenza.

Per gestire i criteri di instradamento delle chiamate di emergenza, è possibile accedere ai criteri per gli interventi di emergenza vocali nell'interfaccia di amministrazione di Microsoft Teams o tramite  >   Windows PowerShell. I criteri possono essere assegnati a utenti e siti [di rete.](cloud-voice-network-settings.md)

Per gli utenti, è possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo. Per i siti di rete è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio di instradamento delle chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in quel sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Creare un criterio personalizzato per l'instradamento delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda Criteri **di instradamento** chiamate.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Per abilitare le chiamate di emergenza dinamiche, attiva **chiamate di emergenza dinamiche.** Quando sono abilitate le chiamate di emergenza dinamiche, Teams recupera le informazioni sulla posizione e sui criteri dal servizio e include queste informazioni nell'ambito della chiamata di emergenza.
5. Definire uno o più numeri di emergenza. A tale scopo, in **Numeri di emergenza** fare clic su **Aggiungi** e quindi eseguire le operazioni seguenti:
    1. **Stringa di composizione per gli interventi di** emergenza: immettere la stringa di composizione per gli interventi di emergenza. Questa stringa di chiamata indica che si tratta di una chiamata di emergenza.
        > [!NOTE]
        > Per l'instradamento diretto, ci stiamo allontanando dai client di Teams per l'invio di chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza. Fino al completamento della transizione, il modello del percorso vocale che corrisponde a una stringa di composizione per gli interventi di emergenza deve garantire la corrispondenza per le stringhe che hanno e non hanno un segno "+" preceduto, ad esempio 911 e +911. Ad esempio, ^ \\ +?911 o *.
    2. **Maschera per le chiamate di** emergenza: per ogni numero di emergenza, è possibile specificare zero o più maschere di composizione per gli interventi di emergenza. Una maschera di composizione è il numero che si desidera tradurre nel valore della stringa di composizione per gli interventi di emergenza. In questo modo è possibile comporre numeri di emergenza alternativi e fare in modo che la chiamata raggiunga i servizi di emergenza. <br>Ad esempio, si aggiunge il 112 come maschera per le chiamate di emergenza, ovvero il numero dei servizi di emergenza per gran parte dell'Europa, e il 911 come stringa di composizione per gli interventi di emergenza. Un utente di Teams dall'Europa che sta visitando potrebbe non sapere che il 911 è il numero di emergenza negli Stati Uniti e, quando compone il 112, la chiamata viene effettuata al 911. Per definire più maschere di chiamata, separare ogni valore con un punto e virgola. Ad esempio, 112;212.
    3. **Record di utilizzo PSTN:** selezionare il record di utilizzo PSTN (Public Switched Telephone Network). Il record di utilizzo PSTN viene usato per determinare quale percorso utilizzare per instradare le chiamate di emergenza da parte di utenti autorizzati a usarle. Il percorso associato a questo utilizzo deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al più vicino punto di risposta per la sicurezza pubblica (PSAP, Public Safety Answering Point).

    > [!NOTE]
    > Le stringhe di composizione e le maschere di chiamata devono essere univoche all'interno di un criterio. Questo significa che per un criterio è possibile definire più numeri di emergenza e impostare più maschere di chiamata per una stringa di composizione, ma ogni stringa di composizione e maschera di chiamata deve essere utilizzata una sola volta.

6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-call-routing-policy"></a>Modificare i criteri di instradamento delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda Criteri **di instradamento** chiamate.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Assegnare un criterio personalizzato per l'instradamento delle chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Assegnare criteri personalizzati per l'instradamento delle chiamate di emergenza a un sito di rete

Usare il cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di instradamento per le chiamate di emergenza a un sito di rete.

Questo esempio mostra come assegnare un criterio denominato Criterio di instradamento chiamate di emergenza 1 al sito Sito1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
