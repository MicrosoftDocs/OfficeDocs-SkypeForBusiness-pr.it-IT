---
title: Gestire le impostazioni e i criteri delle app personalizzati e caricati in sideload
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
description: Informazioni su come gestire criteri e impostazioni per controllare chi nell'organizzazione può trasferire le app in sideload e caricare app personalizzate.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 7cf290c3f031becab73523fceb031cae4e0a55a8
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912415"
---
# <a name="manage-custom-and-sideloaded-apps-in-teams-admin-center"></a>Gestire app personalizzate e sideload nell'interfaccia di amministrazione di Teams

Microsoft Teams consente agli sviluppatori all'interno dell'organizzazione di creare, testare e distribuire app personalizzate per gli utenti interni dell'organizzazione. Tali app sono denominate app personalizzate o app Line of Business (LINE OF BUSINESS). L'organizzazione può richiedere la creazione di app personalizzate per requisiti specifici dell'organizzazione. Gli amministratori controllano l'implementazione e le autorizzazioni per le app personalizzate usando varie impostazioni e criteri.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Screenshot che mostra come consentire le app personalizzate nell'organizzazione nel riquadro delle impostazioni a livello di organizzazione." lightbox="media/custom-app-orgwide-setting.png":::

Dopo aver consentito l'uso di un'app personalizzata, gli utenti finali possono trovarla selezionando **Built per la tua organizzazione** nella barra di spostamento sinistra di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Schermata delle app personalizzate nello store di Teams nell'app desktop di Teams." lightbox="media/built-for-your-org2.png":::

L'amministratore di Teams usa i criteri e le impostazioni delle app personalizzate per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft Teams. Gli amministratori decidono quali utenti possono caricare app personalizzate, mentre gli amministratori e i proprietari di team possono determinare se l'aggiunta di app personalizzate a team sono consentite per team specifici. Dopo aver modificato i criteri dell'app personalizzata, possono essere necessarie alcune ore prima che le modifiche diventino effettive. Per gestire questi criteri, è necessario essere un Amministrazione globale o un amministratore del servizio Teams.

Gli sviluppatori all'interno dell'organizzazione possono aggiungere un'app personalizzata a Teams caricando il pacchetto di un’app, in un file .zip, direttamente in un team o nel contesto personale. Questa operazione è diversa da come vengono aggiunte le app tramite l'App Store di Teams. L'aggiunta di un'app personalizzata caricando un pacchetto dell'app, noto anche come sideload, consente a utenti specifici all'interno dell'organizzazione di testare un'app prima che sia pronta per essere distribuita su larga scala.

<!--- During the creation of an app, the developers create and add an app ID to the manifest file. You can view this external app ID on the Manage apps page after you enable the column `External app ID` from the column settings. You can also view it on the app details page of a custom app. The ID is applicable for custom apps only. --->

## <a name="understand-sideloading-of-custom-apps"></a>Informazioni sul trasferimento locale di app personalizzate

Quando sviluppi app personalizzate e prima di distribuirle agli utenti finali, gli sviluppatori testano le app aggiungendola a Teams Store per testare. Gli sviluppatori possono eseguire il test autonomamente o con un gruppo di utenti specificato, ma l'app non è disponibile per gli altri utenti finali dell'organizzazione tramite lo Store. Questo metodo è detto trasferimento locale delle app e si applica solo alle app personalizzate.

Gli sviluppatori possono caricare un'applicazione per renderla disponibile ai membri di un team specifico, in genere per testare un'applicazione in fase di sviluppo. L'uso di un'app in questo modo limita il suo utilizzo agli sviluppatori dell'app e non richiede l'approvazione dell'amministratore, purché quest'ultimo consenta il sideloading in Teams.

Gli sviluppatori possono condividere un'app in sideload con un team specifico senza inviarla al catalogo app di Teams. Rende l'app personalizzata caricata in sideload disponibile per un gruppo limitato di utenti finali, ma non disponibile nell'app store dell'organizzazione per tutti gli utenti finali.

Come amministratore, è possibile disabilitare il sideloading delle app per tutti gli sviluppatori. Se si disconosce il sideloading, gli sviluppatori possono comunque testare le loro applicazioni creando un [tenant di test separato](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una volta completato lo sviluppo di app personalizzate, gli sviluppatori richiedono agli amministratori di distribuire l'app personalizzata agli utenti finali. Per informazioni dettagliate, vedere [come pubblicare un'app personalizzata](/microsoftteams/upload-custom-apps). Gli amministratori consentono (o bloccano) l'uso di un'app personalizzata per tutti gli utenti o per utenti specifici.

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
1. Specificare un nome e una descrizione per il criterio.
1. Attiva o disattiva l'impostazione **Carica app personalizzate** .
1. Scegliere le altre impostazioni desiderate per il criterio.
1. Selezionare **Salva**.
1. [Applicare il criterio agli utenti](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) che sviluppano app personalizzate e sono autorizzati a caricarle.

> [!NOTE]
> Per modificare questa impostazione, consenti app personalizzate nelle [impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

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
