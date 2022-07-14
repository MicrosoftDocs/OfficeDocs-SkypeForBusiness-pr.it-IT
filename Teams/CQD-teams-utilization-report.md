---
title: Visualizzare l'utilizzo di Microsoft Teams in Power BI con i dati di Call Quality Dashboard
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Usare i report di Power BI di utilizzo di Teams per accedere ai dati di Call Quality Dashboard (CQD) di Microsoft Teams per tenere traccia dell'utilizzo di Microsoft Teams nell'organizzazione.
ms.openlocfilehash: 6e96f9dd06f872f2907d04aa335e2af2d7a75f2b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790341"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Visualizzare l'utilizzo di Microsoft Teams in Power BI con i dati di Call Quality Dashboard

Novità di marzo 2020, abbiamo aggiunto un report utilizzo team ai [modelli di query di Power BI scaricabili per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Questo nuovo report Utilizzo team consente di vedere come (e quanto) gli utenti usano Microsoft Teams accedendo ai dati di Teams Call Quality Dashboard (CQD). Questi report hanno lo scopo di essere una posizione centralizzata a cui gli amministratori e i responsabili aziendali possono accedere rapidamente per questi dati.

Il report di Power BI utilizzo team è costituito da due report principali: **[Riepilogo numero chiamate](#call-count-summary-report)** e **[Riepilogo minuti audio](#audio-minutes-summary-report)**. I report [Utilizzo giornaliero](#daily-usage), [Dettagli audio internazionali](#regional-audio-details), [Dettagli conferenza](#conference-details) ed [Elenco utenti](#user-list) vengono riprodotti quando un utente sfrutta i report drill-down, indicati nelle descrizioni seguenti.

> [!NOTE]
> I dati dell'edificio e della subnet devono essere popolati per fornire funzionalità di filtro regionale e di rete.

## <a name="call-count-summary-report"></a>Report riepilogativo sul numero di chiamate

La pagina principale (Call Count Summary) fornisce immediatamente il numero di sessioni audio, video e di condivisione dello schermo negli ultimi 30 e 90 giorni, come indicato nel titolo della sezione. I dati inizialmente visualizzati sono per l'intera organizzazione e possono essere filtrati usando le opzioni a discesa del filtro dei dati sul lato sinistro della pagina.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report1.png)

1. A destra degli elenchi a discesa del filtro dei dati, il numero di chiamate per tipo di elemento multimediale è suddiviso in una visualizzazione interna/esterna negli ultimi trenta giorni. Possiamo vedere attraverso lo screenshot precedente che ci sono più chiamate in corso da luoghi esterni all'organizzazione, il che ha senso considerando l'ambiente globale corrente.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report2.png)

1. A destra della casella Conteggio tipi di supporto, il numero di chiamate mensili per tipo di contenuto multimediale è disponibile per gli ultimi 90 giorni. Ogni colonna e tipo di elemento multimediale può essere posizionato al passaggio del mouse per visualizzare il conteggio relativo a un mese precedente o al mese corrente fino a oggi, fornendo informazioni sulla tendenza di utilizzo.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report3.png)
 

1. Il grafico centrale funziona come il grafico di 90 giorni, ma fornisce una visualizzazione dell'utilizzo giornaliero per gli ultimi 30 giorni e consente a un utente di fare clic con il pulsante destro del mouse ed eseguire il drill-down nei dettagli per un giorno specifico.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report4.png)

Nella sezione in basso a sinistra della pagina è presente una tabella che fornisce i valori totali per ogni tipo di elemento multimediale nell'ultimo anno. 
    ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report5.png)
    ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report6.png)   

A destra della tabella, un grafico a barre mostra i client con il maggior utilizzo (chiamate/flussi) degli ultimi 30 giorni.
   ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report7.png)

L'ultimo set di grafici di questa pagina mostra ogni tipo di supporto singolarmente, con un'analisi che mostra l'utilizzo di conferenze e P2P. I grafici seguenti mostrano che l'utilizzo delle conferenze è notevolmente superiore rispetto al P2P.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Report riepilogo minuti audio

Nel report Minuti audio utilizzo, l'utilizzo totale dei minuti viene fornito attraverso alcune visualizzazioni diverse. 

Accanto ai filtri dei dati è visualizzato il riepilogo dell'utilizzo di 30 giorni, più facile da usare nelle caselle di testo. Il numero principale mostra il totale di 30 giorni, con scomposizione interna ed esterna al di sotto.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report9.png)

Il grafico a barre in alto a destra offre una visualizzazione annuale dell'uso dell'audio della conferenza. Passare il puntatore del mouse sul mese per visualizzare i minuti dell'audio della conferenza.

Per mostrare la differenza tra P2P e audio conferenza, il grafico in basso a sinistra prende tutto l'audio dell'anno precedente e lo suddivide tra i due tipi.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report10.png)

L'ultimo grafico della pagina Minuti audio mostra l'utilizzo dei minuti audio su una mappa globale sovrapposta. Questo grafico funziona solo se i dati dell'edificio e della subnet vengono caricati nel tenant. È possibile eseguire il drill-down della sovrapposizione del grafico a torta sulla mappa, fornendo successivamente l'uso audio regionale.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Funzionalità drill-through

Come accennato in precedenza, gli utenti possono eseguire il drill-down dei report sull'utilizzo giornaliero e regionale.

### <a name="daily-usage"></a>Utilizzo giornaliero

