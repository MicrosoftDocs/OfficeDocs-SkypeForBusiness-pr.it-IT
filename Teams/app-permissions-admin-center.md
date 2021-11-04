---
title: Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell Microsoft Teams di amministrazione
author: cichur
ms.author: v-mahoffman
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come visualizzare le autorizzazioni richieste dalle app e concedere il consenso dell'amministratore alle app nella pagina Gestisci app dell'Microsoft Teams di amministrazione.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5076c80edfff8e4b36b53ad79c3b17805f4d6df
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775996"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell Microsoft Teams di amministrazione

La [pagina Gestisci app](manage-apps.md) nell'Microsoft Teams di amministrazione consente di visualizzare e gestire tutte le app Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà a livello di organizzazione delle app, approvare o caricare nuove app personalizzate nell'App Store dell'organizzazione, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile concedere il consenso dell'amministratore a livello di organizzazione alle app che richiedono le autorizzazioni per accedere ai dati e visualizzare le autorizzazioni di consenso specifico delle risorse per le app.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Concedere il consenso dell'amministratore a livello di organizzazione a un'app

Gli amministratori globali possono esaminare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. A questo scopo, gli utenti non devono rivedere e accettare le autorizzazioni richieste dall'app quando avviano l'app. Inoltre, a seconda delle impostazioni di consenso dell'utente [in](/azure/active-directory/manage-apps/configure-user-consent) Azure Active Directory (Azure AD), alcuni utenti potrebbero non essere autorizzati a concedere il consenso alle app che accedono ai dati aziendali.

Esempi di autorizzazioni richieste dalle app includono la possibilità di leggere le informazioni archiviate in un team, leggere il profilo di un utente e inviare un messaggio di posta elettronica per conto degli utenti. Per altre informazioni, vedere Autorizzazioni e consenso [nell'endpoint Microsoft Identity Platform.](/azure/active-directory/develop/v2-permissions-and-consent) 

La **colonna Autorizzazioni** indica se un'app ha autorizzazioni che necessitano del consenso. Verrà visualizzato un collegamento Visualizza **dettagli** per ogni app registrata in Azure AD con autorizzazioni che necessitano del consenso. Tenere presente che questa impostazione si applica solo alle app personalizzate e di terze parti. Questo collegamento non è visualizzato o è necessario concedere il consenso dell'amministratore per le app pubblicate da Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot della colonna Autorizzazioni nella pagina Gestisci app.":::

Per concedere il consenso a livello di organizzazione a un'app, seguire questa procedura:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Eseguire una delle operazioni seguenti:
    - Cercare l'app desiderata, fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare la **scheda** Autorizzazioni.
    - Ordinare **la colonna** Autorizzazioni in ordine decrescente per trovare l'app e quindi selezionare Visualizza **dettagli.** Questa operazione consente di accedere alla **scheda Autorizzazioni** della pagina dei dettagli dell'app.

3. In **Autorizzazioni a livello di organizzazione** selezionare **Rivedi autorizzazioni e consenso.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot delle autorizzazioni a livello di organizzazione nella scheda Autorizzazioni per un'app.":::

    Per eseguire questa operazione, è necessario essere un amministratore globale. Questa opzione non è disponibile per gli Teams amministratori del servizio.

4. Nella scheda **Autorizzazioni** esaminare le autorizzazioni richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot delle autorizzazioni richieste da un'app.":::

    > [!IMPORTANT]
    > La concessione del consenso a livello di organizzazione a un'app consente all'app di accedere ai dati dell'organizzazione. Esaminare attentamente le autorizzazioni richieste dall'app prima di concedere il consenso.
5. Se accetti le autorizzazioni richieste dall'app, fai clic **su Accetta** per concedere il consenso. Nella parte superiore della pagina viene visualizzato temporaneamente un banner che indica che sono state concesse le autorizzazioni richieste per l'app. L'app ora ha accesso alle risorse specificate per tutti gli utenti dell'organizzazione e a nessun altro verrà chiesto di rivedere le autorizzazioni.

Dopo aver accettato le autorizzazioni, verrà visualizzato un messaggio **in** Autorizzazioni a livello di organizzazione nella pagina dei dettagli dell'app per insodgerlo. Per visualizzare i dettagli sulle autorizzazioni  dell'app, fare clic sul collegamento Azure Active Directory per passare alla pagina dell'app nel portale Azure AD app.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Screenshot del messaggio visualizzato quando viene concesso il consenso.":::

Se gli utenti dell'organizzazione sono autorizzati a concedere il consenso e se uno o più utenti hanno concesso il consenso a una determinata app, verrà visualizzato anche lo stesso messaggio per insoddirne il consenso e il collegamento Azure Active Directory alla pagina dell'app nel portale di Azure AD.

> [!NOTE]
> Anche se  l'opzione Rivedi autorizzazioni e consenso non è disponibile per gli amministratori del servizio Teams e non può concedere il consenso  dell'amministratore a livello di organizzazione alle app, gli amministratori del servizio Teams possono visualizzare il contenuto nella scheda Autorizzazioni per un'app. Ad esempio, un amministratore Teams servizio  può fare clic sul collegamento Azure Active Directory per visualizzare i dettagli delle autorizzazioni per le app nel portale Azure AD app. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Visualizzare le autorizzazioni di consenso specifiche delle risorse di un'app

Le autorizzazioni RSC consentono ai proprietari del team di concedere il consenso per un'app per accedere e modificare i dati di un team. Le autorizzazioni RSC sono autorizzazioni granulari Teams specifiche che definiscono le attività che un'app può eseguire in un team specifico. Esempi di autorizzazioni RSC includono la possibilità di creare ed eliminare canali, ottenere le impostazioni per un team e creare e rimuovere schede dei canali. 

Le autorizzazioni RSC sono definite nel manifesto dell'app e non Azure AD. L'utente concede il consenso alle autorizzazioni RSC quando si aggiunge l'app a un team. Per altre informazioni, vedere [Consenso specifico delle risorse (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Gli amministratori globali e gli Teams possono visualizzare le autorizzazioni RSC per un'app nella **scheda** Autorizzazioni della pagina dei dettagli dell'app. 

Per visualizzare le autorizzazioni RSC per un'app, seguire questa procedura:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Cercare l'app desiderata, fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare la **scheda** Autorizzazioni.
3. In Microsoft Graph autorizzazioni di consenso specifiche delle risorse **(RSC)** esaminare le autorizzazioni RSC richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Screenshot delle autorizzazioni RSC per un'app.":::

## <a name="known-issues"></a>Problemi noti

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Il collegamento "Visualizza dettagli" non viene visualizzato nella colonna Autorizzazioni per alcune app di terze parti che richiedono autorizzazioni

Attualmente, la possibilità di rivedere le autorizzazioni e concedere il consenso non è disponibile per tutte le app di terze parti registrate Azure AD che richiedono autorizzazioni. Invece del **collegamento Visualizza** dettagli, verrà visualizzato nella **--** **colonna** Autorizzazioni. Stiamo lavorando con gli ISV per abilitare questa funzionalità per le loro app.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Autorizzazioni e consenso nell'endpoint Microsoft Identity Platform utente](/azure/active-directory/develop/v2-permissions-and-consent)
- [Consenso specifico delle risorse in Teams](resource-specific-consent.md)
- [Consenso specifico delle risorse (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Spostamento nel ciclo di Teams dell'app](https://aka.ms/PR132) (sessione Ignite 2020)