---
title: Acquistare app di terze parti per Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Informazioni su come acquistare app di terze parti da Teams Store usando una carta di credito, una carta di debito o tramite fatturazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880240"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acquistare app di terze parti per Teams

Le app di Teams sono gratuite per l'installazione e alcune possono richiedere l'acquisto di abbonamenti ai servizi per sperimentare tutte le funzionalità e l'ambito dell'app. Queste sottoscrizioni ai servizi sono denominate offerte SaaS (Software as a Service), che sono disponibili per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e ora tramite [l'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com).

La pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams consente di visualizzare e gestire tutte le app di Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà delle app a livello di organizzazione, caricare nuove app personalizzate nell'app store dell'organizzazione, bloccare o consentire app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La colonna **Licenze** nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.

![Screenshot della pagina di gestione delle app per l'acquisto di licenze.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acquistare app nell'interfaccia di amministrazione di Teams

> [!IMPORTANT]
> Quando abiliti l'acquisto di app, viene attivato anche l'acquisto in-app. Gli utenti possono vedere offerte di acquisto in-app controllate dall'ISV per la loro app. Se vuoi impedire ai tuoi utenti di acquistare un'app, devi bloccare l'app. Per altre informazioni su come bloccare un'app, vedere [Gestire i criteri delle app](app-policies.md) o [informazioni su come bloccare un'app a livello di organizzazione](manage-apps.md#allow-and-block-apps).

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams passare alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**. Per accedere alla pagina è necessario essere un amministratore globale o un amministratore del servizio Teams.

1. Cercare l'app desiderata in base al nome. Per identificare le app con un abbonamento SaaS a pagamento, cercare nella colonna **Licenze** . Ogni app ha uno dei valori seguenti:
    * **Acquisto**: l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.  
    * **Acquistato**: l'app offre un abbonamento SaaS per cui sono state acquistate licenze.
    * **- -**: l'app non offre un abbonamento SaaS.

1. Quando trovi l'app, seleziona **Acquista** per passare alla scheda **Piani e prezzi** della pagina dei dettagli dell'app. Esamina i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Se hai bisogno di altre informazioni, seleziona **Altre informazioni** per passare alla pagina dell'app in [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > I piani privati possono anche essere elencati per l'acquisto, che includono prezzi speciali che l'organizzazione ha negoziato in precedenza con un ISV. Questi piani avranno l'etichetta **Piano privato** sotto il nome del piano.

1. Per abbonarsi a un'app, scegliere il piano desiderato e selezionare **Acquista**. Il flusso di cassa si apre direttamente nell'interfaccia di amministrazione di Teams.

1. Selezionare il numero di licenze utente da acquistare.

1. Verificare che l'account di fatturazione e l'indirizzo venduto siano corretti. Se non ne hai già uno, seleziona **Aggiungi**. Per altre informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Solo un Amministrazione globale può aggiungere un nuovo account di fatturazione.

1. Verificare che sia selezionato il profilo di fatturazione corretto. Se non ne hai già uno, seleziona **Aggiungi nuovo**. È possibile pagare con carta di credito, carta di debito [o fatturazione.](#invoice-billing) Il profilo di fatturazione consente anche di aggiungere un numero di ordine d'acquisto per identificare l'ordine in un secondo momento. Per altre informazioni sui profili di fatturazione, vedere [Informazioni sui profili di fatturazione](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Seleziona **Effettua ordine**.

1. Selezionare **Configura** per attivare l'abbonamento nel sito Web dell'autore. Se non si configura l'abbonamento dopo l'acquisto, è possibile farlo in un secondo momento selezionando **Gestisci licenze**.

Dopo aver acquistato l'offerta SaaS associata all'app Teams, è possibile visualizzare i dettagli di acquisto seguenti nella scheda **Piani e prezzi** della pagina dei dettagli dell'app.

* **Data di attivazione della licenza**: data di attivazione della licenza. Se l'account non è ancora configurato, viene visualizzato come **Abbonamento in sospeso per l'attivazione**.
* **Licenze**: numero di licenze acquistate.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda Piani e prezzi nella pagina dei dettagli dell'app nell'interfaccia di amministrazione di Teams.":::

Per visualizzare e gestire le licenze acquistate, selezionare **Gestisci licenze** per accedere alla interfaccia di amministrazione di Microsoft 365.

Gli amministratori globali possono aggiungere altre licenze, rimuovere licenze e annullare gli abbonamenti per gli acquisti effettuati da chiunque nell'organizzazione. Gli amministratori del servizio Teams possono eseguire le stesse azioni per gli acquisti effettuati da soli. Tuttavia, se un amministratore del servizio Teams ha anche il ruolo di amministratore fatturazione, può gestire gli acquisti effettuati da chiunque nell'organizzazione.

> [!NOTE]
> Se un Amministrazione globale vuole gestire un abbonamento acquistato da un altro Amministrazione globale, deve trovarsi nello stesso account di fatturazione. È possibile concedere a un altro Amministrazione globale l'accesso a un abbonamento acquistato selezionando l'app nel [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com). Da qui, vai a **Visualizza profilo** >  di fatturazione **Seleziona account** >  di fatturazione **Assegna ruoli** > **Aggiungi altri amministratori globali**.

### <a name="invoice-billing"></a>Fatturazione tramite fattura

* La fatturazione tramite fattura è disponibile come opzione di pagamento per alcune transazioni.
* La prima volta che si usa la fatturazione tramite fattura è necessaria una verifica del credito, che può richiedere fino a 24-48 ore per l'approvazione. La fatturazione tramite fattura sarà disponibile solo dopo il completamento della verifica del credito. Puoi effettuare l'ordine con una carta di credito o riprovare più tardi dopo l'approvazione della revisione del credito.
* La fatturazione è disponibile solo per gli amministratori globali o per gli amministratori con autorizzazioni di amministratore dei servizi di Teams e di fatturazione.
* La fatturazione tramite fattura non è disponibile quando si acquista un piano con una versione di valutazione gratuita di 30 giorni.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Elencare e vendere un'offerta SaaS per un'app Teams

Gli sviluppatori possono creare offerte SaaS associate alle loro app Teams. Queste offerte vengono pubblicate tramite [il Centro per i partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'interfaccia di amministrazione di Microsoft Teams.

Per altre informazioni per gli sviluppatori di app di terze parti, vedi [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Articoli correlati

* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Ruoli predefiniti di Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Ruoli di amministratore di Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
