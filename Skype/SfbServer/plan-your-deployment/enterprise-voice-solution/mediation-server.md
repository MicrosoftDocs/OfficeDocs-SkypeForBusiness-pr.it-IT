---
title: Componente Mediation Server in Skype for Business Server
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
description: Informazioni sui Mediation Server in Skype for Business Server, incluse le topologie supportate e le relative relazioni con i trunk M:N, il bypass multimediale e il controllo di ammissione di chiamata.
ms.openlocfilehash: 9e333486eeae4831604a4e4593dc0a65b4e6588eb38cc08df1b9c2a7ee9dcdcd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284656"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente Mediation Server in Skype for Business Server
 
Informazioni sui Mediation Server in Skype for Business Server, incluse le topologie supportate e le relative relazioni con i trunk M:N, il bypass multimediale e il controllo di ammissione di chiamata.
  
Per distribuire VoIP aziendale, è necessario distribuire uno o più Mediation Server. 
  
Mediation Server converte la segnalazione tra l'infrastruttura VoIP aziendale interna e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). In alcune distribuzioni, converte anche il contenuto multimediale stesso tra questi punti.
  
Sul lato Skype for Business Server, Mediation Server è in ascolto su un singolo indirizzo di trasporto MTLS (Mutual TLS). Sul lato gateway, Mediation Server è in ascolto su tutte le porte di attesa associate ai trunk. Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP. TCP è supportato per i gateway che non supportano TLS.
  
Se nell'ambiente è presente anche un sistema PBX (Public Branch Exchange), Mediation Server gestisce le chiamate tra VoIP aziendale utenti e il SISTEMA PBX. Se il SISTEMA PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra pbx e Mediation Server. Se il SISTEMA PBX è un SISTEMA PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e pbx.
  
Il Mediation Server è collocato con il Front End Server per impostazione predefinita. Il Mediation Server può essere distribuito anche in un pool autonomo.
  
## <a name="what-mediation-server-does"></a>Cosa fa Mediation Server

Le funzioni principali del Mediation Server sono le seguenti:
  
- Crittografia e decrittografia di SRTP sul Skype for Business Server lato. 
    
- Conversione di SIP su TCP (per i gateway che non supportano TLS) a SIP su TLS reciproco.
    
- Traduzione di flussi multimediali tra Skype for Business Server e il peer gateway del Mediation Server.
    
- Connessione di client esterni alla rete a componenti ICE interni, che consentono l'attraversamento multimediale di NAT e firewall.
    
- Funge da intermediario per i flussi di chiamata non supportati da un gateway, ad esempio le chiamate provenienti da lavoratori remoti su un VoIP aziendale clien.t
    
- Nelle distribuzioni che includono il trunking SIP, l'utilizzo del provider di servizi di trunking SIP per fornire il supporto PSTN elimina la necessità di un gateway PSTN.
    
Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali utilizzati dal Mediation Server durante la comunicazione con un gateway PSTN di base e l'VoIP aziendale di rete.
  
**Protocolli di segnalazione e multimediali utilizzati dal Mediation Server**

![Diagramma dei protocolli mediation server](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se si utilizza TCP o RTP/RTCP (anziché SRTP o SRTCP) nella rete tra il gateway PSTN e Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete. 
  
## <a name="mn-trunk"></a>Trunk M:N

Skype for Business Server supporta la flessibilità nella definizione di un trunk a scopo di routing delle chiamate. Un trunk è un'associazione logica tra un Mediation Server e un numero di porta di attesa, con un gateway e un numero di porta di attesa. Ciò implica diversi aspetti: un Mediation Server può avere più trunk per lo stesso gateway; un Mediation Server può avere più trunk a gateway diversi; al contrario, un gateway può avere più trunk per Mediation Server diversi.
  
È comunque necessario creare un trunk radice quando si aggiunge un gateway alla topologia Skype for Business utilizzando Generatore di topologie. Il numero di gateway che un determinato Mediation Server è in grado di gestire dipende dalla capacità di elaborazione del server durante le ore di punta. Se si distribuisce un Mediation Server su hardware che soddisfa i requisiti hardware minimi per Skype for Business Server, come descritto [in Server requirements for Skype for Business Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)un Mediation Server autonomo può gestire circa 1000 chiamate. Il Mediation Server esegue la transcodtura, ma instrada comunque le chiamate per più gateway anche se i gateway non supportano il bypass multimediale.
  
Quando si definisce una route di chiamata, si specificano i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati a tale route. È invece possibile utilizzare Generatore di topologie per associare i trunk ai Mediation Server. In altre parole, il routing determina quale trunk utilizzare per una chiamata e, successivamente, al Mediation Server associato a tale trunk viene inviata la segnalazione per tale chiamata.
  
Il Mediation Server può essere distribuito come pool. questo pool può essere collocato con un pool Front End oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato con un pool Front End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrazione). Nel loro insieme, queste funzionalità aumentano l'affidabilità e la flessibilità di distribuzione per Mediation Server, ma richiedono funzionalità simili nelle seguenti:
  
