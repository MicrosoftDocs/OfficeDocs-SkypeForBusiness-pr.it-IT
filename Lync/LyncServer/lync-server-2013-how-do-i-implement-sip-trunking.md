---
title: 'Lync Server 2013: come implementare il trunking SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062eb44fb79d6ecfa33f449e62341003bbed571b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Come implementare il trunking SIP in Lync Server 2013?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-18_

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra i client di Lync Server 2013 e il provider di servizi e i supporti di transcodifica, se necessario.

Ogni Mediation Server dispone di un'interfaccia di rete interna e di un'interfaccia di rete esterna. L'interfaccia interna si connette ai Front End Server. L'interfaccia esterna è comunemente chiamata interfaccia gateway perché è stata utilizzata tradizionalmente per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX. Per implementare un trunk SIP, è necessario connettere l'interfaccia esterna del Mediation Server al componente perimetrale esterno di ITSP.

<div>


> [!NOTE]  
> Il componente perimetrale esterno dell'ITSP potrebbe essere un servizio Session Border Controller (SBC), un router o un gateway.



</div>

Per informazioni dettagliate su Mediation Server, vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP centralizzato o distribuito

*Centralizzata* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il sito centrale. Il modello di distribuzione centralizzato è semplice, redditizio ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Lync Server 2013.

*Distribuiti* Il trunking SIP è un modello di distribuzione in cui viene implementato un trunk SIP locale in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare attraverso il sito centrale.

Il trunking SIP distribuito è necessario solo nei casi seguenti:

  - Il sito di succursale richiede la connettività del telefono superstite (ad esempio, se la rete WAN va verso il basso). Questo requisito deve essere analizzato per ogni sito di succursale. alcuni dei rami possono richiedere ridondanza e failover, mentre altri potrebbero non essere disponibili.

  - È necessaria una resilienza tra due siti centrali. È necessario verificare che un trunk SIP termini in ogni sito centrale. Ad esempio, se si dispone di siti centrali Dublin e Tukwila ed entrambi utilizzano solo trunk SIP di un sito, se il trunk si abbassa, gli utenti dell'altro sito non possono effettuare chiamate PSTN.

  - Il sito di succursale e il sito centrale si trovano in paesi/aree geografiche diverse. Per motivi legali e di compatibilità, è necessario almeno un trunk SIP per paese. Nell'Unione Europea ad esempio le comunicazioni non possono uscire da un paese senza terminare localmente in un punto centralizzato.

A seconda della posizione geografica dei siti e del traffico previsto all'interno dell'organizzazione, è possibile che non si desideri instradare tutti gli utenti nel trunk SIP centrale oppure che alcuni utenti vengano instradati tramite un trunk SIP nel relativo sito di succursale. Per valutare le proprie esigenze, analizzare gli aspetti seguenti:

  - Quanto è grande ogni sito, ovvero il numero di utenti abilitati per VoIP aziendale.

  - Numeri DID (Direct Inward Dialing) presso ogni sito che ricevono più telefonate

Per scegliere se distribuire il trunking SIP centralizzato o distribuito, è necessaria un'analisi costi-benefici. In alcuni casi può essere vantaggioso scegliere il modello di trunking SIP distribuito, anche quando non è obbligatorio. In una distribuzione completamente centralizzata, tutto il traffico dei siti di succursale viene instradato su collegamenti WAN. Per non incorrere nei costi della larghezza di banda necessaria per i collegamenti WAN, può essere preferibile utilizzare il trunking SIP distribuito. Ad esempio, è consigliabile distribuire un server Standard Edition in un sito di succursale con la Federazione al sito centrale oppure è possibile distribuire un Survivable Branch Appliance o un Survivable Branch Server con un gateway di piccole dimensioni.

<div>


> [!NOTE]  
> Per informazioni dettagliate sul trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione supportati per il trunking SIP

Lync Server supporta i tipi di connessione seguenti per il trunking SIP:

  - MPLS (Multiprotocol Label Switching). Si tratta di una rete privata che indirizza e trasporta i dati da un nodo di rete al successivo. La larghezza di banda in una rete MPLS è condivisa con altri sottoscrittori e a ogni pacchetto dati è assegnata un'etichetta per distinguere i dati di un sottoscrittore da quelli di un altro. Questo tipo di connessione non richiede una rete privata virtuale (VPN). Un potenziale svantaggio è rappresentato dal rischio che un eccessivo traffico IP possa interferire con il funzionamento di VoIP, a meno che non venga assegnata priorità al traffico VoIP.

  - Una connessione privata senza altro traffico, ad esempio una connessione su fibra ottica dedicata o linea T1. Questo tipo di connessione è in genere il più affidabile e sicuro. Garantisce un'elevata capacità di trasporto delle chiamate, ma è anche il più costoso. Non è richiesta una VPN. Le connessioni private sono appropriate per le organizzazioni con un elevato volume di chiamate o con requisiti di disponibilità e sicurezza rigorosi.

  - Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile. La connessione Internet è l'unico tipo di connessione del trunking SIP di Lync Server che richiede la VPN.

<div>

## <a name="selecting-a-connection-type"></a>Scelta di un tipo di connessione

Il tipo di connessione per il trunking SIP più appropriato per la propria azienda dipende dalle diverse esigenze e dal budget a disposizione.

  - Per un'azienda di medie o grandi dimensioni, una rete MPLS in genere è la soluzione più appropriata, poiché offre la larghezza di banda necessaria a una tariffa più conveniente rispetto a una rete privata specializzata.

  - Per le aziende di dimensioni maggiori può essere necessaria una connessione su fibra ottica privata, T1, T3 o superiore (E1, E3 o superiore nell'Unione Europea).

  - Per una piccola azienda o un sito di succursale con volume di chiamata basso, il trunking SIP tramite Internet potrebbe essere la scelta migliore. Questo tipo di connessione non è consigliato per siti di medie o grandi dimensioni.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

La larghezza di banda richiesta da un'implementazione dipende dalla capacità di chiamata, ovvero dal numero di chiamate simultanee che devono essere supportate. È necessario tenere conto della disponibilità della larghezza di banda in modo da poter usufruire pienamente della capacità di picco per cui si paga. Usare la formula seguente per calcolare il requisito di larghezza di banda di picco di un trunk SIP:

Larghezza di banda di picco di trunk SIP = Numero massimo di chiamate simultanee x (64 kbps + dimensioni delle intestazioni)

<div>


> [!NOTE]  
> Le dimensioni massime delle intestazioni corrispondono a 20 byte.



</div>

</div>

<div>

## <a name="codec-support"></a>Supporto di codec

Lync Server 2013 supporta solo i codec seguenti:

  - G.711 a-law (utilizzato principalmente al di fuori dell'America del Nord)

  - G.711 µ-law (utilizzato nell'America del Nord)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Provider di servizi di telefonia Internet

La modalità di implementazione del lato provider di servizi di una connessione trunk SIP varia da un ITSP all'altro. Per informazioni sulla distribuzione, contattare il provider di servizi. Per un elenco dei provider di servizi di trunking SIP certificati, vedere [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).

Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il rappresentante Microsoft.

<div>


> [!IMPORTANT]  
> È necessario usare un provider di servizi certificato Microsoft per garantire che il provider ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi. Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati. Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usarlo come ISP, passando a un provider certificato Microsoft per il trunking SIP.




</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