Il report Utilizzo giornaliero consente all'amministratore di identificare i periodi di picco del consumo nel corso di una giornata. Oltre all'utilizzo, siamo anche in grado di acquisire la valutazione generale e il feedback degli utenti per quel giorno.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report12.png)

Il report Utilizzo giornaliero mostra il numero di condivisioni Audio, Video e Schermo per il giorno selezionato con la possibilità aggiunta di distinguere tra connettività interna ed esterna. Un'analisi conferenza e peer-to-peer si trova a destra immediata della casella totale della modalità. L'angolo in alto a destra del report fornisce un elenco di conferenze con l'ID associato e i partecipanti per la giornata. L'elenco delle conferenze fornisce anche un drill-down aggiuntivo per il report Dettagli conferenza. IMMAGINE SOSTITUISCI

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report13.png)

Il grafico a barre nell'area centrale consente all'utente di identificare i periodi di picco del consumo nel corso di una giornata. Gli utenti possono eseguire il drill-down nell'ora rappresentata nel grafico che presenterà il report Elenco utenti per l'ora.

A destra del grafico a barre, il feedback dell'utente viene presentato in formato visivo. Anche se la valutazione degli utenti può essere soggettiva, fornisce informazioni che possono essere utilizzate per identificare potenziali problemi.

La tabella inferiore fornisce un intervallo di metriche per il giorno. Percentuali scadenti insieme a tassi di errore possono fornire un amministratore con potenziali aree di miglioramento. Ogni ora può anche essere selezionata singolarmente, come illustrato di seguito.

Questi dati possono essere usati per identificare le aree che presentano problemi durante i periodi di picco di consumo.


Fare clic sulla colonna relativa a quel giorno per visualizzare le metriche per quell'ora.
![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report14.png)
  
  1.  La tabella sotto il grafico visualizzerà le metriche per quell'ora. Questo può essere ordinato in base a qualsiasi intestazione di colonna; tuttavia, saremmo interessati a trovare aree problematiche.  
    ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report15.png)
    
  2.  Durante questo intervallo di tempo, l'area IND sta riscontrando prestazioni video scadenti nelle conferenze. Successivamente, i report Microsoft QER di CQD possono essere usati per limitare la posizione problematica man mano che sono stati identificati l'area geografica e l'intervallo di tempo.

### <a name="conference-details"></a>Dettagli conferenza

Il report Dettagli conferenza fornisce informazioni aggiuntive per le riunioni, da un elenco di partecipanti, ai tipi di elementi multimediali usati durante la sessione.

Fare clic con il pulsante destro del mouse su una conferenza sulla barra dei partecipanti nel grafico degli ID conferenza nella pagina Utilizzo giornaliero per eseguire il drill-down dei dettagli della conferenza.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report24.png)

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report25.png)
  

Possiamo vedere i partecipanti alla conferenza e tutte le informazioni pertinenti fino a perdita di pacchetti e instabilità per facilitare potenziali operazioni di risoluzione dei problemi nella tabella inferiore.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Dettagli audio regionali

Il drill-down dettagli audio regionale mostra in modo specifico l'utilizzo dei minuti audio per l'area selezionata. Gli utenti con accesso a Call Quality Dashboard possono visualizzare le tendenze di utilizzo sia per il P2P che per l'audio delle conferenze all'interno dell'area selezionata.

1.  Nella pagina Call Count Summary eseguire il drill-through fino a un'area specifica nella tabella.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report16.png)

2.  Selezionare la riga per cui sono necessarie informazioni aggiuntive per l'area.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report17.png)

3.  Le tendenze dei dati mostrano un numero significativo di minuti di utilizzo nella rete interna, con conferenze che superano di gran lunga l'uso del P2P.
  ![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report18.png)

La tendenza audio regionale può essere utilizzata per mostrare come gli utenti sono influenzati da influenze esterne nel mondo. In particolare, in questo momento, ci aspetteremmo di vedere l'utilizzo esterno per le aree EMEA e APAC aumentare con le persone a cui viene chiesto di lavorare in remoto.


### <a name="user-list"></a>Elenco utenti

Il drill-down elenco utenti fornisce, come ci si potrebbe aspettare, informazioni specifiche dell'utente per un'ora specifica selezionata dalla persona che visualizza il report. Il report Elenco utenti è accessibile tramite il drill-down nel grafico Tendenze orarie del report Utilizzo giornaliero. Fare clic con il pulsante destro del mouse sull'ora per cui sono necessarie altre informazioni e selezionare Drill-through ed Elenco utenti, come illustrato di seguito.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report19.png)

Il report Elenco utenti mostra la connettività interna/esterna tramite il grafico ad anello nella parte superiore centrale della pagina. Possiamo vedere che c'è una grande quantità di partecipazione dall'esterno della rete aziendale nell'immagine seguente.

L'angolo in alto a destra del grafico mostra il numero di chiamate effettuate da ogni utente entro quell'ora.

![Screenshot: Report di utilizzo di Teams.](media/CQD-teams-utilization-report20.png)

La tabella inferiore contiene informazioni dettagliate per le sessioni a cui ogni utente ha partecipato durante quell'ora. La colonna Tipo errore è utile per determinare le cause dell'interruzione di una chiamata. Le colonne Dispositivo di acquisizione e rendering sono utili per identificare il motivo per cui una chiamata è stata segnalata di scarsa qualità.


## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](./monitor-call-quality-qos.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