- **Gateway PSTN.** Un gateway qualificato Skype for Business Server deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di agire come servizio di bilanciamento del carico per un pool di Mediation Server e quindi di bilanciare il carico delle chiamate nel pool.
    
- **Session Border Controller.** Per un trunk SIP, l'entità peer è un session border controller (SBC) presso un provider di servizi di telefonia Internet. Nella direzione dal pool Mediation Server al servizio SBC, il controller SBC può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per ottenere questo risultato è tramite il bilanciamento del carico DNS, se supportato dal provider di servizi e da SBC. Un'alternativa consiste nel fornire al provider di servizi gli indirizzi IP di tutti i Mediation Server nel pool e il provider di servizi ne eseguirà il provisioning nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBC possono supportare queste funzionalità. Inoltre, il provider di servizi può addebitare costi aggiuntivi per questa funzionalità. In genere, ogni trunk SIP alla SBC comporta una tariffa mensile.
    
- **IP-PBX.** Nella direzione dal pool Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la IP-PBXs non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette da IP-PBX a ogni Mediation Server del pool. Il sistema IP-PBX gestirà quindi il bilanciamento del carico distribuendo il traffico sul gruppo di trunk. Si presuppone che il gruppo di trunk disponga di un insieme coerente di regole di routing nel sistema IP-PBX. Prima di poter decidere se un cluster Mediation Server può interagire correttamente con un IP-PBX, è necessario stabilire se un particolare IP-PBX supporta questo concetto di gruppo trunk e come si interseca con l'architettura di ridondanza e clustering del sistema IP-PBX.
    
Un pool Mediation Server deve disporre di una visualizzazione uniforme del gateway peer con cui interagisce. Ciò significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione ed è altrettanto probabile che interagiranno con esso per le chiamate in uscita. Pertanto, non è possibile segmentare il pool in modo che alcuni Mediation Server comunichino solo con determinati peer gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario utilizzare un pool separato di Mediation Server. Ciò si verifica, ad esempio, se le funzionalità associate nei gateway PSTN, nei trunk SIP o IP-PBXs per interagire con un pool come descritto in precedenza in questo argomento non sono presenti.
  
Un determinato gateway PSTN, IP-PBX o trunk peer SIP può essere instradato a più Mediation Server o trunk. Il numero di gateway che un determinato pool di Mediation Server può controllare dipende dal numero di chiamate che utilizzano il bypass multimediale. Se un numero elevato di chiamate utilizza il bypass multimediale, un Mediation Server nel pool può gestire molte altre chiamate, perché è necessaria solo l'elaborazione del livello di segnalazione. 
  
## <a name="call-admission-control-and-mediation-server"></a>Servizio Controllo di ammissione di chiamata e Mediation Server

