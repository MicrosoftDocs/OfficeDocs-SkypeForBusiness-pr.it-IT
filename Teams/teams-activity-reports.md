---
title: Usare i report attività per Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informazioni su come usare i report attività per vedere in che modo gli utenti dell'organizzazione usano Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7346ef19f70366ec32ad6d7a6bcf24fc98e6e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242993"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usare i report attività per Microsoft Teams 
========================================

È possibile usare i report attività nell'interfaccia di amministrazione di Microsoft 365 per vedere in che modo gli utenti dell'organizzazione usano Microsoft teams. Ad esempio, se alcuni utenti non usano ancora Microsoft teams, potrebbero non sapere come iniziare o capire come usare i team per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per decidere dove assegnare la priorità agli sforzi di formazione e comunicazione.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Come visualizzare i report Teams nel dashboard report

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/adminportal/home)selezionare **** > **utilizzo**report.
 
2. Nella pagina **utilizzo** scegliere **Seleziona un report**e quindi in **Microsoft teams** nell'elenco dei report scegliere il report che si vuole visualizzare.

## <a name="teams-activity-reports-that-are-available"></a>Report attività di teams disponibili

Sono attualmente disponibili due report attività che è possibile visualizzare:

- [Report attività utente di Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Report sull'utilizzo di dispositivi Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Report attività utente di Microsoft Teams

Il report attività utente teams offre una panoramica delle attività più comuni eseguite dagli utenti in teams. Questo include il numero di persone che partecipano a una chat in un canale, il numero di comunicazioni tramite il messaggio di chat privata e il numero di partecipanti a chiamate o riunioni. Queste informazioni possono essere visualizzate per l'intera organizzazione e per ogni singolo utente.

![Screenshot del report attività utente nell'interfaccia di amministrazione.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report attività utente di Microsoft Teams

Per visualizzare le attività degli utenti in team, è possibile osservare i grafici **attività** e utente. ****

![Screenshot del report attività utente con callout numerati.](media/teams-user-activity-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report attività utente teams può essere visualizzato per le tendenze degli ultimi 7 giorni, 30 giorni, 90 o 180 giorni. Tuttavia, se si fa clic in un determinato intervallo di tempo nel report, la tabella (7) visualizzerà i dati per 30 giorni fino alla data (2) per la generazione del report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La visualizzazione **attività** Mostra il numero di attività di Microsoft teams per tipo di attività. I tipi di attività sono il numero di messaggi di chat del team, messaggi di chat privati, chiamate e riunioni. |
|**4**   |La visualizzazione **utenti** Mostra il numero di utenti per tipo di attività. I tipi di attività sono il numero di messaggi di chat del team, messaggi di chat privati, chiamate e riunioni. |
|**5**   |L'asse X nei grafici è l'intervallo di date selezionato per il report specifico. <ul><li>Nel grafico **attività** l'asse Y è il numero dell'attività specificata.</ul></li> <ul><li>Nel grafico **utenti** l'asse Y è il numero di utenti che partecipano a chat team, chat private, chiamate o riunioni.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Nel grafico **attività** , ad esempio, fare clic o toccare **canali**, **messaggi di chat**, **chiamate**o **riunioni** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella Grid. |
|**7**   |Elenco di team attivi in un intervallo di tempo di Reporting più ampio (180 giorni).  Il numero di attività varia in base alla selezione della data. <br><br> Per visualizzare le informazioni seguenti nella tabella, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Username** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere anonimo questo campo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'attività di Microsoft teams.</ul></li> <ul><li>**Messaggi di canale** è il numero di messaggi univoci che l'utente ha postato in una chat del team durante il periodo di tempo specificato.</ul></li> <ul><li>**Messaggi di chat** è il numero di messaggi univoci che l'utente ha postato in una chat privata durante il periodo di tempo specificato.</ul></li> <ul><li>**Chiamate** indica il numero di chiamate a cui l'utente ha partecipato durante il periodo di tempo specificato.</ul></li> <ul><li>**Riunioni** è il numero di riunioni online a cui l'utente ha partecipato durante il periodo di tempo specificato.</ul></li> <ul><li>**Altre attività** è il numero di altre attività del team da parte dell'utente, alcune delle quali includono e non limitate a: piacimento i messaggi, le app, l'uso di file, la ricerca, il seguito di team e canali e il loro favorito.</ul></li> <ul><li>**Eliminato** indica se il team viene eliminato. Se il team viene eliminato, ma con attività nel periodo di riferimento, verrà visualizzato nella griglia con l'impostazione eliminata impostata su true.</ul></li> <ul><li>**Data eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Prodotto assegnato** è l'elenco dei prodotti assegnati all'utente.</ul></li>Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come si nascondono i dettagli del livello utente** nell'anteprima dell'interfaccia di [amministrazione di Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Toccare o fare clic su **colonne** per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Fare clic o toccare **Esporta** per esportare i dati del report in un file CSV di Excel. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2.000 utenti, è possibile ordinare e filtrare all'interno della tabella nel report stesso. Se sono presenti più di 2.000 utenti, sarà necessario esportare i dati per filtrare e ordinare il report. 

### <a name="microsoft-teams-device-usage-report"></a>Report sull'utilizzo di dispositivi Microsoft Teams

Il report utilizzo di dispositivi teams fornisce informazioni sul modo in cui gli utenti si connettono ai team, incluse le app per dispositivi mobili. Il report consente di comprendere i dispositivi più diffusi nell'organizzazione e il numero di utenti che lavorano ovunque ci si trovi.

![Screenshot del report utilizzo di dispositivi teams.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretare il report sull'utilizzo del dispositivo Microsoft Teams

È possibile ottenere una visualizzazione nell'utilizzo del dispositivo teams esaminando gli **utenti** e i grafici di **distribuzione** .

![Screenshot del report utilizzo di dispositivi teams con callout numerati.](media/teams-device-usage-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report del dispositivo teams può essere visualizzato per le tendenze degli ultimi 7 giorni, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un determinato intervallo di tempo nel report, la tabella (7) visualizzerà i dati per 30 giorni fino alla data (2) per la generazione del report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La visualizzazione **utenti** Mostra il numero di utenti giornalieri per tipo di dispositivo. |
|**4**   |La visualizzazione **distribuzione** Mostra il numero di utenti per dispositivo nel periodo di tempo selezionato.  |
|**5**   | <ul><li>Nel grafico **utenti** l'asse X è l'intervallo di date selezionato per il report e l'asse Y è il numero di utenti per tipo di dispositivo.</ul></li> <ul><li>Nel grafico di **distribuzione** l'asse X Mostra i diversi dispositivi usati per connettersi ai team e l'asse Y è il numero di utenti che usano il dispositivo.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico di **distribuzione** fare clic o toccare **Windows**, **Mac**, **Web**, **iOS**o **Android** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella Grid. |
|**7**   |Elenco di team attivi in un intervallo di tempo di Reporting più ampio (180 giorni).  Il numero di attività varia in base alla selezione della data. <br><br> Per visualizzare le informazioni seguenti nella tabella, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Username** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere anonimo questo campo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'attività di teams.</ul></li> <ul><li>**Eliminato** indica se il team viene eliminato. Se il team viene eliminato, ma con attività nel periodo di riferimento, verrà visualizzato nella griglia con l'impostazione eliminata impostata su true.</ul></li><ul><li>**Data eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Windows** è selezionato se l'utente era attivo nel client desktop teams in un computer basato su Windows.</ul></li> <ul><li>**Mac** è selezionato se l'utente era attivo nel client desktop teams in un computer MacOS.</ul></li>  <ul><li>**Web** è selezionato se l'utente era attivo nel client Web teams.</ul></li> <ul><li>**iOS** è selezionato se l'utente era attivo nel client per dispositivi mobili teams per iOS.</ul></li> <ul><li>Il **telefono Android** è selezionato se l'utente era attivo nel client per dispositivi mobili teams per Android.</ul></li></li> <ui>Se i criteri dell'organizzazione impediscono di visualizzare i report in cui le informazioni utente sono identificabili, è possibile modificare l'impostazione di privacy per tutti questi report. Vedere la sezione **come si nascondono i dettagli del livello utente** nell'anteprima dell'interfaccia di [amministrazione di Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Toccare o fare clic su **colonne** per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Fare clic o toccare **Esporta** per esportare i dati del report in un file CSV di Excel. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2.000 utenti, è possibile ordinare e filtrare all'interno della tabella nel report stesso. Se sono presenti più di 2.000 utenti, sarà necessario esportare i dati per filtrare e ordinare il report. 

## <a name="who-can-access-the-teams-activity-reports"></a>Utenti autorizzati a accedere ai report attività Teams

I report attività possono essere raggiunti dagli utenti assegnati:

- Ruolo di amministratore globale di Office 365
- Ruolo di amministratore specifico del prodotto (Exchange, Skype for business o SharePoint)
- Ruolo lettore report

### <a name="reports-reader-role"></a>Ruolo lettore report

È possibile assegnare il ruolo di *lettore report* al personale non it a cui si vuole accedere ai report. Assegnando questo ruolo ai responsabili della formazione o agli stakeholder aziendali, puoi assicurarti che abbiano accesso alle informazioni utili per guidare e tenere traccia dei team.

## <a name="other-information-on-the-reports-dashboard"></a>Altre informazioni nel dashboard report

### <a name="at-a-glance-activity-widget"></a>Widget attività at-a-Glance

Il dashboard report include i dati di utilizzo di Teams nel widget attività at-a-Glance, che offre una visualizzazione incrociata del modo in cui gli utenti comunicano e collaborano usando gli altri servizi di Office 365.

![Screenshot del widget attività di team at-a-Glance.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Scheda attività Teams

La scheda attività Teams nel dashboard report offre una panoramica delle attività in teams, incluso il numero di utenti attivi, in modo da poter capire rapidamente in che modo molti utenti usano il servizio. Facendo clic sulla scheda attività nel dashboard si passa al report attività utente teams. 

![Screenshot della scheda attività teams.](media/teams-activity-card.png)
