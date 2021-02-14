---
title: Uso del report di routing diretto PSTN di CQD
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
description: Usa il report di instradamento diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) per monitorare e risolvere i problemi relativi alle chiamate PSTN in Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583103"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Uso del report di routing diretto PSTN di CQD

A marzo 2020 è stato aggiunto un report di Routing diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) ai modelli di query di Power BI scaricabili per [Call Quality](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)Dashboard. 


Il report CQD PSTN Direct Routing (CQD PSTN Direct Routing Report.pbit) consente di conoscere i modelli di utilizzo e la qualità dei servizi PSTN. Usare questo report per monitorare l'utilizzo del servizio, le informazioni sul controller dei confini della sessione (SBC), il servizio di telefonia, i parametri di rete e i dettagli sul rapporto efficacia della rete. Queste informazioni possono aiutarti a identificare i problemi, incluso il motivo delle chiamate eliminate. Ad esempio, potrai vedere quando il volume scende o quante chiamate vengono interessate e per quale motivo.


Il report di routing diretto PSTN di CQD include quattro sezioni:

  - [Panoramica di PSTN](#pstn-overview)

  - [Dettagli del servizio](#service-details)

  - [Network Effectiveness Ratio](#network-effectiveness-ratio)

  - [Parametri di rete](#network-parameters)

## <a name="highlights"></a>Highlights

1. Analizzare per tipo di chiamata, SBC, paese chiamante e chiamato

   Il report Routing diretto PSTN di CQD aggrega metriche di affidabilità e utilizzo per tutti gli SBC del tuo tenant per gli ultimi 7, 30 o 180 giorni (6 mesi). È possibile analizzare i dati per tipo di chiamata, SBC, paese chiamante e chiamato. Se si è interessati a un particolare SBC o paese, sarà possibile identificare le variazioni delle tendenze nell'intervallo di tempo selezionato.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report di routing diretto PSTN di CQD":::
   
2. Tenere traccia delle tendenze

    L'analisi delle tendenze è essenziale quando si prova a comprendere l'utilizzo e l'affidabilità dei servizi. Le tendenze orarie offrono un'analisi ravvicinata delle prestazioni giornaliere, che consente di identificare gli incidenti in tempo reale. Le tendenze giornaliere consentono di vedere l'integrità dei servizi da un punto di vista a lungo termine. È importante poter passare da una modalità all'altra con granularità dei dati appropriata. Il report Dirette PSTN di CQD fornisce una panoramica delle tendenze dei 6 mesi, delle tendenze giornaliere di 7 e 30 giorni e delle tendenze orarie per poter analizzare le prestazioni a ogni livello.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report di routing diretto PSTN di CQD":::

3. Drill-through fino a SBC o a livello utente

   In CQD è stata migliorata la funzionalità drill-through per molte categorie di dati, che consente di comprendere rapidamente l'utilizzo o la distribuzione di affidabilità a livello di utente o SBC. Con il drill-through, è possibile risolvere rapidamente i problemi e comprendere il reale impatto degli utenti. Il report di routing diretto PSTN di CQD include il drill-through nelle metriche Service Detail and Network Effectiveness Ratio. Fare clic sul punto dati a cui si è interessati per eseguire il drill-through fino ai dettagli ABC o a livello utente.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot che mostra la funzionalità drill-through in un punto dati":::


## <a name="pstn-overview"></a>Panoramica di PSTN

Il report di routing pstn diretto di CQD fornisce le seguenti informazioni relative all'integrità generale del servizio negli ultimi 180 giorni.
![Screenshot: Report CQD PSTN](media/CQD-PSTN-report1.png)

Ad esempio, se si è interessati all'utilizzo generale e all'integrità di tutte le chiamate in ingresso tramite SBC abc.bca.adatum.biz con US come paese interno:

| **Call Out** | **Descrizione**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Puoi utilizzare i filtri in alto per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com controller di session boarder e US come paese interno. |
| 2            | Tendenza di utilizzo degli ultimi 180 giorni. Il report dei dettagli sull'utilizzo è presente nella pagina Dettagli servizio.                                                                     |
| 3            | Di tendenza Post Dial Delay, Latency, Jitter e Packet Loss degli ultimi 180 giorni. Il report dei dettagli è nella pagina Parametri di rete.                           |
| 4            | Tendenza di chiamate contemporanee e di utenti attivi giornalieri degli ultimi 180 giorni. Questo grafico consente di comprendere il volume massimo del servizio.                            |
| 5            | Il motivo principale del fine chiamata ha interessato la qualità del servizio degli ultimi 180 giorni. I dettagli sull'integrità dei servizi sono nella pagina Network Effective Ratio (NER).                    |

## <a name="service-details"></a>Dettagli del servizio

Questa pagina contiene le tendenze di utilizzo del servizio ogni giorno e la suddivisione del feedback degli utenti in base all'area geografica.

  - **Totale chiamate tentate -** Totale chiamate di tentativo in tale intervallo di tempo, incluse sia le chiamate riuscite che quelle non effettuate

  - **Totale chiamate connesse -** Totale chiamate connesse in tale intervallo di tempo

  - **Totale minuti -** Utilizzo totale dei minuti in tale intervallo di tempo

  - **Utenti attivi giornalieri (DAU) –** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno

  - **Chiamate contemporanee -** Numero massimo di chiamate attive simultanee in un minuto

  - **Commenti e suggerimenti degli utenti** Il punteggio "Valuta la chiamata" proviene dall'utente. 3-5 è considerato una buona chiamata. 1-2 è considerato una chiamata sbagliata.

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report2.png)

Ad esempio:

1.  Se la durata media della chiamata scende a 0 al 14/02/2020, è possibile verificare prima se il volume della chiamata appare normale e verificare se esiste una grande discrepanza tra il totale delle chiamate di connessione e il totale delle chiamate tentate. Vai quindi alla pagina Network Effectiveness Ratio per investire in motivi di insuccesso di chiamata.

2.  Se si nota l'aumento delle aree rosse nella mappa di feedback dell'utente, è possibile passare alla pagina Network Effectiveness Ratio e a Network Parameter per verificare se esistono anomalie e generare un ticket usando MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Network Effectiveness Ratio

Si tratta della stessa metrica visualizzata nel dashboard Integrità generale. Puoi controllare il numero NER orario con i dettagli delle chiamate interessati sia per le indicazioni telefoniche (in entrata/in uscita) che per il rapporto di efficacia della rete oraria e per il motivo finale della chiamata qui sotto.

  - **NER** - La capacità (%) di una rete per recapitare le chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate effettuate a un destinatario.

  - **Codice di risposta SIP:** un codice di risposta intero a tre cifre mostra lo stato della chiamata.

  - **Codice di risposta Microsoft**-A response code sent out from Microsoft component.

  - **Descrizione:** fase del motivo corrispondente al codice di risposta SIP e al codice di risposta Microsoft.

  - **Numero di chiamate interessate:** il numero totale di chiamate interessate dall'intervallo di tempo selezionato.

> ![Screenshot: Report CQD PSTN](media/CQD-PSTN-report3.png)
> 
Ad esempio:

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report4.png)

Se NER giornaliero ha un tuffo il 05/02/2020, è possibile fare clic sulla data e gli altri grafici ingrandiranno alla data specifica.

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report5.png)

Dalla tendenza oraria NER Good Percentage, la dip si verifica intorno alle 21:00. Quindi fai di nuovo clic per ingrandire all'ora 21 e seleziona Dettagli chiamata effettive per vedere quante chiamate non sono state effettuate in quell'ora e quali sono i motivi per cui la chiamata è stata terminare. Se il problema non è correlato a SBC, è possibile iniziare con la risoluzione dei problemi di auto-problema oppure segnalare a Service Desk.

## <a name="network-parameters"></a>Parametri di rete

Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller dei confini della sessione. Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Microsoft Teams e osservare i valori consigliati da Customer Edge a Microsoft Edge.

  - **Instabilità:** misura in millisecondi della variazione del tempo di ritardo di propagazione della rete calcolata tra due endpoint utilizzando RTCP (RtP Control Protocol).

  - **Perdita pacchetti:** misura del pacchetto che non è riuscito ad arrivare; viene calcolata tra due endpoint.

  - **La latenza** - (nota anche come tempo di round trip) è il tempo di invio di un segnale più il tempo necessario per la conferma di ricezione del segnale. Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.

> ![Screenshot: Report CQD PSTN](media/CQD-PSTN-report6.png)

Ad esempio:

Se viene visualizzato un raccoglitore in uno dei quattro grafici (Latenza, Instabilità, Frequenza di perdita pacchetti, Ritardo post chiamata) per una data specifica, ad esempio Latenza il 14/02/2020, fare clic sul punto di data. Inoltre, il grafico di tendenza oraria in basso viene aggiornato in modo da visualizzare il numero orario. È possibile consultare i provider di servizi SBC o alzare un ticket con Service Desk MICROSOFT.

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di CQD per Microsoft Teams](CQD-PSTN-report.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)