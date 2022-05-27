---
title: Report sull'integrità e sull'utilizzo
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dati del nodo reporting per l'integrità e l'utilizzo dei report
f1keywords: ''
ms.openlocfilehash: f3c8ceec383d801c5992b0e8275cfe5360ef5bfe
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674818"
---
# <a name="health-and-usage-reports"></a>Report sull'integrità e sull'utilizzo

Il nodo di creazione di report contiene i dati relativi all'integrità e all'utilizzo delle chat room gestite Microsoft e delle informazioni dettagliate sui servizi. La **panoramica** mostra le tendenze sanitarie a livello di tenant delle chat room. La scheda **Integrità** visualizza un elenco di sale con i dati sanitari corrispondenti. **L'utilizzo** delle sale in base alle informazioni del calendario e ai dati sulla qualità delle chiamate sono visibili nella scheda Utilizzo.

## <a name="navigating-reports"></a>Spostamento tra i report

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

La sezione panoramica fornisce rappresentazioni grafiche di importanti aspetti della gestione delle sale riunioni. I grafici cambiano a seconda dell'intervallo di tempo selezionato o del gruppo selezionato. Per modificare l'intervallo di tempo, fare clic sul menu a discesa.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

Per modificare il gruppo, fare clic sul menu a discesa di selezione del gruppo nel banner.

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>Biglietti per categoria

