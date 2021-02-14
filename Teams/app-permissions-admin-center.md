---
title: Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Scopri come visualizzare le autorizzazioni richieste dalle app e concedere il consenso dell'amministratore alle app nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827536"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft Teams

La [pagina Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams consente di visualizzare e gestire tutte le app di Teams per l'organizzazione. Ad esempio, puoi visualizzare lo stato e le proprietà delle app a livello di organizzazione, approvare o caricare nuove app personalizzate nello store delle app della tua organizzazione, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile concedere il consenso di amministratore a livello di organizzazione alle app che richiedono le autorizzazioni per accedere ai dati e visualizzare autorizzazioni di consenso specifico delle risorse per le app.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Concedere il consenso dell'amministratore a livello di organizzazione a un'app

Gli amministratori globali possono controllare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. In questo modo gli utenti non devono rivedere e accettare le autorizzazioni richieste dall'app quando avviano l'app. Inoltre, a seconda delle impostazioni del consenso dell'utente [in](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) Azure Active Directory (Azure AD), alcuni utenti potrebbero non essere autorizzati a concedere il consenso alle app che accedono ai dati aziendali.

Esempi di autorizzazioni richieste dalle app includono la possibilità di leggere le informazioni archiviate in un team, leggere il profilo di un utente e inviare un messaggio di posta elettronica per conto degli utenti. Per altre informazioni, vedere Autorizzazioni [e consenso nell'endpoint della piattaforma di identità Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 

La **colonna Autorizzazioni** indica se un'app ha autorizzazioni che devono avere il consenso. Verrà visualizzato un collegamento Visualizza **dettagli per** ogni app registrata in Azure AD che ha autorizzazioni che necessitano del consenso. Tenere presente che questa impostazione si applica solo alle app personalizzate e di terze parti. Non verrà visualizzato questo collegamento né sarà necessario concedere il consenso dell'amministratore per le app pubblicate da Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot della colonna Autorizzazioni nella pagina Gestisci app":::

Per concedere il consenso a livello di organizzazione a un'app, seguire questa procedura:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Eseguire una delle operazioni seguenti:
    - Cercare l'app desiderata, fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare la **scheda** Autorizzazioni.
    - Ordina la **colonna Autorizzazioni** in ordine decrescente per trovare l'app, quindi seleziona **Visualizza dettagli.** Verrà visualizzata la scheda Autorizzazioni **della pagina dei** dettagli dell'app.

3. In **Autorizzazioni a livello di organizzazione** selezionare Controlla autorizzazioni e **consenso.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot delle autorizzazioni a livello di organizzazione nella scheda Autorizzazioni per un'app":::

    Per eseguire questa operazione, è necessario essere un amministratore globale. Questa opzione non è disponibile per gli amministratori dei servizi di Teams.

4. Nella scheda **Autorizzazioni** controllare le autorizzazioni richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot delle autorizzazioni richieste da un'app":::

    > [!IMPORTANT]
    > La concessione di un consenso a livello di organizzazione a un'app consente all'app di accedere ai dati dell'organizzazione. Leggere attentamente le autorizzazioni richieste dall'app prima di concedere il consenso.
5. Se si accettano le autorizzazioni richieste dall'app, fare clic su **Accetta** per concedere il consenso. Nella parte superiore della pagina viene visualizzato temporaneamente un banner per insod chie di sapere che sono state concesse le autorizzazioni richieste per l'app. L'app ha ora accesso alle risorse specificate per tutti gli utenti dell'organizzazione e a nessun altro verrà chiesto di rivedere le autorizzazioni.

Dopo aver accettato le autorizzazioni, nella  pagina dei dettagli dell'app verrà visualizzato un messaggio in Autorizzazioni a livello di organizzazione per notificare che è stato concesso il consenso. Per visualizzare i dettagli sulle autorizzazioni dell'app, fare clic sul collegamento di **Azure Active Directory** per passare alla pagina dell'app nel portale di Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot del messaggio visualizzato quando viene concesso il consenso":::

Se gli utenti della tua organizzazione sono autorizzati a concedere il consenso e se uno o più utenti hanno concesso il consenso a una particolare app, vedrai anche lo stesso messaggio per notificare che il consenso è stato concesso e il collegamento ad Azure Active Directory alla pagina dell'app nel portale di Azure AD.

> [!NOTE]
> Anche se, l'opzione Rivedi autorizzazioni e consenso non è disponibile per gli amministratori dei servizi di Teams e non  può concedere il consenso di amministratore a livello di organizzazione alle app, gli amministratori dei servizi di Teams possono visualizzare il contenuto della scheda Autorizzazioni per un'app.  Ad esempio, un amministratore del servizio Teams può fare clic sul collegamento **di Azure Active Directory** per visualizzare i dettagli delle autorizzazioni per le app nel portale di Azure AD. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Visualizzare autorizzazioni di consenso specifiche per le risorse di un'app

Le autorizzazioni RSC consentono ai proprietari dei team di concedere il consenso a un'app per accedere ai dati di un team e modificarli. Le autorizzazioni RSC sono autorizzazioni granulari e specifiche di Teams che definiscono le attività che un'app può eseguire in un team specifico. Esempi di autorizzazioni RSC includono la possibilità di creare ed eliminare canali, ottenere le impostazioni per un team e creare e rimuovere schede dei canali. 

Le autorizzazioni RSC sono definite nel manifesto dell'app e non in Azure AD. L'utente concede il consenso alle autorizzazioni RSC quando aggiunge l'app a un team. Per altre informazioni, vedere [Il consenso specifico della risorsa (RSC).](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Gli amministratori globali e gli amministratori dei servizi di Teams possono visualizzare le autorizzazioni RSC per un'app nella **scheda** Autorizzazioni della pagina dei dettagli dell'app. 

Per visualizzare le autorizzazioni RSC per un'app, seguire questa procedura:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Cercare l'app desiderata, fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare la **scheda** Autorizzazioni.
3. Nelle **autorizzazioni di consenso specifiche delle risorse (RSC)** di Microsoft Graph, esaminare le autorizzazioni RSC richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot delle autorizzazioni RSC per un'app":::

## <a name="known-issues"></a>Problemi noti

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Il collegamento "Visualizza dettagli" non è visualizzato nella colonna Autorizzazioni per alcune app di terze parti che richiedono autorizzazioni

Attualmente, la possibilità di esaminare le autorizzazioni e concedere il consenso non è disponibile per tutte le app di terze parti registrate in Azure AD che richiedono le autorizzazioni. Invece del **collegamento Visualizza** dettagli, verrà visualizzato nella **--** **colonna** Autorizzazioni. Stiamo lavorando con gli ISV per abilitare questa funzionalità per le loro app.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Autorizzazioni e consenso nell'endpoint della piattaforma di identità Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consenso specifico delle risorse in Teams](resource-specific-consent.md)
- [Consenso specifico della risorsa (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Esplorazione del ciclo di vita dell'app Teams](https://aka.ms/PR132) (sessione Ignite 2020)


