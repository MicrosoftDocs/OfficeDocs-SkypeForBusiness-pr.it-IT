---
title: Uso del report CQD PSTN Direct Routing
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
ms.localizationpriority: medium
description: Usare il report Microsoft Teams Routing diretto PSTN (Call Quality Dashboard) per monitorare e risolvere i problemi relativi alle chiamate PSTN in Microsoft Teams.
ms.openlocfilehash: ae36ff214de2142b74b8493e925e25f32572709c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726425"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Uso del report CQD PSTN Direct Routing

A marzo 2020 è stato aggiunto un report Microsoft Teams Call Quality Dashboard (CQD) PstN Direct Routing ai modelli di query di Power BI scaricabili per [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) 


Il report CQD PSTN Direct Routing Report (CQD PSTN Direct Routing Report.pbit) consente di comprendere i modelli di utilizzo e la qualità dei servizi PSTN. Usare questo report per monitorare l'utilizzo del servizio, informazioni sul session border controller (SBC), sul servizio di telefonia, sui parametri di rete e sui dettagli sul rapporto di efficacia della rete. Queste informazioni consentono di identificare i problemi, incluso il motivo per cui le chiamate sono in uscita. Ad esempio, potrai vedere quando il volume scende o quante chiamate vengono interessate e per quale motivo.


