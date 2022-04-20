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
ms.openlocfilehash: 830850be078da8086253bbb57bb4a29ce6d7c951
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2022
ms.locfileid: "64961239"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app nell'interfaccia di amministrazione di Microsoft Teams

Gli amministratori possono visualizzare e gestire tutte le app Teams per l'organizzazione. Nella pagina Gestisci app dell'interfaccia di amministrazione di Teams è possibile:

- [Consentire o bloccare app a livello di organizzazione](#allow-and-block-apps)
- [App bloccate dagli autori](#apps-blocked-by-publishers)
- [Aggiungere app ai team](#add-an-app-to-a-team)
- [Approvare o caricare nuove app personalizzate nell'app store dell'organizzazione](#publish-a-custom-app-to-your-organizations-app-store)
- [Visualizzare le autorizzazioni richieste dalle app](#view-resource-specific-consent-permissions)
- [Concedere il consenso alle app](#grant-admin-consent-to-apps)
- [Servizio di acquisto per app di terze parti](#purchase-services-for-third-party-apps)
- [Vedi lo stato a livello di organizzazione e le proprietà delle app](#view-apps)
- [Gestire le impostazioni delle app a livello di organizzazione](#manage-org-wide-app-settings)
- [Visualizzare le informazioni sulla sicurezza e la conformità per le app certificate per Microsoft 365](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

La pagina Gestisci app offre una visualizzazione di tutte le app disponibili, fornendo le informazioni necessarie per decidere quali app consentire o bloccare nell'intera organizzazione. È quindi possibile usare [i criteri di autorizzazione delle app](teams-app-permission-policies.md), i [criteri di configurazione delle app](teams-app-setup-policies.md), i [criteri e le impostazioni delle app personalizzati](teams-custom-app-policies-and-settings.md) per configurare l'esperienza dell'app per utenti specifici dell'organizzazione.

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina è necessario essere un amministratore globale o Teams servizio.

![Screenshot della pagina App gestite.](media/manage-apps.png)

> [!NOTE]
> La pagina Gestisci app non è ancora disponibile nelle distribuzioni Microsoft 365 Government Community Cloud High (GCCH) o Del Dipartimento della difesa (DoD) di Teams.

## <a name="view-apps"></a>Visualizzare le app

È possibile visualizzare ogni app, incluse le informazioni seguenti su ogni app.

![Screenshot della pagina dei dettagli delle app per un'app.](media/app-detail-page.jpg)

- **Nome**: nome dell'app. Seleziona il nome dell'app per passare alla pagina dei dettagli dell'app per visualizzare altre informazioni sull'app. Include una descrizione dell'app, che sia consentita o bloccata, versione, informativa sulla privacy, condizioni per l'utilizzo, categorie che si applicano all'app, stato della certificazione, funzionalità supportate e ID app.
- **Certificazione**: se l'app ha superato la certificazione, vedrai **Microsoft 365 certificato** o **Publisher attestazione**. Seleziona il collegamento per visualizzare i dettagli della certificazione per l'app. Se viene visualizzato `--`, non sono disponibili informazioni sulla certificazione per l'app. Per altre informazioni sulle app certificate in Teams, leggi [Microsoft 365 programma di certificazione app](/microsoft-365-app-certification/overview).
- **Publisher**: nome dell'autore.
- **Stato pubblicazione**: stato di pubblicazione delle app personalizzate.
- **Stato**: stato dell'app a livello di organizzazione, che può essere uno dei seguenti:
  - **Consentito**: l'app è disponibile per tutti gli utenti dell'organizzazione.
  - **Bloccata**: l'app è bloccata e non è disponibile per gli utenti dell'organizzazione.
  - **Bloccata dall'autore**: l'app viene bloccata dall'autore e nascosta agli utenti finali per impostazione predefinita. Dopo aver configurato l'app usando le indicazioni dell'autore, è possibile consentire o bloccare l'app per renderla disponibile agli utenti finali.
  - **A livello di organizzazione bloccata**: l'app è bloccata nelle impostazioni dell'app a livello di organizzazione.
      È importante sapere che questa colonna rappresenta lo stato consentito e bloccato delle app precedentemente presenti nel riquadro **delle impostazioni a livello di organizzazione** . Ora puoi visualizzare, bloccare e consentire le app a livello di organizzazione nella pagina **Gestisci app** .
- **Licenze**: indica se un'app offre un abbonamento SaaS (Software as a Service) per l'acquisto. Questa colonna si applica solo alle app di terze parti. Ogni app di terze parti avrà uno dei valori seguenti:
  - **Acquisto**: l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.  
  - **Acquistato**: l'app offre un abbonamento SaaS per cui sono state acquistate licenze.
  - **- -**: l'app non offre un abbonamento SaaS.
- **App personalizzata**: se l'app è un'app personalizzata.
- **Autorizzazioni**: indica se un'app di terze parti o personalizzata registrata in Azure Active Directory (Azure AD) dispone di autorizzazioni che richiedono il consenso. Verrà visualizzato uno dei valori seguenti:
  - **Visualizza dettagli**: l'app dispone di autorizzazioni che richiedono il consenso prima che l'app possa accedere ai dati.
  - **- -**: l'app non dispone di autorizzazioni che richiedono il consenso.
- **Categorie**: categorie applicabili all'app.
- **Versione**: versione dell'app.
- **L'amministratore può installare nelle riunioni**: indica se un'app può essere installata dagli amministratori nelle riunioni del team. [Ulteriori informazioni](teams-app-setup-policies.md#install-apps)

Per visualizzare le informazioni desiderate nella tabella, selezionare **Modifica colonna** nell'angolo in alto a destra per aggiungere o rimuovere colonne dalla tabella.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Pubblicare un'app personalizzata nell'app store dell'organizzazione

Usare la pagina Gestisci app per pubblicare app create appositamente per l'organizzazione. Dopo la pubblicazione, un'app personalizzata è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata nell'app store dell'organizzazione. La modalità di utilizzo dipende da come si ottiene l'app.

- [Approvare un'app personalizzata](#approve-a-custom-app): usare questo metodo se lo sviluppatore invia l'app direttamente alla pagina Gestisci app usando l'API di invio di app Teams. È quindi possibile rivedere e pubblicare (o rifiutare) l'app direttamente dalla pagina dei dettagli dell'app.
- [Upload un pacchetto dell'app](#upload-an-app-package): usare questo metodo se lo sviluppatore invia il pacchetto dell'app in formato .zip. L'app viene pubblicata caricando il pacchetto dell'app.

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

Nella pagina Gestisci app puoi consentire o bloccare singole app a livello di organizzazione. Mostra ogni app disponibile e lo stato corrente dell'app a livello di organizzazione. Il blocco e l'abilitazione di app a livello di organizzazione sono passati dal riquadro **impostazioni app a livello di organizzazione** a qui.

Per consentire o bloccare un'app, selezionala e quindi seleziona **Consenti** o **Blocca**. Quando si blocca un'app, tutte le interazioni con l'app vengono disabilitate e l'app non viene visualizzata in Teams per gli utenti dell'organizzazione.

Quando si blocca o si consente un'app nella pagina Gestisci app, l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione.  Quando si blocca o si consente un'app in un criterio di autorizzazione di un'app Teams, questa viene bloccata o consentita per gli utenti a cui sono assegnati criteri. Per consentire a un utente di installare e interagire con qualsiasi app, è necessario consentire l'app a livello di organizzazione nella pagina Gestisci app e nei criteri di autorizzazione dell'app assegnati all'utente.

 > [!NOTE]
 > Per disinstallare un'app, fare clic con il pulsante destro del mouse sull'app e quindi scegliere **Disinstalla** o usare il menu **Altre app** a sinistra.

## <a name="apps-blocked-by-publishers"></a>App bloccate dagli autori

Quando un ISV pubblica un'app nell'app store globale, potrebbe essere necessario che gli amministratori configurino o personalizzino l'esperienza dell'app. L'amministratore può renderla disponibile agli utenti finali quando l'app è completamente configurata.

Ad esempio, Contoso Electronics è un ISV che ha creato un'app help desk per Microsoft Teams. Contoso Electronics vuole che i clienti configurino alcune proprietà dell'app in modo che, quando gli utenti interagiscono con l'app, funzioni come previsto. Prima che un amministratore possa consentire o bloccare l'applicazione, verrà **visualizzata come Bloccata dall'autore** nell'interfaccia di amministrazione di Teams e verrà nascosta agli utenti finali per impostazione predefinita. Dopo aver seguito le indicazioni dell'autore per configurare l'app, è possibile renderla disponibile per gli utenti passando allo stato **Consentito** o impedire agli utenti di usare l'app impostando lo stato **su Bloccata**.

![Screenshot di bloccato dallo stato dell'autore nell'interfaccia di amministrazione di Teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Aggiungere un'app a un team

Si usa il pulsante **Aggiungi al team** per installare un'app in un team. Tenere presente che questo vale solo per le app che possono essere installate in un ambito del team. Il pulsante **Aggiungi al team** non è disponibile per le app che possono essere installate solo nell'ambito personale.

![Screenshot del pulsante Aggiungi al team.](media/manage-apps-add-app-team.png)

1. Cerca l'app desiderata e quindi seleziona l'app facendo clic a sinistra del nome dell'app.
2. Selezionare **Aggiungi al team**.
3. Nel riquadro **Aggiungi al team** cercare il team a cui si vuole aggiungere l'app, selezionare il team e quindi selezionare **Applica**.

## <a name="customize-an-app"></a>Personalizzare un'app

È ora possibile personalizzare un'app per includere un aspetto specifico in base alle esigenze dell'organizzazione. Vedere [Personalizzare le app in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Acquisto di servizi per app di terze parti

È possibile cercare e acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione direttamente dalla pagina Gestisci app. La colonna **Licenze** nella tabella indica se un'app offre un abbonamento SaaS a pagamento. Selezionare **Acquista ora** per visualizzare i piani e le informazioni sui prezzi e acquistare licenze per gli utenti. Per altre informazioni, vedere [Acquistare servizi per Teams app di terze parti nell'interfaccia di amministrazione di Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Concedere il consenso dell'amministratore alle app

È possibile esaminare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. In questo modo gli utenti non dovranno rivedere e accettare le autorizzazioni richieste dall'app all'avvio dell'app. La colonna **Autorizzazioni** indica se un'app ha autorizzazioni che richiedono il consenso. Vedrai un collegamento **Visualizza dettagli** per ogni app registrata in Azure AD con autorizzazioni che richiedono il consenso. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Visualizzare le autorizzazioni di consenso specifiche per le risorse

Le autorizzazioni per il consenso specifico delle risorse consentono ai proprietari del team di concedere a un'app il consenso per l'accesso e la modifica dei dati di un team. Le autorizzazioni RSC sono granulari, Teams autorizzazioni specifiche che definiscono cosa può fare un'app in un team specifico. È possibile visualizzare le autorizzazioni RSC nella scheda **Autorizzazioni** della pagina dei dettagli dell'app per un'app. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni delle app a livello di organizzazione

Usare le impostazioni delle app a livello di organizzazione per controllare se gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza personalizzata per le app in prima linea, se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con le app personalizzate nell'organizzazione. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. È possibile usarle per controllare eventuali app dannose o problematiche.

> [!NOTE]
> Per informazioni su come usare le impostazioni delle app a livello di organizzazione in Microsoft 365 Government - Government Community Cloud le distribuzioni High GCCH e Department of Defense (DoD) di Teams, vedere [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md).

1. Nella pagina Gestisci app seleziona **Impostazioni app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel riquadro.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot del riquadro Impostazioni app a livello di organizzazione nella pagina Gestisci app":::

1. In **App personalizzate** disattiva o attiva **Mostra app personalizzate**. Quando questa impostazione è attivata, gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza app frontline personalizzata. Questa esperienza aggiunge le app più rilevanti in Teams per gli operatori in prima linea. Per altre informazioni, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

    Questa funzionalità è disponibile per le licenze F. Altri tipi di licenza saranno supportati in futuro.
1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se disattivi questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app viene visualizzato come Bloccato a **livello di organizzazione** nella tabella.

        > [!NOTE]
        > Quando **l'opzione Consenti app di terze parti** è disattivata, [i webhook in uscita sono ancora abilitati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) per tutti gli utenti, ma è possibile controllarli a livello di utente consentendo o bloccando l'app Webhook in uscita tramite [criteri di autorizzazione dell'app](teams-app-permission-policies.md). Se sono presenti [criteri di autorizzazione](teams-app-permission-policies.md) per le **app Microsoft** che usano l'impostazione **Consenti app specifiche e bloccano tutte le altre** e si vogliono abilitare i webhook in uscita per gli utenti, aggiungere l'app Webhook in uscita all'elenco.

        > [!NOTE]
        > Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione.

    - **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa impostazione consente di controllare se eventuali nuove app di terze parti pubblicate nello Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App personalizzate** disattiva o attiva **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [Gestisci criteri e impostazioni app personalizzate in Teams](teams-custom-app-policies-and-settings.md).
1. Seleziona **Salva** per rendere effettive le impostazioni delle app a livello di organizzazione.

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>Visualizzare le informazioni sulla sicurezza e la conformità per le app certificate per Microsoft 365

Quando valutano un'app per la propria organizzazione, gli amministratori possono usare casB (Cloud Access Security Brokers) indipendente, ad esempio Microsoft Cloud App Security (MCAS), per trovare informazioni sulla sicurezza e sui comportamenti di un'app. L'interfaccia di amministrazione di Teams include le informazioni di sicurezza e conformità di MCAS per le app certificate Microsoft 365, in modo da avere maggiori informazioni sulla conformità o meno dell'app alle proprie esigenze.

> [!NOTE]
> Questa funzionalità è disponibile per tutti gli amministratori, indipendentemente dal fatto che l'organizzazione disponga o meno di una licenza che supporta MCAS.

Per accedere a MCAS informazioni, procedere come segue:

1. Nell'interfaccia di amministrazione di Teams seleziona **Gestisci app** in **app Teams**.
1. Seleziona **Certificazione** per ordinare le app ed eseguire il push di tutte le app certificate Microsoft 365 all'inizio della tabella.
1. Scegli un'app certificata per Microsoft 365.
1. Selezionare la scheda **Sicurezza e conformità** .

![Screenshot della scheda Sicurezza e conformità dell'interfaccia di amministrazione di Teams.](media/mcas.png)

In questa scheda sono disponibili informazioni su sicurezza, conformità e protezione dei dati. È anche possibile espandere ogni elenco a discesa per ottenere altri dettagli sulle funzionalità supportate per l'applicazione selezionata.

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
