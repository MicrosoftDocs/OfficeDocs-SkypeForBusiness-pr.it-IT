---
title: Utilizzo del modello utente per la pianificazione della capacità per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: In questo articolo vengono fornite indicazioni su quanti server sono necessari in un sito per il numero di utenti in quel sito, in base all'utilizzo descritto in User Models in Skype for Business Server.
ms.openlocfilehash: e0b145ddfc766ba7db9012d4f3aaa7333f4f5d72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827636"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Utilizzo del modello utente per la pianificazione della capacità per Skype for Business Server

In questo articolo vengono fornite indicazioni su quanti server sono necessari in un sito per il numero di utenti in quel sito, in base all'utilizzo descritto in [User Models in Skype for Business Server](user-models.md).

> [!NOTE]
> Tutti i consigli illustrati in questo articolo presuppongono che l'aggiornamento cumulativo di Skype for business sia stato installato, novembre 2015 o versioni successive nei server.

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

I test delle prestazioni sono stati eseguiti sull'hardware descritto nella tabella seguente. Tutti gli elementi consigliati e i risultati sono basati su questo hardware. Se si decide di provare a utilizzare hardware meno potente rispetto a quello visualizzato in questo articolo, tenere presente che è possibile che si verifichino problemi di funzionalità o prestazioni insufficienti. Questi suggerimenti per l'hardware sono gli stessi di Lync Server 2013, se questo è utile (e in scenari di aggiornamento, potrebbe essere).

