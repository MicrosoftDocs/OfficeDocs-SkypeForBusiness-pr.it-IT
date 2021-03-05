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
- M365-collaboration
description: Informazioni su come usare i report attività per vedere come gli utenti dell'organizzazione usano Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff2c013f286e6a6e64b88f74dc0685e3876f517e
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460636"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usare i report attività per Microsoft Teams 
========================================

È possibile usare i report attività nell'interfaccia di amministrazione di Microsoft 365 per vedere in che modo gli utenti dell'organizzazione usano Microsoft Teams. Ad esempio, se alcuni non usano ancora Microsoft Teams, potrebbero non sapere come iniziare o capire come possono usare Teams per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per stabilire come assegnare la priorità alle attività di formazione e comunicazione.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Come visualizzare i report di Teams nel dashboard Report

1. [Nell'interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home)selezionare Utilizzo   >  **report.**
 
2. Nella pagina **Utilizzo** scegliere **Seleziona un report,** quindi in **Microsoft Teams** nell'elenco dei report scegliere il report da visualizzare.

## <a name="teams-activity-reports-that-are-available"></a>Report attività di Teams disponibili

Sono attualmente disponibili due report attività che è possibile visualizzare:

- [Report Attività degli utenti di Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Report utilizzo dispositivi Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Report Attività degli utenti di Microsoft Teams

Il report Attività degli utenti di Teams offre una visualizzazione delle attività più comuni eseguite dagli utenti in Teams. Ciò include il numero di persone che partecipano a una chat in un canale, quante comunicano tramite messaggio di chat privato e quante partecipano a chiamate o riunioni. Queste informazioni sono disponibili per l'intera organizzazione e per ogni singolo utente.

![Screenshot del report Attività utente nell'interfaccia di amministrazione.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report Attività degli utenti di Microsoft Teams

È possibile avere una visione d'insieme dell'attività degli utenti di Teams esaminando i **grafici** Attività **e** Utenti.

![Screenshot del report attività utente con callout numerati.](media/teams-user-activity-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività degli utenti di Teams può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un intervallo di tempo specifico nel report, la tabella (7) mostrerà dati per 30 giorni, fino alla data (2) per la data in cui è stato generato il report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La **visualizzazione Attività** mostra il numero di attività di Microsoft Teams per tipo di attività. I tipi di attività sono numero di messaggi in chat del team, messaggi in chat privati, chiamate e riunioni. |
|**4**   |La **visualizzazione** Utenti mostra il numero di utenti per tipo di attività. I tipi di attività sono numero di messaggi in chat del team, messaggi in chat privati, chiamate e riunioni. |
|**5**   |L'asse X nei grafici rappresenta l'intervallo di date selezionato per il report specifico. <ul><li>Nel grafico **Attività** l'asse Y rappresenta il conteggio dell'attività specificata.</ul></li> <ul><li>Nel grafico **Utenti,** l'asse Y è il numero di utenti che partecipano a chat di teams, chat private, chiamate o riunioni.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio,  nel grafico Attività toccare o fare clic su  Messaggi del **canale,** Messaggi **in chat,** Chiamate o Riunioni per visualizzare solo le informazioni per ciascun elemento. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. |
|**7**   |L'elenco dei team attivi nel periodo di tempo di riferimento più ampio (180 giorni).  Il numero di attività varia in base alla data selezionata. <br><br> Per visualizzare le informazioni seguenti, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Il nome** utente è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'attività di Microsoft Teams.</ul></li> <ul><li>**Messaggi del canale** è il numero di messaggi univoci che l'utente ha pubblicato in una chat del team durante il periodo di tempo specificato.</ul></li> <ul><li>**I messaggi di** chat sono il numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.</ul></li> <ul><li>**Chiamate** è il numero di chiamate a cui l'utente ha partecipato nel periodo di tempo specificato.</ul></li> <ul><li>**Riunioni** è il numero di riunioni online a cui l'utente ha partecipato nel periodo di tempo specificato.</ul></li> <ul><li>**Altre attività** sono il numero di altre attività del team da parte dell'utente, alcune delle quali includono, e non limitati a: aggiungere mi piace a messaggi, app, lavorare ai file, eseguire ricerche, seguire team e canali e piacerli.</ul></li> <ul><li>**Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con l'opzione eliminata impostata su true.</ul></li> <ul><li>**La data di eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Prodotto assegnato** è l'elenco dei prodotti assegnati all'utente.</ul></li>Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i** dettagli dell'utente nella sezione Report attività nell'anteprima dell'interfaccia di amministrazione di [Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Toccare o **fare clic su** Colonne per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Toccare o fare **clic su Esporta** per esportare i dati del report in un file CSV di Excel. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2.000, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se gli utenti sono più di 2.000, sarà necessario esportare i dati per filtrare e ordinare il report. 

### <a name="microsoft-teams-device-usage-report"></a>Report utilizzo dispositivi Microsoft Teams

Il report Utilizzo di dispositivi Teams fornisce informazioni su come gli utenti si connettono a Teams, incluse le app per dispositivi mobili. Il report consente di identificare i dispositivi più diffusi all'interno dell'organizzazione e il numero di utenti che lavorano in viaggio.

![Screenshot del report Utilizzo dispositivi di Teams.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretare il report Sull'utilizzo di dispositivi Microsoft Teams

È possibile avere una visione d'insieme sull'utilizzo dei dispositivi di Teams esaminando i **grafici Utenti** **e** Distribuzione.

![Schermata del report Utilizzo di dispositivi di Teams con callout numerati.](media/teams-device-usage-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sui dispositivi di Teams può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un intervallo di tempo specifico nel report, la tabella (7) mostrerà dati per 30 giorni, fino alla data (2) per la data in cui è stato generato il report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La **visualizzazione** Utenti mostra il numero di utenti giornalieri per tipo di dispositivo. |
|**4**   |La **visualizzazione** Distribuzione mostra il numero di utenti per dispositivo nel periodo di tempo selezionato.  |
|**5**   | <ul><li>Nel grafico **Utenti** l'asse X è l'intervallo di date selezionato per il report e l'asse Y è il numero di utenti per tipo di dispositivo.</ul></li> <ul><li>Nel grafico **Distribuzione** l'asse X mostra i diversi dispositivi usati per connettersi a Teams e l'asse Y è il numero di utenti che usano il dispositivo.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **Distribuzione** toccare o fare clic su **Windows,** **Mac,** **Linux,** **Web,** **iOS** o **Android** per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. |
|**7**   |L'elenco dei team attivi nel periodo di tempo di riferimento più ampio (180 giorni).  Il numero di attività varia in base alla data selezionata. <br><br> Per visualizzare le informazioni seguenti nella tabella, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Il nome** utente è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'attività di Teams.</ul></li> <ul><li>**Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con l'opzione eliminata impostata su true.</ul></li><ul><li>**La data di eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Windows**  è selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.</ul></li> <ul><li>**Mac** è selezionato se l'utente era attivo nel client desktop di Teams su un computer macOS.</ul></li>  <ul><li>**Linux** è selezionato se l'utente era attivo nel client desktop di Teams su un computer Linux.</ul></li>   <ul><li>**Il** Web è selezionato se l'utente era attivo nel client Web di Teams.</ul></li> <ul><li>**iOS** è selezionato se l'utente era attivo nel client teams per dispositivi mobili iOS.</ul></li> <ul><li>**Il telefono Android**  è selezionato se l'utente era attivo nel client Teams per dispositivi mobili Android.</ul></li></li> <ui>Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i** dettagli dell'utente nella sezione Report attività nell'anteprima dell'interfaccia di amministrazione di [Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Toccare o **fare clic su** Colonne per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Toccare o fare **clic su Esporta** per esportare i dati del report in un file CSV di Excel. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2.000, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se gli utenti sono più di 2.000, sarà necessario esportare i dati per filtrare e ordinare il report. 

## <a name="who-can-access-the-teams-activity-reports"></a>Chi può accedere ai report attività di Teams

I report attività sono accessibili agli utenti assegnati:

- Ruolo di amministratore globale
- Ruolo di amministratore specifico del prodotto (Exchange, Skype for Business o SharePoint)
- Ruolo del lettore di report

### <a name="reports-reader-role"></a>Ruolo del lettore di report

È possibile assegnare il ruolo di lettore di report alle persone che non hanno diritti di amministratore, ma sono responsabili dell'adozione o del monitoraggio dell'uso delle licenze di Teams. Per informazioni su come assegnare ruoli, vedere Assegnare ruoli di amministratore e non amministratore [agli utenti con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>Altre informazioni nel dashboard Report

### <a name="at-a-glance-activity-widget"></a>Widget attività in sintesi

Il dashboard Report include i dati di utilizzo di Teams nel widget attività a colpo d'occhio, che offre una visualizzazione prodotto incrociata di come gli utenti comunicano e collaborano utilizzando altri servizi in Microsoft 365 o Office 365.

![Screenshot del widget Attività a colpo d'occhio di Teams.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Scheda attività di Teams

La scheda Attività di Teams nel dashboard Report offre una panoramica dell'attività in Teams, incluso il numero di utenti attivi, in modo da poter comprendere rapidamente quanti utenti usano il servizio. Se si fa clic sulla scheda attività nel dashboard, viene visualizzato il report Attività utente di Teams. 

![Schermata della scheda attività di Teams.](media/teams-activity-card.png)
