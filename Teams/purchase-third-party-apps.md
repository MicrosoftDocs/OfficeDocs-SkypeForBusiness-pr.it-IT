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
description: Informazioni su come acquistare app di terze parti per Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 84a527fbd8ec59817b4f0d3ee64a970c44d9abd4
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712930"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acquistare app di terze parti per Teams

Teams app sono gratuite per l'installazione e alcune potrebbero richiedere l'acquisto di abbonamenti ai servizi per sfruttare tutte le funzionalità e l'ambito dell'app. Queste sottoscrizioni ai servizi sono denominate offerte SaaS (Software as a Service), che sono disponibili per l'acquisto tramite [AppSource](https://appsource.microsoft.com/) e ora tramite l'interfaccia di amministrazione di Microsoft Teams.

La pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams consente di visualizzare e gestire tutte le app Teams per l'organizzazione. Ad esempio, è possibile visualizzare lo stato e le proprietà delle app a livello di organizzazione, caricare nuove app personalizzate nell'app store dell'organizzazione, bloccare o consentire app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.

Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione. La colonna **Licenze** nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.

![Screenshot della pagina di gestione delle app per l'acquisto di licenze.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acquistare app nell'interfaccia di amministrazione di Teams

> [!IMPORTANT]
> Quando abiliti l'acquisto di app, viene attivato anche l'acquisto in-app. Gli utenti possono vedere offerte di acquisto in-app controllate dall'ISV per la loro app. Se vuoi impedire ai tuoi utenti di acquistare un'app, devi bloccare l'app. Per altre informazioni su come bloccare un'app, vedere [Gestire i criteri delle app](app-policies.md) o [informazioni su come bloccare un'app a livello di organizzazione](manage-apps.md#allow-and-block-apps).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina è necessario essere un amministratore globale o Teams del servizio.
1. Cercare l'app desiderata. Per identificare le app con un abbonamento SaaS a pagamento, cercare nella colonna **Licenze** . Ogni app avrà uno dei valori seguenti:
    - **Acquisto**: l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.  
    - **Acquistato**: l'app offre un abbonamento SaaS per cui sono state acquistate licenze.
    - **- -**: l'app non offre un abbonamento SaaS.
1. Dopo aver trovato l'app, fare clic su **Acquista** per passare alla scheda **Piani e prezzi** della pagina dei dettagli dell'app. Esamina i piani e le informazioni sui prezzi per l'offerta SaaS per l'app. Se hai bisogno di altre informazioni, seleziona **Altre informazioni** per passare alla pagina dell'app in [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > I piani privati possono anche essere elencati per l'acquisto, che includono prezzi speciali che l'organizzazione ha negoziato in precedenza con un ISV. Questi piani avranno l'etichetta **Piano privato** sotto il nome del piano.

1. Per abbonarsi a un'app, scegliere il piano desiderato e selezionare **Acquista**. Il flusso di cassa verrà aperto direttamente nell'interfaccia di amministrazione di Teams.

1. Selezionare il numero di licenze utente da acquistare.
1. Verifica che l'account di fatturazione e l'indirizzo venduto siano corretti. Se non ne hai già uno, aggiungirne uno nuovo selezionando **Aggiungi**. Per altre informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Per aggiungere un nuovo account di fatturazione, è necessario essere un amministratore globale.

1. Verificare che sia selezionato il profilo di fatturazione corretto. Se non ne hai già uno, aggiungirne uno nuovo selezionando **Aggiungi nuovo**. È possibile pagare con carta di credito, carta di debito [o fatturazione.](#invoice-billing) Il profilo di fatturazione consente anche di aggiungere un numero di ordine d'acquisto per identificare l'ordine in un secondo momento. Per altre informazioni sui profili di fatturazione, vedere [Informazioni sui profili di fatturazione](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
1. Seleziona **Effettua ordine**.
1. Selezionare **Configura** per attivare l'abbonamento nel sito Web dell'autore. Se non si configura l'abbonamento dopo l'acquisto, è possibile farlo in un secondo momento selezionando **Gestisci licenze**.

Dopo aver acquistato l'offerta SaaS associata all'app Teams, è possibile visualizzare i dettagli di acquisto seguenti nella scheda **Piani e prezzi** della pagina dei dettagli dell'app.

- **Data di attivazione della licenza**: data di attivazione della licenza. Se l'account non è ancora configurato, viene visualizzato come **Attivazione in sospeso dell'abbonamento**.
- **Licenze**: numero di licenze acquistate.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda Piani e prezzi della pagina dei dettagli dell'app.":::

Selezionare **Gestisci licenze** per passare alla interfaccia di amministrazione di Microsoft 365 per visualizzare e gestire le licenze acquistate.

Gli amministratori globali possono aggiungere altre licenze, rimuovere licenze e annullare gli abbonamenti per gli acquisti effettuati da chiunque nell'organizzazione. Teams amministratori dei servizi possono eseguire le stesse azioni per gli acquisti effettuati da soli. Tuttavia, se un amministratore del servizio Teams ha anche il ruolo di amministratore fatturazione, può gestire gli acquisti effettuati da chiunque nell'organizzazione.

> [!NOTE]
> Se un amministratore globale vuole gestire un abbonamento acquistato da un altro amministratore globale, deve avere lo stesso account di fatturazione. È possibile concedere a un altro amministratore globale l'accesso a un abbonamento acquistato selezionando l'app nel interfaccia di amministrazione di Microsoft 365. Da qui, vai a **Visualizza profilo** >  di **fatturazioneSeleziona account** >  di **fatturazioneAssegnare ruoliAggiungere** >  **altri amministratori globali**.

### <a name="invoice-billing"></a>Fatturazione tramite fattura

- La fatturazione tramite fattura è disponibile come opzione di pagamento per alcune transazioni.
- La prima volta che si usa la fatturazione tramite fattura è necessaria una verifica del credito, che può richiedere fino a 24-48 ore per l'approvazione. La fatturazione tramite fattura sarà disponibile solo dopo il completamento della verifica del credito. Puoi effettuare l'ordine con una carta di credito o riprovare più tardi dopo l'approvazione della revisione del credito.
- La fatturazione è disponibile solo per gli amministratori globali o per gli amministratori con autorizzazioni di amministratore dei servizi di Teams e di fatturazione.
- La fatturazione tramite fattura non è disponibile quando si acquista un piano con una versione di valutazione gratuita di 30 giorni.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Hai un'offerta SaaS per un'app Teams che vuoi elencare e vendere nell'interfaccia di amministrazione di Microsoft Teams e AppSource?

Gli sviluppatori possono creare offerte SaaS associate alle loro app Teams. Queste offerte vengono pubblicate tramite il [Centro per i partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'interfaccia di amministrazione di Microsoft Teams.

Gli sviluppatori di app di terze parti possono accedere a [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) per altre informazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Creare un'offerta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD ruoli predefiniti](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles)
