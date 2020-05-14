---
title: Uso del report di routing diretto PSTN di Call Quality dashboard
ms.author: lolaj
author: LolaJacobsen
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
description: Usare il report routing diretto PSTN di Call Quality dashboard per monitorare e risolvere i problemi di chiamata PSTN in Microsoft teams.
ms.openlocfilehash: a3a7d84a21858b8cb2039f3f5bb6efde6b9adaaa
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221750"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Uso del report di routing diretto PSTN di Call Quality dashboard

Novità di marzo 2020 è stato aggiunto un report di routing diretto PSTN di Call Quality Dashboard ai modelli di [query di Power bi scaricabili per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


Il report routing diretto PSTN di Call Quality Dashboard (Call Quality dashboard PSTN Direct routing report. PBIT) consente di comprendere i modelli di utilizzo e la qualità dei servizi PSTN. Questo report consente di monitorare l'utilizzo del servizio, le informazioni relative a session border controller (SBC), il servizio di telefonia, i parametri di rete e i dettagli del rapporto di efficacia della rete. Queste informazioni consentono di identificare i problemi, incluso il motivo per cui sono state eliminate le chiamate. Ad esempio, potrai vedere quando il volume scende o il numero di chiamate che vengono influenzate e per quale motivo.


Il report routing diretto PSTN di Call Quality dashboard include quattro sezioni:

  - [Panoramica PSTN](#pstn-overview)

  - [Dettagli del servizio](#service-details)

  - [Rapporto efficacia di rete](#network-effectiveness-ratio)

  - [Parametri di rete](#network-parameters)

## <a name="highlights"></a>Evidenzia

1. Analizzare per tipo di chiamata, SBC, chiamante e paese chiamato

   Il report routing diretto PSTN di Call Quality dashboard aggrega le metriche di affidabilità e utilizzo per tutti i SBCs del tenant per gli ultimi 7, 30 o 180 giorni (6 mesi). È possibile analizzare i dati per tipo di chiamata, SBC, chiamante e paese chiamato. Se si è interessati a un determinato SBC o a un paese, sarà possibile identificare le modifiche nelle tendenze nell'intervallo di tempo selezionato.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report di routing diretto PSTN di Call Quality dashboard":::
   
2. Tenere traccia delle tendenze

    L'analisi delle tendenze è essenziale quando si cerca di comprendere l'uso e l'affidabilità del servizio. Le tendenze orarie consentono di analizzare in modo ravvicinato le prestazioni quotidiane, che consentono di identificare gli incidenti in tempo reale. Le tendenze quotidiane consentono di visualizzare l'integrità del servizio da una prospettiva di lungo periodo. È importante essere in grado di spostarsi tra queste due modalità con la corretta granularità dei dati. Il report routing diretto PSTN di Call Quality dashboard offre una panoramica delle tendenze di 6 mesi, le tendenze quotidiane di 7 e 30 giorni e le tendenze orarie in modo da poter analizzare le prestazioni a ogni livello.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report di routing diretto PSTN di Call Quality dashboard":::

3. Eseguire il drill-through a SBC o a livello utente

   È stata creata una funzionalità di drill-through su molte categorie di dati in Call Quality dashboard, che consente di comprendere rapidamente la distribuzione dell'utilizzo o dell'affidabilità a livello di utente o SBC. Usando drill-through puoi poinpoint rapidamente i problemi e capire l'impatto dell'utente reale. Il report routing diretto PSTN di Call Quality dashboard include le metriche dei dettagli del servizio e della percentuale di efficacia della rete. Fare clic sul punto dati a cui si è interessati per eseguire il drill-up a SBC o a livello di utente.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Schermata che mostra la funzionalità di drill-through in un punto dati":::


## <a name="pstn-overview"></a>Panoramica PSTN

Il report routing diretto PSTN di Call Quality dashboard fornisce le informazioni seguenti relative all'integrità complessiva del servizio per gli ultimi 180 giorni.
![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report1.png)

Ad esempio, se si è interessati all'uso e all'integrità generali di tutte le chiamate in ingresso che attraversano SBC abc.bca.adatum.biz con noi come paese interno:

| **Chiamata fuori** | **Descrizione**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | È possibile usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come controller di bordo sessione e Stati Uniti come paese interno. |
| 2            | Tendenza all'uso degli ultimi 180 giorni. È possibile trovare report dettagli utilizzo nella pagina Dettagli servizio.                                                                     |
| 3            | Ritardo di post-chiamata, latenza, jitter e tendenza alla perdita di pacchetti per gli ultimi 180 giorni. È possibile trovare report dettagli nella pagina parametri di rete.                           |
| 4            | Chiamata simultanea e tendenza utente attiva giornaliera per gli ultimi 180 giorni. Questo grafico può aiutare a comprendere il volume massimo del servizio.                            |
| 5            | La qualità del servizio in primo piano è stata interessata per gli ultimi 180 giorni. È possibile trovare informazioni dettagliate sull'integrità dei servizi nella pagina NER (Network effective ratio).                    |

## <a name="service-details"></a>Dettagli del servizio

Questa pagina fornisce le tendenze di utilizzo del servizio al giorno e la ripartizione dei feedback degli utenti per geografica.

  - **Totale chiamate di tentativo-** Totale tentativo chiamate in tale intervallo di tempo, incluse le chiamate successo e non riuscito

  - **Totale chiamate connesse-** Totale chiamate connesse nell'intervallo di tempo

  - **Minuti totali-** Utilizzo totale dei minuti nell'intervallo di tempo

  - **Utenti attivi giornalieri (DAU)-** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno

  - **Chiamate simultanee:** Numero massimo di chiamate attive simultanee in un minuto

  - **Feedback degli utenti:** Il Punteggio "Vota la mia chiamata" proviene dall'utente. 3-5 è considerato una buona chiamata. 1-2 viene considerato come una chiamata errata.

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report2.png)

Ad esempio:

1.  Se viene visualizzata la durata media delle chiamate scende a 0 in 02/14/2020, è possibile verificare se il volume delle chiamate è normale e verificare se esiste una grande discrepanza tra le chiamate di connessione totale e il tentativo totale. Quindi Vai alla pagina rapporto efficacia Network per investire sui motivi di errore di chiamata.

2.  Se nella mappa di feedback degli utenti viene visualizzato un numero crescente di punti rossi, è possibile accedere alla pagina rapporto di efficacia della rete e al parametro di rete per verificare se sono presenti anomalie e si può alzare un biglietto usando il servizio di assistenza MS.

## <a name="network-effectiveness-ratio"></a>Rapporto efficacia di rete

Questa è la stessa metrica visualizzata nel dashboard integrità generale. È possibile controllare il numero di NER ogni ora con le chiamate interessate in dettaglio per entrambe le direzioni delle chiamate (in ingresso/in uscita) nel rapporto oraria di efficacia della rete e nel grafico motivo finale chiamata seguente.

  - **Ner** -l'abilità (%) di una rete per consegnare le chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.

  - **Codice di risposta SIP**: il codice di risposta intero a tre cifre Mostra lo stato della chiamata.

  - **Codice di risposta Microsoft**-codice di risposta inviato dal componente Microsoft.

  - **Descrizione** : la fase di Reason che corrisponde al codice di risposta SIP e al codice di risposta Microsoft.

  - **Numero di chiamate interessate** : il numero totale di chiamate è stato influenzato durante l'intervallo di tempo selezionato.

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report3.png)
> 
Ad esempio:

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report4.png)

Se il Daily NER ha un dip in 02/05/2020, è possibile fare clic sulla data e gli altri grafici faranno zoom su quella specifica data.

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report5.png)

Dalla buona percentuale di tendenza per ogni ora è possibile trovare il DIP che si verifica intorno a 21:00. Quindi fare di nuovo clic per ingrandire l'ora 21 e controllare i dettagli delle chiamate effettuate per vedere quante chiamate non sono state eseguite in quell'ora e quali sono i motivi per le chiamate finali. Se il problema non è correlato a SBC, è possibile iniziare a eseguire le riprese in caso di problemi su qualsiasi problema o report SBC.

## <a name="network-parameters"></a>Parametri di rete

Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller di bordo della sessione. Per informazioni sui valori consigliati, vedere [preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md)e esaminare i valori consigliati di Microsoft Edge per il cliente.

  - **Jitter** : è la misura di millisecondi di variazione nel tempo di ritardo di propagazione della rete calcolato tra due endpoint usando RTCP (il protocollo di controllo RTP).

  - **Perdita di pacchetti** : è una misura del pacchetto che non è riuscita ad arrivare; viene calcolato tra due endpoint.

  - **Latenza** -(nota anche come tempo di andata e ritorno) è il periodo di tempo necessario per l'invio di un segnale più il tempo necessario per il riconoscimento del segnale da ricevere. Questo ritardo temporale è costituito dai tempi di propagazione tra i due punti di un segnale.

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report6.png)

Ad esempio:

Se viene visualizzato un picco su uno dei quattro grafici (latenza, jitter, tasso di perdita del pacchetto, ritardo della chiamata) per una data specifica, ad esempio la latenza in 02/14/2020, fare clic sul punto di data. E il grafico di tendenza oraria in fondo verrà aggiornato per visualizzare il numero orario. È possibile controllare il SBCs o sollevare un biglietto con il servizio di assistenza MS Service Desk.

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams](CQD-PSTN-report.md)