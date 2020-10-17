---
title: Supporto per il trunking SIP di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d9bbf5ea35b6b24180f7853fd3715ad95973051
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519653"
---
# <a name="sip-trunking-support-in-lync-server-2013"></a>Supporto per il trunking SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Se si prevede di utilizzare VoIP aziendale con trunking SIP, è necessario distribuire un Mediation Server e verificare che altre infrastrutture e componenti soddisfino i requisiti di supporto adatti al modello di distribuzione. Per informazioni dettagliate sulla determinazione dell'implementazione del trunking SIP, vedere [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) nella documentazione relativa alla pianificazione.

È possibile utilizzare il programma Microsoft Unified Communications Open Interoperability Program per l'infrastruttura di telefonia aziendale per individuare i gateway PSTN (Public Switched Telephone Network), i sistemi IP-PBX e i servizi di trunking SIP, compresi i provider di servizi di telefonia IP qualificati. Per ulteriori informazioni, vedere il sito Web Microsoft Unified Communications Open Interoperability Program all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .

<div>

## <a name="mediation-server-support"></a>Supporto di Mediation Server

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra i client di Lync Server 2013 e il provider di servizi. Il Mediation Server decodifica il traffico multimediale proveniente da client e server e lo ricodifica prima di inviarlo al provider di servizi. La ricodifica è necessaria perché i trunk SIP non supportano alcuni codec utilizzati, ad esempio la negoziazione di protocollo di accesso interattivi (RTA) o Interactive Connectivity Establishment (ICE) per l'attraversamento del firewall.

Ogni Mediation Server può includere due schede di rete, che forniscono un'interfaccia di rete interna e una esterna. L'interfaccia esterna è comunemente chiamata interfaccia gateway perché, tradizionalmente, è stata utilizzata per la connessione a un gateway PSTN o a un IP-PBX. Per implementare un trunk SIP, connettere l'interfaccia esterna a un SBC (Session Border Controller) presso un provider di servizi.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP centralizzato o distribuito

*Centralizzata* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il Data Center. Il modello di distribuzione centralizzato è semplice, redditizio ed è in genere l'approccio preferito per l'implementazione dei trunk SIP con Lync Server 2013.

A seconda dei modelli di utilizzo adottati dall'organizzazione, è possibile decidere di non instradare tutti gli utente attraverso il trunk SIP centralizzato. Per analizzare le specifiche esigenze, rispondere alle domande seguenti:

  - Quanto è grande ogni sito? Quanti utenti?

  - Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?

Il trunking SIP *distribuito* è un modello di distribuzione in cui si implementa un trunk SIP locale in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente al provider di servizi, senza passare per il data center.

Il trunking SIP distribuito è necessario solo nei casi seguenti:

  - Il sito di succursale richiede la connettività del telefono superstite (ad esempio, se la rete WAN va verso il basso). Se il Branch ha bisogno di ridondanza e failover, il provider di servizi addebiterà di più e la configurazione richiederà più tempo. Questo dovrebbe essere analizzato per ogni sito di succursale. Alcuni dei rami potrebbero richiedere ridondanza e failover, mentre altri potrebbero non essere disponibili.

  - Il sito di succursale e il data center si trovano in paesi o aree geografiche diverse. Per motivi legali e di compatibilità, è necessario almeno un trunk SIP per ogni paese o area geografica.

Se si decide di distribuire il trunking SIP centralizzato o distribuito, è necessaria un'analisi costi/benefici. In alcuni casi, può essere vantaggioso optare per la modalità di distribuzione distribuita, anche se non è obbligatorio. In una distribuzione completamente centralizzata, tutto il traffico dei siti di succursale viene instradato su collegamenti WAN. Per non incorrere nei costi della larghezza di banda necessaria per i collegamenti WAN, può essere preferibile utilizzare il trunking SIP distribuito.

<div>


> [!NOTE]  
> Per informazioni dettagliate sul perché e su come utilizzare il trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">branching SIP trunking site in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione supportati per il trunking SIP

Lync Server 2013 supporta i tipi di connessione seguenti per il trunking SIP:

  - MPLS (Multiprotocol Label Switching) è una rete privata che indirizza e trasferisce i dati da un nodo di rete al successivo. La larghezza di banda di una rete MPLS è condivisa con altri sottoscrittori e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un sottoscrittore da quelli di un altro. Questo tipo di connessione non richiede VPN. Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP a meno che non abbai priorità.

  - Una connessione privata senza altro traffico è in genere il tipo più affidabile e sicuro, ad esempio una connessione in fibra ottica dedicata, o linea T1. Questo tipo di connessione offre la massima capacità per il trasferimento delle chiamate, ma è in genere la più costosa. Non è richiesta una VPN. Le connessioni private sono appropriate per organizzazioni con volumi di chiamate elevate o requisiti rigorosi di sicurezza e disponibilità.

  - La rete Internet pubblica è il tipo di connessione meno costosa, ma anche la meno affidabile e quella con la capacità minore di trasferimento di chiamate. Il provider di servizi di telefonia Internet (ITSP) può contribuire alla protezione di questo tipo di connessione trunk SIP se supporta TLS (Transport Layer Security) e SRTP (Secure Real-Time Transport Protocol) per crittografare la segnalazione e il traffico multimediale. Se non è possibile configurare una connessione di trunk SIP tramite Internet per l'utilizzo di TLS e SRTP, è consigliabile utilizzare un tunnel VPN per una maggiore sicurezza. Contattare l'ITSP per verificare se fornisce il supporto per TLS con SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Selezione di un tipo di connessione

Il tipo di connessione per il trunking SIP più appropriato per la propria azienda dipende dalle diverse esigenze e dal budget a disposizione.

  - Per un'azienda di medie o grandi dimensioni, una rete MPLS fornisce generalmente la maggior parte dei valori. È in grado di fornire la larghezza di banda necessaria a un tasso più conveniente rispetto a una rete privata specializzata.

  - Per le grandi aziende può essere necessaria una connessione in fibra ottica privata o T1.

  - Per una piccola azienda o un sito di succursale con volume di chiamata basso, il trunking SIP tramite Internet potrebbe essere la scelta migliore. Tuttavia, questo tipo di connessione non è consigliato per siti di medie o grandi dimensioni.

</div>

</div>

<div>

## <a name="codec-support"></a>Codec supportati

Il proxy del provider di servizi deve supportare i codec seguenti:

  - G.711 a-law (utilizzato prevalentemente all'esterno del Nord America)

  - G.711 µ-law (utilizzato in Nord America)

</div>

</div>

<span> </span>

</div>

</div>

</div>

