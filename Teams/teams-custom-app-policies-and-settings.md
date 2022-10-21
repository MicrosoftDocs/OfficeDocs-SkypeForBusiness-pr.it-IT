---
title: Gestire le impostazioni e i criteri delle app personalizzate
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire le impostazioni e i criteri delle app personalizzate per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 2bbd6d048fdb3e2f0a0d4f9723552127161d25f8
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656012"
---
# <a name="manage-custom-apps-and-settings-in-teams-admin-center"></a>Gestire app e impostazioni personalizzate nell'interfaccia di amministrazione di Teams

<!--- TBD: Describe custom apps
--->

L'amministratore di Teams usa i criteri e le impostazioni delle app personalizzate per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft Teams. Gli amministratori decidono quali utenti possono caricare app personalizzate, mentre gli amministratori e i proprietari di team possono determinare se l'aggiunta di app personalizzate a team sono consentite per team specifici. Dopo aver modificato i criteri dell'app personalizzata, possono essere necessarie alcune ore prima che le modifiche diventino effettive. Per gestire questi criteri, è necessario essere un Amministrazione globale o un amministratore del servizio Teams.

Gli sviluppatori all'interno dell'organizzazione possono aggiungere un'app personalizzata a Teams caricando il pacchetto di un’app, in un file .zip, direttamente in un team o nel contesto personale. Questa operazione è diversa da come vengono aggiunte le app tramite l'App Store di Teams. L'aggiunta di un'app personalizzata caricando un pacchetto dell'app, noto anche come sideload, consente a utenti specifici all'interno dell'organizzazione di testare un'app prima che sia pronta per essere distribuita su larga scala.

Durante la creazione di un'app, gli sviluppatori creano e aggiungono un ID app al file manifesto. È possibile visualizzare questo ID dell'app esterna nella pagina Gestisci app dopo aver abilitato la colonna `External app ID` dalle impostazioni della colonna. È anche possibile visualizzarlo nella pagina dei dettagli dell'app di un'app personalizzata. L'ID è applicabile solo per le app personalizzate.

## <a name="custom-app-policy-and-settings"></a>Impostazioni e criteri delle app personalizzate

Tre impostazioni determinano se un utente può caricare un'app personalizzata in un team. Offre agli amministratori un controllo granulare su chi può aggiungere app personalizzate a un team e a quali app personalizzate dei team possono essere aggiunte. Queste impostazioni non influiscono sulla possibilità di bloccare le app di terze parti.

