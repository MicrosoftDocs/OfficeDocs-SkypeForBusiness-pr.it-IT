---
title: Installare, gestire e assegnare autorizzazioni per l'app teams Learning (anteprima privata)
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
description: Usare l'app Microsoft teams learning per creare un hub centrale per l'apprendimento in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte di contenuti in un'organizzazione.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703457"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Installare, gestire e assegnare autorizzazioni per l'app teams Learning (anteprima privata)

*Questo articolo contiene contenuto preliminare per l'app teams Learning, che si trova in anteprima privata.*

L'app Microsoft teams Learning (private Preview) autorizza i team e gli utenti dell'organizzazione a rendere l'apprendimento una parte naturale della loro giornata. L'app crea un hub centrale in teams in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte di contenuti nell'organizzazione. Gli amministratori impostano le autorizzazioni e consentono l'apprendimento delle origini contenuto per l'app. Il contenuto di apprendimento può includere LinkedIn Learning, Microsoft Learn, Microsoft 365 training, il contenuto dell'organizzazione archiviato in SharePoint Online e i provider di terze parti supportati dall'app.

Per configurare l'app teams Learning (private Preview), è necessario coinvolgere:

-   Amministratore dell'interfaccia di amministrazione Teams
-   Amministratore dell'interfaccia di amministrazione di Microsoft 365, ovvero Amministratore globale
-   Knowledge admin (un nuovo ruolo nell'interfaccia di amministrazione di Microsoft 365 che un amministratore globale (noto anche come amministratore IT o amministratore di Microsoft 365) può assegnare a tutti gli utenti dell'organizzazione. Questo ruolo gestisce le origini dei contenuti di apprendimento dell'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365. 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Gestire l'app teams Learning (private Preview) nell'interfaccia di amministrazione di Teams

L'amministratore di teams installa l'app teams Learning (private Preview) dall'App Store e applica i criteri di configurazione, gestione e autorizzazioni dell'app tramite l'interfaccia di amministrazione di teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Gestire l'app teams Learning (anteprima privata)

Per gestire le impostazioni per l'app, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.

   ![Spostamento a sinistra nell'interfaccia di amministrazione di teams che mostra le app team e Gestisci la sezione app](media/learning-app-teams-manage-apps-nav.png)

2. Nella casella di ricerca della pagina **Manage Apps** Digitare *Learning* per cercare l'app teams Learning (private Preview).

   ![Pagina Gestisci app nell'interfaccia di amministrazione di teams che mostra la casella di ricerca](media/learning-app-teams-manage-apps-page.png)

3. Nella pagina **apprendimento** :
   1. In **stato** selezionare **consentito** per attivare l'app.
   2. Nella sezione **impostazioni app** della scheda **Impostazioni** accedere all'interfaccia di amministrazione di Microsoft 365 per configurare le origini del contenuto di apprendimento.

   ![Pagina di apprendimento nell'interfaccia di amministrazione di teams che mostra lo stato e la sezione Impostazioni app](media/learning-app-teams-learning-page.png)

4. Dopo aver gestito le impostazioni dell' **app** , passa a **autorizzazioni e criteri di configurazione** per concedere l'autorizzazione ai dipendenti che devono avere accesso all'app come parte della partecipazione dell'organizzazione all'anteprima privata.

> [!NOTE]
>  Se l'organizzazione è in Ring 4,0 come parte del programma teams TAP100, potrebbe essere necessario eseguire le operazioni seguenti per consentire agli utenti approvati in Ring 3,0 di accedere all'app per l'apprendimento dei team (anteprima privata).

Nell'ambito dell'anteprima privata, l'app teams Learning (private Preview) viene rilasciata in Ring 3,0. Se l'organizzazione è in Ring 4,0, l'app non viene visualizzata nell'App Store. Per testare l'app, devi creare un criterio di autorizzazione per le app personalizzate, impostarlo per **consentire tutte le app** e assegnarlo agli utenti approvati di Ring 3,0.

   ![TOCCARE-AppsPermission-plcy pagina che mostra Consenti tutte le app selezionate](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurare le origini di contenuto per l'apprendimento nell'interfaccia di amministrazione di Microsoft 365

Gli amministratori dell'interfaccia di amministrazione di Microsoft 365, da sole o assegnando il ruolo di amministratore della conoscenza agli utenti selezionati nell'organizzazione, possono gestire le impostazioni relative all'app per l'apprendimento dei team (anteprima privata) e possono configurare le origini del contenuto di apprendimento.

> [!TIP]
> L'amministratore della Knowledge deve essere moderatamente tecnico e avere le credenziali di amministratore di SharePoint esistenti, preferibilmente una persona esperta nella parte dell'organizzazione per l'istruzione, l'apprendimento, la formazione o i dipendenti.
 
L'amministratore seleziona le origini di contenuto per l'apprendimento (come LinkedIn Learning o SharePoint) sarà disponibile nell'app. L'amministratore configura quindi tali origini per verificare che il contenuto sia disponibile per la ricerca e l'individuazione e possa essere esplorato dai dipendenti che usano l'app.

### <a name="assign-the-knowledge-admin-role-optional"></a>Assegnare il ruolo di amministratore della conoscenza [facoltativo]

Questi passaggi devono essere eseguiti dall'amministratore per l'interfaccia di amministrazione di Microsoft 365.

1.  Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365 passa a **ruoli**.

2.  Nella scheda **Azure ad** della pagina **roles** selezionare **Knowledge admin**.
 
3.  Nella sezione **amministratori assegnati** della pagina **Knowledge admin** selezionare **Aggiungi** e quindi aggiungere la persona scelta per il ruolo.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Configurare le impostazioni per le origini del contenuto di apprendimento per l'app

Questa procedura deve essere eseguita dall'amministratore di Microsoft 365 o dall'amministratore della Knowledge base.

1.  Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere alle impostazioni dell'organizzazione delle **Impostazioni**  >  .

2.  Nella scheda **servizi & componenti** aggiuntivi della pagina **Impostazioni** selezionare **apprendimento app**.

   ![Pagina impostazioni nell'interfaccia di amministrazione di Microsoft 365 che mostra l'app di apprendimento elencata](media/learning-app-365-settings-page.png)

3.  Nel pannello **app Learning** selezionare le origini di contenuto di apprendimento che si desidera configurare per l'organizzazione e quindi selezionare **Salva**.

   ![Pannello delle app di apprendimento nell'interfaccia di amministrazione di Microsoft 365 che mostra le opzioni di origini contenuto](media/learning-app-365-settings-learning-app-panel.png)

Tra tutte le fonti di apprendimento esistenti, alcune verranno abilitate per impostazione predefinita. Questi includono:

- LinkedIn Learning (contenuto gratuito)
- Microsoft Learn
- Formazione su Microsoft 365

> [!NOTE]
> Se l'organizzazione ha un abbonamento a LinkedIn Learning standard o Pro, il repository di contenuti verrà sbloccato per i dipendenti dell'organizzazione. Solo i dipendenti che hanno l'autorizzazione saranno in grado di usare l'intero repository di contenuto.

Potrebbe essere necessario abilitare o configurare altre origini manualmente. Le fonti di apprendimento non provenienti da Microsoft sono concesse in licenza separatamente tra l'organizzazione e la terza parte. È necessario verificare di aver effettuato l'iscrizione per l'apprendimento per l'utente e gli utenti.

Per abilitare o disabilitare un'origine di contenuto di apprendimento, selezionare la casella di controllo accanto all'origine. Se è abilitata un'origine, un segno di spunta sarà visibile.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Configurare SharePoint come origine del contenuto di apprendimento

È possibile configurare SharePoint come origine del contenuto di apprendimento per l'app teams Learning (private Preview) nell'interfaccia di amministrazione di Microsoft 365.

### <a name="overview"></a>Panoramica

L'amministratore della Knowledge fornisce un URL del sito in cui il servizio di apprendimento può creare un repository di contenuti di apprendimento centralizzato vuoto sotto forma di un elenco di SharePoint strutturato. Questo elenco può essere usato dall'organizzazione per ospitare i collegamenti a cartelle di SharePoint tra società che contengono contenuto di apprendimento. Gli amministratori sono responsabili della raccolta e della cura di un elenco di URL per le cartelle. Queste cartelle devono includere solo il contenuto che può essere reso disponibile nell'app per l'apprendimento di Teams (private Preview).

### <a name="permissions"></a>Autorizzazioni

Gli URL delle cartelle possono essere raccolti da qualsiasi sito di SharePoint nell'organizzazione. Qualsiasi contenuto all'interno di queste cartelle sarà ricercabile, ma solo il contenuto a cui può essere usato il singolo dipendente ha le autorizzazioni.
 
### <a name="learning-service"></a>Servizio di apprendimento

Il servizio di apprendimento usa gli URL della cartella forniti per ottenere metadati da tutto il contenuto archiviato in tali cartelle. Entro 24 ore dall'approvvigionamento dell'URL della cartella nel repository centralizzato, i dipendenti possono cercare e usare il contenuto della società nell'app. L'eliminazione del contenuto dal repository non è supportata a questo punto. Il contenuto con superficie involontaria può essere rimosso solo fornendo un nuovo URL del sito di SharePoint nell'interfaccia di amministrazione di Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurare SharePoint come origine

Questi passaggi devono essere eseguiti dall'amministratore di Microsoft 365 o dall'amministratore della Knowledge base.

1.  Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere a **Impostazioni**.
 
2.  Nella scheda **servizi & componenti** aggiuntivi della pagina **Impostazioni** selezionare **apprendimento app**.

   ![Pagina impostazioni nell'interfaccia di amministrazione di Microsoft 365 che mostra l'app di apprendimento elencata](media/learning-app-365-settings-page.png)

3.  Nel pannello **app Learning** fornisci l'URL del sito al sito di SharePoint in cui vuoi che l'app crei un repository centralizzato.

   ![Pannello delle app di apprendimento nell'interfaccia di amministrazione di Microsoft 365 che mostra SharePoint selezionato](media/learning-app-365-panel-sharepoint-selected.png)

4.  Un elenco di SharePoint viene creato automaticamente nel sito di SharePoint dell'organizzazione specificata. Nella barra di spostamento sinistra del sito di SharePoint selezionare **learning content app repository**. 

   ![Spostamento a sinistra in SharePoint che mostra la sezione del repository del contenuto dell'app Learning](media/learning-app-content-repository-nav.png)

 
5. Nella pagina **Learning app content repository** compilare l'elenco di SharePoint con gli URL per le cartelle del contenuto di apprendimento.

   1.   Selezionare **nuovo** per visualizzare il pannello **nuovo elemento** . 

   ![Pagina del repository del contenuto dell'app di apprendimento in SharePoint che mostra la nuova opzione](media/learning-app-content-repository-new.png)
 
   2.   Nel riquadro **nuovo elemento** , nel campo **titolo** , aggiungere il nome della directory desiderata. Nel campo **URL cartella** aggiungere l'URL alla cartella contenuto di apprendimento. Selezionare **Salva**.

   ![Pannello nuovo elemento in SharePoint che mostra i campi titolo e URL cartella](media/learning-app-new-item-panel.png)

   3. La pagina del repository del contenuto dell'app Learning viene aggiornata con il nuovo contenuto di apprendimento.

   ![Pagina del repository del contenuto dell'app di apprendimento in SharePoint che mostra le informazioni aggiornate](media/learning-app-content-repository-populated.png)


 