Il report di routing diretto PSTN CQD include quattro sezioni:

  - [Panoramica di PSTN](#pstn-overview)

  - [Dettagli servizio](#service-details)

  - [Rapporto di efficacia della rete](#network-effectiveness-ratio)

  - [Parametri di rete](#network-parameters)

## <a name="highlights"></a>Highlights

1. Analizza per tipo di chiamata, SBC, paese chiamante e chiamato

   Il report CQD PSTN Direct Routing aggrega le metriche di affidabilità e utilizzo per tutti gli SBC nel tenant per gli ultimi 7, 30 o 180 giorni (6 mesi). È possibile analizzare i dati per tipo di chiamata, SBC, paese chiamante e chiamato. Se si è interessati a un determinato SBC o paese, sarà possibile identificare le modifiche alle tendenze nell'intervallo di tempo selezionato.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report CQD PSTN Direct Routing.":::
   
2. Tenere traccia delle tendenze

    L'analisi delle tendenze è essenziale quando si cerca di comprendere l'utilizzo e l'affidabilità dei servizi. Le tendenze orarie offrono un'analisi ravvicinata delle prestazioni quotidiane, che consente di identificare gli incidenti in tempo reale. Le tendenze quotidiane consentono di vedere l'integrità dei servizi da una prospettiva a lungo termine. È importante poter passare da una modalità all'altra con una granularità dei dati appropriata. Il report CQD PSTN Direct Routing fornisce una panoramica delle tendenze di 6 mesi, tendenze giornaliere di 7 e 30 giorni e tendenze orarie per poter analizzare le prestazioni a ogni livello.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report CQD PSTN Direct Routing.":::

3. Drill-through fino a SBC o a livello utente

   Abbiamo creato funzionalità di drill-through su molte categorie di dati in CQD, che consente di comprendere rapidamente l'utilizzo o la distribuzione dell'affidabilità a livello di SBC o utente. Usando il drill-through, è possibile individuare rapidamente i problemi e comprendere l'impatto reale degli utenti. Il report CQD PSTN Direct Routing include funzionalità di drill-through nelle metriche Service Detail e Network Effectiveness Ratio. Fare clic sul punto dati a cui si è interessati per eseguire il drill-through fino ai dettagli ABC o a livello di utente.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot che mostra la funzionalità drill-through in un punto dati.":::


## <a name="pstn-overview"></a>Panoramica di PSTN

Il report di routing diretto PSTN CQD fornisce le informazioni seguenti relative all'integrità generale del servizio per gli ultimi 180 giorni.
![Screenshot: report CQD PSTN.](media/CQD-PSTN-report1.png)

Ad esempio, se si è interessati all'utilizzo generale e all'integrità di tutte le chiamate in ingresso che attraversano SBC abc.bca.adatum.biz stati uniti come paese interno:

| **Call Out** | **Descrizione**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | È possibile usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come session boarder controller e US come paese interno. |
| 2            | Tendenza di utilizzo degli ultimi 180 giorni. Il report dei dettagli sull'utilizzo è presente nella pagina Dettagli servizio.                                                                     |
| 3            | Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days. Il report dei dettagli è presente nella pagina Parametri di rete.                           |
| 4            | Tendenza delle chiamate simultanee e degli utenti attivi giornalieri degli ultimi 180 giorni. Questo grafico consente di comprendere il volume massimo del servizio.                            |
| 5            | Il motivo principale di fine chiamata ha interessato la qualità del servizio degli ultimi 180 giorni. I dettagli sull'integrità dei servizi sono nella pagina Network Effective Ratio(NER).                    |

## <a name="service-details"></a>Dettagli servizio

Questa pagina fornisce le tendenze di utilizzo dei servizi al giorno e la suddivisione del feedback degli utenti in base all'area geografica.

  - **Totale chiamate di tentativo -** Numero totale di chiamate di tentativo nell'intervallo di tempo specificato, incluse sia le chiamate riuscite che quelle non riuscite

  - **Totale chiamate connesse -** Totale chiamate connesse in tale intervallo di tempo

  - **Totale minuti :** Utilizzo totale dei minuti in tale intervallo di tempo

  - **Utenti attivi giornalieri (DAU) –** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno

  - **Chiamate simultanee :** Numero massimo di chiamate attive simultanee in un minuto

  - **Feedback degli utenti :** Il punteggio "Valuta la mia chiamata" proviene dall'utente. 3-5 è considerato una buona chiamata. 1-2 è considerato una chiamata non disponibile.

![Screenshot: report CQD PSTN.](media/CQD-PSTN-report2.png)

Ad esempio:

1.  Se la durata media delle chiamate scende a 0 al 14/02/2020, è prima di tutto possibile verificare se il volume della chiamata sembra normale e verificare se esiste una grande discrepanza tra le chiamate di connessione totali e le chiamate di tentativo totali. Passare quindi alla pagina Network Effectiveness Ratio per investire per motivi di errore di chiamata.

2.  Se nella mappa dei feedback degli utenti sono presenti punti rossi crescenti, è possibile passare alla pagina Network Effectiveness Ratio e a Network Parameter per vedere se ci sono anomalie e si potrebbe generare un ticket usando MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Rapporto di efficacia della rete

Si tratta della stessa metrica visualizzata nel dashboard Integrità generale. È possibile controllare il numero NER orario con i dettagli delle chiamate interessate per entrambe le direzioni di chiamata (in ingresso/uscita) nel grafico rapporto di efficacia della rete oraria e motivo finale della chiamata riportato di seguito.

  - **NER** - La possibilità (%) di una rete di effettuare chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.

  - **Codice di risposta SIP:** un codice di risposta intero a tre cifre mostra lo stato della chiamata.

  - **Codice di risposta Microsoft**- Codice di risposta inviato dal componente Microsoft.

  - **Descrizione:** fase del motivo corrispondente al codice di risposta SIP e al codice di risposta Microsoft.

  - **Numero di chiamate interessate:** il numero totale di chiamate interessate durante l'intervallo di tempo selezionato.

> ![Screenshot: report CQD PSTN.](media/CQD-PSTN-report3.png)
> 
Ad esempio:

![Screenshot: report CQD PSTN.](media/CQD-PSTN-report4.png)

Se NER giornaliero ha un tuffo il 05/02/2020, è possibile fare clic sulla data e gli altri grafici ingrandiranno la data specifica.

![Screenshot: report CQD PSTN.](media/CQD-PSTN-report5.png)

Dalla tendenza oraria NER Good Percentage, è possibile trovare che il tuffo si verifica intorno alle 21:00. Quindi fare di nuovo clic per fare zoom sull'ora 21 e selezionare Dettagli chiamata effettive per vedere quante chiamate non sono riuscite in quell'ora e quali sono i motivi di fine della chiamata. È possibile iniziare con la risoluzione dei problemi relativi a SBC o segnalare a Service Desk se il problema non è correlato a SBC.

## <a name="network-parameters"></a>Parametri di rete

Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al session border controller. Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Microsoft Teams e osservare Customer Edge per Microsoft Edge valori consigliati.

  - **Instabilità:** misura in millisecondo della variazione del tempo di ritardo della propagazione della rete calcolata tra due endpoint usando RTCP (RtP Control Protocol).

  - **Perdita di pacchetti:** misura del pacchetto che non è riuscito ad arrivare. viene calcolato tra due endpoint.

  - **Latenza-** (noto anche come tempo di andata e ritorno) è il tempo necessario per l'invio di un segnale più il tempo necessario per la ricezione del riconoscimento del segnale. Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.

> ![Screenshot: report CQD PSTN.](media/CQD-PSTN-report6.png)

Ad esempio:

Se viene visualizzato un picco in uno dei quattro grafici (Latenza, Instabilità, Tasso di perdita pacchetti, Ritardo post chiamata) per una data specifica, ad esempio Latenza il 14/02/2020, fare clic sul punto della data. Il grafico di tendenza oraria nella parte inferiore verrà aggiornato per visualizzare il numero orario. È possibile controllare gli SBC o sollevare un ticket con MS Service Desk.

![Screenshot: report CQD PSTN.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di CQD per Microsoft Teams](CQD-PSTN-report.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)