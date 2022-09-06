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
description: Informazioni su come usare e gestire i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa accade quando un utente di Teams nell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 658e7191a821069d3fa9b13e02cc7cbcdfb29413
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606555"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gestire i criteri per le chiamate di emergenza in Microsoft Teams

Se l'organizzazione utilizza Piani per chiamate Microsoft, Operator Connect, Connessione con operatore di telefonia mobile (versione di anteprima pubblica) o Routing diretto come [opzione di connettività PSTN](pstn-connectivity.md), è possibile usare i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa accade quando un utente di Teams nell'organizzazione effettua una chiamata di emergenza.

È possibile impostare chi deve inviare una notifica e come riceverla quando un utente a cui sono stati assegnati i criteri chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri in modo da informare automaticamente il security desk dell'organizzazione e fare in modo che vengano ascoltate durante le chiamate di emergenza.  

Puoi gestire i criteri per le chiamate di emergenza accedendo ai **criteri di emergenza** **vocale** >  nell'interfaccia di amministrazione di Microsoft Teams o usando Windows PowerShell. I criteri possono essere assegnati agli utenti e ai [siti di rete](cloud-voice-network-settings.md).

Per gli utenti, è possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo. Per i siti di rete è possibile creare e assegnare criteri personalizzati.

Se hai assegnato un criterio di chiamata di emergenza a un sito di rete e a un utente e se quell'utente si trova in quel sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="create-a-custom-emergency-calling-policy"></a>Creare criteri personalizzati per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Criteri di emergenza** **vocale** >  e quindi fai clic sulla scheda **Criteri per le chiamate**.

2. Fare clic su **Aggiungi**.

3. Immettere un nome e una descrizione per il criterio.

4. Impostare la **modalità di ricerca della posizione esterna** su attivato per consentire agli utenti finali di configurare il proprio indirizzo per gli interventi di emergenza quando lavorano da un percorso di rete esterno alla rete aziendale.

5. Imposta la modalità di notifica alle persone dell'organizzazione, in genere il security desk, quando viene effettuata una chiamata di emergenza. A tale scopo, in **Modalità di notifica** seleziona una delle opzioni seguenti:

    - **Invia solo notifica**: viene inviato un messaggio di chat di Teams agli utenti e ai gruppi specificati.
    - **Con conferenza disattivata e non è possibile riattivare l'audio**: un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati e possono ascoltare (ma non partecipare) alla conversazione tra il chiamante e l'operatore PSAP.
    - **Con conferenza disattivata ma in grado di riattivare l'audio**: un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati e possono riattivare l'audio per ascoltare e partecipare alla conversazione tra il chiamante e l'operatore PSAP.

6.  Imposta la **dichiarazione di non responsabilità per i servizi di emergenza** per visualizzare un banner per ricordare agli utenti finali di confermare la loro posizione per gli interventi di emergenza.

7.  Se è stata selezionata una delle opzioni conferenza in modalità di notifica **disattivata** , nella casella **Numeri per comporre le notifiche per le chiamate di emergenza** , è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. Ad esempio, immettere il numero del desk di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltarla. Non è possibile riattivare l'audio del telefono PSTN anche se la modalità è impostata su **Con conferenza disattivata, ma è possibile riattivarla**.

8. Cerca e seleziona uno o più utenti o gruppi, ad esempio il security desk dell'organizzazione, per avvisare quando viene effettuata una chiamata di emergenza.  La notifica può essere inviata a indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza. È possibile ricevere una notifica a un massimo di 50 utenti.

9. Fare clic su **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modificare i criteri per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Criteri di emergenza** **vocale** >  e quindi fai clic sulla scheda **Criteri per le chiamate**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare criteri personalizzati per le chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Assegnare criteri personalizzati per le chiamate di emergenza a un sito di rete

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile assegnare i criteri globali o i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Topologia rete** **percorsi** >  e fare clic sulla scheda **Siti di rete**.
2. Selezionare il sito facendo clic a sinistra del nome e quindi su **Modifica**.
3. In **Criteri per le chiamate di emergenza** seleziona il criterio e quindi fai clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell
Utilizzare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di chiamata di emergenza a un sito di rete.

Nell'esempio seguente viene illustrato come assegnare un criterio denominato Contoso Emergency Calling Policy 1 al sito Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di routing delle chiamate di emergenza in Teams](manage-emergency-call-routing-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
