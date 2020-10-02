---
title: Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
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
description: Informazioni su come gestire le app teams nella pagina Manage Apps dell'interfaccia di amministrazione di Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: d75664a6d3884529936f8adcb69a928bdd238b3d
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336956"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
======================================================

Come amministratore, la pagina Gestisci app nell'interfaccia di amministrazione di Microsoft teams consente di visualizzare e gestire tutte le app teams per l'organizzazione. In questo caso, puoi vedere lo stato e le proprietà a livello di organizzazione delle app, approvare o caricare nuove app personalizzate nell'App Store, bloccare o consentire le app a livello aziendale, aggiungere app ai team (in anteprima), acquistare servizi per app di terze parti, visualizzare le autorizzazioni richieste dalle app, concedere il consenso dell'amministratore alle app e gestire le impostazioni dell'app.

La pagina Gestisci app consente di visualizzare tutte le app disponibili, fornendo le informazioni necessarie per decidere quali app consentire o bloccare nell'organizzazione. Puoi quindi usare i [criteri di autorizzazione](teams-app-permission-policies.md)per le app, i [criteri di configurazione delle app](teams-app-setup-policies.md)e i [criteri e le impostazioni delle app personalizzate](teams-custom-app-policies-and-settings.md) per configurare l'esperienza dell'app per utenti specifici dell'organizzazione.

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**. Per accedere alla pagina è necessario essere un amministratore globale o un servizio di teams.

> [!NOTE]
> La pagina Gestisci app non è ancora disponibile nelle distribuzioni di team di Microsoft 365 Government community Cloud (GCC).

## <a name="view-apps"></a>Visualizzare le app

Puoi visualizzare tutte le app, incluse le informazioni seguenti su ogni app.

![Screenshot della pagina delle app gestite](media/manage-apps.png)

