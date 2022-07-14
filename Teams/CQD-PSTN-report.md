---
title: Uso del report Routing diretto PSTN CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Usare il report Routing diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD)) per monitorare e risolvere i problemi relativi alle chiamate PSTN in Microsoft Teams.
ms.openlocfilehash: 8d6e971adc3cd7e4ec9b4038356e744d4451146f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789891"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Uso del report Routing diretto PSTN CQD

Novità di marzo 2020, abbiamo aggiunto un report routing diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) ai [modelli di query di Power BI scaricabili per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


Il report CQD PSTN Direct Routing (CQD PSTN Direct Routing Report.pbit) consente di comprendere i modelli di utilizzo e la qualità dei servizi PSTN. Utilizza questo report per monitorare l'utilizzo del servizio, informazioni sul controller di frontiera della sessione (SBC), il servizio di telefonia, i parametri di rete e i dettagli del rapporto efficacia rete. Queste informazioni possono aiutare a identificare i problemi, incluso il motivo delle chiamate interrotte. Ad esempio, sarai in grado di vedere quando il volume diminuisce o quante chiamate vengono influenzate e per quale motivo.


Il report routing diretto PSTN di Call Quality Dashboard include quattro sezioni:

  - [Panoramica PSTN](#pstn-overview)

  - [Dettagli servizio](#service-details)

  - [Network Effectiveness Ratio](#network-effectiveness-ratio)

  - [Parametri di rete](#network-parameters)

## <a name="highlights"></a>Attrazioni

1. Analizzare per tipo di chiamata, SBC, paese chiamante e chiamato

   Il report Routing diretto PSTN di Call Quality Dashboard aggrega metriche di affidabilità e utilizzo per tutti gli SBC nel tenant per gli ultimi 7, 30 o 180 giorni (6 mesi). È possibile analizzare i dati per tipo di chiamata, SBC, paese chiamante e chiamato. Se si è interessati a un determinato paese o ABC, è possibile identificare le modifiche delle tendenze nell'intervallo di tempo selezionato.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report Routing diretto PSTN CQD.":::
   
2. Tenere traccia delle tendenze

    L'analisi delle tendenze è essenziale per comprendere l'utilizzo dei servizi e l'affidabilità. Le tendenze orarie forniscono un'analisi più approfondita delle prestazioni quotidiane, che consente di identificare gli incidenti in tempo reale. Le tendenze quotidiane ti consentono di vedere l'integrità dei servizi da un punto di vista a lungo termine. È importante essere in grado di spostarsi tra queste due modalità con la granularità dei dati appropriata. Il report Routing diretto PSTN di Call Quality Dashboard offre una panoramica delle tendenze di 6 mesi, tendenze giornaliere di 7 e 30 giorni e tendenze orarie che consentono di analizzare le prestazioni a ogni livello.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report Routing diretto PSTN di Call Quality Dashboard.":::

3. Eseguire il drill-through fino a SBC o a livello di utente

   Abbiamo creato funzionalità drill-through su molte categorie di dati in Call Quality Dashboard, che consente di comprendere rapidamente l'utilizzo o la distribuzione dell'affidabilità a livello di SBC o utente. Il drill-through consente di individuare rapidamente i problemi e comprendere l'impatto reale degli utenti. Il report Routing diretto PSTN di Call Quality Dashboard esegue il drill-down delle metriche Service Detail e Network Effectiveness Ratio. Fare clic sul punto dati di interesse per visualizzare i dettagli A livello di utente o SBC.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot che mostra la funzionalità drill-through in un punto dati.":::


## <a name="pstn-overview"></a>Panoramica PSTN

Il report routing diretto PSTN di Call Quality Dashboard fornisce le informazioni seguenti relative all'integrità generale del servizio negli ultimi 180 giorni.
![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report1.png)

Ad esempio, se sei interessato all'utilizzo generale e all'integrità di tutte le chiamate in ingresso che passano attraverso SBC abc.bca.adatum.biz con gli Stati Uniti come paese interno:

| **Chiamata in uscita** | **Descrizione**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Puoi usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come controller del boarder di sessione e Stati Uniti come paese interno. |
| 2            | Tendenza di utilizzo negli ultimi 180 giorni. Il report dettagli utilizzo è reperibile nella pagina Dettagli servizio.                                                                     |
| 3            | Tendenza post-ritardo di chiamata, latenza, instabilità e perdita di pacchetti negli ultimi 180 giorni. È possibile trovare un report dettagliato nella pagina Parametri di rete.                           |
| 4            | Chiamate simultanee e tendenza utente attivo giornaliero negli ultimi 180 giorni. Questo grafico consente di comprendere il volume massimo del servizio.                            |
| 5            | Top Call End Motivo ha influenzato la qualità del servizio negli ultimi 180 giorni. I dettagli sull'integrità dei servizi sono disponibili nella pagina Network Effective Ratio (NER).                    |

## <a name="service-details"></a>Dettagli servizio

Questa pagina fornisce le tendenze di utilizzo dei servizi al giorno e la suddivisione del feedback degli utenti per area geografica.

  - **Total Attempt Calls -** Chiamate del tentativo totale in quell'intervallo di tempo, incluse le chiamate riuscite e non riuscite

  - **Totale chiamate connesse -** Totale chiamate connesse in quell'intervallo di tempo

  - **Totale minuti –** Utilizzo totale dei minuti in tale intervallo di tempo

  - **Utenti attivi giornalieri(DAU) -** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno

  - **Chiamate simultanee -** Massimo chiamate attive simultanee in un minuto

  - **Feedback degli utenti -** Il punteggio "Valuta la mia chiamata" proviene dall'utente. 3-5 è considerato una buona chiamata. 1-2 è considerato una chiamata errata.

![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report2.png)

Ad esempio:

1.  Se vedi che la durata media delle chiamate scende a 0 al 14/02/2020, puoi innanzitutto verificare se il volume delle chiamate è normale e verificare se esiste una grande discrepanza tra le chiamate totali di connessione e le chiamate con tentativo totale. Vai quindi alla pagina Network Effectiveness Ratio per investire sui motivi degli errori delle chiamate.

2.  Se si notano punti rossi crescenti sulla mappa di feedback degli utenti, è possibile passare alla pagina Network Effectiveness Ratio e a Network Parameter per vedere se ci sono anomalie e si potrebbe sollevare un ticket utilizzando MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Network Effectiveness Ratio

Questa è la stessa metrica visualizzata nel dashboard Integrità complessiva. È possibile controllare il numero NER orario con i dettagli delle chiamate interessate sia per le indicazioni di chiamata (in ingresso/uscita) nel rapporto di efficacia oraria della rete che nel grafico del motivo della fine delle chiamate di seguito.

  - **NER** - La capacità (%) di una rete di effettuare chiamate misurando il numero di chiamate inviate e il numero di chiamate inviate a un destinatario.

  - **Codice di risposta SIP**: un codice di risposta intero a tre cifre mostra lo stato della chiamata.

  - **Codice di risposta Microsoft-A** inviato dal componente Microsoft.

  - **Descrizione** : fase del motivo corrispondente al codice di risposta SIP e al codice di risposta Microsoft.

  - **Numero di chiamate interessate** : il numero totale di chiamate è stato interessato nell'intervallo di tempo selezionato.

> ![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report3.png)
> 
Ad esempio:

![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report4.png)

Se il NER giornaliero ha un'anteprima il 05/02/2020, è possibile fare clic sulla data e altri grafici ingrandiranno la data specifica.

![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report5.png)

Dal NER Good Percentage Hourly Trend, si può scoprire che il calo avviene intorno alle 21:00. Quindi fai di nuovo clic per ingrandire l'ora 21 e controlla Dettagli chiamata attivati per vedere quante chiamate hanno avuto esito negativo in quell'ora e quali sono i motivi del fine chiamata. È possibile iniziare con riprese auto-problemi su eventuali problemi SBC o segnalare al Service Desk se il problema non è correlato a SBC.

## <a name="network-parameters"></a>Parametri di rete

Tutti i parametri di rete vengono misurati dall'interfaccia routing diretto al controller dei confini della sessione. Per informazioni sui valori consigliati, vedere [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md) e esaminare i valori consigliati da Customer Edge a Microsoft Edge.

  - **Jitter** : misura in millisecondi della variazione del tempo di ritardo di propagazione di rete calcolata tra due endpoint tramite RTCP (The RTP Control Protocol).

  - **Packet Loss** : misura del pacchetto che non è riuscito ad arrivare; viene calcolata tra due endpoint.

  - **Latenza** - (anche nota come tempo di round trip) è il tempo necessario per inviare un segnale più il tempo necessario per ricevere la conferma del segnale. Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.

> ![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report6.png)

Ad esempio:

Se viene visualizzato un picco su uno dei quattro grafici (Latenza, Instabilità, Frequenza di perdita pacchetti, Ritardo post chiamata) per una data specifica, ad esempio latenza il 14/02/2020, fare clic sul punto di data. Il grafico di tendenza orario nella parte inferiore verrà aggiornato in modo da visualizzare il numero orario. È possibile controllare gli SBC o sollevare un ticket con MS Service Desk.

![Screenshot: Report call quality dashboard PSTN.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di Call Quality Dashboard per Microsoft Teams](CQD-PSTN-report.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)