---
title: Installare, gestire e assegnare autorizzazioni per Microsoft Viva Learning (anteprima privata)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Usare Microsoft Viva Learning (anteprima privata) per creare un hub centrale per l'apprendimento in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte contenuto in un'organizzazione.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880380"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a>Installare, gestire e assegnare autorizzazioni per Microsoft Viva Learning (anteprima privata)

*Questo articolo contiene contenuto preliminare per Microsoft Viva Learning, in anteprima privata.*

Microsoft Viva Learning (anteprima privata) consente ai team e agli utenti dell'organizzazione di rendere l'apprendimento una parte naturale della loro giornata. L'app crea un hub centrale in Teams in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte contenuto dell'organizzazione.

Gli amministratori impostano le autorizzazioni e consentono l'apprendimento delle origini contenuto per Viva Learning (anteprima privata). I contenuti didattici possono includere LinkedIn Learning, Microsoft Learn, formazione su Microsoft 365, contenuti dell'organizzazione archiviati in SharePoint online e provider di terze parti supportati da Viva Learning (anteprima privata).

## <a name="admin-roles"></a>Ruoli di amministratore

Per configurare Viva Learning (anteprima privata), sono necessarie le autorizzazioni seguenti:

- Amministratore di Microsoft Teams
- Amministratore globale di Microsoft 365 o amministratore di SharePoint
- Amministratore della conoscenza: si tratta di un nuovo ruolo nell'interfaccia di amministrazione di Microsoft 365 che può essere assegnato a chiunque nell'organizzazione. Questo ruolo gestisce le origini contenuto di apprendimento dell'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365. 

> [!TIP]
> L'amministratore della knowledge base deve essere moderatamente tecnico e avere le credenziali di amministratore di SharePoint esistenti, preferibilmente una persona esperta nell'ambito dell'istruzione, dell'apprendimento, della formazione o dell'esperienza dei dipendenti nell'organizzazione.
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a>Gestire Viva Learning (anteprima privata) nell'interfaccia di amministrazione di Teams

L'amministratore di Teams installa Viva Learning (anteprima privata) dall'App Store e quindi applica i criteri di configurazione, gestione e autorizzazione tramite l'interfaccia di amministrazione di Teams.

### <a name="manage-settings-for-viva-learning-private-preview"></a>Gestire le impostazioni per Viva Learning (anteprima privata)

Per eseguire queste attività, è necessario essere un amministratore nell'interfaccia di amministrazione di Teams.