- **Nome**: nome dell'app. Fai clic sul nome dell'app per accedere alla pagina dei dettagli dell'app per visualizzare altre informazioni sull'app. Ciò include una descrizione dell'app, che sia consentita o bloccata, versione, politica sulla privacy, condizioni per l'uso, categorie che si applicano all'app, stato di certificazione, funzionalità supportate e ID app. Ecco un esempio:

  ![Screenshot della pagina Dettagli app per un'app](media/manage-apps-app-details.png)
  
- **Certificazione**: se l'app ha superato la certificazione, verrà visualizzata l' **attestazione** **certificata o Publisher Microsoft 365** . Fare clic sul collegamento per visualizzare i dettagli di certificazione per l'app. Se viene visualizzato " **--** ", non sono disponibili informazioni sulla certificazione per l'app. Per altre informazioni sulle app certificate in teams, leggere il [programma di certificazione delle app Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Publisher**: nome del server di pubblicazione.
- **Stato della pubblicazione**: stato di pubblicazione delle app personalizzate.
- **Stato**: stato dell'app a livello di organizzazione, che può essere uno dei seguenti:

    - **Consentito**: l'app è disponibile per tutti gli utenti dell'organizzazione.
    
    - **Bloccata**: l'app è bloccata e non è disponibile per tutti gli utenti dell'organizzazione.
    
    - **Bloccata a livello di organizzazione**: l'app è bloccata nelle impostazioni dell'app a livello di organizzazione.
    
      È importante sapere che questa colonna rappresenta lo stato consentito e bloccato delle app che in precedenza erano nel riquadro **impostazioni a livello di organizzazione** . Ora puoi visualizzare, bloccare e consentire le app a livello di organizzazione nella pagina **Gestisci app** . 
- **Licenze**: indica se un'app offre un abbonamento a un software come servizio (SaaS) per l'acquisto. Questa colonna si applica solo alle app di terze parti. Ogni app di terze parti avrà uno dei valori seguenti:
    - **Acquista ora**: l'app offre un abbonamento a Saas ed è disponibile per l'acquisto.  
    - **Acquistato**: l'app offre un abbonamento a Saas e ne hai acquistato le licenze.
    - **--**: L'app non offre un abbonamento a Saas.
- **App personalizzata**: se l'app è un'app personalizzata.
- **Autorizzazioni**: indica se un'app di terze parti o personalizzata registrata in Azure Active Directory (Azure ad) dispone delle autorizzazioni necessarie per il consenso. Verrà visualizzato uno dei valori seguenti:
    - **Visualizza dettagli**: l'app ha le autorizzazioni che richiedono il consenso prima che l'app possa accedere ai dati. 
    - **--**: L'app non dispone delle autorizzazioni necessarie per il consenso.
- **Categorie**: categorie che si applicano all'app.
- **Versione**: versione dell'app.

Per visualizzare le informazioni desiderate nella tabella, fare clic su **modifica colonna** nell'angolo in alto a destra per aggiungere o rimuovere colonne alla tabella.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Pubblicare un'app personalizzata nell'App Store dell'organizzazione

Usare la pagina Gestisci app per pubblicare le app create appositamente per l'organizzazione. Dopo aver pubblicato un'app personalizzata, è disponibile per gli utenti nell'App Store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata nell'App Store dell'organizzazione. Il modo in cui si usa dipende da come si ottiene l'app.

- [Approvare un'app personalizzata](#approve-a-custom-app): usa questo metodo se lo sviluppatore invia l'app direttamente alla pagina Gestisci app usando l'API di invio dell'app teams. Puoi quindi rivedere e pubblicare (o rifiutare) l'app direttamente dalla pagina dei dettagli dell'app.
- [Carica un pacchetto dell'app](#upload-an-app-package): usa questo metodo se lo sviluppatore ti invia il pacchetto dell'app in formato zip. Puoi pubblicare l'app caricando il pacchetto dell'app.

###  <a name="approve-a-custom-app"></a>Approvare un'app personalizzata

Il widget **approvazioni in sospeso** nella pagina Gestisci app informa quando uno sviluppatore Invia un'app usando l'API di invio dell'app teams. Un'app appena presentata è elencata con uno **stato di pubblicazione** **inviato** e uno **stato** **bloccato**. Accedere alla pagina dettagli dell'app per visualizzare altre informazioni sull'app, quindi per pubblicarla, impostare **lo stato di pubblicazione** su **pubblica**.

Sei anche avvisato quando uno sviluppatore Invia un aggiornamento a un'app personalizzata. Puoi quindi rivedere e pubblicare (o rifiutare) l'aggiornamento nella pagina dettagli dell'app. Tutti i criteri di autorizzazione per le app e i criteri di configurazione delle app restano applicati per l'app aggiornata.

Per altre informazioni, Vedi [pubblicare un'app personalizzata inviata tramite l'API di invio di app teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Caricare un pacchetto dell'app

Lo sviluppatore crea un pacchetto dell'app teams usando [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)e lo invia in formato zip. Quando hai il pacchetto dell'app, puoi caricarlo nell'App Store dell'organizzazione.

Per caricare una nuova app personalizzata, seleziona **carica** per caricare il pacchetto dell'app. L'app non viene evidenziata dopo il caricamento, quindi dovrai cercare l'elenco delle app nella pagina Gestisci app per trovarlo.

Per aggiornare un'app dopo il caricamento, nell'elenco delle app nella pagina Gestisci app fare clic sul nome dell'app e quindi su **Aggiorna**. Questa operazione sostituisce l'app esistente e tutti i criteri di autorizzazione delle app e i criteri di configurazione delle app restano applicati per l'app aggiornata.

Per altre informazioni, Vedi [pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Consentire e bloccare le app

La pagina Gestisci app è la posizione in cui puoi consentire o bloccare singole app a livello di organizzazione. Mostra tutte le app disponibili e lo stato corrente dell'app a livello di organizzazione. (Bloccando e consentendo alle app a livello di organizzazione di spostarsi dal riquadro **delle impostazioni dell'app per l'intera organizzazione** a questo punto).

Per consentire o bloccare un'app, selezionarla e quindi fare clic su **Consenti** o **blocca**. Quando blocchi un'app, tutte le interazioni con l'app sono disabilitate e l'app non viene visualizzata in teams per tutti gli utenti dell'organizzazione.

Quando blocchi o Consenti un'app nella pagina Gestisci app, questa app è bloccata o consentita per tutti gli utenti dell'organizzazione.  Quando blocchi o Consenti un'app in un criterio di autorizzazione dell'app teams, è bloccata o consentita per gli utenti a cui è stato assegnato il criterio. Affinché un utente sia in grado di installare e interagire con qualsiasi app, devi consentire l'app a livello di organizzazione nella pagina Gestisci app e nei criteri di autorizzazione dell'app assegnati all'utente.

 > [!NOTE]
 > Per disinstallare un'app, fai clic con il pulsante destro del mouse sull'app e quindi fai clic su **Disinstalla** o usa il menu **Altre app** sul lato sinistro.

## <a name="add-an-app-to-a-team"></a>Aggiungere un'app a un team

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Puoi usare il pulsante **Aggiungi al team** per installare un'app in un team. Tieni presente che questo è solo per le app che possono essere installate in un ambito del team. Il pulsante **Aggiungi al team** non è disponibile per le app che possono essere installate solo nell'ambito personale.

![Screenshot del pulsante Aggiungi al team](media/manage-apps-add-app-team.png)

1. Cerca l'app desiderata e quindi seleziona l'app facendo clic a sinistra del nome dell'app.
2. Selezionare **Aggiungi al team**.
3. Nel riquadro **Aggiungi al team** cercare il team a cui si vuole aggiungere l'app, selezionare il team e quindi fare clic su **applica**.

## <a name="purchase-services-for-third-party-apps"></a>Acquisto di servizi per app di terze parti

È possibile cercare e acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione direttamente dalla pagina Manage Apps. La colonna **licenze** nella tabella indica se un'app offre un abbonamento a Saas pagato. Fare clic su **Acquista ora** per visualizzare i piani e le informazioni sui prezzi e acquistare licenze per gli utenti. Per altre informazioni, vedere [servizi di acquisto per le app di terze parti nell'interfaccia di amministrazione di Microsoft teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Concedere l'autorizzazione di amministratore alle app

Puoi rivedere e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. Puoi eseguire questa operazione in modo che gli utenti non debbano rivedere e accettare le autorizzazioni richieste dall'app quando avviano l'app. La colonna **autorizzazioni** indica se un'app dispone delle autorizzazioni necessarie per il consenso. Verrà visualizzato un collegamento **Visualizza dettagli** per ogni app registrata in Azure ad con autorizzazioni che richiedono il consenso. Per altre informazioni, Vedi [visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Visualizzare le autorizzazioni di consenso specifiche delle risorse

Le autorizzazioni di consenso specifiche delle risorse consentono ai proprietari del team di concedere il consenso per un'app per accedere e modificare i dati di un team. Le autorizzazioni RSC sono granulari, autorizzazioni specifiche per i team che definiscono le operazioni che un'app può eseguire in un team specifico. È possibile visualizzare le autorizzazioni RSC nella scheda **autorizzazioni** della pagina Dettagli app per un'app. Per altre informazioni, Vedi [visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni dell'app a livello di organizzazione

Usa le impostazioni dell'app a livello di organizzazione per controllare se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con app personalizzate nella tua azienda. Le impostazioni dell'app a livello di organizzazione regolano il comportamento per tutti gli utenti ed eseguono l'override di qualsiasi altro criterio di autorizzazione dell'app assegnato agli utenti. Puoi usarle per controllare le app malevole o problematiche.

> [!NOTE]
> Per informazioni su come usare le impostazioni dell'app a livello di organizzazione in Microsoft 365 Government-distribuzioni di GCC per i team, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

1. Nella pagina Manage Apps selezionare **impostazioni dell'app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel pannello.

    ![Screenshot delle impostazioni dell'app a livello di organizzazione](media/manage-apps-org-wide-app-settings.png)
    
2. In **app di terze parti**disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consenti app di terze parti**: controlla se gli utenti possono usare app di terze parti. Se disattivi questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app viene visualizzato come bloccato a **livello di organizzazione** nella tabella.

        > [!NOTE]
        > Quando le **app di terze parti** sono disattivate, i [webhook in uscita](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sono disabilitati, il che significa che gli utenti non possono crearli. Quando questa impostazione è attivata, i webhook in uscita sono abilitati per tutti gli utenti e puoi controllarli a livello di utente consentendo o bloccando l'app webhook in uscita tramite i [criteri di autorizzazione dell'app](teams-app-permission-policies.md). <br><br>Tieni presente che se hai i [criteri di autorizzazione delle app](teams-app-permission-policies.md) esistenti per le app **Microsoft** che usano l'opzione **Consenti app specifiche e blocca tutte le altre** impostazioni e vuoi abilitare i webhook in uscita per gli utenti, Aggiungi l'app webhook in uscita all'elenco.
    - **Consenti a tutte le nuove app di terze parti pubblicate nello Store per impostazione predefinita**: questo controlla se le nuove app di terze parti pubblicate nell'app store teams diventano automaticamente disponibili in teams. Puoi impostare questa opzione solo se Consenti app di terze parti.

3. In **app personalizzate**disattivare o attivare **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [gestire i criteri e le impostazioni dell'app personalizzata in teams](teams-custom-app-policies-and-settings.md).
4. Fare clic su **Salva** per applicare le impostazioni dell'app a livello di organizzazione.

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)