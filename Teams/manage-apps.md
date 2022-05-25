---
title: Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire le app di Teams nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: c0ee3c70e4f01aa3931006c3b9d03ae372ddf999
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671612"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gestire Teams app nell'interfaccia di amministrazione di Microsoft Teams

Le app per l'organizzazione possono essere gestite in **Teams app** nell'interfaccia di amministrazione. Usare la pagina [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) per visualizzare e gestire tutte le app Teams nel catalogo app dell'organizzazione. La pagina Gestisci app offre una visualizzazione di tutte le app disponibili nel catalogo tenant, fornendo le informazioni necessarie per decidere quali app consentire o bloccare nell'intera organizzazione. Puoi visualizzare lo stato e le proprietà delle app a livello di organizzazione, bloccare o consentire app a livello di organizzazione, caricare nuove app personalizzate nel catalogo tenant e gestire le impostazioni delle app a livello di organizzazione.

![Screenshot della pagina Gestisci app.](media/manage-apps.png)

Per usare Teams'interfaccia di amministrazione, è necessario essere un amministratore globale o un amministratore del servizio Teams. Per informazioni dettagliate, vedere [Teams ruoli di amministratore](./using-admin-roles.md).

Per gestire le app, usare i criteri per controllare le autorizzazioni per gli utenti, l'installazione delle app e il caricamento di app personalizzate create all'interno dell'organizzazione. Per informazioni sui criteri, vedere [Panoramica dei criteri delle app](app-policies.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> La pagina Gestisci app non è disponibile nelle distribuzioni Microsoft 365 Government Community Cloud High (GCCH) o DoD (Department of Defense) di Teams.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Pubblicare un'app personalizzata nell'app store dell'organizzazione

Usare la pagina Gestisci app per pubblicare app create appositamente per l'organizzazione. Dopo la pubblicazione, un'app personalizzata è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata nell'app store dell'organizzazione. La modalità di utilizzo dipende da come si ottiene l'app.