Per gestire le impostazioni per Viva Learning, seguire questa procedura:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Gestisci app di Teams.**  >  

   ![Spostamento a sinistra nell'interfaccia di amministrazione di Teams con le app di Teams e la sezione Gestisci app](media/learning-app-teams-manage-apps-nav.png)

2. Nella casella di ricerca **della** pagina Gestisci app digitare *learning* per cercare l'app Teams Learning (anteprima privata).

   ![Pagina Gestisci app nell'interfaccia di amministrazione di Teams con la casella di ricerca](media/learning-app-teams-manage-apps-page.png)

3. Nella pagina **Apprendimento:**
   1. In **Stato** selezionare **Consentito per** attivare l'app.
   2. Nella sezione **Impostazioni** app  della scheda Impostazioni passare all'interfaccia di amministrazione di Microsoft 365 per configurare le origini contenuto di apprendimento.

   ![Pagina Di apprendimento nell'interfaccia di amministrazione di Teams con la sezione Impostazioni stato e app](media/learning-app-teams-learning-page.png)

4. Dopo gestire le impostazioni  **dell'app,** passare a Autorizzazioni e Criteri di configurazione per concedere l'autorizzazione ai dipendenti che devono avere accesso all'app come parte della partecipazione dell'organizzazione all'anteprima privata.

> [!NOTE]
>  Se l'organizzazione si trova nell'Anello 4.0 come parte del programma TAP100 di Teams, potrebbe essere necessario eseguire le operazioni seguenti per consentire agli utenti approvati in Ring 3.0 di accedere a Viva Learning (anteprima privata).

Nell'ambito dell'anteprima privata, Viva Learning (anteprima privata) viene rilasciato nell'Anello 3.0. Se l'organizzazione si trova nell'Anello 4.0, l'app non verrà visualizzata nell'app store. Per testare l'app, è necessario creare un criterio di autorizzazione app personalizzato, impostarlo su Consenti tutte le app e assegnarlo agli utenti approvati di Ring 3.0.

   ![Tap-AppsPermission-Plcy page showing Allow all apps selected](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurare le origini contenuto di apprendimento nell'interfaccia di amministrazione di Microsoft 365

Gli amministratori dell'interfaccia di amministrazione di Microsoft 365, da soli o assegnando il ruolo di amministratore della conoscenza a persone selezionate nell'organizzazione, possono gestire le impostazioni relative a Viva Learning (anteprima privata) e configurare le origini contenuto di apprendimento.

L'amministratore seleziona le origini di contenuto didattiche aggiuntive, ad esempio SharePoint o le origini provider di contenuto di terze parti supportate, che saranno disponibili per gli utenti di Viva Learning (anteprima privata). L'amministratore configura quindi queste origini per assicurarsi che il contenuto sia disponibile per la ricerca e l'individuazione e possa essere esplorato dai dipendenti che usano Viva Learning (anteprima privata).

> [!NOTE]
>  Gli utenti a cui si accede a apprendimenti non Microsoft e LinkedIn Learning Pro in un browser o in un visualizzatore incorporato. Questo apprendimento configurato è soggetto alle condizioni di licenza, privacy e servizio separate tra l'organizzazione e la terza parte e non le condizioni viva learning (anteprima privata). Prima di selezionare questo tipo di apprendimento, verificare di avere un accordo per l'organizzazione e gli utenti.

### <a name="assign-the-knowledge-admin-role-optional"></a>Assegnare il ruolo di amministratore della conoscenza [Facoltativo]

Per eseguire queste attività, è necessario essere un amministratore globale di Microsoft 365.

Per assegnare un amministratore della knowledge base per Viva Learning, seguire questa procedura:

1.  Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Ruoli.**

2.  Nella scheda **Azure** **AD** della pagina Ruoli selezionare **Amministratore conoscenza.**
 
3.  Nella sezione **Amministratori assegnati** della pagina Amministratore della knowledge **base** selezionare **Aggiungi** e quindi aggiungere la persona scelta per il ruolo.

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a>Configurare le impostazioni per le origini contenuto di apprendimento per Viva Learning (anteprima privata)

Per eseguire queste attività, è necessario essere un amministratore globale di Microsoft 365 o un amministratore della knowledge base.

Per configurare le impostazioni per le origini contenuto di apprendimento in Viva Learning, seguire questa procedura:

1.  Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni**  >  **organizzazione**.

2.  Nella scheda **Servizi della**  pagina Impostazioni organizzazione selezionare App di **apprendimento (anteprima).**

     ![Pagina Impostazioni nell'interfaccia di amministrazione di Microsoft 365 con l'app Apprendimento elencata](media/learning-sharepoint-configure1.png)

3.  Nel riquadro **App di apprendimento (anteprima)** selezionare le origini contenuto di apprendimento da configurare per l'organizzazione e quindi scegliere **Salva**.

     ![Riquadro di apprendimento nell'interfaccia di amministrazione di Microsoft 365 con le opzioni relative alle origini contenuto](media/learning-sharepoint-configure2.png)

Tra tutte le origini di apprendimento esistenti, alcune saranno abilitate per impostazione predefinita. Questi includono:

- LinkedIn Learning (contenuto gratuito)
- Microsoft Learn
- Formazione su Microsoft 365

> [!NOTE]
> Se l'organizzazione ha un abbonamento a LinkedIn Learning Standard o Pro, il repository dei contenuti verrà sbloccato per i dipendenti dell'organizzazione. Solo i dipendenti che hanno l'autorizzazione potranno usare l'intero archivio del contenuto. <br>Potrebbe essere necessario attivare o configurare manualmente altre origini. Le origini di apprendimento non provenienti da Microsoft sono concesse separatamente in licenza tra l'organizzazione e la terza parte. Dovrai verificare di aver effettuato l'accesso per il loro apprendimento per te e per i tuoi utenti.

Per abilitare o disabilitare un'origine contenuto di apprendimento, selezionare la casella di controllo accanto all'origine. Se un'origine è abilitata, sarà visibile un segno di spunta.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Configurare SharePoint come origine contenuto didattica

È possibile configurare SharePoint come origine contenuto didattica per rendere disponibile il contenuto dell'organizzazione in Viva Learning (anteprima privata).

### <a name="overview"></a>Panoramica

L'amministratore della knowledge base (o amministratore globale) fornisce un URL del sito in cui il servizio di apprendimento può creare una posizione centralizzata vuota, ovvero l'archivio di contenuto delle app di apprendimento, sotto forma di elenco di SharePoint strutturato. Questo elenco può essere usato dall'organizzazione per ospitare collegamenti a cartelle di SharePoint tra aziende che contengono contenuto didattico. Gli amministratori sono responsabili della raccolta e della gestione di un elenco di URL per le cartelle. Queste cartelle devono includere solo il contenuto che può essere reso disponibile in Viva Learning (anteprima privata).

Viva Learning (anteprima privata) supporta i tipi di documento seguenti:

- Word, PowerPoint, Excel, PDF
- Audio (.m4a)
- Video (mov, mp4, avi)

Per altre informazioni, vedere la documentazione [di SharePoint Online.](https://docs.microsoft.com/sharepoint/introductionlink) 

### <a name="permissions"></a>Autorizzazioni

Gli URL delle cartelle della raccolta documenti possono essere raccolti da qualsiasi sito di SharePoint nell'organizzazione. Viva Learning (anteprima privata) segue tutte le autorizzazioni di contenuto esistenti. Di conseguenza, solo il contenuto per cui un utente ha l'autorizzazione di accesso è disponibile per la ricerca e può essere utilizzato all'interno di Viva Learning (anteprima privata). Qualsiasi contenuto all'interno di queste cartelle sarà disponibile per la ricerca, ma è possibile usare solo il contenuto per cui il singolo dipendente ha le autorizzazioni.

L'eliminazione del contenuto dal repository dell'organizzazione non è attualmente supportata.

Per rimuovere il contenuto inavvicinatamente estraneo, seguire questa procedura:

1.  Per limitare l'accesso alla raccolta documenti, selezionare **l'opzione Mostra** azioni e quindi selezionare **Gestisci accesso.**
     
     ![Pagina della raccolta documenti in SharePoint con l'opzione Mostra azioni con l'opzione Gestisci accesso elevato.](media/learning-sharepoint-permissions2.png)

2.  Eliminare il documento originale all'interno della raccolta documenti.

Per altre informazioni, vedere [Condivisione e autorizzazioni nell'esperienza moderna di SharePoint.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) 

### <a name="learning-service"></a>Servizio di apprendimento

Il servizio di apprendimento usa gli URL delle cartelle forniti per ottenere i metadati da tutto il contenuto archiviato in tali cartelle. Entro 24 ore dalla fornitura dell'URL della cartella nel repository centralizzato, i dipendenti possono cercare e usare il contenuto dell'organizzazione all'interno di Viva Learning (anteprima privata). Tutte le modifiche al contenuto, inclusi i metadati e le autorizzazioni aggiornati, verranno applicate anche nel servizio di apprendimento entro 24 ore.

### <a name="configure-sharepoint-as-a-source"></a>Configurare SharePoint come origine

Per eseguire queste attività, è necessario essere un amministratore globale di Microsoft 365, un amministratore di SharePoint o un amministratore della knowledge base.

Per configurare SharePoint come origini contenuto didattiche in Viva Learning (anteprima privata), seguire questa procedura:

1.  Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni**  >  **organizzazione**.
 
2.  Nella scheda **Servizi della**  pagina Impostazioni organizzazione selezionare App di **apprendimento (anteprima).**

     ![Pagina Impostazioni nell'interfaccia di amministrazione di Microsoft 365 con Viva Learning elencato.](media/learning-sharepoint-configure1.png)

3.  Nel riquadro **App di apprendimento (anteprima),** in **SharePoint,** specificare l'URL del sito di SharePoint in cui si vuole che Viva Learning crei un archivio centralizzato.

     ![Riquadro di apprendimento nell'interfaccia di amministrazione di Microsoft 365 con SharePoint selezionato.](media/learning-sharepoint-configure2.png)

4.  Un elenco di SharePoint viene creato automaticamente all'interno del sito di SharePoint specificato.

     ![Elenco di SharePoint appena creato all'interno del sito di SharePoint.](media/learning-sharepoint-configure3.png)

     Nella barra di spostamento sinistra del sito di SharePoint selezionare **Contenuto** del sito  >  **Archivio contenuto app di apprendimento**. 

     ![Elenco di SharePoint che mostra la struttura di spostamento Contenuto del sito e la sezione Archivio contenuto app di apprendimento.](media/learning-sharepoint-configure4.png) 

5. Nella pagina **Archivio contenuto app di** apprendimento popolare l'elenco di SharePoint con URL nelle cartelle del contenuto di apprendimento.

   1. Selezionare **Nuovo** per visualizzare il **riquadro Nuovo** elemento. 

       ![Pagina Archivio contenuto didattico in SharePoint con l'opzione Nuovo.](media/learning-sharepoint-configure5.png)
 
   2. Nel campo **Titolo del**  riquadro Nuovo elemento aggiungere un nome di directory a scelta. Nel campo **URL cartella** aggiungere l'URL alla cartella del contenuto didattico. Selezionare **Salva**.

       ![Riquadro Nuovo elemento in SharePoint con i campi Titolo e URL cartella.](media/learning-sharepoint-configure6.png)

   3. La **pagina Archivio contenuto app di** apprendimento viene aggiornata con il nuovo contenuto di apprendimento.

       ![Pagina Archivio contenuto didattico in SharePoint che mostra le informazioni aggiornate.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> Per consentire un accesso più ampio al repository dei contenuti delle app di apprendimento, presto sarà disponibile un collegamento all'elenco nell'interfaccia Viva Learning (anteprima privata), in cui gli utenti possono richiedere l'accesso e, in ultima analisi, aiutare a popolare l'elenco. I proprietari dei siti e gli amministratori globali saranno tenuti a concedere l'accesso all'elenco. Access è specifico solo per l'elenco e non si applica al sito in cui è archiviato l'elenco.

### <a name="folder-url-document-library-curation"></a>Gestione della raccolta documenti URL cartella

I metadati predefiniti, ad esempio la data di modifica, creati da, il nome del documento, il tipo di contenuto e il nome dell'organizzazione, vengono automaticamente estratti in Viva Learning (anteprima privata) dall'API Microsoft Graph.
 
Per migliorare l'individuazione generale e la pertinenza della ricerca del contenuto, è consigliabile aggiungere una **colonna Descrizione.**

Per aggiungere una **colonna Descrizione** alla pagina della raccolta documenti, seguire questa procedura:

1.  Nella pagina **Documenti** selezionare **Aggiungi colonna.**

2. Selezionare **l'opzione Mostra** azioni e quindi selezionare **Riga di testo singola.**

     ![Pagina Documenti in SharePoint che mostra le opzioni Mostra azioni con l'opzione Singola riga di testo evidenziata.](media/learning-sharepoint-curation1.png)

3. Nel riquadro **Crea colonna** aggiungere  un nome descrittivo per la colonna nel campo Nome. Selezionare **Salva**.

     ![Creare un riquadro a colonne in SharePoint con il nome e altri campi.](media/learning-sharepoint-curation2.png)
 
4. Nella **colonna** Descrizione  della pagina Documenti aggiungere descrizioni personalizzate per ogni elemento. Se non viene fornita alcuna descrizione, Viva Learning (anteprima privata) fornirà un messaggio predefinito che evidenzia il contenuto come contenuto della propria raccolta di SharePoint. 

     ![Pagina Documenti in SharePoint che mostra le descrizioni nella colonna Descrizione.](media/learning-sharepoint-curation3.png)
 