La ciambella mostra il totale dei biglietti generati per il periodo di tempo e il gruppo selezionati (l'impostazione predefinita è sette giorni, tutti i gruppi). I ticket sono rappresentati nelle categorie principali: Audio, Schermo, Periferiche, Connettività, Controllo delle versioni e Segnalazione cliente.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

Se l'opzione è selezionata, viene visualizzato un riquadro a comparsa per la visualizzazione dettagliata dei biglietti di tale categoria.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

Nel riquadro a comparsa è possibile filtrare l'elenco dei biglietti in base alla sottocategoria selezionando la rispettiva parte della ciambella. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

Per tornare indietro, fare clic sulla ciambella o fare clic sul percorso di navigazione in alto a sinistra.

Per passare a un ticket specifico in questa visualizzazione elenco, fai clic sul link sotto la **colonna Ticket di supporto**.

### <a name="ticket-history"></a>Cronologia dei biglietti

Il grafico della cronologia dei ticket mostra un confronto degli eventi assegnati a te o a Microsoft nel periodo di tempo specificato.

> [!NOTE]
> Se un biglietto cambia proprietario in un giorno, chi è il proprietario dell'attività per la maggior parte di quel giorno avrà il biglietto conteggiato nei loro confronti. Ad esempio, se si assegna il ticket a Microsoft all'inizio della giornata, il ticket viene conteggiato per **Assegnato a Microsoft** per il giorno.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>Cronologia della salute

Questo grafico mostra l'integrità media (definizione nella sezione Integrità) per tutte le chat room nel tenant e la salute media di tutti i clienti MMR giorno per giorno. È possibile visualizzare la salute media per un massimo di 90 giorni.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>Camere più affidabili/meno affidabili

Due tabelle mostrano le stanze più affidabili e meno affidabili in base all'integrità. Per la visualizzazione elenco completo, selezionare Integrità, quindi ordinare l'elenco in base alla colonna Integrità.

### <a name="rooms-history"></a>Cronologia delle camere

Fornisce una visualizzazione cronologica delle chat room registrate nel servizio e fornisce una visualizzazione comparata delle chat room che erano integro o non monitorato nello stesso periodo di tempo.

## <a name="health"></a>Salute

Per passare al report di integrità per tutte le sale, selezionare Report, quindi selezionare  **Integrità**.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

Il punteggio di integrità è una metrica progettata per surface room che più probabilmente causano frustrazione da parte dell'utente finale. Una stanza può essere sana o malsana per un determinato giorno. È considerato malsano se un biglietto o molti biglietti hanno influito sulla stanza per più di 20 minuti totali durante gli orari di non manutenzione (5:00 -21:00 ora locale della macchina). Ad esempio, se un ticket viene aperto alle 5:00 ma chiuso alle 5:15, la stanza è ancora considerata sana. Tuttavia, se si verificasse un secondo biglietto dalle 09:00 alle 9:10, la stanza sarebbe considerata non sana per il giorno. Analogamente, se un ticket si verificava dalle 5:00 alle 5:21, è considerato non integro per il giorno.

> [!NOTE]
> L'integrità del giorno viene aggregata una volta al giorno alle 12:00 ORA UTC. Per i clienti in prossimità della riga della data internazionale, l'aggregazione dell'integrità può verificarsi verso la metà della giornata lavorativa.

> [!NOTE]
> Le chat room onboarding sono nascoste per l'elenco delle chat room nella scheda Integrità e non vengono conteggiate per l'integrità media del tenant.

Facendo clic su una chat room elencata in questa visualizzazione vengono visualizzati altri dettagli.

Il grafico a barre mostra il numero di biglietti per ogni giorno. I biglietti aperti in quel rispettivo giorno vengono visualizzati in blu. I biglietti aperti prima del rispettivo giorno appaiono in arancione. Facendo clic su un giorno sul grafico, il grafico filtra il grafico a torta e la tabella in base ai biglietti pertinenti. Per invertire il filtro, spostarsi con il percorso di navigazione o fare clic sul grafico.

La categorizzazione dei biglietti è rappresentata nel grafico delle ciambelle. L'interazione con questa opzione filtra il grafico della sequenza temporale e la tabella. Per invertire il filtro, spostarsi con il percorso di navigazione o fare clic sul grafico.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

La visualizzazione dell'impatto della riunione mostra le riunioni pianificate durante le quali era aperto un ticket con gravità "Importante" o "Critico". Lo scopo di questa visione è fornire un'approssimazione delle riunioni in cui i partecipanti potrebbero aver riscontrato problemi.

La visualizzazione dell'impatto della riunione mostra le riunioni pianificate durante le quali era aperto un ticket con gravità "Importante" o "Critico". Lo scopo di questa visione è fornire un'approssimazione delle riunioni in cui i partecipanti potrebbero aver riscontrato problemi.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

La scheda Impostazioni visualizza i metadati della sala, ad esempio le informazioni sull'hardware, le impostazioni del dispositivo, le informazioni sul BIOS, le impostazioni dell'app e la posizione.

## <a name="usage"></a>Utilizzo

Per visualizzare il report Utilizzo per tutte le chat room, selezionare **Report->Utilizzo**.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

I titoli forniscono alcuni dati analitici:

- Totale chat room nel tenant
- Quanti non hanno riunioni prenotate, offline o online
- Percentuale di utilizzo delle chat room nel tenant
- Numero totale di riunioni prenotate tramite scambio
- Percentuale di riunioni prenotate che includevano un collegamento Skype o Teams
- Totale chiamate con partecipazione in chat room
- Aggregate call performance score from all calls classified with "Good" quality to all calls. 

Sotto le metriche del titolo c'è una tabella di sale con metriche corrispondenti. Selezionare una sala per visualizzare altri dettagli sull'utilizzo. Le metriche nella tabella sono descritte nella tabella seguente.

|Colonna|Descrizione|
|---|---|
|Utilizzo|Percentuale di tempo in cui la camera è stata prenotata durante l'orario di ufficio nel periodo selezionato. Ad esempio, Periodo di tempo impostato su 7 giorni. Utilizzo dell'80% dei mezzi la camera è stata prenotata per 32/40 ore|
|Prenotato online|Delle riunioni prenotate, la percentuale delle quali è stata abilitata con Teams. Ad esempio, Sono state prenotate 10 riunioni. Di questo, 8 aveva un collegamento Teams. Prenotato online = 80%|
|Riunioni pianificate|Numero assoluto di riunioni pianificate nella sala|
|Totale chiamate|Numero assoluto di chiamate con la chat room come partecipante.|
Prestazioni delle chiamate|Percentuale di chiamate con valutazione "Buona". Ogni chiamata viene valutata e riceve una valutazione Buona, Scarsa, Sconosciuta. Questa metrica viene calcolata da Chiamate buone/Chiamate totali|

L'utilizzo viene calcolato alla fine di ogni giorno a mezzanotte (00:00) ora locale del dispositivo della sala riunioni. L'utilizzo viene calcolato in base all'orario totale prenotato per la riunione per tale giorno diviso per 8 ore.

## <a name="usage-details-of-a-room"></a>Dettagli di utilizzo di una chat room

Se si fa clic su una sala nella visualizzazione elenco, viene visualizzato un riquadro a comparsa con informazioni più approfondite. Nella scheda Utilizzo del riquadro a comparsa è presente un grafico che mostra le ore di utilizzo degli ultimi cinque giorni lavorativi. Per ogni giorno ci sono due barre: blu rappresenta l'orario della riunione prenotato; viola rappresenta l'ora pianificata delle riunioni abilitate per Teams/Skype. Nella parte inferiore vengono calcolati la durata media delle prenotazioni e delle riunioni degli ultimi cinque giorni lavorativi.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

La tabella **Chiamate** mostra le riunioni in cui la sala ha partecipato a una chiamata Teams. La qualità audio della sala viene valutata solo per la chat room, non per tutti i partecipanti. Per visualizzare la qualità della chiamata per tutti i partecipanti di una chiamata specifica, selezionare una chiamata facendo clic sull'ora di inizio.

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

Per visualizzare i dettagli del flusso per il club, fare clic sull'ora di inizio della sessione.
