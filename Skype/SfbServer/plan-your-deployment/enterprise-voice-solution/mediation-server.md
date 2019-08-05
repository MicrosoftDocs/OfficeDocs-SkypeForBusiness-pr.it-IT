---
title: Componente Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Informazioni su Mediation Servers in Skype for Business Server, incluse le topologie supportate e le sue relazioni con i trunk M:N, il bypass multimediale e il controllo di ammissione alle chiamate.
ms.openlocfilehash: 8c58e0b866d62e7dd1ea60888ba611d78328489f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187625"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente Mediation Server in Skype for Business Server
 
Informazioni su Mediation Servers in Skype for Business Server, incluse le topologie supportate e le sue relazioni con i trunk M:N, il bypass multimediale e il controllo di ammissione alle chiamate.
  
Per distribuire VoIP aziendale, è necessario distribuire uno o più server di mediazione. 
  
Il Mediation Server traduce il segnale tra l'infrastruttura VoIP aziendale interna e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). In alcune distribuzioni l'elemento multimediale si traduce anche tra questi punti.
  
Sul lato di Skype for Business Server, Mediation Server è in ascolto su un unico indirizzo di trasporto Mutual TLS (MTLS). Sul lato del gateway, Mediation Server è in ascolto su tutte le porte di ascolto associate associate ai trunk. Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP. TCP è supportato per i gateway che non supportano TLS.
  
Se si ha anche un PBX (Public Branch Exchange) esistente nell'ambiente, Mediation Server gestisce le chiamate tra gli utenti di VoIP aziendale e il PBX. Se il PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra il PBX e il Mediation Server. Se il PBX è un PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e il PBX.
  
Il Mediation Server è collocato con il front end server per impostazione predefinita. Il Mediation Server può essere distribuito anche in un pool autonomo.
  
## <a name="what-mediation-server-does"></a>Cosa fa Mediation Server

Di seguito sono riportate le funzioni principali di Mediation Server:
  
- Crittografia e decrittografia di SRTP sul lato di Skype for Business Server. 
    
- Traduzione di SIP su TCP (per i gateway che non supportano TLS) per il SIP tramite TLS reciproco.
    
- Traduzione di flussi multimediali tra Skype for Business Server e il peer gateway del Mediation Server.
    
- Connettere i client esterni alla rete ai componenti ICE interni, che consentono l'attraversamento multimediale di NAT e firewall.
    
- Fungendo da intermediario per i flussi di chiamata non supportati da un gateway, ad esempio le chiamate di operatori remoti in una voce clien. t aziendale
    
- Nelle distribuzioni che includono il trunking SIP, che collabora con il provider di servizi di trunking SIP per ottenere il supporto PSTN, che elimina la necessità di un gateway PSTN.
    
Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali usati dal Mediation Server quando si comunica con un gateway PSTN di base e con l'infrastruttura VoIP aziendale.
  
**Segnalazioni e protocolli multimediali usati dal Mediation Server**

![Diagramma dei protocolli del Mediation Server](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se si usa TCP o RTP/RTCP (invece di SRTP o SRTCP) nella rete tra il gateway PSTN e il Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete. 
  
## <a name="mn-trunk"></a>Trunk con relazioni molti-a-molti

Skype for Business Server supporta la flessibilità nella definizione di un trunk per scopi di routing delle chiamate. Un trunk è un'associazione logica tra un Mediation Server e un numero di porta in ascolto, con un gateway e un numero di porta in ascolto. Questo implica diversi elementi: un Mediation Server può avere più Trunks nello stesso gateway; un Mediation Server può avere più Trunks in Gateway diversi; viceversa, un gateway può avere più Trunks in diversi server di mediazione.
  
È comunque necessario creare un trunk radice quando si aggiunge un gateway alla topologia di Skype for business tramite Generatore di topologie. Il numero di gateway che un server di mediazione specifico può gestire dipende dalla capacità di elaborazione del server durante le ore di punta occupato. Se si distribuisce un Mediation Server su hardware che soddisfa i requisiti hardware minimi per Skype for Business Server, come descritto in [requisiti server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), un Mediation Server autonomo può gestire approssimativamente 1000 chiamate. Il Mediation Server esegue la transcodifica, ma continua a eseguire chiamate per più gateway anche se i gateway non supportano il bypass multimediale.
  
Quando si definisce una route di chiamata, è necessario specificare i trunk associati alla route, ma non si specificano i server di mediazione associati alla route. Puoi invece usare generatore di topologia per associare Trunks a Mediation Servers. In altre parole, il routing determina il trunk da usare per una chiamata e, successivamente, il Mediation Server associato a tale trunk viene inviato alla segnalazione per la chiamata.
  
Il Mediation Server può essere distribuito come pool; questo pool può essere collocato con un pool Front-end oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato in un pool Front-End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrar). Queste funzionalità aumentano la flessibilità di affidabilità e distribuzione per i server di mediazione, ma richiedono funzionalità simili nelle seguenti:
  
