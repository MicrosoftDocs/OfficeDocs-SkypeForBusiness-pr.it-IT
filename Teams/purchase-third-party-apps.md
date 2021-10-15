---
title: Acquistare app di terze parti per Teams
author: KarliStites
ms.author: kastites
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
ms.openlocfilehash: 6d7a6e1a38327cef327a9de119321127b58909fb
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367534"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acquistare app di terze parti per Teams

Teams le app sono gratuite e alcune potrebbero richiedere abbonamenti al servizio di acquisto per sperimentare tutte le funzionalità e l'ambito dell'app. Questi abbonamenti ai servizi sono chiamati offerte Software as a Service (SaaS), che sono disponibili per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e ora tramite l'interfaccia di amministrazione Microsoft Teams.

La [pagina Gestisci app](manage-apps.md) nell'Microsoft Teams di amministrazione consente di visualizzare e gestire tutte le app Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà a livello di organizzazione delle app, caricare nuove app personalizzate nell'App Store dell'organizzazione, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La **colonna Licenze** nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.

![Screenshot della pagina di gestione delle app per l'acquisto di licenze.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acquistare app nell'interfaccia Teams di amministrazione

> [!IMPORTANT]
> Se si vuole impedire agli utenti di acquistare un'app tramite Teams app store, è necessario bloccare l'app. Per altre informazioni su come bloccare un'app, vedere Gestire i criteri [dell'app](app-policies.md) o come bloccare un'app [a livello di organizzazione.](manage-apps.md#allow-and-block-apps)

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina, è necessario essere un amministratore globale o Teams del servizio.
2. Cercare l'app desiderata. Per identificare le app con un abbonamento SaaS a pagamento, cercare nella **colonna Licenze.** Ogni app avrà uno dei valori seguenti:
    - **Acquisto:** l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.  
    - **Acquistato:** l'app offre un abbonamento SaaS e sono state acquistate licenze per l'app.
    - **- :** l'app non offre un abbonamento SaaS.
3. Dopo aver trovato l'app, fare clic **su Acquista** per passare alla scheda Piani e **prezzi** della pagina dei dettagli dell'app. Esaminare i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Per altre informazioni, selezionare **Altre** informazioni per passare alla pagina dell'app in [AppSource.](https://appsource.microsoft.com/)

> [!NOTE]
> I piani privati possono anche essere elencati per l'acquisto, che includono prezzi speciali che l'organizzazione ha precedentemente negoziato con un ISV. Questi piani avranno l'etichetta **Piano privato** sotto il nome del piano.

4. Per sottoscrivere un'app, scegliere il piano desiderato e selezionare **Acquista.** Il flusso di estrazione si aprirà direttamente nell'Teams di amministrazione.
5. Selezionare il numero di licenze utente da acquistare.
6. Verificare che l'account di fatturazione e l'indirizzo di vendita siano corretti. Se non ne hai già uno, aggiungirne uno nuovo selezionando **Aggiungi**. Per altre informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione.](/microsoft-365/commerce/manage-billing-accounts)

> [!NOTE]
> Per aggiungere un nuovo account di fatturazione, è necessario essere un amministratore globale.

7. Verificare che sia selezionato il profilo di fatturazione corretto. Se non ne hai già uno, aggiungirne uno nuovo selezionando **Aggiungi nuovo**. È possibile pagare con carta di credito, carta di debito o fattura. Il profilo di fatturazione consente anche di aggiungere un numero di ordine di acquisto per identificare l'ordine in un secondo momento. Per altre informazioni sui profili di fatturazione, vedere [Informazioni sui profili di fatturazione.](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)

> [!NOTE]
> La fatturazione tramite fattura è disponibile solo per le transazioni con importo di $ 500.

8. Selezionare **Ordina .**
9. Selezionare **Configura per** attivare l'abbonamento nel sito Web dell'autore. Se non si configura l'abbonamento dopo l'acquisto, è possibile farlo in un secondo momento selezionando **Gestisci licenze.**

Dopo aver acquistato l'offerta SaaS associata all'app Teams, è possibile  visualizzare i dettagli dell'acquisto seguenti nella scheda Piani e prezzi della pagina dei dettagli dell'app.

- **Data di attivazione della licenza:** data in cui è stata attivata la licenza. Se l'account non è ancora configurato, viene visualizzato come Abbonamento in **attesa di attivazione.**
- **Licenze:** numero di licenze acquistate.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda Piani e prezzi della pagina dei dettagli dell'app.":::

Selezionare **Gestisci licenze** per passare al interfaccia di amministrazione di Microsoft 365 per visualizzare e gestire le licenze acquistate.

Gli amministratori globali possono aggiungere altre licenze, rimuovere licenze e annullare abbonamenti per gli acquisti effettuati da chiunque nell'organizzazione. Teams gli amministratori dei servizi possono eseguire le stesse azioni per gli acquisti effettuati da soli. Tuttavia, se un amministratore Teams ha anche il ruolo di amministratore fatturazione, può gestire gli acquisti effettuati da chiunque nell'organizzazione.

> [!NOTE]
> Se un amministratore globale vuole gestire un abbonamento acquistato da un altro amministratore globale, deve essere nello stesso account di fatturazione. È possibile concedere a un altro amministratore globale l'accesso a un abbonamento acquistato selezionando l'app nel interfaccia di amministrazione di Microsoft 365. Da qui, passare a **Visualizza profilo di fatturazione** Selezionare  >  **l'account di fatturazione**  >  **Assegnare ruoli** Aggiungere altri amministratori  >  **globali.**

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Hai un'offerta SaaS per un'app Teams che vuoi elencare e vendere nell'interfaccia di amministrazione di Microsoft Teams AppSource?

Gli sviluppatori possono creare offerte SaaS associate alle Teams app. Queste offerte vengono pubblicate tramite il Centro per i [partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'Microsoft Teams di amministrazione.

Gli sviluppatori di app di terze parti possono passare [a Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) per altre informazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD ruoli predefiniti](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 di amministratore](/microsoft-365/admin/add-users/about-admin-roles)