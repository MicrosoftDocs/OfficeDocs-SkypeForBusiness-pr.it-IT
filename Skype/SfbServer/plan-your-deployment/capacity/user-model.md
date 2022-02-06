---
title: Utilizzo del modello utente per la pianificazione della capacità per Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: 'In questo articolo vengono fornite indicazioni sul numero di server necessari in un sito per il numero di utenti in tale sito, in base all''utilizzo descritto in Modelli utente in Skype for Business Server.'
---

# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Utilizzo del modello utente per la pianificazione della capacità per Skype for Business Server

In questo articolo vengono fornite indicazioni sul numero di server necessari in un sito per il numero di utenti in tale sito, in base all'utilizzo descritto [in Modelli utente in Skype for Business Server](user-models.md).

> [!NOTE]
> Tutti i suggerimenti in questo articolo presuppongono che sia stato installato Skype for Business aggiornamento cumulativo, novembre 2015 o versione successiva nei server.

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

Abbiamo eseguito i test delle prestazioni sull'hardware descritto nella tabella seguente. Tutti i suggerimenti e i risultati sono basati su questo hardware. Se decidi di provare a usare hardware meno potente di quello elencato qui, tieni presente che potrebbero verificarsi problemi di funzionalità o prestazioni ridotte. Questi suggerimenti hardware sono gli stessi di Lync Server 2013, se utile (e negli scenari di aggiornamento, potrebbe essere).

**Hardware utilizzato nei test delle prestazioni**

|Componente hardware|Consigliata|
|:-----|:-----|
|CPU   |Doppio processore a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli Skype for Business Server server.   |
|Memoria   |32 gigabyte (GB).   |
|Disco   |8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco. Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.  <br/> -OPPURE- <br/>Unità SSD (Solid State Drive) che offrono prestazioni simili a 8 unità disco meccaniche da 10.000 RPM.  |
|Rete   |1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliato, che richiede la condivisione con un singolo indirizzo MAC e un singolo indirizzo IP).   |

## <a name="summary-of-results"></a>Riepilogo dei risultati

Nella tabella seguente sono riepilogati i suggerimenti.

|Ruolo del server|Numero massimo di utenti supportati|
|:-----|:-----|
|Pool Front End con dodici Front End Server e un server back-end o una coppia di server back-end con mirroring.   |80.000 utenti univoci connessi contemporaneamente, più il 50% di punti di presenza multipli (MPOP) che rappresentano istanze non mobili, più il 40% degli utenti abilitati per dispositivi mobili per un totale di 152.000 endpoint.   |
|A/V Conferencing   |Il servizio A/V Conferencing fornito da un pool Front End supporta le conferenze del pool presupponendo una dimensione massima di conferenza di 250 utenti e una sola conferenza di grandi dimensioni in esecuzione alla volta.  <br/> **Nota:** È inoltre possibile supportare conferenze di grandi dimensioni tra 250 e 1000 utenti distribuendo un pool Front End separato con due Front End Server per ospitare le conferenze di grandi dimensioni. Per informazioni dettagliate, vedere [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).   |
|Un server perimetrale   |12.000 utenti remoti simultanei.   |
|Un Director   |12.000 utenti remoti simultanei.   |
|Monitoraggio e archiviazione   |I servizi front-end di monitoraggio e archiviazione vengono eseguiti in ogni Front End Server, anziché in ruoli del server distinti.  <br/> Il monitoraggio e l'archiviazione richiedono comunque i propri archivi di database. Se si esegue anche Exchange 2013 o versioni successive, è possibile mantenere i dati di archiviazione in Exchange, anziché in un database SQL dedicato.   |
|Un Mediation Server   |Mediation Server collocato con Front End Server viene eseguito in ogni Front End Server di un pool e deve fornire capacità sufficiente per gli utenti nel pool. Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.   |
|Un server Standard Edition   |Se si utilizzano server di edizione Standard per ospitare gli utenti, è consigliabile utilizzare sempre due server, abbinati alle indicazioni fornite in [Planning for High Availability and Disaster Recovery](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery). Ogni server nella coppia può ospitare fino a 2.500 utenti e, se un server non riesce, il server rimanente può supportare 5.000 utenti in uno scenario di failover.  <br/>  Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server potrebbero risentire di più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere altri server edizione Standard o passare a Skype for Business Server edizione Enterprise.  |

