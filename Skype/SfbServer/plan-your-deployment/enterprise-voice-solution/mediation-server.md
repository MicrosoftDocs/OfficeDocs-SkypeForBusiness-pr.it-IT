---
title: Componente di Mediation Server in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Informazioni su Mediation Server in Skype for Business Server, incluse le topologie supportate e le relative relazioni ai trunk M:N, al bypass multimediale e al controllo di ammissione di chiamata.
ms.openlocfilehash: 14cf5fff38146622467698ffa58ccb244fac8fad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813676"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente di Mediation Server in Skype for Business Server
 
Informazioni su Mediation Server in Skype for Business Server, incluse le topologie supportate e le relative relazioni ai trunk M:N, al bypass multimediale e al controllo di ammissione di chiamata.
  
Per distribuire VoIP aziendale, è necessario distribuire uno o più Mediation Server. 
  
Il Mediation Server converte la segnalazione tra l'infrastruttura VoIP aziendale interna e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). In alcune distribuzioni, anche il contenuto multimediale viene traslato tra questi punti.
  
Sul fronte di Skype for Business Server, Mediation Server è in attesa su un singolo indirizzo di trasporto Mutual TLS (MTLS). Sul fronte del gateway, Mediation Server è in attesa su tutte le porte di attesa associate ai trunk. Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP. TCP è supportato per i gateway che non supportano TLS.
  
Se nel proprio ambiente è presente anche un PBX (Public Branch Exchange), Mediation Server gestisce le chiamate tra gli utenti di VoIP aziendale e il sistema PBX. Se il sistema PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra il PBX e il Mediation Server. Se il PBX è un PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e il sistema PBX.
  
Il Mediation Server è collocato con il front end server per impostazione predefinita. Il Mediation Server può anche essere distribuito in un pool autonomo.
  
## <a name="what-mediation-server-does"></a>Cosa fa Mediation Server

Di seguito sono riportate le funzioni principali del Mediation Server:
  
- Crittografia e decrittografia di SRTP sul server Skype for business. 
    
- Conversione di SIP su TCP (per i gateway che non supportano TLS) per SIP su TLS reciproco.
    
- Tradurre i flussi multimediali tra Skype for Business Server e il peer gateway del Mediation Server.
    
- Connettere i client che si trovano all'esterno della rete per i componenti ICE interni, che consentono l'attraversamento multimediale di NAT e firewall.
    
- Che funge da intermediario per i flussi di chiamata che un gateway non supporta, ad esempio le chiamate da operatori remoti su un VoIP aziendale clien. t
    
- Nelle distribuzioni che includono il trunking SIP, l'utilizzo del provider di servizi di trunking SIP per fornire il supporto PSTN, eliminando la necessità di un gateway PSTN.
    
Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali utilizzati dal Mediation Server per la comunicazione con un gateway PSTN di base e l'infrastruttura VoIP aziendale.
  
**Protocolli di segnalazione e multimediali utilizzati dal Mediation Server**

![Diagramma protocolli Mediation Server](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se si utilizza TCP o RTP/RTCP (invece di SRTP o SRTCP) sulla rete tra il gateway PSTN e il Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete. 
  
## <a name="mn-trunk"></a>Trunk M:N

Skype for Business Server supporta la flessibilità per la definizione di un trunk per il routing delle chiamate. Un trunk è un'associazione logica tra un Mediation Server e un numero di porta di attesa, con un gateway e un numero di porta di attesa. Questo implica diverse operazioni: un Mediation Server può disporre di più trunk allo stesso gateway; un Mediation Server può disporre di più trunk per Gateway diversi; viceversa, un gateway può disporre di più trunk per diversi Mediation Server.
  
È comunque necessario creare un trunk radice quando si aggiunge un gateway alla topologia di Skype for business tramite Generatore di topologie. Il numero di gateway che un determinato Mediation Server può gestire dipende dalla capacità di elaborazione del server durante le ore di punta occupato. Se si distribuisce un Mediation Server sull'hardware che soddisfa i requisiti hardware minimi per Skype for Business Server, come descritto in [requisiti server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), un Mediation Server autonomo può gestire circa 1000 chiamate. Il Mediation Server esegue la transcodifica, ma continua a instradare le chiamate per più gateway anche se i gateway non supportano il bypass multimediale.
  
Quando si definisce una route di chiamata, è necessario specificare i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati a tale route. In alternativa, è possibile utilizzare il generatore di topologie per associare trunk a Mediation Server. In altre parole, il routing determina quale trunk utilizzare per una chiamata e, successivamente, il Mediation Server associato a tale trunk viene inviato alla segnalazione per la chiamata.
  
Il Mediation Server può essere distribuito come pool. questo pool può essere collocato con un pool Front end oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato con un pool Front End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrazione). Insieme, queste funzionalità aumentano la flessibilità di affidabilità e distribuzione per i Mediation Server, ma richiedono funzionalità simili nelle seguenti:
  
