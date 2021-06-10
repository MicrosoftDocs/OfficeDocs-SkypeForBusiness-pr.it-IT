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
ms.openlocfilehash: 9c975bf4a3f2253dbc99230f85b48a9ae9cd0d65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107192"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usare i report attività per Microsoft Teams 
========================================

È possibile usare i report attività nell'Microsoft 365 di amministrazione per vedere in che modo gli utenti dell'organizzazione usano Microsoft Teams. Ad esempio, se alcuni non usano ancora Microsoft Teams, potrebbero non sapere come iniziare o capire come usare Teams per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per stabilire come assegnare la priorità alle attività di formazione e comunicazione.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Come visualizzare i Teams report nel dashboard Report

1. [Nell'Microsoft 365 di amministrazione selezionare](https://portal.office.com/adminportal/home) **Utilizzo**  >  **report.**
 
2. Nella pagina **Utilizzo** scegliere **Seleziona un report** e quindi in Microsoft Teams nell'elenco dei report scegliere il report da visualizzare. 

## <a name="teams-activity-reports-that-are-available"></a>Teams report attività disponibili

Al momento sono disponibili due report attività che è possibile visualizzare:

- [Microsoft Teams attività utente](#microsoft-teams-user-activity-report) 
- [Microsoft Teams utilizzo dei dispositivi](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams attività utente

Il Teams attività degli utenti offre una visualizzazione delle attività più comuni eseguite dagli utenti in Teams. Questo include il numero di persone che partecipano a una chat in un canale, quante comunicano tramite messaggio di chat privato e quante partecipano a chiamate o riunioni. È possibile visualizzare queste informazioni per l'intera organizzazione e per ogni singolo utente.

![Screenshot del report attività utente nell'interfaccia di amministrazione.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report attività Microsoft Teams utente

È possibile ottenere una visualizzazione delle Teams utente esaminando i grafici **Attività** **e Utenti.**

![Schermata del report attività utente con callout numerati.](media/teams-user-activity-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il Teams attività degli utenti può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un intervallo di tempo specifico nel report, la tabella (7) mostrerà i dati per 30 giorni, fino alla data (2) per la data in cui è stato generato il report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La **visualizzazione** Attività mostra il numero di Microsoft Teams attività per tipo di attività. I tipi di attività sono il numero di messaggi di chat del team, messaggi di chat privata, chiamate e riunioni. |
|**4**   |La **visualizzazione** Utenti mostra il numero di utenti per tipo di attività. I tipi di attività sono il numero di messaggi di chat del team, messaggi di chat privata, chiamate e riunioni. |
|**5**   |L'asse X nei grafici è l'intervallo di date selezionato per il report specifico. <ul><li>Nel grafico **Attività** l'asse Y è il conteggio dell'attività specificata.</ul></li> <ul><li>Nel grafico **Utenti,** l'asse Y è il numero di utenti che partecipano a chat di team, chat private, chiamate o riunioni.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **Attività** toccare o fare clic su  Messaggi del **canale,** **Messaggi chat,** **Chiamate** o Riunioni per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. |
|**7**   |Elenco dei team attivi nell'intervallo di tempo più ampio (180 giorni).  Il numero di attività varia in base alla selezione della data. <br><br> Per visualizzare le informazioni seguenti nella tabella, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Nomeutente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere anonimo questo campo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'Microsoft Teams attività.</ul></li> <ul><li>**Messaggi del canale** è il numero di messaggi univoci che l'utente ha pubblicato in una chat del team durante il periodo di tempo specificato.</ul></li> <ul><li>**Messaggi chat** è il numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.</ul></li> <ul><li>**Chiamate** è il numero di chiamate a cui l'utente ha partecipato durante il periodo di tempo specificato.</ul></li> <ul><li>**Riunioni** è il numero di riunioni online a cui l'utente ha partecipato durante il periodo di tempo specificato.</ul></li> <ul><li> Altre attività sono il numero di altre attività del team da parte dell'utente, alcune delle quali includono, e non solo, messaggi di gradimento, app, lavorare sui file, cercare, seguire team e canale e favorirli.</ul></li> <ul><li>**Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma ha avuto attività nel periodo di riferimento, verrà visualizzato nella griglia con eliminato impostato su true.</ul></li> <ul><li>**Data eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Prodotto assegnato** è l'elenco di prodotti assegnati all'utente.</ul></li>Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come si nascondono i dettagli** a livello di utente nella sezione Report attività [nell'anteprima](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)dell Microsoft 365 di amministrazione.</ui> |
|**8**   |Toccare o fare **clic su** Colonne per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Toccare o fare clic **su Esporta** per esportare i dati del report in Excel .csv file. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2.000 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se si hanno più di 2.000 utenti, sarà necessario esportare i dati per filtrare e ordinare il report. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams utilizzo dei dispositivi

Il report Teams utilizzo dei dispositivi mobili fornisce informazioni su come gli utenti si connettono a Teams, incluse le app per dispositivi mobili. Il report consente di capire quali dispositivi sono più diffusi nell'organizzazione e quanti utenti lavorano in viaggio.

![Schermata del report sull'Teams di utilizzo dei dispositivi.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretare il report sull Microsoft Teams di utilizzo dei dispositivi

È possibile ottenere una visualizzazione dell'Teams dell'utilizzo dei dispositivi esaminando i grafici **Utenti** **e** Distribuzione.

![Schermata del report sull'Teams di utilizzo dei dispositivi con callout numerati.](media/teams-device-usage-report-with-callouts.png)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Teams dispositivo può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un intervallo di tempo specifico nel report, la tabella (7) mostrerà i dati per 30 giorni, fino alla data (2) per la data in cui è stato generato il report. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |La **visualizzazione** Utenti mostra il numero di utenti giornalieri per tipo di dispositivo. |
|**4**   |La **visualizzazione** Distribuzione mostra il numero di utenti per dispositivo nel periodo di tempo selezionato.  |
|**5**   | <ul><li>Nel grafico **Utenti** l'asse X è l'intervallo di date selezionato per il report e l'asse Y è il numero di utenti per tipo di dispositivo.</ul></li> <ul><li>Nel grafico **Distribuzione** l'asse X mostra i diversi dispositivi usati per connettersi a Teams e l'asse Y è il numero di utenti che usano il dispositivo.</ul></li> |
|**6**   |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **Distribuzione** toccare o **fare** clic su Windows , **Mac**, **Linux**, **Web**, **iOS** o **Android** per visualizzare solo le informazioni relative a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. |
|**7**   |Elenco dei team attivi nell'intervallo di tempo più ampio (180 giorni).  Il numero di attività varia in base alla selezione della data. <br><br> Per visualizzare le informazioni seguenti nella tabella, assicurarsi di aggiungere le colonne alla tabella. <ul><li>**Nomeutente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere anonimo questo campo.</ul></li> <ul><li>**Data ultima attività (UTC)** si riferisce all'ultima data in cui l'utente ha partecipato a un'Teams attività.</ul></li> <ul><li>**Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma ha avuto attività nel periodo di riferimento, verrà visualizzato nella griglia con eliminato impostato su true.</ul></li><ul><li>**Data eliminazione** è la data in cui l'utente è stato eliminato.</ul></li> <ul><li>**Windows** è selezionato se l'utente era attivo nel client desktop Teams in un computer Windows basato su Windows.</ul></li> <ul><li>**Mac** è selezionato se l'utente era attivo nel client desktop Teams in un computer macOS.</ul></li>  <ul><li>**Linux** è selezionato se l'utente era attivo nel client desktop Teams in un computer Linux.</ul></li>   <ul><li>**Web** è selezionato se l'utente era attivo nel Teams web client.</ul></li> <ul><li>**iOS** è selezionato se l'utente era attivo nel client Teams per dispositivi mobili per iOS.</ul></li> <ul><li>**Il telefono Android** è selezionato se l'utente era attivo nel client Teams mobile per Android.</ul></li></li> <ui>Se i criteri dell'organizzazione impediscono la visualizzazione di report in cui le informazioni utente sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come si nascondono i dettagli** a livello di utente nella sezione Report attività [nell'anteprima](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)dell Microsoft 365 di amministrazione.</ui> |
|**8**   |Toccare o fare **clic su** Colonne per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Toccare o fare clic **su Esporta** per esportare i dati del report in Excel .csv file. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2.000 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se si hanno più di 2.000 utenti, sarà necessario esportare i dati per filtrare e ordinare il report. 

## <a name="who-can-access-the-teams-activity-reports"></a>Who accedere ai report Teams attività

I report attività sono accessibili agli utenti assegnati:

- Ruolo di amministratore globale
- Ruolo di amministratore specifico del prodotto (Exchange, Skype for Business o SharePoint)
- Ruolo di lettore report

### <a name="reports-reader-role"></a>Ruolo di lettore report

È possibile assegnare il ruolo di lettore report a persone che non hanno diritti di amministratore, ma sono responsabili dell'adozione o del monitoraggio dell'uso delle licenze Teams. Per informazioni su come assegnare ruoli, vedere [Assegnare](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)ruoli di amministratore e non amministratore agli utenti con Azure Active Directory .

## <a name="other-information-on-the-reports-dashboard"></a>Altre informazioni nel dashboard Report

### <a name="at-a-glance-activity-widget"></a>Widget Attività a colpo d'occhio

Il dashboard Report include i dati sull'utilizzo di Teams nel widget attività a colpo d'occhio, che offre una visualizzazione cross-product del modo in cui gli utenti comunicano e collaborano usando gli altri servizi di Microsoft 365 o Office 365.

![Schermata del widget Teams attività a colpo d'occhio.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams attività

La scheda Teams attività nel dashboard Report offre una panoramica dell'attività in Teams, incluso il numero di utenti attivi, in modo da comprendere rapidamente quanti utenti usano il servizio. Se si fa clic sulla scheda attività nel dashboard, viene visualizzato il report attività Teams utente. 

![Schermata della scheda Teams attività.](media/teams-activity-card.png)