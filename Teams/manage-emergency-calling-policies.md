---
title: Gestire i criteri per le chiamate di emergenza in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa succede quando un Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d4bfe0305939e287c262848dd25665898ba79a6
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605452"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gestire i criteri per le chiamate di emergenza in Microsoft Teams

Se l'organizzazione usa Piani per chiamate Microsoft, Connessione con operatore o Routing diretto come opzione di connettività [PSTN,](pstn-connectivity.md)è possibile usare i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.

È possibile impostare gli utenti a cui inviare una notifica e la modalità di notifica quando un utente a cui è assegnato il criterio chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri per inviare automaticamente una notifica al desk di sicurezza dell'organizzazione e fare in modo che ascoltino le chiamate di emergenza.  

Per gestire i criteri per le chiamate di emergenza, è possibile accedere ai criteri di emergenza vocale nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell. I criteri possono essere assegnati a utenti e [siti di rete.](cloud-voice-network-settings.md)

Per gli utenti, è possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo. Per i siti di rete, è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e l'utente si trova in tale sito di rete, i criteri assegnati al sito di rete sostituiscono i criteri assegnati all'utente.

## <a name="create-a-custom-emergency-calling-policy"></a>Creare criteri personalizzati per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda **Criteri chiamate.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Impostare la modalità di notifica alle persone dell'organizzazione, in genere il desk di sicurezza, quando viene effettuata una chiamata di emergenza. A questo scopo, in **Modalità di notifica** selezionare una delle opzioni seguenti:
    - **Invia solo notifica:** viene Teams messaggio di chat agli utenti e ai gruppi specificati.
    - Conferenza con audio disattivato e non in grado di riattivare l'audio: un messaggio di chat Teams viene inviato agli utenti e ai gruppi specificati dall'utente e può ascoltare (ma non partecipare) alla conversazione tra il **chiamante** e l'operatore PSAP.
    - Conferenza con audio disattivato ma in grado di riattivare l'audio: un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati dall'utente e può riattivare l'audio per ascoltare e partecipare alla conversazione tra il **chiamante** e l'operatore PSAP.
5.  Se è stata selezionata una delle modalità di  notifica Conferenza **in** modalità di notifica disattivata, nella casella Numeri da chiamare per le notifiche di emergenza è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. Ad esempio, immettere il numero del desk di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare la chiamata. Il telefono PSTN non può essere riattivato anche quando la modalità è impostata su Conferenza con audio disattivato, ma è possibile **riattivare l'audio.**
6. Cercare e selezionare uno o più utenti o gruppi, ad esempio il desk di sicurezza dell'organizzazione, per inviare una notifica quando viene effettuata una chiamata di emergenza.  La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza. È possibile ricevere una notifica a un massimo di 50 utenti.
7. Fare clic **su Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modificare i criteri per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda **Criteri chiamate.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare un criterio personalizzato per le chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Assegnare un criterio personalizzato per le chiamate di emergenza a un sito di rete

Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.

L'esempio seguente mostra come assegnare un criterio denominato Contoso Emergency Calling Policy 1 al sito Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di routing delle chiamate di emergenza in Teams](manage-emergency-call-routing-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)