- **Gateway PSTN.** Un gateway abilitato per Skype for Business Server deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di fungere da servizio di bilanciamento del carico per un pool di Mediation Server e, quindi, per il bilanciamento del carico delle chiamate tra il pool.
    
- **Session border controller.** Per un trunk SIP, l'entità peer è un session border controller (SBC) in un provider di servizi di telefonia Internet. Nella direzione del pool di Mediation Server verso l'SBC, l'SBC può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per raggiungere questo obiettivo avviene tramite il bilanciamento del carico DNS, se supportato dal provider di servizi e dal servizio SBC. Un'alternativa consiste nel fornire al provider di servizi gli indirizzi IP di tutti i Mediation Server nel pool e il provider di servizi provisionerà questi nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBCs possono supportare queste funzionalità. Inoltre, è possibile che il provider di servizi richieda una tariffa supplementare per questa funzionalità. In genere, ciascun trunk SIP per il SBC comporta una tariffa mensile.
    
- **IP-PBX.** Nella direzione dal pool di Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la maggior parte IP-PBXs non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette dall'IP-PBX a ogni Mediation Server nel pool. Il sistema IP-PBX gestirà quindi il bilanciamento del carico distribuendo il traffico sul gruppo di trunk. Si presuppone che il gruppo di trunk disponga di un insieme coerente di regole di routing nel sistema IP-PBX. Se un determinato IP-PBX supporta questo concetto di gruppo Trunk e la modalità di intersezione con la ridondanza e l'architettura di clustering del sistema IP-PBX deve essere determinata prima di poter decidere se un cluster di Mediation Server può interagire correttamente con un IP-PBX.
    
Un pool di Mediation Server deve disporre di una visualizzazione uniforme del gateway peer con cui interagisce. Questo significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione e sono ugualmente suscettibili di interagire con esso per le chiamate in uscita. Pertanto, non esiste alcun modo per segmentare il pool in modo che alcuni Mediation Server comunicano con solo alcuni peer gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario utilizzare un pool separato di Mediation Server. Questo è il caso, ad esempio, se le funzionalità associate nei gateway PSTN, trunk SIP o IP-PBXs di interagire con un pool come descritto in precedenza in questo argomento non sono presenti.
  
Un particolare gateway PSTN, IP-PBX o peer trunk SIP può essere instradato a più server Mediation o trunk. Il numero di gateway che un pool specifico di Mediation Server può controllare dipende dal numero di chiamate che utilizzano il bypass multimediale. Se un numero elevato di chiamate utilizza il bypass multimediale, un Mediation Server nel pool è in grado di gestire molte più chiamate, perché è necessario solo l'elaborazione dei layer di segnalazione. 
  
## <a name="call-admission-control-and-mediation-server"></a>Servizio Controllo di ammissione di chiamata e Mediation Server

