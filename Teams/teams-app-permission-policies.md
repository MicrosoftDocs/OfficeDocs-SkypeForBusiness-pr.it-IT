---
title: Gestire i criteri di autorizzazione app in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Ulteriori informazioni sui criteri di autorizzazione app in Microsoft Teams e su come controllare la disponibilità delle app per i propri utenti finali.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 5797486fb0993aa8630a8dedde131ad7751e7e5f
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656022"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>Gestire l'accesso alle app Teams usando i criteri di autorizzazione per le app

Gli amministratori possono usare i criteri di autorizzazione per le app per controllare le app disponibili per ogni utente dell'organizzazione. Le autorizzazioni impostate per consentire o bloccare tutte le app o app specifiche sono applicabili a tutti i [tipi di app in Teams](deploy-apps-microsoft-teams-landing-page.md). Per gestire questi criteri, è necessario essere un Amministrazione globale o un amministratore del servizio Teams.

Per consentire un'app, è necessario consentirla nelle [impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings), nelle [impostazioni delle singole app](manage-apps.md#allow-and-block-apps) e nei criteri di autorizzazione dell'app. Anche se gli altri due metodi consentono semplicemente l'uso di un'app nell'organizzazione, i criteri di autorizzazione consentono di controllare quali utenti possono usare un'app specifica. È possibile controllare l'accesso per utente e per app creando e applicando il criterio a utenti specifici.

L'interfaccia di amministrazione di Teams consente di creare due tipi di criteri di autorizzazione:

* `Global (Org-wide default)` esiste per impostazione predefinita e si applica a tutti gli utenti. Le modifiche apportate a questo criterio influiscono su tutti gli utenti perché questo criterio viene applicato a tutti gli utenti per impostazione predefinita.
* I criteri creati dall'amministratore si applicano solo agli utenti a cui sono applicati. Creare un nuovo criterio per consentire le app per utenti o gruppi di utenti specifici.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Screenshot che mostra un nuovo criterio di autorizzazione per le app in corso di creazione." lightbox="media/app-permission-policy.png":::

Se l'organizzazione fa già parte di Teams, le impostazioni dell'app configurate nelle **impostazioni a livello di tenant** nel interfaccia di amministrazione di Microsoft 365 si riflettono nelle impostazioni delle app a livello di organizzazione nella pagina [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) nell'interfaccia di amministrazione di Teams. Per impostazione predefinita, se non si conosce Teams e si è appena iniziati, tutte le app sono consentite nell'impostazione globale a livello di organizzazione. Include app pubblicate da Microsoft, da provider di software di terze parti e dall'organizzazione.

> [!NOTE]
> Per informazioni sulle impostazioni delle app di terze parti in Microsoft 365 Government Community Cloud High (GCCH) e nell'ambiente DoD (Department of Defense), vedere [Gestire le impostazioni delle app a livello di organizzazione per Microsoft 365 Government](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-an-app-permission-policy"></a>Creare criteri di autorizzazione per le app

Usare uno o più criteri di autorizzazione app personalizzati, se si vogliono controllare le app disponibili per gruppi di utenti diversi. È possibile creare e assegnare criteri personalizzati in base a chi pubblica le app: Microsoft, terze parti o l'organizzazione. Dopo aver creato un criterio personalizzato, non è possibile cambiarlo se le app di terze parti sono disabilitate nelle impostazioni delle app a livello di organizzazione.

1. Accedere all'interfaccia di amministrazione di Teams e accedere ai **[criteri di autorizzazione](https://admin.teams.microsoft.com/policies/app-permission)** **delle app** >  di Teams.
1. Selezionare **Aggiungi**.
1. Specificare un nome e una descrizione per il criterio.
1. In **App Microsoft**, **App di terze parti** e **App personalizzate** seleziona una delle opzioni seguenti:

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. Se si è selezionato **Consentire app specifiche e bloccare tutte le altre**, aggiungere le app che si vuole consentire:

    1. Selezionare **Consenti app**.
    1. Cercare le app che si desidera consentire e fare clic su **Aggiungi**. I risultati della ricerca vengono filtrati in base allo sviluppatore di app (**App Microsoft**, **App di terze parti** o **App personalizzate**).
    1. Dopo aver scelto una o più app, seleziona **Consenti**.

1. Se hai selezionato **Blocca app specifiche e consenti tutte le altre**, allo stesso modo cerca e scegli le app che vuoi bloccare, quindi seleziona **Blocca**.

1. Selezionare **Salva**.

## <a name="edit-an-app-permission-policy"></a>Modificare un criterio di autorizzazione app

È possibile usare l'interfaccia di amministrazione di Teams per modificare i criteri globali o i criteri personalizzati creati.

1. Accedere all'interfaccia di amministrazione di Teams e accedere ai **[criteri di autorizzazione](https://admin.teams.microsoft.com/policies/app-permission)** **delle app** >  di Teams.
1. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
1. Apporta le modifiche per consentire o bloccare app specifiche in ognuna delle tre categorie.
1. Selezionare **Salva**.

## <a name="assign-a-custom-policy-for-app-permissions-to-users"></a>Assegnare criteri personalizzati per le autorizzazioni delle app agli utenti

I criteri di autorizzazione per le app vengono applicati solo quando si applicano criteri a un utente o a un gruppo di utenti. Vedere i diversi modi per [assegnare i criteri agli utenti](policy-assignment-overview.md#ways-to-assign-policies).

## <a name="considerations-when-using-app-permission-policies"></a>Considerazioni sull'uso dei criteri di autorizzazione per le app

Quando si usano criteri di autorizzazione per le app per concedere l'accesso o disabilitare l'accesso alle app, tenere presente quanto segue:

* I criteri di autorizzazione per le app vengono applicati solo quando si applicano criteri a un utente o a un gruppo di utenti.

* La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

* Un utente finale non può interagire con le funzionalità di un'app che l'utente non è autorizzato a usare.

* Gli utenti possono cercare le app bloccate e richiedere l'approvazione dell'amministratore. Gli amministratori mantengono il controllo completo per [approvare o ignorare le richieste degli utenti](user-requests-approve-apps.md).

* I criteri di configurazione delle app interagiscono con i criteri di autorizzazione delle app. Selezioni le app da aggiungere ai criteri di configurazione da un set di app consentite. Tuttavia, se un utente ha un criterio di autorizzazione per l'app che blocca l'uso di un'app aggiunta, l'utente non può usare l'app.

* I criteri per le app si applicano agli utenti che usano Teams su web, mobile o desktop.

## <a name="related-articles"></a>Articoli correlati

* [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
* [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
* [Confronto della disponibilità delle funzionalità di Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
