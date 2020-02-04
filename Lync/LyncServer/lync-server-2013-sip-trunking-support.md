---
title: 'Lync Server 2013: Supporto per il trunking SIP'
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
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Supporto per il trunking SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Se si prevede di usare VoIP aziendale con il trunking SIP, è necessario distribuire un Mediation Server e verificare che altri componenti e infrastrutture soddisfino i requisiti di supporto appropriati per il modello di distribuzione. Per informazioni dettagliate su come determinare se implementare il trunking SIP, vedere [Panoramica del trunking SIP in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) nella documentazione relativa alla pianificazione.

È possibile usare il programma Microsoft Unified Communications Open Interoperability per l'infrastruttura per la telefonia aziendale per trovare i gateway PSTN (Public Switched Telephone Network) qualificati, i PBX IP e i servizi di trunking SIP, inclusa la telefonia IP qualificata provider di servizi. Per informazioni dettagliate, vedere il sito Web Microsoft Unified Communications Open Interoperability Program all' [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)indirizzo.

<div>

## <a name="mediation-server-support"></a>Supporto di Mediation Server

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra client Lync Server 2013 e il provider di servizi. Il Mediation Server decodifica il traffico multimediale da client e server e lo codifica di nuovo prima di inviarlo al provider di servizi. La ricodifica è necessaria perché i trunk SIP non supportano alcuni codec usati, come la negoziazione in Real time audio (RTA) o il protocollo ICE (Interactive Connectivity Establishment) per l'attraversamento del firewall.

Ogni Mediation Server può avere due schede di rete, che offrono un'interfaccia di rete interna e esterna. L'interfaccia esterna viene comunemente chiamata interfaccia gateway perché, tradizionalmente, è stata usata per la connessione a un gateway PSTN o a un IP-PBX. Per implementare un trunk SIP, Connetti l'interfaccia esterna a un SBC (Session Border Controller) in un provider di servizi.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP distribuito o centralizzato

*Centralizzato* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il Data Center. Il modello di distribuzione centralizzato è semplice, conveniente ed è in genere l'approccio preferito per l'implementazione di trunk SIP con Lync Server 2013.

A seconda dei modelli di utilizzo all'interno dell'organizzazione, potrebbe non essere necessario instradare tutti gli utenti tramite il trunk SIP centralizzato. Per analizzare le proprie esigenze, rispondere alle domande seguenti:

  - Quant'è grande ogni sito? Quanti utenti?

  - Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?

*Distribuiti* Trunking SIP è un modello di distribuzione in cui è possibile implementare un trunk SIP locale in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito della filiale direttamente al proprio provider di servizi, senza passare al Data Center.

Il trunking SIP distribuito è obbligatorio solo nei casi seguenti:

  - Il sito della filiale richiede una connettività telefonica superstite, ad esempio se la rete WAN viene rimandata. Se il ramo ha bisogno di ridondanza e failover, il provider di servizi addebiterà di più e la configurazione richiederà più tempo. Questa operazione deve essere analizzata per ogni sito di succursale. Alcune delle branche potrebbero richiedere ridondanza e failover, mentre altre potrebbero non essere disponibili.

  - Il sito e il centro dati della filiale si trovano in paesi/aree geografiche diverse. Per motivi di compatibilità e legali, è necessario almeno un trunk SIP per paese/area geografica.

Decidere se distribuire il trunking SIP centralizzato o distribuito richiede un'analisi costi/benefici. In alcuni casi, può essere vantaggioso optare per la modalità di distribuzione distribuita, anche se non è obbligatoria. In una distribuzione completamente centralizzata, tutto il traffico del sito della filiale viene instradato su collegamenti WAN. Invece di pagare la larghezza di banda necessaria per il collegamento WAN, è consigliabile usare il trunking SIP distribuito.

<div>


> [!NOTE]  
> Per informazioni dettagliate sul motivo e sulla modalità di utilizzo del trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione di trunking SIP supportati

Lync Server 2013 supporta i tipi di connessione seguenti per il trunking SIP:

  - Il cambio di etichetta Multiprotocol (MPLS) è una rete privata che indirizza e trasporta i dati da un nodo di rete a quello successivo. La larghezza di banda in una rete MPLS viene condivisa con altri abbonati e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un utente da un altro. Questo tipo di connessione non richiede VPN. Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP, a meno che non venga data priorità al traffico VoIP.

  - Una connessione privata senza altro traffico è in genere il tipo di connessione più affidabile e sicuro, ad esempio una connessione in fibra ottica affittata o una linea T1. Questo tipo di connessione offre la maggiore capacità di trasporto delle chiamate, ma in genere è la più costosa. La VPN non è obbligatoria. Le connessioni private sono appropriate per le organizzazioni con elevati volumi di chiamate o requisiti di sicurezza e disponibilità severi.

  - Internet pubblico è il tipo di connessione meno costoso, ma anche il meno affidabile e quello con la più bassa capacità di trasporto delle chiamate. Il provider di servizi di telefonia Internet (ITSP) può aiutare a proteggere questo tipo di connessione trunk SIP se supporta TLS (Transport Layer Security) e SRTP (Secure Real-Time Transport Protocol) per crittografare il traffico di segnalazione e multimediale. Se non è possibile configurare una connessione trunk SIP tramite Internet per l'uso di TLS e SRTP, è consigliabile usare un tunnel VPN per garantire una connessione più sicura. Contattare il ITSP per determinare se fornisce il supporto per TLS con SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Selezione di un tipo di connessione

Il tipo di connessione di trunking SIP più appropriato per l'azienda dipende dalle esigenze e dal budget.

  - Per un'azienda di medie dimensioni o più grande, una rete MPLS fornisce in genere il valore più elevato. Può specificare la larghezza di banda necessaria a una tariffa più economica rispetto a una rete privata specializzata.

  - Le grandi imprese possono richiedere una connessione a fibre ottiche o T1 private.

  - Per una piccola impresa o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore. Questo tipo di connessione non è tuttavia consigliato per i siti di medie dimensioni o più grandi.

</div>

</div>

<div>

## <a name="codec-support"></a>Supporto per codec

Il proxy del provider di servizi deve supportare i codec seguenti:

  - G. 711 a-Law (usato principalmente al di fuori del Nord America)

  - G. 711 µ-Law (usato in Nord America)

</div>

</div>

<span> </span>

</div>

</div>

</div>

