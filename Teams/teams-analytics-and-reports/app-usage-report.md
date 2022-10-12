---
title: Report utilizzo app Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull'utilizzo dell'app Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c437676df215ead9b588091f2cb58c19d1e136fd
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532266"
---
# <a name="microsoft-teams-app-usage-report"></a>Report utilizzo app Microsoft Teams

Il report Utilizzo app Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni dettagliate sulle app usate dagli utenti in Teams. È possibile ottenere informazioni approfondite sull'attività delle app nell'organizzazione per diverse app Microsoft (Viva Learning, Turni e così via), di terze parti (Polly, Trello e così via) & app Line of Business (LOB) di Teams.   

Puoi usare questo report per capire dove vengono usate esattamente le app diverse e approfondire i dati di utilizzo per ogni app.

I dati rappresentati in questo report forniscono le risposte alle domande seguenti:

-  Quante app installate hanno gli utenti nel tuo ambiente?
-  Quante app hanno almeno un utente attivo nel tuo ambiente in base al tipo (Microsoft, terze parti e LOB)?
-  Quante app vengono usate per piattaforma (Windows, Mac, Web o mobile)?
-  Quanti utenti attivi e team attivi usano un'app?

> [!NOTE]
> L'utilizzo per le app line-of-business **caricate** in sideload non è incluso in questo report.

Questo articolo spiega come accedere al report e visualizzare e interpretare le diverse metriche all'interno del report. 

## <a name="view-the-app-usage-report"></a>Visualizzare il report sull'utilizzo delle app

Per visualizzare i report nell'interfaccia di amministrazione di Microsoft Teams, è necessario essere un amministratore globale, un lettore globale o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo app**.

2. In **Intervallo di date** selezionare un intervallo e quindi **Selezionare Esegui report**.

:::image type="content" alt-text="Screenshot del report utilizzo app Teams nell'interfaccia di amministrazione di Teams con callout." source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report utilizzo app può essere visualizzato per le tendenze degli ultimi 7, 30, 90 e 180 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24-48 ore rispetto al momento in cui è stata usata un'app. Ad esempio, i dati relativi al 10 gennaio dovrebbero essere visualizzati nel report intorno al 12 gennaio. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi.</li> </ul>Passare il puntatore del mouse sul punto che rappresenta un elemento in una data specificata per visualizzare il numero di istanze dell'elemento in tale data specificata.|
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Ad esempio, seleziona **App Attive Microsoft**, **Totale app installate** e altro ancora per visualizzare solo le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. <ul><li>**App Microsoft attive** è il numero di app Microsoft (ad esempio Viva Learning) usate nell'organizzazione. </li> <li>**App di terze parti attive** è il numero di app di terze parti usate nell'organizzazione, ad esempio Polly.  </li> <li>**App line-of-business attive** è il numero di app Line of Business usate nell'organizzazione. </li><li>**Il totale delle app attive** è il numero totale di app usate nell'organizzazione. </li><li>**Il totale delle app inattive** è il numero di app non usate nell'organizzazione. </li><li>**Il totale delle app installate** è il numero totale di app installate all'interno dell'organizzazione. La data di inizio per tutte le metriche di installazione è ottobre 2021. Verranno conteggiate solo le app installate dopo tale data.</li></ul> Il grafico mostra le metriche aggregate in tutta l'organizzazione ogni giorno in un periodo selezionato. Ad esempio, se selezioni il 28 gennaio e metriche **App di terze parti attive**, il grafico mostra il numero totale di app di terze parti usate il 28 gennaio all'interno dell'organizzazione.  |
|**5**   |La tabella fornisce una suddivisione dell'utilizzo per ogni app. <ul><li>**ID app** è l'identificatore esterno dell'app presente nel manifesto dell'app. <br/>Per altre informazioni sull'app, vedere la [sezione Gestisci app nell'interfaccia di amministrazione di Teams](/microsoftteams/manage-apps) facendo riferimento a quest'ultima usando questo ID app esterno.</li> <li>**Nome app** è il nome dell'applicazione presente nel manifesto dell'app. </li> <li>**Publisher** è l'autore dell'applicazione presente nel manifesto dell'app. Questa opzione è disponibile solo per le app pubblicate nello Store globale.</li> <li>**Teams che usa questa app** è il numero di team di Teams distinti che usano questa app con almeno un utente. </li><li>**Gli utenti che usano questa app** sono il numero di utenti distinti dell'organizzazione che usano questa app.</li> <li>**Usato in Windows** indica se l'app è stata usata in Windows da almeno un utente dell'organizzazione.</li><li>**Usato su Mac** indica se l'app è stata usata in MAC da almeno un utente dell'organizzazione.</li><li>**Usato sul Web** indica se l'app è stata usata sul Web da almeno un utente dell'organizzazione. </li> <li>**Data ultimo utilizzo** è la data dell'ultimo utilizzo dell'app da parte di tutti gli utenti dell'organizzazione. </li></ul> |
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Esportare il report in un file CSV per l'analisi offline. Selezionare l'icona **Esporta in Excel** per scaricare il report nel browser.|
|**8** |I dati della serie temporale rappresentati nel grafico superiore mostrano metriche di utilizzo diverse aggregate per l'intero tenant.|
|**9** |I dati tabulari rappresentati nella metà inferiore mostrano metriche di utilizzo diverse aggregate per team.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Gestione delle app nell'interfaccia di amministrazione di Microsoft Teams

Per altre informazioni su come gestire le app di Teams, vedere [Informazioni sulle app in Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Per collegare un'app in questo report all'esperienza Gestisci app nell'interfaccia di amministrazione di Microsoft Teams, è possibile usare quanto segue:

- Nome app
- ID app esterno

Gli ID delle app esterni equivalgono all'ID nella pagina Gestisci app per le app dello Store. Per le app line-of-business, la colonna **ID dell'app esterna**  può essere abilitata nella [sezione Gestisci app nelle impostazioni della colonna dell'interfaccia di amministrazione di Teams](/microsoftteams/manage-apps) . È anche possibile visualizzarlo nella pagina dei dettagli dell'app di un'app line-of-business personalizzata.

## <a name="related-articles"></a>Articoli correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
