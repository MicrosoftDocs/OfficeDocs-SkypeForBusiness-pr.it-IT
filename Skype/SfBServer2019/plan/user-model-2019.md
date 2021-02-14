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
description: Gli argomenti di questa sezione consentono di comprendere come pianificare e distribuire Skype for Business Server in modo da poter pianificare in modo adeguato il numero di utenti nell'organizzazione e pianificare il carico del server generato dalle loro attività.
ms.openlocfilehash: 15f59d2052a4d73f6e1b1c09b10525b503958fea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824030"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Pianificazione della capacità per Skype for Business Server 2019

In questo articolo vengono fornite indicazioni sul numero di server necessari in un sito per il numero di utenti in tale sito, in base all'utilizzo descritto in Modelli utente [in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

Abbiamo eseguito i test delle prestazioni sull'hardware descritto nella tabella seguente. Tutti i suggerimenti e i risultati sono basati su questo hardware. Se decidi di provare a usare hardware meno potente di quello elencato qui, tieni presente che potrebbero verificarsi problemi di funzionalità o prestazioni scarse.

**Hardware utilizzato nei test delle prestazioni**

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 v3 dual, 6 core, 2,4 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |UNO DEI DUE:  <br/> • 8 o più unità disco rigido da 1.0000 RPM con almeno 72 GB di spazio libero su disco (due dei dischi che utilizzano RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 8 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a due porte, 1 Gbps o superiore (è possibile usare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed non sono **supportate** per i Front End Server, i server back-end e i server Standard Edition. <br/> Finché non vengono esposti al sistema operativo e vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multi-homed ed è supportato.  <br/> |

## <a name="summary-of-results"></a>Riepilogo dei risultati

Nella tabella seguente sono riepilogati i suggerimenti.

|**Ruolo del server**|**Numero massimo di utenti supportati**|
|:-----|:-----|
|Pool Front End con sedici Front End Server e server back-end o una coppia di server back-end con SQL Always On per la disponibilità elevata.  <br/> |106.000 utenti univoci connessi contemporaneamente, più il 50% di più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per i dispositivi mobili per un totale di 210.000 endpoint.  <br/> |
|A/V Conferencing  <br/> |Il servizio A/V Conferencing fornito da un pool Front End supporta le conferenze del pool presupponendo una dimensione massima di conferenza di 250 utenti e una sola conferenza di grandi dimensioni in esecuzione alla volta.  <br/> **Nota:** È inoltre possibile supportare conferenze di grandi dimensioni tra 250 e 1000 utenti distribuendo un pool Front End separato con due Front End Server per ospitare le conferenze di grandi dimensioni. Per informazioni dettagliate, vedere [Pianificare riunioni di grandi dimensioni in Skype for Business Server.](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md) <br/> |
|Un server perimetrale  <br/> |18.000 utenti remoti simultanei.  <br/> |
|Un Director  <br/> |18.000 utenti remoti simultanei.  <br/> |
|Monitoraggio e archiviazione  <br/> |I servizi front-end di monitoraggio e archiviazione vengono eseguiti in ogni Front End Server, anziché in ruoli del server separati.  <br/> Il monitoraggio e l'archiviazione richiedono comunque archivi di database propri. Se si esegue anche Exchange 2013 o versione successiva, è possibile conservare i dati di archiviazione in Exchange, anziché in un database SQL dedicato.  <br/> |
|Un Mediation Server  <br/> |Mediation Server collocato con Front End Server viene eseguito in tutti i Front End Server di un pool e deve fornire capacità sufficiente per gli utenti del pool. Per il Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.  <br/> |
|Un server Standard Edition  <br/> |Se si utilizzano server Standard Edition per ospitare gli utenti, è consigliabile utilizzare sempre due server, abbinati ai suggerimenti forniti in Pianificazione della disponibilità elevata e del ripristino [di emergenza.](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx) Ogni server della coppia può ospitare fino a 2.500 utenti e, in caso di errore di un server, il server rimanente può supportare 5.000 utenti in uno scenario di failover.  <br/>  Se la distribuzione include una notevole quantità di traffico audio o video, le prestazioni del server possono risentirne con più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere altri server Standard Edition o passare a Skype for Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Front End Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

In un pool Front End è consigliabile disporre di un Front End Server ogni 6.660 utenti ospitati nel pool, presupponendo che l'hyperthreading sia abilitato in tutti i server del pool, che si utilizzi SQL Server Express Edition e che l'hardware del server soddisfi i requisiti dei server per [Skype for Business Server 2019.](system-requirements.md) Il numero massimo di utenti in un pool Front End è 106.000, presupponendo di nuovo che l'hyperthreading sia abilitato e che in tutti i server del pool sia utilizzato SQL Server Express Edition. Se si dispone di più di 106.000 utenti in un sito, è possibile distribuire più di un pool Front End.

Quando si specifica il numero di utenti in un pool Front End, includere tutti gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a questo pool Front End.

Quando un server attivo non è disponibile, le relative connessioni vengono trasferite automaticamente agli altri server del pool. In uno scenario in cui sono presenti 30.000 utenti e cinque Front End Server, se un server non è disponibile, è necessario trasferire le connessioni di 6000 utenti agli altri quattro server rimanenti. Questi quattro server rimanenti avranno quindi 7500 utenti, un numero superiore a quello consigliato.

Se invece si è iniziato con sei Front End Server per i 30.000 utenti e uno diventa non disponibile, un totale di 5.000 utenti dovrà passare ai cinque server rimanenti. Questi cinque server rimanenti ospiteranno quindi 6.000 utenti, che sono nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front End è 106.000. Il numero massimo di Front End Server in un pool è 16.

Per un pool Front End con 80.000 utenti, 16 Front End Server sono ottimali per le prestazioni, nelle distribuzioni tipiche che seguono i modelli utente [in Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md) Le distribuzioni progettate per supportare il failover di ripristino di emergenza presuppongono che un massimo di 53.000 utenti possa essere ospitato in ognuno dei due pool Front End abbinati, in cui ogni pool dispone di un numero sufficiente di Front End Server per contenere gli utenti in entrambi i pool, nel caso in cui sia necessario eseguire il failover di un pool all'altro.

Il numero di utenti supportati con buone prestazioni da un determinato pool Front End può essere diverso da questi numeri per i motivi seguenti:

- L'hardware per i Front End Server non soddisfa i suggerimenti.
- Anziché utilizzare SQL Server Express Edition, si utilizza un'altra SQL Server Edition, è possibile ospitare altri utenti in ogni pool Front End.
- L'utilizzo dell'organizzazione è molto diverso dai modelli utente, ad esempio se si dispone di un traffico di conferenza molto maggiore.

La tabella seguente mostra la larghezza di banda media per la messaggistica istantanea e la presenza, in base al modello utente, come definito nei modelli utente [in Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

|**Larghezza di banda media per utente**|**Requisiti di larghezza di banda per Front End Server con 6.660 utenti**|
|:-----|:-----|
|3-3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Per migliorare le prestazioni multimediali delle funzionalità A/V Conferencing e Mediation Server co-collocate nei Front End Server, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) nelle schede di rete dei Front End Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, [vedere Receive Side Scaling (RSS) nella documentazione di Windows Server 2012.](https://go.microsoft.com/fwlink/p/?LinkId=620365) Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="conferencing-maximums"></a>Valori massimi per le conferenze

Dato il modello utente che il 5% degli utenti di un pool può essere in una conferenza contemporaneamente, un pool di 106.000 utenti potrebbe avere circa 5.300 utenti in conferenza contemporaneamente. Le conferenze saranno variabili nel tipo di contenuti multimediali (ad esempio alcune solo di messaggistica istantanea, altre di messaggistica istantanea e audio, altre audio/video) e nel numero di partecipanti. Non esiste un limite rigido per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive. Ad esempio, se l'organizzazione dispone di molte più conferenze in modalità mista di quelle ipotizzate nel modello utente, potrebbe essere necessario distribuire più Front End Server o A/V Conferencing Server rispetto ai consigli riportati in questo articolo. Per informazioni dettagliate sui presupposti nel modello utente, vedere [Modelli utente in Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

La dimensione massima supportata per le conferenze ospitata da un normale pool Front End di Skype for Business Server che ospita anche gli utenti è di 250 partecipanti. Mentre è in corso una conferenza con 250 utenti, il pool supporta comunque anche altre conferenze, in modo che un totale del 5% degli utenti del pool si trova in conferenze simultanee. Ad esempio, in un pool di 16 Front End Server e 106.000 utenti, mentre la conferenza con 250 utenti è in corso, Skype for Business Server supporta 5.050 altri utenti che partecipano a conferenze più piccole.

Indipendentemente dal numero di utenti ospitati nel pool Front End o nel server Standard Edition, Skype for Business Server supporta almeno 125 altri utenti che partecipano a conferenze più piccole nello stesso pool o server che ospita una conferenza di 250 utenti.

Per abilitare le conferenze con un numero di utenti compreso tra 250 e 1000, è possibile configurare un pool Front End separato solo per ospitare tali conferenze. Questo pool Front End non ospiterà alcun utente. Per informazioni dettagliate, vedere [Pianificare riunioni di grandi dimensioni in Skype for Business Server.](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)

Se l'organizzazione dispone di un numero di conferenze in modalità mista molto superiore a quello previsto nel modello utente, potrebbe essere necessario distribuire più Front End Server di quanto consigliato in questo documento (fino a un limite di 16 Front End Server). Per informazioni dettagliate sui presupposti nel modello utente, vedere [Modelli utente in Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="edge-server"></a>Edge Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

È consigliabile distribuire un server perimetrale ogni 18.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due server perimetrali. Questi consigli presuppongono che l'hardware per i server perimetrali soddisfi i suggerimenti forniti nelle [piattaforme hardware dei server.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Quando si calcola il numero di utenti per i server perimetrali, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

> [!NOTE]
> Per migliorare le prestazioni del servizio A/V Conferencing Edge nei server perimetrali è opportuno abilitare Receive-Side Scaling (RSS) nelle schede di rete dei server perimetrali. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, [vedere Receive Side Scaling (RSS) in Windows Server 2012.](https://go.microsoft.com/fwlink/p/?linkId=268731) Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="director"></a>Direttore

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

Se si distribuisce il ruolo del server Director, è consigliabile distribuire un Director ogni 18.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due Director. Questi consigli presuppongono che l'hardware per i server perimetrali soddisfi i suggerimenti forniti nelle [piattaforme hardware dei server.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Quando si calcola il numero di utenti per i Director, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

## <a name="mediation-server"></a>Mediation Server

> [!NOTE]
> I pool stretch non sono supportati per questo ruolo del server.

Se si colloca Mediation Server con Front End Server, il Mediation Server viene eseguito in tutti i Front End Server del pool e deve fornire capacità sufficiente per gli utenti del pool.

Se si distribuisce un pool Mediation Server autonomo, il numero di Mediation Server da distribuire dipende da molti fattori, tra cui l'hardware utilizzato per il Mediation Server, il numero di utenti VoIP di cui si dispone, il numero di peer gateway che ogni pool Mediation Server controlla, il traffico di ore di punta attraverso tali gateway e la percentuale di chiamate con supporti che ignorano il Mediation Server.

Nelle tabelle seguenti vengono fornite linee guida per il numero di chiamate simultanee che un Mediation Server è in grado di gestire, presupponendo che l'hardware per i Mediation Server soddisfi i requisiti delle piattaforme hardware dei [server](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) e che l'hyperthreading sia abilitato. Per informazioni dettagliate sulla scalabilità di Mediation Server, vedere Stima dell'utilizzo vocale e del traffico per [Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) e linee guida per la distribuzione di Mediation Server in Skype for Business [Server.](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)

Tutte le tabelle seguenti presuppongono l'utilizzo come riepilogato nei [modelli utente in Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

**Capacità mediation server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non bypass (transcodnzione multimediale eseguita dal Mediation Server)**

|**Hardware dei server**|**Numero massimo di chiamate**|**Numero massimo di linee T1**|**Numero massimo di linee E1**|
|:-----|:-----|:-----|:-----|
|Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore con **hyperthreading** disabilitato, con 64 GB di memoria e una scheda di rete a due porte.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore, con 64 GB di memoria e una scheda di rete a due porte.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Sebbene i server con 64 GB di memoria siano stati utilizzati per il testing delle prestazioni, i server con 32 GB di memoria sono supportati per il Mediation Server autonomo e sono sufficienti a garantire le prestazioni illustrate in questa tabella.

**Capacità mediation server (Mediation Server collocato con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non bypass (elaborazione multimediale eseguita dal Mediation Server)**

|**Hardware dei server**|**Numero massimo di chiamate**|
|:-----|:-----|
|Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore, con 64 GB di memoria e 2 schede di rete da 1 GB.  <br/> |200  <br/> |

> [!NOTE]
> Questo numero è molto più piccolo rispetto ai numeri del Mediation Server autonomo. Questo perché il Front End Server deve gestire altre funzionalità e funzioni per i 6600 utenti ospitati su di esso, oltre alla transcoddtura necessaria per le chiamate vocali.

> [!NOTE]
> Per migliorare le prestazioni del Mediation Server, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) nelle schede di rete nei Mediation Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere " Ridimensionamento sul[lato ricezione in Windows Server 2012".](https://go.microsoft.com/fwlink/p/?linkId=268731) Per informazioni dettagliate su come abilitare RSS, è necessario fare riferimento alla documentazione della scheda di rete.

## <a name="back-end-server"></a>Server back-end

Sebbene gran parte delle informazioni sui database sia archiviata principalmente nei Front End Server, è consigliabile verificare che i server back-end soddisfino i suggerimenti relativi all'hardware elencati in precedenza in questa sezione e nelle piattaforme [hardware dei server.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Per garantire la disponibilità elevata del server back-end, è consigliabile distribuire i gruppi di disponibilità AlwaysOn o il mirroring del server. Per ulteriori informazioni, vedere [Disponibilità elevata del server back-end in Skype for Business Server.](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

Se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei Front End Server, ognuno dei quali utilizza il proprio archivio database, separato dall'archivio back-end. In alternativa, se è stato distribuito Exchange 2013, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

Nella tabella seguente viene indicata approssimativamente la quantità di spazio di archiviazione del database necessaria per utente al giorno per i dati di monitoraggio e archiviazione.

||**CDR (Monitoraggio)** <br/> |**QoE (monitoraggio)** <br/> |**Archiviazione** <br/> |
|:-----|:-----|:-----|:-----|
|Spazio su disco richiesto per utente al giorno  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft ha utilizzato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante i test delle prestazioni. Il test ha raccolto i dati di due pool Front End, ognuno dei quali conteneva 80.000 utenti.

**Hardware utilizzato nei test delle prestazioni di monitoraggio e archiviazione**

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 v3 dual, 6 core, 2,4 gigahertz (GHz) o superiore.  <br/> |
|Memoria  <br/> |48 GB  <br/> |
|Disco  <br/> | UNO DEI DUE:<br/> • 4 o più unità disco rigido da 1.0000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione RAID 1 2x). <br/>OPPURE <br/>• Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 4 unità disco meccaniche da 10000 RPM.   <br/> |
|Rete  <br/> | 1 scheda di rete a due porte, 1 Gbps o superiore (2 consigliato, che richiede l'utilizzo di un singolo indirizzo MAC e di un singolo indirizzo IP).  <br/> |

**Configurazioni disco consigliate**

|**Unità** <br/> |**Configurazione RAID** <br/> |**Numero di dischi** <br/> |
|:-----|:-----|:-----|
|CdR, QoE e file di dati del database di archiviazione in una singola unità  <br/> |1+0  <br/> |16   <br/> |
|File di registro del database CDR  <br/> |1   <br/> |2   <br/> |
|File di registro del database QoE  <br/> |1   <br/> |2   <br/> |
|File di registro del database di archiviazione  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Capacità di Video Interop Server

Se si distribuisce Video Interop Server ed è necessario determinare la capacità, si osserva il numero massimo di VTC (Video Teleconferencing Systems) che saranno presenti in chiamate simultanee. Ad esempio, se nell'organizzazione sono presenti 250 VTC e il modello utente stima che al massimo il 20% di essi potrebbe essere in chiamate simultanee, si basa la pianificazione della capacità su 50 VTC simultanei.

