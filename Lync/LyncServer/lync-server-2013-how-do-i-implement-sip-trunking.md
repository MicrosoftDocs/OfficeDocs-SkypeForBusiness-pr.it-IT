---
title: 'Lync Server 2013: Come implementare il trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Come implementare il trunking SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-18_

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra client Lync Server 2013 e il provider di servizi e transcodifica il contenuto multimediale, se necessario.

Ogni Mediation Server include un'interfaccia di rete interna e un'interfaccia di rete esterna. L'interfaccia interna si connette ai server front-end. L'interfaccia esterna viene comunemente chiamata interfaccia gateway perché è stata usata tradizionalmente per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX. Per implementare un trunk SIP, Connetti l'interfaccia esterna di Mediation Server al componente bordo esterno di ITSP.

<div>


> [!NOTE]  
> Il componente bordo esterno di ITSP può essere un SBC (Session Border Controller), un router o un gateway.



</div>

Per informazioni dettagliate su Mediation Server, vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP distribuito o centralizzato

*Centralizzato* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, attraverso il sito centrale. Il modello di distribuzione centralizzato è semplice, conveniente ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Lync Server 2013.

*Distribuiti* Trunking SIP è un modello di distribuzione in cui è possibile implementare un trunk SIP locale in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare al sito centrale.

Il trunking SIP distribuito è obbligatorio solo nei casi seguenti:

  - Il sito della filiale richiede una connettività telefonica superstite, ad esempio se la rete WAN viene rimandata. Questo requisito deve essere analizzato per ogni sito filiale; alcune delle branche potrebbero richiedere ridondanza e failover, mentre altre potrebbero non essere disponibili.

  - La resilienza è necessaria tra due siti centrali. È necessario assicurarsi che un trunk SIP termini in ogni sito centrale. Se ad esempio sono presenti i siti centrali Dublin e Tukwila ed entrambi usano solo il trunk SIP di un sito, se il trunk scende, gli utenti dell'altro sito non possono effettuare chiamate PSTN.

  - Il sito della filiale e il sito centrale si trovano in paesi/aree geografiche diverse. Per motivi di compatibilità e legali, è necessario almeno un trunk SIP per paese/area geografica. Ad esempio, nell'Unione europea le comunicazioni non possono uscire da un paese/area geografica senza terminare localmente in un punto centralizzato.

A seconda della posizione geografica dei siti e della quantità di traffico che anticipi all'interno dell'organizzazione, potresti non voler instradare tutti gli utenti tramite il trunk SIP centrale oppure scegliere di instradare alcuni utenti attraverso un trunk SIP presso il proprio sito di succursale. Per analizzare le proprie esigenze, rispondere alle domande seguenti:

  - Quanto è grande ogni sito, ovvero il numero di utenti abilitati per VoIP aziendale?

  - Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?

La decisione di distribuire il trunking SIP centralizzato o distribuito richiede un'analisi costi/benefici. In alcuni casi, può essere vantaggioso optare per il modello di distribuzione distribuita anche se non è obbligatorio. In una distribuzione completamente centralizzata, tutto il traffico del sito della filiale viene instradato su collegamenti WAN. Invece di pagare la larghezza di banda necessaria per il collegamento WAN, è consigliabile usare il trunking SIP distribuito. Ad esempio, potresti voler distribuire un server standard in un sito di succursale con la Federazione al sito centrale oppure vuoi distribuire un Survivable Branch Appliance o un Survivable Branch Server con un piccolo gateway.

<div>


> [!NOTE]  
> Per informazioni dettagliate sul trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione di trunking SIP supportati

Lync Server supporta i tipi di connessione seguenti per il trunking SIP:

  - Il cambio di etichetta Multiprotocol (MPLS) è una rete privata che indirizza e trasporta i dati da un nodo di rete a quello successivo. La larghezza di banda in una rete MPLS viene condivisa con altri abbonati e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un utente da un altro. Questo tipo di connessione non richiede una rete privata virtuale (VPN). Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP, a meno che non venga data priorità al traffico VoIP.

  - Una connessione privata senza altro traffico, ad esempio una connessione in fibra ottica affittata o una linea T1, è in genere il tipo di connessione più affidabile e sicuro. Questo tipo di connessione offre la maggiore capacità di trasporto delle chiamate, ma in genere è la più costosa. La VPN non è obbligatoria. Le connessioni private sono appropriate per le organizzazioni con elevati volumi di chiamate o requisiti di sicurezza e disponibilità severi.

  - Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile. Connessione Internet è l'unico tipo di connessione di trunking SIP di Lync Server che richiede VPN.

<div>

## <a name="selecting-a-connection-type"></a>Selezione di un tipo di connessione

Il tipo di connessione di trunking SIP più appropriato per l'azienda dipende dalle esigenze e dal budget.

  - Per un'azienda di medie dimensioni o più grande, una rete MPLS offre in genere il valore più grande. Può specificare la larghezza di banda necessaria a una tariffa più economica rispetto a una rete privata specializzata.

  - Le grandi imprese possono richiedere una connessione a fibre ottiche, T1, T3 o superiore privata (E1, E3 o superiore nell'Unione europea).

  - Per una piccola impresa o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore. Questo tipo di connessione non è consigliato per i siti di medie dimensioni o più grandi.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

La quantità di larghezza di banda necessaria per l'implementazione dipende dalla capacità delle chiamate (il numero di chiamate simultanee che è necessario supportare). È necessario prendere in considerazione la disponibilità della larghezza di banda, in modo da poter sfruttare al massimo la capacità di picco pagata. Usare la formula seguente per calcolare il fabbisogno di larghezza di banda Peak del trunk SIP:

Larghezza di banda massima del trunk SIP = chiamate simultanee max x (64 kbps + Dimensione intestazione)

<div>


> [!NOTE]  
> La dimensione dell'intestazione è massima di 20 byte.



</div>

</div>

<div>

## <a name="codec-support"></a>Supporto per codec

Lync Server 2013 supporta solo i codec seguenti:

  - G. 711 a-Law (usato principalmente al di fuori del Nord America)

  - G. 711 µ-Law (usato in Nord America)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Provider di servizi di telefonia Internet

Il modo in cui implementare il lato provider di servizi di una connessione trunk SIP varia da un ITSP a un altro. Per informazioni sulla distribuzione, contattare il provider di servizi. Per un elenco dei provider di servizi di trunking SIP certificati, vedere [sito Web Microsoft Unified Communications Open Interoperability Program](http://go.microsoft.com/fwlink/?linkid=287029).

Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il proprio rappresentante Microsoft.

<div>


> [!IMPORTANT]  
> Devi usare un provider di Servizi certificati Microsoft per assicurarti che ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi. Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati. Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usare il provider come ISP e usare un provider certificato da Microsoft per il trunking SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