Call Admission Control (CAC), gestisce l'establishment delle sessioni in tempo reale, in base alla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti nelle reti congestionate. Per supportarlo, il Mediation Server è responsabile della gestione della larghezza di banda per le sue due interazioni sul fronte del server Skype for business e sul fianco del gateway. Nel controllo di ammissione di chiamata, l'entità di terminazione di una chiamata deve gestire la prenotazione della larghezza di banda. I peer gateway (gateway PSTN, IP-PBX, SBC) su cui interagiscono i Mediation Server con il gateway non supportano il controllo di ammissione di chiamata di Skype for Business Server. Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer gateway. Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo. In caso contrario, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer gateway, la larghezza di banda viene riservata al momento dell'esecuzione della chiamata. Questo comportamento può causare una richiesta eccessiva di larghezza di banda, ma è l'unico modo per impedire squilli falsi..
  
Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamata non viene eseguito per la chiamata. Il concetto alla base di questo comportamento è che non vi sono collegamenti con larghezza di banda limitata interessati dalla chiamata. Se il controllo di ammissione di chiamata viene utilizzato per una chiamata specifica che implica il Mediation Server, la chiamata non può impiegare il bypass multimediale.
  
Per informazioni dettagliate sul bypass multimediale o sul controllo di ammissione di chiamata, vedere [Plan for Media Bypass in Skype for business](media-bypass.md) o [Plan for Call Admission Control in Skype for Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Enhanced 9-1-1 (E9-1-1) e Mediation Server

Il Mediation Server dispone di funzionalità estese che consentono di interagire correttamente con i provider di servizi Enhanced 9-1-1 (E9-1-1). Non è necessaria alcuna configurazione speciale sul Mediation Server. Le estensioni SIP richieste per l'interazione E9-1-1 sono, per impostazione predefinita, incluse nel protocollo SIP del Mediation Server per le interazioni con un peer gateway (gateway PSTN, IP-PBX o SBC di un provider di servizi di telefonia Internet, inclusi i provider di servizi E9-1-1)
  
Se il trunk SIP di un provider di servizi E9-1-1 può essere interrotto su un pool di Mediation Server esistente o richiederà Mediation Server autonomi, dipenderà dalla possibilità di interagire con un pool di Mediation Server. Per informazioni dettagliate, vedere [Trunk M:N in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Bypass multimediale e Mediation Server

Il bypass multimediale è una funzionalità di Skype for Business Server che consente a un amministratore di configurare il routing delle chiamate per il flusso direttamente tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il Mediation Server. Il bypass multimediale consente di migliorare la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore. Se un sito remoto senza Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito remoto di fluire direttamente sul gateway locale senza prima dover fluire sul collegamento WAN a un Mediation Server nel sito centrale e viceversa. Questa riduzione dell'elaborazione multimediale integra inoltre la capacità del Mediation Server di controllare più gateway.
  
Le funzionalità di bypass multimediale e controllo di ammissione di chiamata (CAC) si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamate per tale chiamata non viene eseguito. Il presupposto è che nella chiamata non siano coinvolti link con larghezza di banda limitata.
  
## <a name="topologies-for-mediation-server"></a>Topologie per Mediation Server

Il server di Skype for business, Mediation Server è collocato per impostazione predefinita con il server Standard Edition, un pool Front end o un Survivable Branch Appliance. Tutti i Mediation Server in un pool Front end devono essere configurati in modo identico.
  
Se le prestazioni sono un problema, potrebbe essere preferibile distribuire uno o più Mediation Server in un pool autonomo dedicato. Se si sta distribuendo il trunking SIP, è consigliabile utilizzare un pool autonomo. 
  
Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool Mediation Server autonomo. Questo perché i gateway qualificati sono in grado di eseguire il bilanciamento del carico DNS in un pool di Mediation Server e possono ricevere traffico da qualsiasi Mediation Server in un pool.
  
È inoltre consigliabile collocare il Mediation Server in un pool Front end quando è stata distribuita IP-PBXs o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:
  
- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.
    
- Il sistema IP-PBX non supporta il bypass multimediale, ma il pool Front end che ospita il Mediation Server è in grado di gestire la transcodifica vocale per le chiamate a cui non si applica il bypass multimediale.
    
È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool Front end in cui si desidera collocare il Mediation Server è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
Nella figura seguente viene illustrata una semplice topologia costituita da due siti connessi tramite un collegamento WAN. Mediation Server è collocato in un pool Front End nel sito 1. I Mediation Server nel sito 1 controllano sia il gateway PSTN nel sito 1 che il gateway nel sito 2. In questa topologia il bypass multimediale è abilitato a livello globale per utilizzare informazioni su siti e aree ed è abilitato anche per i trunk a ogni gateway PSTN (GW1 e GW2).
  
**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un gateway PSTN nel sito 2**

![Topologia vocale con gateway WAN Mediation Server](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Nella figura seguente è illustrata una topologia semplice in cui Mediation Server è collocato nel pool Front end del sito 1 e dispone di una connessione SIP diretta al sistema IP-PBX nel sito 1. In questa figura, Mediation Server controlla anche un gateway PSTN nel sito 2. Si supponga che gli utenti di Skype for business siano presenti in entrambi i siti 1 e 2. Si supponga inoltre che il sistema IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti i supporti provenienti da endpoint Skype for business prima di essere inviati agli endpoint multimediali controllati dall'IP-PBX. In questa topologia, il bypass multimediale è abilitato a livello globale per l'utilizzo delle informazioni relative a siti e aree geografiche, mentre i trunk del PBX e del gateway PSTN dispongono del bypass multimediale abilitato.
  
**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un sistema PBX nel sito 2**

![Topologia vocale Mediation Server WAN PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
Nell'ultima figura di questo argomento viene illustrata una topologia in cui Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisioni di pianificazione per Mediation Server

In questo argomento vengono descritte le decisioni di pianificazione necessarie per la distribuzione di Mediation Server.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Per impostazione predefinita, Mediation Server è collocato nel server Standard Edition o Front End Server in un pool Front-End nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipendono dai seguenti elementi:
  
- Il numero di peer gateway che il pool di Mediation Server controlla
    
- I periodi di traffico ad alto volume tramite quei gateway
    
- La percentuale di chiamate che sono chiamate con il supporto bypassare il Mediation Server
    
Durante la pianificazione, tenere conto dei requisiti di elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V che non sono configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di occupato che devono essere supportate. Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server. i gateway PSTN, IP-PBX e SBCs dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e nei Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di Mediation Server, tra cui i seguenti, dovranno essere associati a un pool autonomo costituito da un singolo Mediation Server:
  
- Eseguire il bilanciamento del carico DNS (Domain Name System) di Network layer su Mediation Server in un pool (o altrimenti instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)
    
- Accettazione del traffico proveniente da qualsiasi server Mediation Server in un pool
    
È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

 I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un server Mediation Server presso il sito in cui ogni trunk termina. Per fare in modo che un server Mediation Server nel sito centrale instradi le chiamate per un IP-PBX o un gateway PSTN in un sito derivato, non è necessario utilizzare Media Bypass. Tuttavia, se è possibile abilitare il bypass multimediale, in questo modo si riduce la latenza del percorso multimediale e si migliora la qualità multimediale perché il percorso multimediale non è più necessario per seguire il percorso di segnalazione. Il bypass multimediale diminuisce anche il carico di elaborazione del pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel [programma Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. (L'assunzione con resilienza del sito di succursale è che la presenza e la conferenza non sono resilienti nel sito). Per istruzioni sulla pianificazione dei siti di succursale per la voce, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](enterprise-voice-resiliency.md).
  
Per le interazioni con un IP-PBX, se il sistema IP-PBX non supporta correttamente le interazioni tra i media iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile che vengano ritagliate le prime parole del messaggio di saluto per le chiamate in arrivo dal sistema IP-PBX agli endpoint Skype for business. Questo problema può essere più grave se un Mediation Server in un sito centrale è il routing delle chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.
  
> [!NOTE]
> Per migliorare le prestazioni dei supporti di Mediation Server autonomo, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete su questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere la [sezione relativa ai miglioramenti della scala di ricezione in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731). Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete. 
  

