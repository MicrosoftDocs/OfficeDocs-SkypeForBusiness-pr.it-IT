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
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire le app teams nella pagina Manage Apps dell'interfaccia di amministrazione di Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: d4abedbd24f9f0211a66b0890fe9d3db2fc977cd
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868483"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
======================================================

Come amministratore, la pagina **Gestisci app** nell'interfaccia di amministrazione di Microsoft teams è la posizione in cui puoi visualizzare e gestire tutte le app Teams nel catalogo app dell'organizzazione. In questa sezione puoi vedere lo stato e le proprietà a livello di organizzazione delle app, caricare nuove app personalizzate nel catalogo dell'app tenant, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni dell'app in tutta l'organizzazione.

La pagina **Gestisci app** consente di visualizzare tutte le app disponibili nel catalogo del tenant, fornendo le informazioni necessarie per decidere quali app consentire o bloccare in tutta l'organizzazione. Puoi quindi usare i [criteri di autorizzazione](teams-app-permission-policies.md)per le app, i [criteri di configurazione delle app](teams-app-setup-policies.md)e i [criteri e le impostazioni delle app personalizzate](teams-custom-app-policies-and-settings.md) per configurare l'esperienza dell'app per utenti specifici dell'organizzazione.

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**. Per accedere alla pagina è necessario essere un amministratore globale o un servizio di teams.

## <a name="view-apps-in-your-tenant-app-catalog"></a>Visualizzare le app nel catalogo dell'app tenant

Puoi visualizzare tutte le app nel catalogo delle app del tenant, incluse le informazioni seguenti su ogni app.

![Screenshot della pagina delle app gestite](media/manage-apps.png)

