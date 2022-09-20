---
title: Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Scopri come visualizzare le autorizzazioni richieste dalle app e concedere il consenso dell'amministratore alle app nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft Teams.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ba381d5d6806c1abd7a2766228ff74f843b156a
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837516"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams

Gli amministratori visualizzano e gestiscono tutte le app di Teams dalla pagina Gestisci app nell'interfaccia di amministrazione di Teams. È possibile gestire le app personalizzate create all'interno dell'organizzazione e disponibili solo per gli utenti finali e gestire le terze parti disponibili nell'App Store di Teams. Ad esempio, è possibile visualizzare lo stato a livello di organizzazione e le proprietà delle app, approvare o caricare nuove app personalizzate nell'app store dell'organizzazione, consentire le app a livello di organizzazione o per singoli utenti finali.

Qui è anche possibile concedere il consenso di amministratore a livello di organizzazione alle app che richiedono autorizzazioni per accedere ai dati e visualizzare le autorizzazioni RSC (Resource Specific Consent) per le app.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Concedere il consenso di amministratore a livello di organizzazione a un'app

Gli amministratori globali possono esaminare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. In questo modo gli utenti non dovranno rivedere e accettare le autorizzazioni richieste dall'app all'avvio dell'app. Inoltre, a seconda delle [impostazioni di consenso](/azure/active-directory/manage-apps/configure-user-consent) dell'utente in Azure Active Directory (Azure AD), alcuni utenti potrebbero non essere autorizzati a concedere il consenso alle app che accedono ai dati aziendali.

Esempi di autorizzazioni richieste dalle app includono la possibilità di leggere le informazioni archiviate in un team, leggere il profilo di un utente e inviare un messaggio di posta elettronica per conto degli utenti. Per altre informazioni, vedere [Autorizzazioni e consenso nell'endpoint Microsoft Identity Platform](/azure/active-directory/develop/v2-permissions-and-consent).

La colonna **Autorizzazioni** indica se un'app ha autorizzazioni che richiedono il consenso. Verrà visualizzato un collegamento **Visualizza dettagli** per ogni app registrata in Azure AD con autorizzazioni che richiedono il consenso. Tieni presente che questo vale solo per le app personalizzate e di terze parti. Il collegamento non è disponibile per le app fornite da Microsoft. Inoltre, gli amministratori non devono concedere il consenso per tali app.

Per concedere il consenso a livello di organizzazione a un'app, seguire questa procedura:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Eseguire una delle operazioni seguenti:
    * Cerca l'app desiderata, seleziona il nome dell'app per passare alla pagina dei dettagli dell'app e quindi seleziona la scheda **Autorizzazioni** .
    * Ordinare la colonna **Autorizzazioni** in ordine decrescente per trovare l'app e quindi selezionare **Visualizza dettagli**. In questo modo viene visualizzata la scheda **Autorizzazioni** della pagina dei dettagli dell'app.

1. In **Autorizzazioni a livello di organizzazione** selezionare **Rivedi autorizzazioni e consenso**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot delle autorizzazioni a livello di organizzazione nella scheda Autorizzazioni per un'app.":::

    Per eseguire questa operazione, è necessario essere un amministratore globale. Questa opzione non è disponibile per gli amministratori del servizio Teams.

1. Nella scheda **Autorizzazioni** esaminare le autorizzazioni richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot delle autorizzazioni richieste da un'app.":::

    > [!IMPORTANT]
    > La concessione del consenso a livello di organizzazione a un'app consente all'app di accedere ai dati dell'organizzazione. Esamina attentamente le autorizzazioni richieste dall'app prima di concedere il consenso.

1. Se accetti le autorizzazioni richieste dall'app, seleziona **Accetta** per concedere il consenso. Nella parte superiore della pagina viene temporaneamente visualizzato un banner per segnalare che sono state concesse le autorizzazioni richieste per l'app. L'app ha ora accesso alle risorse specificate per tutti gli utenti dell'organizzazione e a nessun altro verrà richiesto di rivedere le autorizzazioni.

Dopo aver accettato le autorizzazioni, verrà visualizzato un messaggio in **Autorizzazioni a livello di organizzazione** nella pagina dei dettagli dell'app per informarti che è stato concesso il consenso. Per visualizzare i dettagli sulle autorizzazioni dell'app, selezionare il collegamento **Azure Active Directory** per passare alla pagina dell'app nel portale di Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Screenshot del messaggio visualizzato quando viene concesso il consenso.":::

Se gli utenti dell'organizzazione sono autorizzati a concedere il consenso e se uno o più utenti hanno concesso il consenso a una determinata app, verrà visualizzato lo stesso messaggio per informarti che il consenso è stato concesso e il collegamento ad Azure Active Directory alla pagina dell'app nel portale di Azure AD.

> [!NOTE]
> Anche se l'opzione **Rivedi autorizzazioni e consenso** non è disponibile per gli amministratori del servizio Teams e non possono concedere il consenso di amministratore a livello di organizzazione alle app, gli amministratori dei servizi di Teams possono visualizzare il contenuto nella scheda **Autorizzazioni** per un'app. Ad esempio, un amministratore del servizio Teams può fare clic sul collegamento **Azure Active Directory** per visualizzare i dettagli delle autorizzazioni dell'app nel portale di Azure AD.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Visualizzare le autorizzazioni di consenso specifiche per le risorse di un'app

Le autorizzazioni RSC consentono ai proprietari del team di concedere il consenso per un'app per l'accesso e la modifica dei dati di un team. Le autorizzazioni RSC sono granulari, autorizzazioni specifiche di Teams che definiscono cosa può fare un'app in un team specifico. Esempi di autorizzazioni RSC includono la possibilità di creare ed eliminare canali, ottenere le impostazioni per un team e creare e rimuovere le schede dei canali.

Le autorizzazioni RSC sono definite nel manifesto dell'app e non in Azure AD. Concedi il consenso alle autorizzazioni RSC quando aggiungi l'app a un team. Per altre informazioni, vedere [Consenso specifico delle risorse (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Gli amministratori globali e gli amministratori del servizio Teams possono visualizzare le autorizzazioni RSC per un'app nella scheda **Autorizzazioni** della pagina dei dettagli dell'app.

Per visualizzare le autorizzazioni RSC per un'app, procedere come segue:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
1. Cerca l'app desiderata, seleziona il nome dell'app per passare alla pagina dei dettagli dell'app e quindi seleziona la scheda **Autorizzazioni** .
1. In **Autorizzazioni per il consenso specifico delle risorse di Microsoft Graph** esaminare le autorizzazioni RSC richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Screenshot delle autorizzazioni RSC per un'app.":::

## <a name="known-issues"></a>Problemi noti

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Il collegamento "Visualizza dettagli" non viene visualizzato nella colonna Autorizzazioni per alcune app di terze parti che richiedono autorizzazioni

La possibilità di rivedere le autorizzazioni e concedere il consenso non è disponibile per tutte le app di terze parti. In genere, le app di terze parti vengono registrate in Azure Active Directory quando le app richiedono le autorizzazioni. Invece del collegamento **Visualizza dettagli** , verrà visualizzata `--` la colonna **Autorizzazioni** .

## <a name="related-articles"></a>Articoli correlati

* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Autorizzazioni e consenso nell'endpoint Microsoft Identity Platform](/azure/active-directory/develop/v2-permissions-and-consent)
* [Consenso specifico delle risorse in Teams](resource-specific-consent.md)
* [Consenso specifico delle risorse (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Esplorare il ciclo di vita dell'app Teams](https://aka.ms/PR132) (sessione Ignite 2020)
