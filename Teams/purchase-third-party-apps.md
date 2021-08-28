---
title: Acquistare app di terze parti per Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Informazioni su come acquistare app di terze parti per Teams nell'Microsoft Teams di amministrazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: da917d2c58282554e3e2a68464cea1f2249bd324
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616182"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acquistare app di terze parti per Teams

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo negli Stati Uniti.

Teams le app sono gratuite e alcune potrebbero richiedere l'acquisto di abbonamenti al servizio per sperimentare tutte le funzionalità e l'ambito dell'app. Questi abbonamenti al servizio sono denominati offerte Software as a Service (SaaS), che sono disponibili per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e ora tramite l'interfaccia di amministrazione Microsoft Teams di amministrazione.

La [pagina Gestisci app](manage-apps.md) nell'Microsoft Teams di amministrazione consente di visualizzare e gestire tutte le app Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà a livello di organizzazione delle app, caricare nuove app personalizzate nell'App Store dell'organizzazione, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La **colonna Licenze** nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot che mostra app di terze parti con abbonamenti SaaS":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Cercare e acquistare servizi per un'app di terze parti

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina, è necessario essere un amministratore globale o Teams del servizio.
2. Cercare l'app desiderata. Per identificare le app con un abbonamento SaaS a pagamento, cercare nella **colonna Licenze.** Ogni app avrà uno dei valori seguenti:
    - **Acquista ora:** l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.  
    - **Acquistato:** l'app offre un abbonamento SaaS e sono state acquistate licenze per l'app.
    - **- :** l'app non offre un abbonamento SaaS.
3. Dopo aver trovato l'app, fare clic **su** Acquista ora per passare alla scheda Piani e **prezzi** della pagina dei dettagli dell'app. Esaminare i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Per altre informazioni, fare clic sul **collegamento** Altre informazioni per passare alla pagina dell'app in [AppSource.](https://appsource.microsoft.com/)  
4. Per acquistare un piano, fare clic **su Acquista adesso.** Si verrà reindirizzati all'esperienza di acquisto per l'offerta associata all'app Teams app. Qui completerai l'acquisto del servizio o dell'offerta SaaS.
5. Scegliere il piano desiderato. Se l'offerta SaaS include più piani, fare clic su **Cambia** per visualizzare l'elenco dei piani disponibili.
6. Selezionare il periodo di fatturazione **(mensile** o **annuale)** e quindi immettere il numero di licenze utente da acquistare.
7. Immetti il metodo di pagamento.
8. Al termine, selezionare Crea **ordine.**
9. Fare **clic su Configura ora** per attivare l'abbonamento nel sito Web dell'autore.

Dopo aver acquistato l'offerta SaaS associata all'app Teams, è possibile  visualizzare i dettagli dell'acquisto seguenti nella scheda Piani e prezzi della pagina dei dettagli dell'app.

- **Data di attivazione della licenza:** data in cui è stata attivata la licenza. Se l'account non è ancora configurato, viene visualizzato come Abbonamento in **attesa di attivazione.**
- **Licenze:** numero di licenze acquistate.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda Piani e prezzi della pagina dei dettagli dell'app":::

Selezionare **Gestisci licenze** per passare al interfaccia di amministrazione di Microsoft 365 per visualizzare e gestire le licenze acquistate e per gestire le assegnazioni delle licenze per gli utenti.

Gli amministratori globali possono visualizzare gli acquisti effettuati da chiunque nell'organizzazione, mentre Teams gli amministratori dei servizi possono visualizzare solo gli acquisti effettuati da soli.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Hai un'offerta SaaS per un'app Teams che vuoi elencare e vendere nell'interfaccia di amministrazione di Microsoft Teams e in AppSource?

Gli sviluppatori possono creare offerte SaaS associate alle Teams app. Queste offerte vengono pubblicate tramite il Centro per i [partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'Microsoft Teams di amministrazione.
 
Gli sviluppatori di app di terze parti possono passare [a Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) per altre informazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)