* [Approvare un'app personalizzata](#approve-a-custom-app): usare questo metodo se lo sviluppatore invia l'app direttamente alla pagina Gestisci app usando l'API di invio di app Teams. È quindi possibile rivedere e pubblicare (o rifiutare) l'app direttamente dalla pagina dei dettagli dell'app.
* [Upload un pacchetto dell'app](#upload-an-app-package): usare questo metodo se lo sviluppatore invia il pacchetto dell'app in formato .zip. L'app viene pubblicata caricando il pacchetto dell'app.

### <a name="approve-a-custom-app"></a>Approvare un'app personalizzata

Il widget **Approvazioni in sospeso** nella pagina Gestisci app ti invia una notifica quando uno sviluppatore invia un'app usando l'API di invio di app Teams. Viene elencata un'app appena inviata con **lo stato Pubblicazione** **inviato** e **lo stato** **Bloccato**. Passare alla pagina dei dettagli dell'app per visualizzare altre informazioni sull'app e quindi, per pubblicarla, impostare **Lo stato pubblicazione** su **Pubblica**.

Riceverai anche una notifica quando uno sviluppatore invia un aggiornamento a un'app personalizzata. È quindi possibile rivedere e pubblicare (o rifiutare) l'aggiornamento nella pagina dei dettagli dell'app. Tutti i criteri di autorizzazione e i criteri di configurazione delle app rimangono applicati per l'app aggiornata.

Per altre informazioni, vedi [Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Upload un pacchetto dell'app

Lo sviluppatore crea un pacchetto di app Teams usando [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) e quindi lo invia all'utente in .zip formato. Quando si dispone del pacchetto dell'app, è possibile caricarlo nell'app store dell'organizzazione.

Per caricare una nuova app personalizzata, selezionare **Upload** per caricare il pacchetto dell'app. L'app non viene evidenziata dopo il caricamento, quindi è necessario cercare nell'elenco delle app nella pagina Gestisci app per trovarla.

Per aggiornare un'app dopo il caricamento, seleziona il nome dell'app nell'elenco delle app nella pagina Gestisci app e quindi seleziona **Aggiorna**. In questo modo vengono sostituiti l'app esistente e tutti i criteri di autorizzazione e i criteri di configurazione dell'app rimangono applicati per l'app aggiornata.

Per altre informazioni, vedere [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Consentire e bloccare le app

Nella pagina Gestisci app puoi consentire o bloccare singole app a livello di organizzazione. Mostra ogni app disponibile e lo stato corrente dell'app a livello di organizzazione.

Per consentire o bloccare un'app:

1. Passa all Teams interfaccia di amministrazione > Teams alle app > Gestisci app.
1. Seleziona un'app dall'elenco delle app.
1. Selezionare **Consenti** o **Blocca**.

Quando si blocca o si consente un'app nella pagina Gestisci app, l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione.  Quando si blocca o si consente un'app in un criterio di autorizzazione di un'app Teams, questa viene bloccata o consentita per gli utenti a cui sono assegnati criteri. Per consentire a un utente di installare e interagire con qualsiasi app, è necessario consentire l'app a livello di organizzazione nella pagina Gestisci app e nei criteri di autorizzazione dell'app assegnati all'utente.

 > [!NOTE]
 > Per disinstallare un'app, fare clic con il pulsante destro del mouse sull'app e quindi scegliere **Disinstalla** o usare il menu **Altre app** a sinistra.

## <a name="manage-user-requests-to-unblock-apps"></a>Gestire le richieste degli utenti di sbloccare le app

Puoi visualizzare le richieste di rendere disponibile un'app bloccata per l'uso. La richiesta viene inviata all'amministratore IT, che può visualizzare e gestire le richieste utente nell'interfaccia di amministrazione di Teams.

  :::image type="content" source="media/user-request.png" alt-text="Effettuare una richiesta di approvazione delle app bloccate":::

### <a name="view-a-request"></a>Visualizzare una richiesta

 1. Accedi all'interfaccia di amministrazione di Teams e seleziona [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="Richiesta da parte degli utenti" lightbox="media/requested-apps.png" border="true":::

 1. Per visualizzare e controllare il numero di richieste per ogni app, ordinare le richieste nella colonna **Richieste per utente** .
 1. Seleziona il nome dell'app che vuoi sbloccare e apre la pagina dei dettagli dell'app.
 1. Selezionare **Gestisci richieste** e completare i passaggi visualizzati nella finestra di dialogo popup. La procedura per approvare un'app varia in base al metodo usato per bloccarla.

    * Se l'app viene bloccata tramite criteri di autorizzazione, consentire l'app modificando i [criteri di autorizzazione](teams-app-permission-policies.md).
    * Se l'app è bloccata per tutti gli utenti, [consenti l'app](#allow-and-block-apps).
    * Se tutte le app sono bloccate per tutti gli utenti, modificare [le impostazioni a livello di organizzazione](#manage-org-wide-app-settings).

 Se un amministratore consente un'app, non informa l'utente finale che la richiesta viene agito su di essa. L'utente deve visitare l'app nello Store per verificare se l'app è sbloccata o meno.

### <a name="dismiss-a-user-request"></a>Ignorare una richiesta utente

 1. Seleziona il nome dell'app per cui vuoi ignorare le richieste dell'utente.
 1. Selezionare **Gestisci richieste** e quindi **Ignora tutte le richieste** nella finestra di dialogo.
 1. Quando una richiesta viene ignorata, l'utente viene reimpostato su zero.

  :::image type="content" source="media/reject.png" alt-text="il rifiuto delle app bloccate."border="true":::

Se un amministratore ignora una richiesta, non informa l'utente finale che la richiesta viene agito su di essa. L'utente deve visitare l'app nello Store per verificare se l'app è sbloccata o meno.

## <a name="apps-blocked-by-publishers"></a>App bloccate dagli autori

Quando un ISV pubblica un'app nell'app store globale, potrebbe essere necessario che gli amministratori configurino o personalizzino l'esperienza dell'app. L'amministratore può renderla disponibile agli utenti finali quando l'app è completamente configurata.

Ad esempio, Contoso Electronics è un ISV che ha creato un'app help desk per Microsoft Teams. Contoso Electronics vuole che i clienti configurino alcune proprietà dell'app in modo che, quando gli utenti interagiscono con l'app, funzioni come previsto. Prima che un amministratore possa consentire o bloccare l'applicazione, verrà **visualizzata come Bloccata dall'autore** nell'interfaccia di amministrazione di Teams e verrà nascosta agli utenti finali per impostazione predefinita. Dopo aver seguito le indicazioni dell'autore per configurare l'app, è possibile renderla disponibile agli utenti impostando lo stato **su Consentito** o impedire agli utenti di usarla impostando lo stato su **Bloccata**.

![Screenshot di bloccato dallo stato dell'autore nell'interfaccia di amministrazione di Teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Aggiungere un'app a un team

Si usa il pulsante **Aggiungi al team** per installare un'app in un team. Tenere presente che questo vale solo per le app che possono essere installate in un ambito del team. Il pulsante **Aggiungi al team** non è disponibile per le app che possono essere installate solo nell'ambito personale.

![Screenshot del pulsante Aggiungi al team.](media/manage-apps-add-app-team.png)

1. Cerca l'app desiderata e quindi seleziona l'app facendo clic a sinistra del nome dell'app.
1. Selezionare **Aggiungi al team**.
1. Nel riquadro **Aggiungi al team** cercare il team a cui si vuole aggiungere l'app, selezionare il team e quindi selezionare **Applica**.

## <a name="customize-an-app"></a>Personalizzare un'app

È ora possibile personalizzare un'app per includere un aspetto specifico in base alle esigenze dell'organizzazione. Vedere [Personalizzare le app in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Acquisto di servizi per app di terze parti

È possibile cercare e acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione direttamente dalla pagina Gestisci app. La colonna **Licenze** nella tabella indica se un'app offre un abbonamento SaaS a pagamento. Selezionare **Acquista ora** per visualizzare i piani e le informazioni sui prezzi e acquistare licenze per gli utenti. Per altre informazioni, vedere [Acquistare servizi per Teams app di terze parti nell'interfaccia di amministrazione di Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Concedere il consenso dell'amministratore alle app

È possibile esaminare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. In questo modo gli utenti non dovranno rivedere e accettare le autorizzazioni richieste dall'app all'avvio dell'app. La colonna **Autorizzazioni** indica se un'app ha autorizzazioni che richiedono il consenso. Verrà visualizzato un collegamento **Visualizza dettagli** per ogni app registrata in Azure AD con autorizzazioni che richiedono il consenso. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Visualizzare le autorizzazioni di consenso specifiche per le risorse

Le autorizzazioni per il consenso specifico delle risorse consentono ai proprietari del team di concedere a un'app il consenso per l'accesso e la modifica dei dati di un team. Le autorizzazioni RSC sono granulari, Teams autorizzazioni specifiche che definiscono cosa può fare un'app in un team specifico. È possibile visualizzare le autorizzazioni RSC nella scheda **Autorizzazioni** della pagina dei dettagli dell'app per un'app. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni delle app a livello di organizzazione

Usare le impostazioni delle app a livello di organizzazione per controllare se gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza delle app frontline personalizzate (presto disponibili), se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con le app personalizzate nell'organizzazione. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. È possibile usarle per controllare eventuali app dannose o problematiche.

> [!NOTE]
> Per informazioni su come usare le impostazioni delle app a livello di organizzazione in Microsoft 365 Government - Government Community Cloud le distribuzioni High GCCH e Department of Defense (DoD) di Teams, vedere [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md).

1. Nella pagina Gestisci app seleziona **Impostazioni app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel riquadro.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot del riquadro Impostazioni app a livello di organizzazione nella pagina Gestisci app":::

1. (Presto disponibile) In **App personalizzate** disattiva o attiva **Mostra app personalizzate**. Quando questa impostazione è attivata, gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza app frontline personalizzata. Questa esperienza aggiunge le app più rilevanti in Teams per gli operatori in prima linea. Per altre informazioni, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

    Questa funzionalità è disponibile per le licenze F. Altri tipi di licenza saranno supportati in futuro.
1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    * **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se disattivi questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app viene visualizzato come Bloccato a **livello di organizzazione** nella tabella.

        > [!NOTE]
        > Quando **l'opzione Consenti app di terze parti** è disattivata, [i webhook in uscita sono ancora abilitati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) per tutti gli utenti, ma è possibile controllarli a livello di utente consentendo o bloccando l'app Webhook in uscita tramite [criteri di autorizzazione dell'app](teams-app-permission-policies.md). Se sono presenti [criteri di autorizzazione](teams-app-permission-policies.md) per le **app Microsoft** che usano l'impostazione **Consenti app specifiche e bloccano tutte le altre** e si vogliono abilitare i webhook in uscita per gli utenti, aggiungere l'app Webhook in uscita all'elenco.

        > [!NOTE]
        > Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione.

    * **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa impostazione consente di controllare se eventuali nuove app di terze parti pubblicate nello Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App personalizzate** disattiva o attiva **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [Gestisci criteri e impostazioni app personalizzate in Teams](teams-custom-app-policies-and-settings.md).
1. Seleziona **Salva** per rendere effettive le impostazioni delle app a livello di organizzazione.
