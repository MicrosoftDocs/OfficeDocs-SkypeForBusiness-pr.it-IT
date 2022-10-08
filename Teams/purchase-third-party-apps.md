---
title: Acquistare app di terza parte per Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Informazioni su come acquistare app di terze parti da Teams Store usando una carta di credito, una carta di debito o tramite fatturazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 20abb80fed79995bd8496a04936737265503e67e
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377194"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acquistare app di terza parte per Teams

Le app di Teams sono gratuite e alcune possono richiedere l’acquisto di sottoscrizioni assistenza per sperimentare la funzionalità e l'ambito completi dell'app. Queste sottoscrizioni assistenza sono denominate offerte SaaS (Software as a Service), disponibili per l'acquisto tramite[AppSource](https://appsource.microsoft.com/) e ora tramite [l'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com).

La pagina[Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams consente di visualizzare e gestire tutte le app di Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà delle app a livello di organizzazione, caricare nuove app personalizzate nell'app store dell'organizzazione, bloccare o consentire app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La colonna **Licenze** nella tabella indica se un'app offre una sottoscrizione SaaS da acquistare. Gli utenti finali possono acquistare app con una carta di credito, una carta di debito o con fatturazione.

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Screenshot che mostra la pagina di gestione delle app per le licenze di acquisto.":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acquistare app nell'interfaccia di amministrazione di Teams

Per acquistare app nell'interfaccia di amministrazione di Teams, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**. Per accedere alla pagina, è necessario essere un amministratore globale o un amministratore del servizio Teams.

1. Cercare l'app desiderata in base al nome. Per identificare le app con un abbonamento SaaS a pagamento, vedere la colonna **Licenze**. Ogni app ha uno dei valori seguenti:
    * **Acquistare**: l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.
    * **Acquistato**: l'app offre un abbonamento SaaS e le relative licenze sono state acquistate.
    * **- -**: l'app non offre un abbonamento SaaS.

1. Quando trovi l'app, seleziona **Acquista** per passare alla scheda **Piani e abbonamenti** della pagina dei dettagli dell'app. Esaminare i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Se si ha bisogno di altre informazioni, selezionare **Altre informazioni** per passare alla pagina dell'app in [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > I piani privati possono anche essere elencati per l'acquisto a un prezzo speciale che l'organizzazione ha precedentemente negoziato con uno sviluppatore app. Questi piani hanno l'etichetta **Piano privato** sotto il nome del piano.

1. Per abbonarsi a un'app, scegliere il piano desiderato e selezionare **Acquista**. Il flusso di checkout si apre direttamente nell'interfaccia di amministrazione di Teams.

1. Selezionare il numero di licenze utente da acquistare.

1. Verificare che l'account di fatturazione e l'indirizzo venduto siano corretti. Se non se ne ha già uno, selezionare **Aggiungi**. Per altre informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Solo un Amministrazione globale può aggiungere un nuovo account di fatturazione.

1. Verificare che sia selezionato il profilo di fatturazione corretto. Se non se ne ha già uno, selezionare **Aggiungi nuovo**. È possibile pagare con carta di credito, carta di debito [o fatturazione.](#invoice-billing) Il profilo di fatturazione consente anche di aggiungere un numero di ordine di acquisto per identificare l'ordine in un secondo momento. Per altre informazioni sui profili di fatturazione, vedere [Informazioni sui profili di fatturazione](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Selezionare **Esegui ordine**.

1. Selezionare **Configura** per attivare l'abbonamento al sito Web dello sviluppatore dell'app. Se non si configura l'abbonamento dopo l'acquisto, è possibile farlo in un secondo momento selezionando **Gestisci abbonamenti**.

Dopo aver acquistato l'offerta SaaS associata all'app Teams, è possibile visualizzare i dettagli di acquisto seguenti nella scheda **Piani e abbonamenti** della pagina dei dettagli dell'app.

* **Data di attivazione della licenza**: la data in cui è stata attivata la licenza.
* **Licenze**: numero di licenze acquistate.

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Screenshot della scheda Piani e prezzi nella pagina dei dettagli dell'app nell'interfaccia di amministrazione di Teams." lightbox="media/purchase-third-party-apps-details-page.png":::

Selezionare **Gestisci abbonamenti** per visualizzare e gestire le licenze acquistate.

Gli amministratori globali possono visualizzare gli abbonamenti acquistati da chiunque nell'organizzazione, ma possono solo aggiungere altre licenze, rimuovere licenze e annullare gli abbonamenti per gli acquisti effettuati da chiunque nel proprio account di fatturazione. Gli amministratori del servizio Teams possono eseguire le stesse azioni per gli acquisti effettuati autonomamente.

> [!NOTE]
> Se un Amministrazione globale vuole gestire un abbonamento acquistato da un altro Amministrazione globale, deve trovarsi nello stesso account di fatturazione. È possibile concedere a un altro Amministrazione globale l'accesso a un abbonamento acquistato selezionando l'app nell’[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com). Nell'interfaccia di amministrazione, accedere a **Visualizza profilo di fatturazione** > **Seleziona account di fatturazione** > **Assegna ruoli** > **Aggiungi altri amministratori globali**.

> [!IMPORTANT]
> Quando si abilita l'acquisto di app, verrà attivato anche l'acquisto in-app. Gli utenti possono visualizzare le offerte di acquisto in-app controllate dallo sviluppatore app per la propria app. Se si vuole impedire agli utenti di acquistare un'app, è necessario bloccare l'app.

### <a name="invoice-billing"></a>Emissione fattura

* Il pagamento tramite fattura è disponibile come opzione di pagamento per alcune transazioni.
* La prima volta che si usa il pagamento tramite fattura è necessaria una verifica del credito, che può richiedere fino a 24-48 ore per l'approvazione. Il pagamento tramite fattura sarà disponibile solo dopo il completamento della verifica del credito. Puoi effettuare l'ordine con una carta di credito o riprovare più tardi dopo l'approvazione della revisione del credito.
* La fatturazione è disponibile solo per gli amministratori globali o per gli amministratori con autorizzazioni di amministratore dei servizi di Teams e di fatturazione.
* Il pagamento tramite fattura non è disponibile quando si acquista un piano con una versione di valutazione gratuita di 30 giorni.

## <a name="manage-subscriptions-in-teams-admin-center"></a>Gestire gli abbonamenti nell'interfaccia di amministrazione di Teams

Nell'interfaccia di amministrazione di Teams è possibile gestire le sottoscrizioni delle app e le licenze acquistate. Puoi visualizzare l'elenco delle sottoscrizioni delle app e i relativi dettagli ed eseguire le azioni seguenti:

* Modificare un piano
* Acquistare o rimuovere una licenza
* Aggiornare un metodo di pagamento
* Annullare un abbonamento
* Visualizzare la fattura

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="Screenshot dei dettagli dell'abbonamento di un'app." lightbox="media/manage-existing-subscriptions-all.png":::

Per gestire gli abbonamenti, procedere come segue:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams**[**Gestire le app**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Selezionare la scheda **Abbonamenti** per visualizzare gli abbonamenti acquistati.

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="Screenshot dell'opzione di abbonamento per un'app nella pagina Gestisci app." lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> Nell'interfaccia di amministrazione di Teams è possibile gestire le sottoscrizioni delle app acquistate dall'utente o da altri amministratori che fanno parte dello stesso account di fatturazione. Per visualizzare tutte le sottoscrizioni di app acquistate per lo stesso tenant da altri amministratori o acquistate con account di fatturazione diversi, visitare il [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/adminportal/home#/homepage).

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Elencare e vendere un'offerta SaaS per un'app Teams

Gli sviluppatori possono creare offerte SaaS associate alle loro app Teams. Queste offerte vengono pubblicate tramite [il Centro per i partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'interfaccia di amministrazione di Microsoft Teams.

Per altre informazioni per gli sviluppatori di app di terze parti, vedi [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Articoli correlati

* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Ruoli predefiniti di Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Ruoli di amministratore di Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
