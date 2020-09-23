---
title: Gestire i criteri delle chiamate di emergenza in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come usare e gestire i criteri delle chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217667"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gestire i criteri delle chiamate di emergenza in Microsoft Teams

Se l'organizzazione usa i [piani di chiamata](set-up-calling-plans.md) o il [routing diretto del sistema telefonico](direct-routing-landing-page.md)distribuito, è possibile usare i criteri per le chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza. Puoi impostare gli utenti a cui inviare una notifica e il modo in cui vengono informati quando un utente a cui viene assegnato il criterio chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente alla scrivania di sicurezza dell'organizzazione e farli ascoltare in chiamate di emergenza.  

Puoi gestire i criteri delle chiamate di emergenza **Voice**passando ai  >  **criteri di emergenza** vocale nell'interfaccia di amministrazione di Microsoft teams oppure usando Windows PowerShell. I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).

Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati. Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle. Per i siti di rete, è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.

## <a name="create-a-custom-emergency-calling-policy"></a>Creare un criterio di chiamata di emergenza personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di chiamata** .
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Impostare il modo in cui si vuole informare gli utenti dell'organizzazione, in genere il servizio di sicurezza, quando viene effettuata una chiamata di emergenza. A questo scopo, in **modalità notifica**selezionare una delle opzioni seguenti:
    - **Invia solo notifica**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati.
    - **In conferenza ma in sordina**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati, che possono ascoltare, ma non partecipare, nella conversazione tra il chiamante e l'operatore di PSAP.
    - **Conferenze in e sono riattivate** **(presto disponibile)**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati e possono riattivare l'audio per ascoltare e partecipare alla conversazione tra il chiamante e l'operatore di PSAP.
5.  Se è stata selezionata la modalità di notifica **in conferenza ma è disattivata** , nella casella **numeri da chiamare per le chiamate di emergenza** è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. Ad esempio, immettere il numero del servizio di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare la chiamata.
6. Cercare e selezionare uno o più utenti o gruppi, ad esempio il servizio di sicurezza dell'organizzazione, per avvisare quando viene effettuata una chiamata di emergenza.  La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza. Può essere notificato un massimo di 50 utenti.
7. Fare clic su **applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modificare un criterio per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di chiamata** .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare un criterio di chiamata di emergenza personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Assegnare un criterio di chiamata di emergenza personalizzato a un sito di rete

Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.

L'esempio seguente mostra come assegnare un criterio denominato criteri di chiamata di emergenza contoso 1 al sito di Microsoft1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di routing delle chiamate di emergenza in teams](manage-emergency-call-routing-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare criteri agli utenti in teams](assign-policies.md)