- **Gateway PSTN.** Un gateway abilitato per Skype for Business Server deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di fungere da servizio di bilanciamento del carico per un pool di server di mediazione e quindi di effettuare il bilanciamento del carico attraverso il pool .
    
- **Controller di bordo della sessione.** Per un trunk SIP, l'entità peer è un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet. Nella direzione dal pool di Mediation Server a SBC, SBC può ricevere connessioni da qualsiasi server di mediazione nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per raggiungere questo obiettivo è il bilanciamento del carico DNS, se supportato dal provider di servizi e da SBC. In alternativa, è possibile assegnare al provider di servizi gli indirizzi IP di tutti i server di mediazione nel pool e il provider di servizi li provisionerà nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBCs potrebbero supportare queste funzionalità. Inoltre, il provider di servizi può addebitare un supplemento per questa funzionalità. In genere, ogni trunk SIP all'SBC comporta una tariffa mensile.
    
- **IP-PBX.** Nella direzione dal pool di Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi server di mediazione nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la maggior parte dei sistemi IP-PBX non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette da IP-PBX a ogni Mediation Server nel pool. L'IP-PBX gestirà il proprio bilanciamento del carico distribuendo il traffico sul gruppo Trunk. Il presupposto è che il gruppo Trunk abbia una serie di regole di routing coerenti in IP-PBX. Se un determinato IP-PBX supporta questo concetto di gruppo Trunk e il modo in cui interseca l'architettura di ridondanza e clustering dell'IP-PBX deve essere determinato prima di poter decidere se un cluster di Mediation Server può interagire correttamente con un IP-PBX.
    
Un pool di Mediation Server deve avere una visualizzazione uniforme del gateway peer con cui interagisce. Questo significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione e hanno ugualmente la possibilità di interagire con essa per le chiamate in uscita. Di conseguenza, non è possibile segmentare il pool in modo che alcuni Mediation Server comunicano solo con determinati peer del gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario usare un pool separato di server di mediazione. Questo è il caso, ad esempio, se le funzionalità associate in gateway PSTN, trunk SIP o IP-PBX per interagire con un pool come descritto in precedenza in questo argomento non sono presenti.
  
Un particolare gateway PSTN, IP-PBX o un peer trunk SIP può essere indirizzato a più server di mediazione o trunk. Il numero di gateway che un determinato pool di server di mediazione può controllare dipende dal numero di chiamate che usano il bypass multimediale. Se un numero elevato di chiamate usa il bypass multimediale, un Mediation Server nel pool può gestire molte altre chiamate, perché è necessario solo l'elaborazione dei livelli di segnalazione. 
  
## <a name="call-admission-control-and-mediation-server"></a>Controllo ammissione chiamata e Mediation Server

