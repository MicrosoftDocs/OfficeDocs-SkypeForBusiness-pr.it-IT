---
title: Domande frequenti su Call Quality Dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leggere le domande frequenti e le risposte su Call Quality Dashboard (CQD) di Microsoft Teams.
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110259"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Domande frequenti su Call Quality Dashboard (CQD)

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché Call Call Call contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno avuto un'esperienza scarsa?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché viene visualizzata una differenza fino a uno 0,2% di valori relativi al numero di chiamate e di utenti nelle misure e come ottenere volumi più precisi? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché i dati di CQD di Skype for Business sono diversi da quelli di Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Perché non riesco a vedere euii in CQD?](#why-cant-i-see-euii-in-cqd)

[Perché le informazioni di Skype for Business sono visualizzate in CQD quando sono filtrate solo per Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Perché i report personalizzati restituiscono un massimo di 10.000 righe solo se è necessario specificare altre voci?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché Call Call Call contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno avuto un'esperienza scarsa?

Vedere le regole che CQD usa per la [classificazione dei flussi.](stream-classification-in-call-quality-dashboard.md)
 
Per i flussi audio, uno qualsiasi dei 5 classificatori, che vengono calcolati per la media in base alla lunghezza della chiamata, potrebbe rientrare tutti in parametri "validi". Non significa che gli utenti non hanno avuto un audio che ha contribuito a un'uscita audio, statica o problemi. 

Per determinare se si è verificato un problema di rete, esaminare il delta tra i valori medi della sessione e i valori massimi. I valori massimi sono i valori massimi rilevati e riportati durante la sessione.
 
Ecco un esempio di come risolvere questo problema. Supponiamo di avere una traccia di rete durante una chiamata e i primi 20 minuti non ci sono pacchetti persi, ma in seguito si ha uno spazio vuoto di 1,5 secondi di pacchetti e quindi un valore valido per il resto della chiamata. La media sarà pari al <10% (0,1) della perdita di pacchetti anche in un'analisi RTP di Traccia Wireshark. Qual era la perdita massima dei pacchetti? 1,5 secondi in un periodo di 5 secondi è 30% (0,3). Tale problema si è verificata nel cinque secondo periodo di campionamento (forse o potrebbe essere suddiviso nel periodo di campionamento)?
 
Se le metriche di rete sono buone nelle medie e nei valori massimi, cercare altri dati di telemetria: 
- Controllare il rapporto di evento insufficiente della CPU per verificare se le risorse di CPU disponibili erano insufficienti e hanno causato la scarsa qualità. 
- Il dispositivo audio in modalità Half Duplex impediva il feedback dovuto ai microfoni vicini agli altoparlanti? 
- Controllare il rapporto eventi AEC Half Duplex del dispositivo. I problemi del dispositivo o dei problemi del microfono causavano rumore o problemi statici a causa delle gocce dell'audio USB quando collegati a un hub o a un alloggiamento di espansione:  
- Controllare i rapporti di evento glitch del dispositivo e del microfono. Il dispositivo funzionava correttamente?  
- Controllare i rapporti di evento del dispositivo di acquisizione e di rendering non funzionanti.


Per altre informazioni sulle dimensioni e le misure disponibili nella telemetria di Call Quality Dashboard, vedere Dimensioni e [misure disponibili in Call Quality Dashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Per il rumore di fondo, controlla il rapporto dell'audio degli eventi per vedere per quanto tempo i partecipanti hanno disattivato l'audio.
 
Creare report dettagliati in CQD e filtrare in base all'ID riunione per visualizzare tutti gli utenti e i flussi in una riunione e aggiungere i campi a cui si è interessati. Il problema potrebbe non essere stato segnalato da un utente. Stanno solo segnalando l'esperienza.
 
La telemetria non richiama necessariamente il problema, ma consente di comprendere meglio dove esaminare e informare le decisioni. Rete, dispositivo, aggiornamenti del driver o firmware, utilizzo o utente?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Perché viene visualizzata una differenza fino a uno 0,2% di valori relativi al numero di chiamate e di utenti nelle misure e come ottenere volumi più precisi? 
Per calcolare il numero di chiamate e le misure del numero di utenti, viene eseguita un'operazione countif distinta sulla chiamata o gli identificatori utente nel set di dati. Nei set di dati di grandi dimensioni è presente un errore fino a 0,2% implicito nell'operazione countif distinta. Per ottenere il volume più accurato, è consigliabile fare affidamento sulle misure di conteggio dei flussi perché non si basano su questa distinta operazione countif. L'applicazione di filtri per ridurre il volume dei dati può ridurre l'errore, ma non eliminare questa origine di errore in chiamate distinte e conteggi degli utenti. Consulta Dimensioni [e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) per le misure su cui sono influenzate.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Perché i dati di CQD di Skype for Business sono diversi da quelli di Teams? 


> [!IMPORTANT]
> A partire dal 1° luglio 2020, il precedente CQD (CQD.lync.com) usa i dati del CQD più recente. Teams.microsoft.com). I dati di CQD meno recenti non sono più disponibili e non è possibile esportare i dati dell'edificio o del report. È ancora possibile usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for Business), ma presto verrà disattivato l'accesso CQD.lync.com, quindi è consigliabile passare a CQD. Teams.microsoft.com se non è già stato fatto.


Se stai tentando di confrontare i dati tra il precedente CQD del portale legacy di Skype for Business (cqd.lync.com) e il più recente CQD dell'interfaccia di amministrazione di Teams (cqd.teams.microsoft.com), noterai rapidamente che i dati non corrispondono. Questo dipende dal fatto che i report di CQD più recenti su molti scenari di chiamata aggiuntivi. Se usi ancora i report del call quality dashboard precedente, utilizza questo articolo per aiutarti a interpretare questi rapporti: [Call Quality Dashboard per Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non riesco a vedere euii in CQD?

Questi ruoli di amministratore possono accedere a CQD, ma non possono visualizzare le informazioni di identificazione dell'utente finale (EUII):
- Lettore di report di Microsoft 365
- Teams Communications Support Specialist

Per altre informazioni sui ruoli che possono accedere a CQD, inclusa l'UEII, vedere Assegnare ruoli per l'accesso a [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché le informazioni di Skype for Business sono visualizzate in CQD quando sono filtrate solo per Teams?

Quando si filtra per Teams solo nei report di CQD (isTeams = 1), si filtrano tutte le chiamate in cui il *primo endpoint* è Teams. Se il *secondo endpoint* è Skype for Business, queste informazioni verranno visualizzate nel report di CQD.

CQDv2 e CQDv3 avranno sempre conteggi diversi perché CQDv3 avrà nuovi scenari che non saranno supportati da CQDv2. Ecco perché il confronto dei numeri totali di riepilogo o aggregati senza filtri avrà queste differenze previste.  

A seconda dello scenario dei clienti, CQDv3 includerà le chiamate locali SFB 2019 (se SFB 2019 viene utilizzato con un connettore dati), le chiamate Ai Bot di Skype (AA, CVI, VDI), gli eventi live e le chiamate PSTN. Scenari/funzionalità disponibili per i clienti, ma i loro dati non sono in CQD V2.

Ad esempio, si prevede che i clienti vedano 200.000 flussi audio, con 5.000 errori nel report di riepilogo CQD V2; vs 300.000 flussi audio con 5500 errori (provenienti da chiamate in locale 2019, chiamate CVI, chiamate PSTN ecc.) in CQD V3.

Per determinare se esistono differenze impreviste, è necessario esaminare le varie suddivisioni dei dati complessivi.  Confrontare con lo scopo.  L'applicazione della licenza ai dati in base alla coppia di categorie agente utente è una delle prime cose che consigliamo.  *Anche First Product* *e Second Product* sono ottimi filtri dei dati.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Perché i report personalizzati restituiscono un massimo di 10.000 righe solo se è necessario specificare altre voci?

CQD è progettato per query di dati riepilogate e non è progettato per l'esportazione dei dati. Se possibile, è consigliabile modificare i report per evitare di superare il limite di 10.000 righe. Iniziare esaminando gli indicatori KPI usando dimensioni di cardinalità più ampie e inferiori, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down in dimensioni di cardinalità sempre più elevate. Entrambi i report helpdesk e Location-Enhanced offrono ottimi esempi di questo flusso di lavoro drill-down.

## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Usare Call Quality Quality Call per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