## <a name="front-end-server"></a>Front End Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

In un pool Front End, è necessario disporre di un Front End Server per ogni 6.660 utenti ospitati nel pool, presupponendo che l'hyperthreading sia abilitato in tutti i server del pool e che l'hardware del server soddisfi i requisiti di [server per Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md) o Requisiti di sistema per [Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Il numero massimo di utenti in un pool Front End è 80.000, presupponendo che l'hyperthreading sia abilitato in tutti i server del pool. Se in un sito sono presenti più di 80.000 utenti è possibile distribuire più pool Front End.

Quando si specifica il numero di utenti in un pool Front End, includere tutti gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a questo pool Front End.

Quando un server attivo non è disponibile, le relative connessioni vengono trasferite automaticamente agli altri server del pool. In uno scenario in cui sono presenti 30.000 utenti e cinque Front End Server, se un server non è disponibile, le connessioni di 6000 utenti devono essere trasferite agli altri quattro server rimanenti. Questi quattro server rimanenti avranno quindi 7500 utenti, un numero superiore a quello consigliato.

Se invece si è iniziato con sei Front End Server per i 30.000 utenti e uno non è più disponibile, un totale di 5.000 utenti deve passare ai cinque server rimanenti. Questi cinque server rimanenti ospiteranno quindi 6.000 utenti, che si trova nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front End è 80.000. Il numero massimo di Front End Server in un pool è 12.

Per un pool Front End con 80.000 utenti, dodici Front End Server sono ottimali per le prestazioni, nelle distribuzioni tipiche che seguono i modelli utente [in Skype for Business Server](user-models.md). Le distribuzioni progettate per supportare il failover di ripristino di emergenza presuppongono che un massimo di 40.000 utenti possa essere ospitato in ognuno dei due pool Front End abbinati, in cui ogni pool dispone di un numero sufficiente di Front End Server per contenere gli utenti in entrambi i pool, nel caso in cui sia necessario eseguire il failover di un pool nell'altro.

Il numero di utenti supportati con buone prestazioni da un determinato pool Front End può essere diverso da questi numeri per i motivi seguenti:

- L'hardware per i Front End Server non soddisfa i suggerimenti.

- L'utilizzo dell'organizzazione è molto diverso dai modelli utente, ad esempio se si dispone di molto più traffico di conferenza.

Nella tabella seguente viene mostrata la larghezza di banda media per la messaggistica istantanea e la presenza, in base al modello utente, come definito in [Modelli utente in Skype for Business Server](user-models.md).

|Larghezza di banda media per utente|Requisiti di larghezza di banda per Front End Server con 6.660 utenti|
|:-----|:-----|
|1,3 Kpbs   |13 Mbps   |

> [!NOTE]
> Per migliorare le prestazioni multimediali della funzionalità A/V Conferencing e Mediation Server nei Front End Server, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) sulle schede di rete nei Front End Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, [vedere Receive Side Scaling (RSS) nella documentazione Windows Server 2012.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="conferencing-maximums"></a>Valori massimi per le conferenze

Dato il modello utente che il 5% degli utenti di un pool può essere in una conferenza contemporaneamente, un pool di 80.000 utenti potrebbe avere circa 4.000 utenti in conferenze contemporaneamente. Le conferenze saranno variabili nel tipo di contenuti multimediali (ad esempio alcune solo di messaggistica istantanea, altre di messaggistica istantanea e audio, altre audio/video) e nel numero di partecipanti. Non esiste un limite rigido per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive. Ad esempio, se nell'organizzazione sono presenti molte più conferenze in modalità mista rispetto a quelle ipotizzate nel modello utente, potrebbe essere necessario distribuire più Front End Server o A/V Conferencing Server rispetto ai suggerimenti riportati in questo articolo. Per informazioni dettagliate sui presupposti nel modello utente, vedere [User models in Skype for Business Server](user-models.md).

La dimensione massima supportata per le conferenze ospitata da un pool Front End Skype for Business Server che ospita anche gli utenti è di 250 partecipanti. Mentre è in corso una conferenza per 250 utenti, il pool supporta ancora anche altre conferenze, in modo che un totale del 5% degli utenti del pool si trova in conferenze simultanee. Ad esempio, in un pool di 12 Front End Server e 80.000 utenti, mentre è in corso la conferenza con 250 utenti, Skype for Business Server supporta altri 3.750 utenti che partecipano a conferenze più piccole.

Indipendentemente dal numero di utenti ospitati nel pool Front End o nel server edizione Standard, Skype for Business Server supporta almeno 125 altri utenti che partecipano a conferenze più piccole nello stesso pool o server che ospita una conferenza per 250 utenti.

Per abilitare conferenze con un numero di utenti compreso tra 250 e 1000, è possibile configurare un pool Front End separato solo per ospitare tali conferenze. Questo pool Front End non ospiterà alcun utente. Per informazioni dettagliate, vedere [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Se nell'organizzazione sono presenti più conferenze in modalità mista di quelle ipotizzate nel modello utente, potrebbe essere necessario distribuire più Front End Server di quanto consigliato in questo documento (fino a un limite di 12 Front End Server). Per informazioni dettagliate sui presupposti nel modello utente, vedere [User models in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edge Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

È consigliabile distribuire un server perimetrale ogni 12.000 utenti remoti che accederanno a un sito contemporaneamente. Per la disponibilità elevata è consigliabile un minimo di due server perimetrali. Questi suggerimenti presuppongono che l'hardware per i server perimetrali soddisfi i suggerimenti in [Server Hardware Platforms](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

Quando si calcola il numero di utenti per i server perimetrali, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

> [!NOTE]
> Per migliorare le prestazioni del servizio A/V Conferencing Edge nei server perimetrali è opportuno abilitare Receive-Side Scaling (RSS) nelle schede di rete dei server perimetrali. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Receive Side Scaling (RSS) in Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="director"></a>Direttore

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

Se si distribuisce il ruolo del server Director, è consigliabile distribuire un Server Director ogni 12.000 utenti remoti che accederanno a un sito contemporaneamente. Per la disponibilità elevata è consigliabile un minimo di due Director. Questi suggerimenti presuppongono che l'hardware per i server perimetrali soddisfi i suggerimenti in [Server Hardware Platforms](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

Quando si calcola il numero di utenti per i Director, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

## <a name="mediation-server"></a>Mediation Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in ogni Front End Server del pool e deve fornire capacità sufficiente per gli utenti del pool.

Se si distribuisce un pool Mediation Server autonomo, il numero di Mediation Server da distribuire dipende da molti fattori, tra cui l'hardware utilizzato per Mediation Server, il numero di utenti VoIP disponibili, il numero di peer gateway che ogni pool Mediation Server controlla, il traffico di ore di punta attraverso tali gateway e la percentuale di chiamate con supporti che ignorano il Mediation Server.

Le tabelle seguenti forniscono una linea guida per il numero di chiamate simultanee che un Mediation Server è in grado di gestire, presupponendo che l'hardware per i Mediation Server soddisfi i requisiti in [Piattaforme hardware](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) server e che l'hyperthreading sia abilitato. Per informazioni dettagliate sulla scalabilità di Mediation Server, vedere [Estimating voice usage and traffic for Skype for Business Server](estimating-voice-traffic.md) and [Deployment guidelines for Mediation Server in Skype for Business Server](mediation-server-deployment-guidelines.md).

Tutte le tabelle seguenti presuppongono che l'utilizzo sia riepilogato [in Modelli utente in Skype for Business Server](user-models.md).

**Capacità mediation server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non bypass (transcodamento multimediale eseguito da Mediation Server)**

|Hardware dei server|Numero massimo di chiamate|Numero massimo di linee T1|Numero massimo di linee E1|
|:-----|:-----|:-----|:-----|
|Doppio processore, core esadecimale, CPU hyperthread da 2,26 GHz con **hyperthreading** disabilitato, con 32 GB di memoria e una scheda di rete a doppia porta.   |1100   |46   |35   |
|Processore doppio, core esadecimale, CPU hyper-thread da 2,26 GHz, con 32 GB di memoria e una scheda di rete a doppia porta.   |1500   |63   |47   |

> [!NOTE]
> Anche se nei test delle prestazioni sono stati utilizzati server con 32 GB di memoria, i server con 16 GB di memoria sono sono supportati in Mediation Server autonomo e sono sufficienti a garantire le prestazioni indicate in questa tabella.

**Mediation Server Capacity (Mediation Server collocato con Front End Server) 70% utenti interni, 30% utenti esterni, capacità delle chiamate non bypass (elaborazione multimediale eseguita da Mediation Server)**

|Hardware dei server|Numero massimo di chiamate|
|:-----|:-----|
|Doppio processore, core esadecimale, CPU hyper-thread da 2,26 GHz, con 32 GB di memoria e 2 schede di rete da 1 GB.   |150   |

> [!NOTE]
> Questo numero è molto più piccolo rispetto ai numeri per il Mediation Server autonomo. Questo perché il Front End Server deve gestire altre funzionalità e funzioni per i 6600 utenti ospitati su di esso, oltre alla transcodatura necessaria per le chiamate vocali.

> [!NOTE]
> Per migliorare le prestazioni del Mediation Server, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) sulle schede di rete nei Mediation Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Receive-Side Scaling in Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="back-end-server"></a>Server back-end

Sebbene gran parte delle informazioni del database sia archiviata principalmente nei Front End Server, è consigliabile verificare che i server back-end soddisfino i suggerimenti hardware elencati in precedenza in questa sezione e in [Piattaforme hardware server](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

Per garantire la disponibilità elevata del server back-end, è consigliabile distribuire gruppi di disponibilità AlwaysOn o mirroring del server. Per ulteriori informazioni, vedere [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

Se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei Front End Server, ognuno dei quali utilizza il proprio archivio database, separato dall'archivio back-end. In alternativa, se è stata Exchange 2013, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

Nella tabella seguente viene indicata approssimativamente la quantità di spazio di archiviazione del database necessaria per utente al giorno per i dati di monitoraggio e archiviazione.

|&nbsp;|Registrazione dei dati (monitoraggio)  |QoE (monitoraggio)  |Archiviazione  |
|:-----|:-----|:-----|:-----|
|Spazio su disco richiesto per utente al giorno   |49 KB   |28 KB   |57 KB   |

Microsoft ha utilizzato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante i test delle prestazioni. Il test ha raccolto i dati di due pool Front End, ognuno dei quali conteneva 80.000 utenti.

**Hardware utilizzato nei test delle prestazioni di monitoraggio e archiviazione**

|Componente hardware|Consigliata|
|:-----|:-----|
|CPU   |Processore doppio a 64 bit, hex core, 2,26 GHz o superiore   |
|Memoria   |48 gigabyte (GB)   |
|Disco   |25 unità disco rigido da 10.000 RPM con 300 GB su ogni disco, con la configurazione nella tabella seguente   |
|Rete   | Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)   |

**Configurazioni disco consigliate**

|Unità  |Configurazione RAID  |Numero di dischi  |
|:-----|:-----|:-----|
|CdR, QoE e file di dati del database di archiviazione in una singola unità   |1+0   |16    |
|File di registro del database CDR   |1   |2   |
|File di registro del database QoE   |1   |2   |
|File di registro del database di archiviazione   |1   |2   |

## <a name="video-interop-server-capacity"></a>Capacità di Video Interop Server

Se si distribuisce Video Interop Server ed è necessario determinare la capacità, si osserva il numero massimo di VTC (Video Teleconferencing Systems) che saranno presenti in chiamate simultanee. Ad esempio, se nell'organizzazione sono presenti 250 VTC e il modello utente stima che al massimo, il 20% di essi potrebbe essere in chiamate simultanee, si basa la pianificazione della capacità su 50 VTC simultanei.