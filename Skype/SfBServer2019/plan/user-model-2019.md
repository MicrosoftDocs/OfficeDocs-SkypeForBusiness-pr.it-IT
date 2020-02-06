---
title: Pianificazione della capacità per Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: Gli argomenti di questa sezione consentono di capire come pianificare e distribuire Skype for Business Server in modo che sia possibile pianificare adeguatamente il numero di utenti dell'organizzazione e pianificare il carico del server che le proprie attività generano.
ms.openlocfilehash: 15f59d2052a4d73f6e1b1c09b10525b503958fea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824030"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Pianificazione della capacità per Skype for Business Server 2019

Questo articolo fornisce indicazioni su quanti server sono necessari in un sito per il numero di utenti in tale sito, in base all'uso descritto in [modelli utente in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

Abbiamo eseguito i test delle prestazioni sull'hardware descritto nella tabella seguente. Tutte le raccomandazioni e i risultati sono basati su questo hardware. Se si decide di provare a usare hardware meno potente rispetto a quanto indicato in questo articolo, tenere presente che è possibile che si verifichino problemi di funzionalità o prestazioni scadenti.

**Hardware usato nei test delle prestazioni**

|**Componente hardware**|**Consigliato**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o versioni successive.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |SIA  <br/> • 8 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (due dischi che usano RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • SSD (Solid State Drive) in grado di assicurare lo stesso spazio libero e prestazioni simili alle unità disco meccaniche di 8 10000 RPM.  <br/> |
|Rete  <br/> |1 adattatore di rete a doppia porta, 1 Gbps o superiore (2 schede di rete possono essere usate, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multihomed **non** sono supportate per i server front-end, i server back-end e i server Standard Edition. <br/> Purché non siano esposti al sistema operativo e vengano usati per monitorare e gestire l'hardware del server, è possibile avere sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multihomed ed è supportato.  <br/> |

## <a name="summary-of-results"></a>Riepilogo dei risultati

La tabella seguente riepiloga le nostre raccomandazioni.

|**Ruolo del server**|**Numero massimo di utenti supportati**|
|:-----|:-----|
|Pool Front-end con sedici server front-end e back end server o una coppia di server back-end con SQL sempre attiva per una disponibilità elevata.  <br/> |106.000 utenti univoci collegati contemporaneamente, più 50% più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 210.000 endpoint.  <br/> |
|Servizi di conferenza A/V  <br/> |Il servizio di conferenza A/V fornito da un pool di front-end supporta le conferenze del pool che presuppongono una dimensione massima per la conferenza di 250 utenti e una sola Conferenza di grandi dimensioni in esecuzione alla volta.  <br/> **Nota:** È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front-end separato con due server front-end per ospitare le conferenze di grandi dimensioni. Per informazioni dettagliate, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Un server perimetrale  <br/> |18.000 utenti remoti concorrenti.  <br/> |
|Un amministratore  <br/> |18.000 utenti remoti concorrenti.  <br/> |
|Monitoraggio e archiviazione  <br/> |I servizi front end di monitoraggio e archiviazione vengono eseguiti in ogni server front-end, anziché in ruoli server distinti.  <br/> Il monitoraggio e l'archiviazione di ognuno richiede ancora i propri archivi di database. Se si esegue anche Exchange 2013 o versione successiva, è possibile conservare i dati di archiviazione in Exchange, anziché in un database SQL dedicato.  <br/> |
|Un Mediation Server  <br/> |Mediation Server collocato con Front End Server viene eseguito in tutti i server front-end di un pool e dovrebbe avere sufficiente capacità per gli utenti nel pool. Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.  <br/> |
|Un server Standard Edition  <br/> |Se si usano server standard per ospitare gli utenti, è consigliabile usare sempre due server, abbinati con i suggerimenti [per la pianificazione della disponibilità elevata e il ripristino di emergenza](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server non riesce, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.  <br/>  Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono avere più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere più server standard o passare a Skype for Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Server front-end

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

In un pool Front-End è necessario disporre di un server front-end per ogni utente di 6.660 ospitato nel pool, presupponendo che l'Hyper-Threading sia abilitato in tutti i server del pool, che si stia usando SQL Server Express Edition e che l'hardware del server soddisfi le raccomandazioni dei [requisiti del server per Skype for Business Server 2019](system-requirements.md). Il numero massimo di utenti in un pool Front-End è 106.000, sempre supponendo che l'Hyper-Threading sia abilitato e SQL Server Express Edition venga usato in tutti i server del pool. Se si hanno più di 106.000 utenti in un sito, è possibile distribuire più di un pool Front-end.

Quando si tiene conto del numero di utenti in un pool Front-End, includere eventuali utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a questo pool Front-end.

Quando un server attivo non è disponibile, le connessioni vengono trasferite automaticamente agli altri server del pool. In uno scenario in cui si hanno 30.000 utenti e cinque server front-end, se un server non è disponibile, le connessioni di 6000 degli utenti devono essere trasferite agli altri quattro server rimanenti. Questi quattro server rimanenti avranno quindi ognuno gli utenti di 7500, che è un numero più grande di quello raccomandato.

Se invece si è iniziato con sei server front-end per gli utenti di 30.000 e uno diventa non disponibile, per un totale di 5000 gli utenti devono essere spostati sui cinque server rimanenti. Questi cinque server rimanenti verranno quindi tutti gli utenti di 6000 host, che si trova nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front-End è 106.000. Il numero massimo di server front-end in un pool è 16.

Per un pool Front-end con gli utenti di 80.000, 16 server front-end saranno un bene per le prestazioni, in distribuzioni tipiche che seguono i [modelli di utenti in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Le distribuzioni progettate per supportare il failover del ripristino di emergenza presuppongono che un massimo di 53.000 utenti possano essere ospitati in ognuno dei due pool Front-End associati, in cui ogni pool ha sufficienti server front-end per contenere gli utenti in entrambi i pool, in caso di un pool deve essere fallito su t o l'altra.

Il numero di utenti supportati con prestazioni ottimali per un determinato pool Front-end può essere diverso da questi numeri per i motivi seguenti:

- L'hardware per i server front-end non soddisfa le raccomandazioni.
- Anziché usare SQL Server Express Edition, è possibile usare un'altra versione di SQL Server, che potrebbe essere in grado di ospitare altri utenti in ogni pool Front-end.
- L'utilizzo dell'organizzazione è molto diverso rispetto ai modelli utente, ad esempio se si dispone di un traffico di conferenza molto più elevato.

La tabella seguente mostra la larghezza di banda media per la messaggistica istantanea e la presenza, dato il modello utente, come definito nei [modelli utente in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Larghezza di banda media per utente**|**Requisiti di larghezza di banda per server front-end con utenti di 6.660**|
|:-----|:-----|
|3-3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Per migliorare le prestazioni multimediali della funzionalità di conferenza A/V Conferencing e Mediation Server co-ubicata nei server front-end, è necessario abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei server front-end. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere [ricezione di proporzioni secondarie (RSS) nella documentazione di Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Per informazioni dettagliate su come abilitare l'RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="conferencing-maximums"></a>Massimali per le conferenze

Considerato il modello utente in cui il 5% degli utenti di un pool può partecipare a una conferenza in qualsiasi momento, un pool di utenti di 106.000 potrebbe avere circa 5.300 utenti in conferenze contemporaneamente. Queste conferenze dovrebbero essere una combinazione di elementi multimediali (alcuni messaggi istantanei, alcuni messaggi istantanei con audio, alcuni audio/video, ad esempio) e il numero di partecipanti. Non esiste un limite fisso per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive. Ad esempio, se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end o A/V Conferencing Server rispetto ai suggerimenti presenti in questo articolo. Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli di utenti in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

Le dimensioni massime supportate per le conferenze ospitate da un normale pool Front-End di Skype for Business Server che ospita anche gli utenti sono 250 partecipanti. Mentre è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che un totale del 5% degli utenti del pool si trovi in conferenze simultanee. Ad esempio, in un pool di 16 server front-end e utenti di 106.000, mentre la conferenza di 250 utenti sta accadendo, Skype for Business Server supporta 5.050 altri utenti che partecipano a conferenze più piccole.

Indipendentemente dal numero di utenti ospitati nel pool Front-end o in un server Standard Edition, Skype for Business Server supporta almeno 125 altri utenti che partecipano a conferenze più piccole nello stesso pool o server in cui è in uso una conferenza di 250 utenti.

Per abilitare le conferenze che hanno tra gli utenti di 250 e 1000, è possibile configurare un pool Front-end separato solo per ospitare tali conferenze. Questo pool Front-end non ospita gli utenti. Per informazioni dettagliate, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end rispetto a quanto raccomandato in questo documento (fino a un massimo di 16 server front-end). Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli di utenti in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Edge Server

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

Devi distribuire un server perimetrale per ogni utente remoto di 18.000 che accede simultaneamente a un sito. È consigliabile almeno due server Edge per una disponibilità elevata. Questi suggerimenti presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando si tiene conto del numero di utenti per gli Edge Server, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.

> [!NOTE]
> Per migliorare le prestazioni del servizio A/V Conferencing Edge in un server perimetrale, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete degli Edge Server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, selezionare [RSS (Receive Side Scaling) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731). Per informazioni dettagliate su come abilitare l'RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="director"></a>Director

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

Se si distribuisce il ruolo del server Director, è consigliabile distribuire un amministratore per ogni utente remoto di 18.000 che accede simultaneamente a un sito. Consigliamo almeno due direttori per una disponibilità elevata. Questi suggerimenti presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando si tiene conto del numero di utenti per gli amministratori, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.

## <a name="mediation-server"></a>Mediation Server

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i server front-end del pool e deve avere sufficiente capacità per gli utenti del pool.

Se si distribuisce un pool di Mediation Server autonomo, il numero di server di mediazione da distribuire dipende da molti fattori, tra cui l'hardware usato per Mediation Server, il numero di utenti VoIP che si ha, la quantità di peer del gateway che ogni pool di Mediation Server controlli, il traffico ora occupato attraverso i gateway e la percentuale di chiamate con elementi multimediali che ignorano il Mediation Server.

Le tabelle seguenti includono una linea guida per il numero di chiamate simultanee che possono essere gestite da un Mediation Server, presupponendo che l'hardware per i server di mediazione soddisfi i requisiti nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) e che l'Hyper-Threading sia abilitato. Per informazioni dettagliate sulla scalabilità di Mediation Server, vedere [stima dell'uso delle voci e del traffico per Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) e [linee guida per la distribuzione di Mediation Server in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Tutte le tabelle seguenti presuppongono l'utilizzo come riepilogato nei [modelli utente in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacità di mediazione del server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non bypass (transcodifica multimediale eseguita da Mediation Server)**

|**Hardware del server**|**Numero massimo di chiamate**|**Numero massimo di righe T1**|**Numero massimo di righe E1**|
|:-----|:-----|:-----|:-----|
|Processori Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o versioni successive **con Hyper-Threading disabilitato**, con memoria di 64 GB e una scheda di rete a doppia porta.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o versioni successive, con 64 GB di memoria e una scheda di rete a doppia porta.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Anche se i server con 64 GB di memoria sono stati usati per il test delle prestazioni, i server con 32 GB di memoria sono supportati per Mediation Server autonomo e sono sufficienti per dare le prestazioni illustrate in questa tabella.

**Capacità Mediation Server (Mediation Server con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non bypass (elaborazione multimediale eseguita da Mediation Server)**

|**Hardware del server**|**Numero massimo di chiamate**|
|:-----|:-----|
|Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o versioni successive, con 64 GB di memoria e 2 schede di rete da 1GB.  <br/> |200  <br/> |

> [!NOTE]
> Questo numero è molto più piccolo dei numeri per il Mediation Server autonomo. Questo perché il server front-end deve gestire altre funzionalità e funzioni per gli utenti di 6600 ospitati, oltre alla transcodifica necessaria per le chiamate vocali.

> [!NOTE]
> Per migliorare le prestazioni del Mediation Server, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei media server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "[adattamento sul lato ricezione in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Per informazioni dettagliate su come abilitare l'RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="back-end-server"></a>Server back-end

Anche se gran parte delle informazioni sul database viene archiviata principalmente nei server front-end, è necessario assicurarsi che i server back-end soddisfino le raccomandazioni hardware elencate in precedenza in questa sezione e nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Per ottenere una disponibilità elevata del server back-end, è consigliabile distribuire gruppi di disponibilità AlwaysOn o mirroring del server. Per altre informazioni, vedi la [disponibilità elevata del server back-end in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

Se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei server front-end, il monitoraggio e l'archiviazione di ogni uso di un proprio archivio database, separato dallo Store back-end. In alternativa, se è stato distribuito Exchange 2013, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

La tabella seguente indica approssimativamente la quantità di spazio di archiviazione del database necessaria per ogni utente per giorno per il monitoraggio e l'archiviazione dei dati.

||**CDR (monitoraggio)** <br/> |**QoE (monitoraggio)** <br/> |**Archiviazione** <br/> |
|:-----|:-----|:-----|:-----|
|Spazio su disco richiesto per ogni utente per giorno  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft ha usato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il test delle prestazioni. Il test ha raccolto i dati di due pool Front-End, ognuno dei quali conteneva gli utenti di 80.000.

**Hardware usato per il monitoraggio e l'archiviazione del test delle prestazioni**

|**Componente hardware**|**Consigliato**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o versioni successive.  <br/> |
|Memoria  <br/> |48 GB  <br/> |
|Disco  <br/> | SIA<br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione di 2x RAID 1). <br/>OPPURE <br/>• SSD (Solid State Drive) in grado di assicurare lo stesso spazio libero e prestazioni simili alle unità disco meccaniche di 4 10000 RPM.   <br/> |
|Rete  <br/> | 1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> |

**Configurazioni disco consigliate**

|**Unità** <br/> |**Configurazione RAID** <br/> |**Numero di dischi** <br/> |
|:-----|:-----|:-----|
|CDR, QoE e archiviazione dei file di dati del database in un'unica unità  <br/> |1 + 0  <br/> |16  <br/> |
|File di log del database CDR  <br/> |1  <br/> |2  <br/> |
|File di log del database QoE  <br/> |1  <br/> |2  <br/> |
|File di log del database di archiviazione  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacità del server di interoperabilità video

Se si distribuisce video Interop server ed è necessario determinare la capacità, si esamina il numero massimo di sistemi di videoconferenza (VTCs) che saranno in chiamate simultanee. Ad esempio, se si ha 250 VTCs nell'organizzazione e il modello di utente stima che al massimo, il 20% di essi potrebbe essere in chiamate simultanee, si basa la pianificazione della capacità in 50 concorrenti VTCs.

