---
title: Gestire i criteri per le chiamate di emergenza in Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa accade quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973140"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gestire i criteri per le chiamate di emergenza in Microsoft Teams

Se l'organizzazione utilizza [](direct-routing-landing-page.md)Piani per chiamate o un sistema telefonico distribuito, è possibile utilizzare criteri per le chiamate di emergenza in Microsoft Teams per definire cosa accade quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza. [](set-up-calling-plans.md) È possibile impostare le persone a cui inviare una notifica e la modalità di notifica quando un utente a cui è assegnato il criterio chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri in modo da inviare automaticamente una notifica al desk sicurezza dell'organizzazione e fare in modo che ascoltino le chiamate di emergenza.  

Per gestire i criteri per le chiamate di emergenza, è **possibile** accedere ai criteri per gli interventi di emergenza vocali nell'interfaccia di amministrazione di Microsoft Teams o tramite  >   Windows PowerShell. I criteri possono essere assegnati a utenti e siti [di rete.](cloud-voice-network-settings.md)

Per gli utenti, è possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo. Per i siti di rete è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in quel sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="create-a-custom-emergency-calling-policy"></a>Creare un criterio personalizzato per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda **Criteri chiamate.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Impostare la modalità di notifica alle persone dell'organizzazione, in genere il desk per la sicurezza, quando viene effettuata una chiamata di emergenza. A questo scopo, in **modalità notifica** selezionare una delle opzioni seguenti:
    - **Invia solo una notifica:** un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati.
    - Conferenza con audio disattivato e non possibile riattivare l'audio: un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati dall'utente e possono ascoltare (ma non partecipare) alla conversazione tra il **chiamante** e l'operatore PSAP.
    - Conferenza con audio disattivato ma in grado di riattivare l'audio: viene inviato un messaggio di chat di Teams agli utenti e ai gruppi specificati e possono riattivare l'audio per ascoltare e partecipare alla conversazione tra il **chiamante** e l'operatore PSAP.
5.  Se è stata  selezionata una delle due modalità  di notifica audio, nella casella Numeri da chiamare per le notifiche di emergenza è possibile immettere il numero di telefono PSTN di un utente o gruppo per chiamare e partecipare alla chiamata di emergenza. Ad esempio, immettere il numero del desk sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà poi ascoltare la chiamata. Il telefono PSTN non può essere riattivato anche quando la modalità è impostata su Conferenza con audio disattivato, ma **è possibile riattivare l'audio.**
6. Cercare e selezionare uno o più utenti o gruppi, ad esempio il desk sicurezza dell'organizzazione, per notificare una chiamata di emergenza.  La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza. È possibile in notificare un massimo di 50 utenti.
7. Fare clic **su Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>Modificare un criterio per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda **Criteri chiamate.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare un criterio personalizzato per le chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Assegnare criteri personalizzati per le chiamate di emergenza a un sito di rete

Usare il [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.

L'esempio seguente mostra come assegnare un criterio denominato Criterio chiamate di emergenza Contoso 1 al sito Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di instradamento delle chiamate di emergenza in Teams](manage-emergency-call-routing-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