Controllo di ammissione di chiamata (CAC), gestisce lo stabilimento in tempo reale della sessione, basato sulla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti sulle reti congestionate. Per supportarlo, il Mediation Server è responsabile della gestione della larghezza di banda per le sue due interazioni sul lato del server Skype for business e sul lato gateway. In controllo di ammissione di chiamata, l'entità di terminazione per una chiamata gestisce la prenotazione della larghezza di banda. I peer gateway (gateway PSTN, IP-PBX, SBC) con cui interagisce il Mediation Server sul lato gateway non supportano il controllo di ammissione alle chiamate di Skype for Business Server. Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer del gateway. Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo. Se non è possibile, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer del gateway, la larghezza di banda viene riservata quando viene inserita la chiamata. Questo comportamento può causare un sovraabbonamento della larghezza di banda, ma è l'unico modo per evitare anelli falsi.
  
Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda. Se per una chiamata viene impiegato il bypass multimediale, il controllo di ammissione delle chiamate non viene eseguito per la chiamata. Il presupposto è che non ci sono collegamenti con larghezza di banda limitata coinvolta nella chiamata. Se per una determinata chiamata viene usato il controllo di ammissione alle chiamate che coinvolge il Mediation Server, tale chiamata non può impiegare il bypass multimediale.
  
Per informazioni dettagliate sul controllo del bypass multimediale o sull'ammissione alle chiamate, vedere [pianificare il bypass multimediale in Skype for business](media-bypass.md) o [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Servizi di emergenza avanzati e Mediation Server

Il Mediation Server offre funzionalità estese in modo da poter interagire correttamente con i provider di servizi avanzati di 9-1-1 (E9-1-1). Nel Mediation Server non è necessaria alcuna configurazione speciale. Le estensioni SIP necessarie per l'interazione E9-1-1 sono, per impostazione predefinita, incluse nel protocollo SIP del server di mediazione per le interazioni con un peer gateway (gateway PSTN, IP-PBX o SBC di un provider di servizi di telefonia Internet, incluso il servizio E9-1-1) Provider
  
