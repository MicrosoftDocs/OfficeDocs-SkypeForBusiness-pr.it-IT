---
title: Servizi di acquisto per le app di terze parti nell'interfaccia di amministrazione di Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come acquistare servizi per le app di terze parti di teams nella pagina Manage Apps dell'interfaccia di amministrazione di Microsoft teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: aeff6f363c1ae594a4a122055204d98b43d246e8
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818155"
---
<a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a>Servizi di acquisto per le app di terze parti nell'interfaccia di amministrazione di Microsoft Teams
======================================================

> [!NOTE]
> Questa caratteristica è attualmente disponibile solo negli Stati Uniti.

Le app teams sono gratuite per l'installazione e alcune possono richiedere l'acquisto di abbonamenti ai servizi per provare la piena funzionalità e l'ambito dell'app. Questi abbonamenti ai servizi sono denominati offerte SaaS (software as a Service), disponibili per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e ora tramite l'interfaccia di amministrazione di Microsoft teams.

La pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams consente di visualizzare e gestire tutte le app teams per l'organizzazione. Ad esempio, puoi vedere lo stato e le proprietà a livello di organizzazione delle app, caricare le nuove app personalizzate nell'App Store dell'azienda, bloccare o consentire le app a livello di organigramma e gestire le impostazioni dell'app in tutto l'organigramma.

In questa sezione puoi anche acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La colonna **licenze** nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot che mostra le app di terze parti con abbonamenti SaaS":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Cercare e acquistare servizi per un'app di terze parti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**. Per accedere alla pagina è necessario essere un amministratore globale o un servizio di teams.
2. Cercare l'app desiderata. Per identificare le app che hanno un abbonamento a SaaS pagato, cercare nella colonna **licenze** . Ogni app avrà uno dei valori seguenti:
    - **Acquista ora**: l'app offre un abbonamento a Saas ed è disponibile per l'acquisto.  
    - **Acquistato**: l'app offre un abbonamento a Saas e ne hai acquistato le licenze.
    - **--**: L'app non offre un abbonamento a Saas.
3. Quando si trova l'app, fare clic su **Acquista ora** per accedere alla scheda **piani e prezzi** della pagina Dettagli app. Esaminare i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Se sono necessarie altre informazioni, fare clic sul collegamento **Leggi altre** per accedere alla pagina dell'app in [AppSource](https://appsource.microsoft.com/).  
4. Per acquistare un piano, fare clic su **Acquista ora**. Verrai reindirizzato all'esperienza di acquisto per l'offerta associata all'app teams. Questo è il punto in cui si completa l'acquisto del servizio o dell'offerta SaaS.
5. Scegliere il piano desiderato. Se l'offerta SaaS include più di un piano, fare clic su **Cambia** per visualizzare l'elenco dei piani disponibili.
6. Selezionare il termine di fatturazione ( **mensile** o **annuale**) e quindi immettere il numero di licenze utente che si vuole acquistare.
7. Immettere il metodo di pagamento.
8. Quando si è pronti, selezionare **Inserisci ordine**.
9. Fare clic su **Configura ora** per attivare l'abbonamento nel sito Web dell'autore.

Dopo aver acquistato l'offerta SaaS associata all'app teams, è possibile visualizzare i dettagli di acquisto seguenti nella scheda **piani e prezzi** della pagina Dettagli app.

- **Data di attivazione della licenza**: data in cui è stata attivata la licenza. Se l'account non è ancora configurato, viene visualizzato come **attivazione in sospeso dell'abbonamento**.
- **Licenze**: numero di licenze acquistate.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda piani e prezzi della pagina Dettagli app":::

Selezionare **Gestisci licenze** per accedere all'interfaccia di amministrazione di Microsoft 365 per visualizzare e gestire le licenze acquistate e gestire le assegnazioni di licenze per gli utenti.

Gli amministratori globali possono visualizzare gli acquisti effettuati da chiunque nell'organizzazione, mentre gli amministratori del servizio teams possono solo visualizzare gli acquisti effettuati da soli.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Avere un'offerta SaaS per un'app teams che si vuole elencare e vendere nell'interfaccia di amministrazione di Microsoft teams e AppSource?

Gli sviluppatori possono creare offerte SaaS associate alle app teams. Queste offerte vengono pubblicate tramite [centro partner](https://partner.microsoft.com) e sono disponibili per le organizzazioni per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e l'interfaccia di amministrazione di Microsoft teams.
 
Gli sviluppatori di app di terze parti possono scegliere di [creare un'offerta SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) per altre informazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Creare un'offerta SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