* [Criteri delle app personalizzate di utenti](#user-custom-app-policy)
* [Impostazioni app personalizzate di team](#team-custom-app-setting)
* [Impostazioni app personalizzate a livello di organizzazione](#org-wide-custom-app-setting)

### <a name="user-custom-app-policy"></a>Criteri delle app personalizzate di utenti

[Nell'ambito dei criteri di configurazione delle app](teams-app-setup-policies.md), gli amministratori possono usare l'impostazione **Carica app personalizzate** per controllare se un utente può caricare app personalizzate in Teams.

Se le impostazioni sono disattivate:

* L'utente non può caricare un'app personalizzata in alcun team dell'organizzazione o nel contesto personale.
* L'utente può interagire con le app personalizzate, a seconda delle impostazioni app personalizzate a livello di organizzazione.

Se le impostazioni sono attivate:

* L'utente può caricare app personalizzate nei team che lo consentono e nei team di cui sono proprietari, a seconda delle impostazioni app personalizzate a livello di organizzazione.
* L'utente può caricare app personalizzate al contesto personale.
* L'utente può interagire con le app personalizzate, a seconda delle impostazioni app personalizzate a livello di organizzazione.

È possibile modificare le impostazioni del criterio di installazione globale per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti dell'organizzazione, è possibile creare e assegnare uno o più criteri di installazione delle app personalizzate.

#### <a name="set-a-user-custom-app-policy"></a>Impostare criteri delle app personalizzate di utenti

1. Accedere all'interfaccia di amministrazione di Teams e accedere ai **[criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)** **delle app** >  di Teams.
1. Selezionare **Aggiungi**.
1. Attivare o disattivare **Carica app personalizzate**.
1. Scegliere le altre impostazioni desiderate per il criterio.
1. Selezionare **Salva**.

### <a name="team-custom-app-setting"></a>Impostazioni app personalizzate di team

Gli amministratori e i proprietari di team possono controllare se l’aggiunta di app personalizzate a team è consentita. Queste impostazioni, **Consenti ai membri di caricare app personalizzate**, insieme ai criteri delle app personalizzate di utenti, determinano chi può aggiungere app personalizzate a un particolare team.

Se le impostazioni sono disattivate:

* I proprietari del team possono aggiungere app personalizzate se i criteri delle app personalizzate lo consentono.
* I membri del team che non sono proprietari del team non possono aggiungere app personalizzate al team.

Se le impostazioni sono attivate:

* I proprietari del team possono aggiungere app personalizzate se i criteri delle app personalizzate lo consentono.
* I membri del team che non sono proprietari del team possono aggiungere app personalizzate se i criteri delle app personalizzate lo consentono.

#### <a name="configure-the-team-custom-app-setting"></a>Configurare le impostazioni app personalizzate del team

1. In Teams, passare a un team e selezionare **Altre opzioni ...** >  **Gestire il team**.
1. Selezionare **Impostazioni** ed espandere **Autorizzazioni membro**.
1. Selezionare o deselezionare la casella di controllo **Consenti ai membri di caricare app personalizzate**.

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="Screenshot che mostra le impostazioni app personalizzate del team." lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>Impostazioni app personalizzate a livello di organizzazione

Le impostazioni app a livello di organizzazione **Consenti interazione con app personalizzate** nella pagina [Gestisci app](manage-apps.md) si applicano a tutti gli utenti dell'organizzazione e regolano se possono caricare o interagire con app personalizzate. Queste impostazioni fungono da interruttore master di attivazione/disattivazione per le impostazioni dei criteri delle app personalizzate di utenti e team. La funzione come interruttore master di attivazione/disattivazione è voluta durante gli eventi di sicurezza. Di conseguenza, le impostazioni dei criteri delle app personalizzate di utenti e team non verranno applicate a meno che le impostazioni app personalizzate a livello di organizzazione non siano abilitate anche se sono abilitate le impostazioni dei criteri delle app personalizzate di utenti e team.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurare le impostazioni app personalizzate a livello di organizzazione

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Seleziona **Impostazioni app a livello di organizzazione**.
1. In **App personalizzate** attivare o disattivare **Consenti interazione con app personalizzate**.

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="Screenshot che mostra le impostazioni app personalizzate a livello di organizzazione.":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>Come interagiscono le impostazioni e i criteri delle app personalizzate

Questa tabella riepiloga le impostazioni e i criteri delle app personalizzate, il loro modo di lavorare insieme e l'effetto combinato sul controllo degli utenti dell'organizzazione che possono caricare app personalizzate in Teams.

Se, ad esempio, si vuole consentire solo ai proprietari di team di caricare app personalizzate in team specifici. Impostare quanto segue:

* Attivare le impostazioni **Consenti interazione con le app personalizzate** nell'interfaccia di amministrazione di Microsoft Teams.
* Disattivare **Consenti ai membri di caricare app personalizzate** per ogni team a cui si vuole limitare l’accesso.
* Creare e assegnare criteri personalizzati nei criteri di configurazione delle app nell'interfaccia di amministrazione di Microsoft Teams con l'impostazione **Carica app personalizzate** attivata e assegnarla ai proprietari del team.

|Impostazioni app personalizzate a livello di organizzazione |Impostazioni app personalizzate di team |Criteri delle app personalizzate di utenti |Effetto  |
|---------|---------|---------|---------|
| Disattivato    | Disattivato    | Disattivato     |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio di Teams o di un Amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.   |
| Disattivato     | Disattivato     | Attivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio di Teams o di un Amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Disattivato    | Attivato        | Disattivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio di Teams o di un Amministratore globale. È possibile usare Windows PowerShell per eliminare app personalizzate.         |
| Disattivato    | Attivato      | Attivato       |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio di Teams o di un Amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Attivato    | Disattivato       | Disattivato         |  L'utente non può caricare app personalizzate.      |
| Attivato     | Disattivato       | Attivato         | Se l'utente è un proprietario di team, può caricare app personalizzate nel team. Se l'utente non è proprietario di un team, non può caricare app personalizzate nel team. L'utente può caricare app personalizzate nel contesto personale.     |
| Attivato     | Attivato     | Disattivato         | L'utente non può caricare app personalizzate.       |
| Attivato    | Attivato        | Attivato        | L’utente può caricare app personalizzate nel team, che l'utente sia o meno proprietario del team. L'utente può caricare app personalizzate nel contesto personale.       |

## <a name="related-articles"></a>Articoli correlati

* [Amministrazione impostazioni per le app in Teams](admin-settings.md).
* [Assegnare criteri agli utenti in Teams](assign-policies-users-and-groups.md).