Controllo di ammissione di chiamata gestisce la creazione di sessioni in tempo reale, in base alla larghezza di banda disponibile, per evitare problemi di qualità dell'esperienza (QoE) per gli utenti su reti congestionate. A tale scopo, Mediation Server è responsabile della gestione della larghezza di banda per le sue due interazioni sul lato Skype for Business Server e sul lato gateway. Nel controllo di ammissione di chiamata, l'entità di terminazione di una chiamata deve gestire la prenotazione della larghezza di banda. I peer gateway (gateway PSTN, IP-PBX, SBC) con cui il Mediation Server interagisce sul lato gateway non supportano il Skype for Business Server di ammissione di chiamata. Il Mediation Server deve pertanto gestire le interazioni con la larghezza di banda per conto del peer gateway. Quando possibile, Mediation Server riserva la larghezza di banda in anticipo. In caso contrario, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer gateway, la larghezza di banda viene riservata al momento dell'esecuzione della chiamata. Questo comportamento può causare una richiesta eccessiva di larghezza di banda, ma è l'unico modo per impedire squilli falsi..
  
Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamata non viene eseguito per tale chiamata. Il concetto alla base di questo comportamento è che non vi sono collegamenti con larghezza di banda limitata interessati dalla chiamata. Se viene utilizzato il controllo di ammissione di chiamata per una determinata chiamata che coinvolge il Mediation Server, tale chiamata non può utilizzare il bypass multimediale.
  