**Hardware utilizzato nei test delle prestazioni**

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli del server Skype for Business Server.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco. Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.  <br/> -OPPURE- <br/>Unità SSD (Solid State Drive) che offrono prestazioni simili alle unità disco meccaniche 8 10.000-RPM. <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (2 consigliate, che richiede la collaborazione con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> |

## <a name="summary-of-results"></a>Riepilogo dei risultati

Nella tabella seguente sono riepilogati i suggerimenti.

|**Ruolo del server**|**Numero massimo di utenti supportati**|
|:-----|:-----|
|Pool Front end con dodici front end server e un server back-end o una coppia con mirroring dei server back-end.  <br/> |80.000 utenti univoci connessi contemporaneamente, oltre al 50% di più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 152.000 endpoint.  <br/> |
|A/V Conferencing  <br/> |Il servizio A/V Conferencing fornito da un pool Front end supporta le conferenze del pool assumendo una dimensione massima per le conferenze di 250 utenti e solo una conferenza di questo tipo è in esecuzione alla volta.  <br/> **Nota:** È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front end separato con due front end server per ospitare le conferenze di grandi dimensioni. Per ulteriori informazioni, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un server perimetrale  <br/> |12.000 utenti remoti simultanei.  <br/> |
|Un Director  <br/> |12.000 utenti remoti simultanei.  <br/> |
|Monitoraggio e archiviazione  <br/> |I servizi front end di monitoraggio e archiviazione vengono eseguiti su ogni Front End Server, anziché su ruoli server distinti.  <br/> Monitoring and Archiving each richiedono ancora i propri archivi di database. Se si esegue anche Exchange 2013 o versione successiva, è possibile mantenere i dati di archiviazione in Exchange anziché in un database SQL dedicato.  <br/> |
|Un Mediation Server  <br/> |Mediation Server collocato con Front End Server viene eseguito in tutti i front end server in un pool e deve fornire capacità sufficiente per gli utenti nel pool. Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.  <br/> |
|Un server Standard Edition  <br/> |Se si utilizzano i server Standard Edition per ospitare gli utenti, è consigliabile utilizzare sempre due server, abbinati con i suggerimenti per la [pianificazione della disponibilità elevata e del ripristino di emergenza](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server ha esito negativo, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.  <br/>  Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono subire più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere più server Standard Edition o passare a Skype for Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Front End Server

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

In un pool Front End, è necessario disporre di un front end server per ogni 6.660 utenti ospitati nel pool, presupponendo che l'Hyper-Threading sia abilitato su tutti i server del pool e che l'hardware del server soddisfi i requisiti consigliati nei [Server per Skype for Business server 2015](../requirements-for-your-environment/server-requirements.md) o  [requisiti di sistema per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Il numero massimo di utenti in un pool Front End è pari a 80.000, presupponendo che Hyper-Threading sia abilitato su tutti i server del pool. Se in un sito sono presenti più di 80.000 utenti è possibile distribuire più pool Front End.

Quando si tiene conto del numero di utenti in un pool Front End, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a questo pool Front end.

Quando un server attivo non è disponibile, le relative connessioni vengono trasferite automaticamente agli altri server del pool. In uno scenario in cui sono disponibili 30.000 utenti e cinque front end server, se un server non è disponibile, le connessioni di 6000 degli utenti devono essere trasferite agli altri quattro server rimanenti. Questi quattro server rimanenti avranno ciascuno 7500 utenti, che è un numero maggiore di quello consigliato.

Se invece si è iniziato con sei front end server per gli utenti di 30.000 e uno diventa non disponibile, per un totale di 5000 gli utenti devono passare ai restanti cinque server. Questi cinque server restanti verranno quindi ogni host 6000 utenti, che si trova nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front End è 80.000. Il numero massimo di front end server in un pool è 12.

Per un pool Front end con 80.000 utenti, dodici front end server saranno utili per le prestazioni, nelle distribuzioni tipiche che seguono i [modelli utente in Skype for Business Server](user-models.md). Le distribuzioni progettate per supportare il failover del ripristino di emergenza presumono che un massimo di 40.000 utenti possano essere ospitati in ognuno dei due pool Front End associati, in cui ogni pool disponga di front end server sufficienti per contenere gli utenti in entrambi i pool, in caso di errore di un pool nell'altro.

Il numero di utenti supportati con prestazioni ottimali da parte di un pool Front end specifico potrebbe differire da questi numeri per i motivi seguenti:

- L'hardware per i Front End Server non soddisfa gli elementi consigliati.

- L'utilizzo dell'organizzazione è molto diverso rispetto ai modelli degli utenti, ad esempio se si dispone di un traffico di conferenza molto più grande.

Nella tabella seguente viene illustrata la larghezza di banda media per la messaggistica istantanea e la presenza, in base al modello utente, come definito nei [modelli utente in Skype for Business Server](user-models.md).

|**Larghezza di banda media per utente**|**Requisiti di larghezza di banda per front end server con 6.660 utenti**|
|:-----|:-----|
|1,3 Kpbs  <br/> |13 Mbps  <br/> |

> [!NOTE]
> Per migliorare le prestazioni multimediali delle funzionalità di A/V Conferencing e Mediation Server in base ai server front end, è necessario abilitare il riversamento sul lato ricezione (RSS) nelle schede di rete nei Front End Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere [Receive Side Scaling (RSS) nella documentazione di Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione relativa alla scheda di rete.

## <a name="conferencing-maximums"></a>Valori massimi per le conferenze

Dato il modello utente per il quale il 5% degli utenti in un pool può trovarsi in una conferenza in qualsiasi momento, un pool di 80.000 utenti potrebbe avere circa 4.000 utenti nelle conferenze contemporaneamente. Le conferenze saranno variabili nel tipo di contenuti multimediali (ad esempio alcune solo di messaggistica istantanea, altre di messaggistica istantanea e audio, altre audio/video) e nel numero di partecipanti. Non esiste un limite fisso per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive. Ad esempio, se nell'organizzazione sono presenti molte più conferenze in modalità miste rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più Front End Server o A/V Conferencing Server rispetto alle indicazioni riportate in questo articolo. Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Skype for Business Server](user-models.md).

Le dimensioni massime supportate da un pool Front End di Skype for Business Server normale, che ospita anche gli utenti, sono di 250 partecipanti. Anche se è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che il 5% degli utenti del pool si trovi in conferenze simultanee. Ad esempio, in un pool di dodici front end server e 80.000 utenti, mentre la conferenza di 250 utenti è in corso, Skype for Business Server supporta 3.750 altri utenti che partecipano a conferenze di piccole dimensioni.

Indipendentemente dal numero di utenti che si trovano nel pool Front end o nel server Standard Edition, Skype for Business Server supporta almeno 125 altri utenti che partecipano a conferenze di piccole dimensioni nello stesso pool o server che ospita una conferenza di 250 utenti.

Per abilitare le conferenze che hanno tra gli utenti 250 e 1000, è possibile configurare un pool Front end separato solo per ospitare tali conferenze. Questo pool Front end non ospiterà alcun utente. Per ulteriori informazioni, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Se nell'organizzazione sono presenti molte più conferenze in modalità miste rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più Front End Server rispetto a quelli consigliati in questo documento (fino a un massimo di 12 Front End Server). Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edge Server

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

È necessario distribuire un server perimetrale per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due server perimetrali. Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando si calcola il numero di utenti per i server perimetrali, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

> [!NOTE]
> Per migliorare le prestazioni del servizio A/V Conferencing Edge nei server perimetrali è opportuno abilitare Receive-Side Scaling (RSS) nelle schede di rete dei server perimetrali. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Receive Side Scaling (RSS) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione relativa alla scheda di rete.

## <a name="director"></a>Direttore

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

Se si distribuisce il ruolo server Director, è consigliabile distribuire un amministratore per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due Director. Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando si calcola il numero di utenti per i Director, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

## <a name="mediation-server"></a>Mediation Server

> [!NOTE]
> I pool allungati non sono supportati per questo ruolo del server.

Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i Front End Server nel pool e deve fornire una capacità sufficiente per gli utenti nel pool.

Se si distribuisce un pool di Mediation Server autonomo, il numero di Mediation Server da distribuire dipende da molti fattori, tra cui l'hardware utilizzato per Mediation Server, il numero di utenti VoIP che si dispone di, la quantità di peer gateway che ogni pool di Mediation Server controlla, il traffico di ora occupato attraverso tali gateway e la percentuale di chiamate con supporto che ignora Mediation Server

Nelle tabelle seguenti vengono fornite linee guida per il numero di chiamate simultanee che un Mediation Server può gestire, presupponendo che l'hardware per i Mediation Server soddisfi i requisiti nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) e che l'Hyper-Threading sia abilitato. Per informazioni dettagliate sulla scalabilità dei Mediation Server, vedere [Estimating Voice Usage and traffic for Skype for Business Server](estimating-voice-traffic.md) e [linee guida per la distribuzione di Mediation Server in Skype for Business Server](mediation-server-deployment-guidelines.md).

Tutte le tabelle seguenti presumono l'utilizzo come riepilogato nei [modelli utente in Skype for Business Server](user-models.md).

**Capacità Mediation Server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non di bypass (transcodifica multimediale eseguita da Mediation Server)**

|**Hardware dei server**|**Numero massimo di chiamate**|**Numero massimo di linee T1**|**Numero massimo di linee E1**|
|:-----|:-----|:-----|:-----|
|Doppio processore, hex core, CPU Hyper-Threading da 2,26 GHz **con Hyper-Threading disabilitato**, con 32 GB di memoria e una scheda di rete a doppia porta.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Processore duale, Core esagonale, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e una scheda di rete a doppia porta.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Anche se nei test delle prestazioni sono stati utilizzati server con 32 GB di memoria, i server con 16 GB di memoria sono sono supportati in Mediation Server autonomo e sono sufficienti a garantire le prestazioni indicate in questa tabella.

**Capacità Mediation Server (Mediation Server collocato con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non di bypass (elaborazione multimediale eseguita da Mediation Server)**

|**Hardware dei server**|**Numero massimo di chiamate**|
|:-----|:-----|
|Processore duale, Core Hex, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e 2 schede di rete da 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Questo numero è molto più piccolo dei numeri per il Mediation Server autonomo. Ciò è dovuto al fatto che il front end server deve gestire altre caratteristiche e funzionalità per gli utenti 6600 ospitati in esso, oltre alla transcoding necessaria per le chiamate vocali.

> [!NOTE]
> Per migliorare le prestazioni del Mediation Server, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete dei Mediation Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Receive-Side Scaling in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione relativa alla scheda di rete.

## <a name="back-end-server"></a>Server back-end

Anche se molte delle informazioni del database vengono archiviate principalmente nei Front End Server, è necessario assicurarsi che i server back-end soddisfino i requisiti hardware elencati in precedenza in questa sezione e nelle [piattaforme hardware del server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Per garantire la disponibilità elevata del server back-end, è consigliabile distribuire i gruppi di disponibilità AlwaysOn o il mirroring del server. Per ulteriori informazioni, vedere [disponibilità elevata del server back-end in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

Se si distribuisce il monitoraggio o l'archiviazione, le funzionalità front-end di questi servizi vengono eseguite nei Front End Server, il monitoraggio e l'archiviazione di ogni utilizzo del proprio archivio di database sono separati dall'archivio back-end. In alternativa, se si dispone di Exchange 2013 distribuito, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

La tabella seguente indica approssimativamente la quantità di spazio di archiviazione dei database necessaria per utente al giorno per il monitoraggio e l'archiviazione di dati.

||**CDR (monitoraggio)** <br/> |**QoE (monitoraggio)** <br/> |**Archiviazione** <br/> |
|:-----|:-----|:-----|:-----|
|Spazio su disco necessario per utente per giorno  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft ha utilizzato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il testing delle prestazioni. Il test ha raccolto i dati di due pool Front End, ognuno dei quali conteneva 80.000 utenti.

**Hardware utilizzato per il monitoraggio e il testing delle prestazioni di archiviazione**

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore doppio a 64 bit, hex core, 2,26 GHz o superiore  <br/> |
|Memoria  <br/> |48 gigabyte (GB)  <br/> |
|Disco  <br/> |25 10.000-RPM unità disco rigido con 300 GB su ogni disco, con la configurazione nella tabella seguente  <br/> |
|Rete  <br/> | Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)  <br/> |

**Configurazioni disco consigliate**

|**Unità** <br/> |**Configurazione RAID** <br/> |**Numero di dischi** <br/> |
|:-----|:-----|:-----|
|File di dati CDR, QoE e di archiviazione per database, in un'unica unità  <br/> |1 + 0  <br/> |16   <br/> |
|File di registro del database CDR  <br/> |1   <br/> |2   <br/> |
|File di registro del database QoE  <br/> |1   <br/> |2   <br/> |
|File di registro del database di archiviazione  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Capacità del server di interoperabilità video

Se si distribuisce video Interop server ed è necessario determinare la capacità, si esamina il numero massimo di sistemi di teleconferenza video (VTCs) che saranno presenti nelle chiamate simultanee. Ad esempio, se si dispone di 250 VTCs nell'organizzazione e il modello utente stima che al massimo, il 20% di essi potrebbe essere nelle chiamate simultanee, si basa la pianificazione della capacità su 50 concorrenti VTCs.