- **Nome**: nome dell'app. Fai clic sul nome dell'app per visualizzare altre informazioni sull'app. Questo include una descrizione dell'app, che sia consentita o bloccata, versione, categorie che si applicano all'app, stato di certificazione, funzionalità supportate e ID app. Ecco un esempio:<br> 
![Screenshot della pagina Dettagli app per un'app](media/manage-apps-app-details.png)
- **Certificazione**: se l'app ha superato la certificazione, verrà visualizzata l' **attestazione** **certificata o Publisher Microsoft 365** . Fare clic sul collegamento per visualizzare i dettagli di certificazione per l'app. Se viene visualizzato " **--** ", non sono disponibili informazioni sulla certificazione per l'app. Per altre informazioni sulle app certificate in teams, leggere il [programma di certificazione delle app Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Categorie**: categorie che si applicano all'app.
- **Stato dell'app**: stato dell'app a livello di organizzazione, che può essere uno dei seguenti:
    - **Consentito**: l'app è disponibile per tutti gli utenti dell'organizzazione.
    - **Bloccata**: l'app è bloccata e non è disponibile per tutti gli utenti dell'organizzazione.
    - **Bloccata a livello di organizzazione**: l'app è bloccata nelle impostazioni dell'app a livello di organizzazione. <br>
È importante sapere che questa colonna rappresenta lo stato consentito e bloccato delle app che in precedenza erano nel riquadro **impostazioni a livello di organizzazione** . Ora puoi visualizzare, bloccare e consentire le app a livello di organizzazione nella pagina **Gestisci app** . 
- **Versione**: versione dell'app.

Per visualizzare le informazioni desiderate nella tabella, fare clic su **modifica colonna** nell'angolo in alto a destra per aggiungere o rimuovere colonne alla tabella.

## <a name="upload-a-new-app"></a>Caricare una nuova app

Puoi usare il catalogo app per testare e distribuire applicazioni personalizzate create appositamente per l'organizzazione. Viene creato un pacchetto dell'app teams con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Quando si ha il pacchetto dell'app, è possibile aggiungerlo al catalogo dell'app. Mentre tutti gli utenti dell'organizzazione possono visualizzare il catalogo delle app, solo gli amministratori globali e i servizi di teams possono pubblicarli e gestirli.

Per caricare una nuova app personalizzata nel catalogo dell'app tenant, fai clic su **carica nuova app** per caricare il pacchetto dell'app in formato zip. L'app non viene evidenziata dopo il caricamento, quindi dovrai cercare il catalogo dell'app per trovarlo.

Per aggiornare un'app dopo il caricamento, nell'elenco delle app nella pagina **Gestisci** app fare clic sul nome dell'app e quindi su **Aggiorna**. Questa operazione sostituisce l'app esistente nel catalogo delle app e tutti i criteri di autorizzazione delle app e i criteri di configurazione delle app restano applicati per l'app aggiornata.

Per altre informazioni, vedere [gestire le app personalizzate in teams](manage-your-custom-apps.md).

## <a name="allow-and-block-apps"></a>Consentire e bloccare le app

La pagina **Gestisci app** è la posizione in cui puoi consentire o bloccare singole app a livello di organizzazione. Mostra tutte le app disponibili e lo stato corrente dell'app a livello di organizzazione. (Bloccando e consentendo alle app a livello di organizzazione di spostarsi dal riquadro **delle impostazioni dell'app per l'intera organizzazione** a questo punto).

Per consentire o bloccare un'app, selezionarla e quindi fare clic su **Consenti** o **blocca**. Quando blocchi un'app, tutte le interazioni con l'app sono disabilitate e l'app non viene visualizzata in teams per tutti gli utenti dell'organizzazione.

Quando blocchi o Consenti un'app nella pagina **Gestisci** app, questa app è bloccata o consentita per tutti gli utenti dell'organizzazione.  Quando blocchi o Consenti un'app in un criterio di autorizzazione dell'app teams, è bloccata o consentita per gli utenti a cui è stato assegnato il criterio. Affinché un utente sia in grado di installare e interagire con qualsiasi app, devi consentire l'app a livello di organizzazione nella pagina **Gestisci** app e nei criteri di autorizzazione dell'app assegnati all'utente.

 > [!NOTE]
 > Per disinstallare un'app, fai clic con il pulsante destro del mouse sull'app e quindi fai clic su **Disinstalla** o usa il menu **Altre app** sul lato sinistro. 

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni dell'app a livello di organizzazione

Usa le impostazioni dell'app a livello di organizzazione per controllare se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con app personalizzate nella tua azienda. Le impostazioni dell'app a livello di organizzazione regolano il comportamento per tutti gli utenti ed eseguono l'override di qualsiasi altro criterio di autorizzazione dell'app assegnato agli utenti. Puoi usarle per controllare le app malevole o problematiche.

1. Nella pagina **Manage Apps** selezionare **impostazioni dell'app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel pannello.

    ![Screenshot delle impostazioni dell'app a livello di organizzazione](media/manage-apps-org-wide-app-settings.png)
    
2. In **app di terze parti**disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consenti app di terze parti**: controlla se gli utenti possono usare app di terze parti. Se disattivi questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app viene visualizzato come bloccato a **livello di organizzazione** nella tabella.

        > [!NOTE]
        > In una distribuzione di team di Microsoft 365 Government-GCC, l'impostazione **Consenti app di terze parti in teams** è disimpostata per impostazione predefinita.

        Quando le **app di terze parti** sono disattivate, i [webhook in uscita](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sono disabilitati, il che significa che gli utenti non possono crearli. Quando questa impostazione è attivata, i webhook in uscita sono abilitati per tutti gli utenti, indipendentemente dal fatto che l'impostazione sia inserita o disattivata nei criteri di autorizzazione delle app degli utenti.
    - **Consenti a tutte le nuove app di terze parti pubblicate nello Store per impostazione predefinita**: questo controlla se le nuove app di terze parti pubblicate nell'app store teams diventano automaticamente disponibili in teams. Puoi impostare questa opzione solo se Consenti app di terze parti.

3. In **app personalizzate**disattivare o attivare **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [gestire i criteri e le impostazioni dell'app personalizzata in teams](teams-custom-app-policies-and-settings.md).
4. Fare clic su **Salva** per applicare le impostazioni dell'app a livello di organizzazione.

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