Per informazioni dettagliate sul bypass multimediale o sul controllo di ammissione di chiamata, vedere [Plan for media bypass in Skype for Business](media-bypass.md) o Plan for call admission control in [Skype for Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Enhanced 9-1-1 (E9-1-1) e Mediation Server

Mediation Server dispone di funzionalità estese che consentono di interagire correttamente con i provider di servizi Enhanced 9-1-1 (E9-1-1). Non è necessaria alcuna configurazione speciale nel Mediation Server. Le estensioni SIP necessarie per l'interazione E9-1-1 sono, per impostazione predefinita, incluse nel protocollo SIP del Mediation Server per le interazioni con un peer gateway (gateway PSTN, IP-PBX o SBC di un provider di servizi di telefonia Internet, inclusi i provider di servizi E9-1-1)
  
Se il trunk SIP a un provider di servizi E9-1-1 può essere terminato in un pool Mediation Server esistente o richiederà Mediation Server autonomi, dipenderà se il controller SBC di E9-1-1 può interagire con un pool di Mediation Server. Per informazioni dettagliate, vedere [Trunk M:N in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Bypass multimediale e Mediation Server

Il bypass multimediale è una funzionalità Skype for Business Server che consente a un amministratore di configurare il routing delle chiamate in modo che fluirà direttamente tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il Mediation Server. Il bypass multimediale migliora la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore. Se un sito remoto senza Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda limitata, il bypass multimediale riduce il requisito di larghezza di banda consentendo ai supporti di un client di un sito remoto di fluire direttamente al gateway locale senza dover prima passare attraverso il collegamento WAN a un Mediation Server nel sito centrale e di nuovo. Questa riduzione dell'elaborazione multimediale integra inoltre la capacità del Mediation Server di controllare più gateway.
  
Le funzionalità di bypass multimediale e controllo di ammissione di chiamata (CAC) si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamate per tale chiamata non viene eseguito. Il presupposto è che nella chiamata non siano coinvolti link con larghezza di banda limitata.
  
## <a name="topologies-for-mediation-server"></a>Topologie per Mediation Server

Il Skype for Business Server Mediation Server è collocato per impostazione predefinita edizione Standard server, un pool Front End o un Survivable Branch Appliance. Tutti i Mediation Server in un pool Front End devono essere configurati in modo identico.
  
Se le prestazioni sono un problema, può essere preferibile distribuire uno o più Mediation Server in un pool autonomo dedicato. È consigliabile utilizzare un pool autonomo se si distribuisce il trunking SIP. 
  
Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario un pool Mediation Server autonomo. Questo perché i gateway qualificati sono in grado di eseguire il bilanciamento del carico DNS in un pool di Mediation Server e possono ricevere traffico da qualsiasi Mediation Server in un pool.
  
È inoltre consigliabile collocare il Mediation Server in un pool Front End dopo aver distribuito IP-PBXs o connettersi al Session Border Controller (SBC) di un provider di servizi di telefonia Internet, purché siano soddisfatte le condizioni seguenti:
  
- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.
    
- L'IP-PBX non supporta il bypass multimediale, ma il pool Front End che ospita il Mediation Server può gestire la transcodatura vocale per le chiamate a cui il bypass multimediale non è applicabile.
    
È possibile utilizzare lo Strumento di pianificazione di Microsoft Lync Server 2013 per valutare se il pool Front End in cui si desidera collocare il Mediation Server è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
Nella figura seguente viene illustrata una semplice topologia costituita da due siti connessi tramite un collegamento WAN. Mediation Server è collocato in un pool Front End nel sito 1. I Mediation Server nel sito 1 controllano sia il gateway PSTN nel sito 1 che il gateway nel sito 2. In questa topologia il bypass multimediale è abilitato a livello globale per utilizzare informazioni su siti e aree ed è abilitato anche per i trunk a ogni gateway PSTN (GW1 e GW2).
  
**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un gateway PSTN nel sito 2**

![Topologia vocale con gateway WAN Mediation Server](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Nella figura seguente viene illustrata una topologia semplice in cui Mediation Server è collocato nel pool Front End nel sito 1 e dispone di una connessione SIP diretta all'IP-PBX nel sito 1. In questa figura, il Mediation Server controlla anche un gateway PSTN nel sito 2. Si supponga Skype for Business utenti presenti sia nei siti 1 che in quello 2. Si supponga inoltre che l'IP-PBX abbia un processore multimediale associato che deve essere attraversato da tutti i supporti provenienti da endpoint Skype for Business prima di essere inviato agli endpoint multimediali controllati dall'IP-PBX. In questa topologia, il bypass multimediale è abilitato a livello globale per l'utilizzo delle informazioni su siti e aree e i trunk per il PBX e il gateway PSTN hanno il bypass multimediale abilitato.
  
**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un sistema PBX nel sito 2**

![Topologia vocale Mediation Server WAN PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
L'ultima figura di questo argomento mostra una topologia in cui il Mediation Server è connesso al servizio SBC di un provider di servizi di telefonia Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Pianificazione delle decisioni per Mediation Server

In questo argomento vengono descritte le decisioni di pianificazione necessarie per la distribuzione di Mediation Server,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Per impostazione predefinita, Mediation Server è collocato nel server Standard Edition o Front End Server in un pool Front-End nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderanno dai seguenti elementi:
  
- Numero di peer gateway che il pool Mediation Server controlla
    
- I periodi di traffico con volume elevato attraverso tali gateway
    
- Percentuale di chiamate il cui bypass multimediale nel Mediation Server
    
Durante la pianificazione, assicurarsi di prendere in considerazione i requisiti di elaborazione multimediale per le chiamate PSTN e le conferenze audio/video non configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di punta che devono essere supportate. Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server. e i gateway PSTN, i server IP-IP e gli SBC dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e dai Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBC o SBC (Session Border Controller) che non supportano le funzionalità corrette per interagire con un pool di Mediation Server, inclusi i seguenti, dovranno essere associati a un pool autonomo costituito da un singolo Mediation Server:
  
- Eseguire il bilanciamento del carico DNS (Domain Name System) a livello di rete tra Mediation Server in un pool (o instradare il traffico in modo uniforme a tutti i Mediation Server di un pool)
    
- Accettazione del traffico proveniente da qualsiasi server Mediation Server in un pool
    
È possibile utilizzare lo Strumento di pianificazione di Microsoft Lync Server 2013 per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

 I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un server Mediation Server presso il sito in cui ogni trunk termina. Per fare in modo che un server Mediation Server nel sito centrale instradi le chiamate per un IP-PBX o un gateway PSTN in un sito derivato, non è necessario utilizzare Media Bypass. Tuttavia, se è possibile abilitare il bypass multimediale, in questo modo si riduce la latenza del percorso multimediale e si migliora la qualità del supporto perché il percorso multimediale non è più necessario per seguire il percorso di segnalazione. Il bypass multimediale riduce anche il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PBC Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program - Lync Server.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. Il presupposto con resilienza del sito di succursale è che la presenza e le conferenze non siano resilienti nel sito. Per indicazioni sulla pianificazione del sito di succursale per la funzionalità [vocale, vedere Plan for VoIP aziendale resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo dall'IP-PBX agli endpoint Skype for Business. Questo problema può essere più grave se un Mediation Server in un sito centrale instrada le chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.
  
> [!NOTE]
> Per migliorare le prestazioni multimediali del Mediation Server autonomo, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) sulle schede di rete in questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "Miglioramenti della scalabilità sul lato [ricezione in Windows Server"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Per informazioni dettagliate su come abilitare RSS, vedere la documentazione della scheda di rete. 