Se il trunk SIP a un provider di servizi E9-1-1 può essere terminato in un pool di Mediation Server esistente o richiederà che i server di mediazione autonoma dipendano dal fatto che il SBC-1-1 può interagire con un pool di server di mediazione. Per informazioni dettagliate, vedere [trunk di M:N in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Bypass multimediale e Mediation Server

Media Bypass è una funzionalità di Skype for Business Server che consente a un amministratore di configurare il routing delle chiamate in modo che fluisca direttamente tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il server Mediation. Il bypass multimediale migliora la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore. Se un sito remoto senza un Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il fabbisogno di larghezza di banda consentendo agli elementi multimediali di un client in un sito remoto di scorrere direttamente nel gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa. Questa riduzione dell'elaborazione multimediale completa inoltre la capacità del server mediatore di controllare più gateway.
  
Il bypass multimediale e il controllo di ammissione delle chiamate (CAC) si escludono a vicenda. Se per una chiamata viene usato il bypass multimediale, CAC non viene eseguito per la chiamata. Il presupposto è che non ci sono collegamenti con larghezza di banda vincolata coinvolta nella chiamata.
  
## <a name="topologies-for-mediation-server"></a>Topologie per Mediation Server

Il server di Skype for business, Mediation Server è collocato per impostazione predefinita con il server Standard Edition, un pool Front-end o un Survivable Branch Appliance. Tutti i Mediation Server in un pool Front-end devono essere configurati in modo identico.
  
In caso di problemi di prestazioni, può essere preferibile distribuire uno o più server di mediazione in un pool autonomo dedicato. Se si distribuisce il trunking SIP, è consigliabile un pool autonomo. 
  
Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool di Mediation Server autonomo. Il motivo è che i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool.
  
È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:
  
- IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.
    
- IP-PBX non supporta il bypass multimediale, ma il pool Front-end che ospita il Mediation Server può gestire la transcodifica vocale per le chiamate a cui il bypass multimediale non si applica.
    
È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
La figura seguente mostra una semplice topologia costituita da due siti collegati da un collegamento WAN. Mediation Server è collocato in un pool Front-End nel sito 1. I Mediation Server del sito 1 controllano sia il gateway PSTN sul sito 1 che il gateway nel sito 2. In questa topologia, il bypass multimediale è abilitato globalmente per l'uso delle informazioni sul sito e le aree geografiche e i trunk per ogni gateway PSTN (GW1 e GW2) hanno un bypass abilitato.
  
**Esempio di siti collegati da un collegamento WAN a un Mediation Server presso il sito 1 e un gateway PSTN sul sito 2**

![Topologia vocale con Mediation Server e gateway WAN](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Nella figura seguente è illustrata una semplice topologia in cui Mediation Server è collocato nel pool Front-end del sito 1 e ha una connessione SIP diretta con IP-PBX nel sito 1. In questa figura il Mediation Server controlla anche un gateway PSTN sul sito 2. Supponiamo che gli utenti di Skype for business siano presenti in entrambi i siti 1 e 2. Supponiamo inoltre che IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti i contenuti multimediali provenienti da endpoint Skype for business prima di essere inviati agli endpoint multimediali controllati da IP-PBX. In questa topologia, il bypass multimediale è abilitato globalmente per l'uso di informazioni sul sito e le aree geografiche e i Trunks per il PBX e il gateway PSTN sono abilitati per il bypass multimediale.
  
**Esempio di siti collegati da un collegamento WAN con un Mediation Server presso il sito 1 e un PBX presso il sito 2**

![Topologia vocale con Mediation Server e PBX WAN](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
L'ultima figura in questo argomento Mostra una topologia in cui il Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisioni di pianificazione per Mediation Server

Questo argomento descrive le decisioni di pianificazione che è necessario apportare per la distribuzione di Mediation Server
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Mediation Server è collocato per impostazione predefinita nel server Standard Edition o front end server in un pool Front-end presso i siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderà dalle operazioni seguenti:
  
- Numero di peer gateway che il pool di Mediation Server controlla
    
- I periodi di traffico ad alto volume tramite questi gateway
    
- Percentuale di chiamate che vengono chiamate il cui elemento multimediale ignora il Mediation Server
    
Quando si pianifica, tenere presente che i requisiti di elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V non sono configurati per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario occupato che è necessario essere supportato. Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server; i gateway PSTN, IP-PBX e SBCs dovranno essere divisi in subset controllati dai server di mediazione collocati in un pool e i Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di server di mediazione, inclusi i seguenti, sarà necessario associarli a un pool autonomo costituito da di un singolo Mediation Server:
  
- Eseguire il bilanciamento del carico DNS (Network layer Domain Name System) in Mediation Servers in un pool (o in caso contrario instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)
    
- Accettare il traffico da qualsiasi Mediation Server in un pool
    
È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione di Mediation Server con il pool Front-end può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerazioni sul sito centrale e sulla filiale

 I Mediation Server nel sito centrale possono essere usati per instradare le chiamate per i PBX IP o i gateway PSTN nei siti di succursale. Se si distribuiscono trunk SIP, tuttavia, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina. L'uso di un Mediation Server presso la route del sito centrale richiede un gateway IP-PBX o PSTN presso un sito di succursale non richiede l'utilizzo di bypass multimediale. Tuttavia, se è possibile abilitare il bypass multimediale, questa operazione ridurrà la latenza dei percorsi multimediali e migliorerà la qualità multimediale, perché il percorso del supporto non è più necessario per seguire il percorso di segnalazione. Il bypass multimediale riduce anche il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Se è necessaria la resilienza del sito di succursale, è necessario distribuire un Survivable Branch Appliance o una combinazione di un server front-end, un Mediation Server e un gateway nel sito della filiale. Il presupposto con la resilienza del sito di succursale è che la presenza e i servizi di conferenza non sono resilienti nel sito. Per informazioni sulla pianificazione del sito di succursale per la voce, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](enterprise-voice-resiliency.md).
  
Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e interazioni RFC 3960, può essere possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo da IP-PBX a Skype for Endpoint aziendali. Questo problema può essere più grave se un Mediation Server presso un sito centrale sta instradando le chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione. Se si verifica questo comportamento, la distribuzione di un Mediation Server presso il sito della filiale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se il sito centrale ha un PBX TDM o se il tuo IP-PBX non elimina la necessità di un gateway PSTN, devi distribuire un gateway sulla route di chiamata che connette Mediation Server e il PBX.
  
> [!NOTE]
> Per migliorare le prestazioni multimediali di Mediation Server autonomo, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete in questi server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere ["miglioramenti della scala sul lato ricezione in Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete. 
  

