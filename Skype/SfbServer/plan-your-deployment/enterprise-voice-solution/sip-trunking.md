---
title: Trunking SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Informazioni sul trunking SIP in Skype for Business Server VoIP aziendale
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802416"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Trunking SIP in Skype for Business Server

Informazioni sul trunking SIP in Skype for Business Server VoIP aziendale

SIP (Session Initiation Protocol) viene usato per avviare e gestire sessioni di comunicazioni VoIP (Voice over IP) per il servizio telefonico di base e per servizi di comunicazione in tempo reale aggiuntivi, ad esempio messaggistica istantanea, conferenza, rilevamento presenza e multimediali. Questa sezione fornisce informazioni sulla pianificazione per l'implementazione di trunk SIP, un tipo di connessione SIP che si estende oltre il limite della rete locale.

## <a name="what-is-sip-trunking"></a>Che cos'è il trunking SIP?

Un trunk SIP è una connessione IP che stabilisce un collegamento di comunicazioni SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall. In genere, viene usato un trunk SIP per connettere il sito centrale dell'organizzazione a un ITSP. In alcuni casi, è anche possibile scegliere di usare il trunking SIP per connettere il sito di succursale a un ITSP.

La distribuzione del trunking SIP può essere un grande passo verso la semplificazione delle telecomunicazioni dell'organizzazione e la preparazione di miglioramenti aggiornati alle comunicazioni in tempo reale. Uno dei vantaggi principali del trunking SIP è che puoi consolidare le connessioni dell'organizzazione con la rete PSTN (Public Switched Telephone Network) in un sito centrale, in contrapposizione al suo predecessore, il trunking di Time Division Multiplexing (TDM), che in genere richiede un trunk separato da ogni sito di succursale.

### <a name="cost-savings"></a>Risparmi sui costi

Il risparmio di costi associato al trunking SIP può essere sostanziale:

- Le chiamate interurbane in genere costano molto meno attraverso un trunk SIP.

- È possibile tagliare i costi di gestibilità e ridurre la complessità della distribuzione.

- Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al proprio ITSP a costi decisamente più bassi. In TDM trunking i provider di servizi caricano le chiamate al minuto. Il costo del trunking SIP può essere basato sull'utilizzo della larghezza di banda, che è possibile acquistare in incrementi più piccoli e più economici. Il costo effettivo dipende dal modello di servizio della ITSP scelta.

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Trunking SIP e hosting di un gateway PSTN o IP-PBX

Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN e i costi e la complessità della gestione. L'uso di un trunk SIP può determinare un notevole risparmio di costi tramite la riduzione della manutenzione e dell'amministrazione.

### <a name="expanded-voip-services"></a>Servizi VoIP espansi

Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio. Con il trunking SIP puoi estendere le funzionalità VoIP e abilitare Skype for Business Server per offrire un set di servizi più completo. Ad esempio:

- Il rilevamento della presenza avanzata per i dispositivi che non sono in uso in Skype for Business Server può offrire una migliore integrazione con i telefoni cellulari, in modo da vedere quando un utente si trova in una chiamata telefonica mobile.

- La chiamata di emergenza E9-1-1 consente alle autorità che rispondono alle chiamate di 911 di determinare la posizione del chiamante dal proprio numero di telefono.

> [!NOTE]
> Contattare l'ITSP per un elenco dei servizi supportati e che possono essere abilitati per l'organizzazione.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Trunk SIP e connessioni SIP dirette

Il termine trunk è derivato dalla tecnologia Circuit-Switched. Si riferisce a una linea fisica dedicata che connette il dispositivo di commutazione telefonica. Come il predecessore, i trunk di Time Division Multiplexing (TDM), i trunk SIP sono connessioni tra due reti SIP separate: Skype for Business Server Enterprise e ITSP. Diversamente dai trunk a scambio di circuiti, i trunk SIP sono connessioni virtuali che possono essere stabilite su uno dei tipi di connessione di trunking SIP supportati.

Le connessioni SIP dirette, invece, sono connessioni SIP che non superano il limite di rete locale, ovvero si connettono a un gateway PSTN (Public Switched Telephone Network) o PBX (Private Branch Exchange) all'interno della rete interna. Per informazioni dettagliate su come usare le connessioni SIP dirette con Skype for Business Server, vedere [connessioni SIP dirette in Skype for Business Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Come si implementa il trunking SIP?

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra client di Skype for Business Server e il provider di servizi e Transcodes media, quando necessario.

Ogni Mediation Server include un'interfaccia di rete interna e un'interfaccia di rete esterna. L'interfaccia interna si connette ai server front-end. L'interfaccia esterna viene comunemente chiamata interfaccia gateway perché è stata usata tradizionalmente per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX. Per implementare un trunk SIP, Connetti l'interfaccia esterna di Mediation Server al componente bordo esterno di ITSP. Il componente bordo esterno di ITSP può essere un SBC (Session Border Controller), un router o un gateway.

Per informazioni dettagliate su Mediation Server, vedere [Componente Mediation Server in Skype for Business Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP distribuito o centralizzato

Il trunking SIP centralizzato instrada tutto il traffico VoIP, incluso il traffico del sito di succursale, tramite il sito centrale. Il modello di distribuzione centralizzato è semplice, conveniente ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Skype for Business Server.

Il trunking SIP distribuito è un modello di distribuzione in cui vengono implementati i trunk SIP locali in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare al sito centrale.

Il trunking SIP distribuito è obbligatorio solo nei casi seguenti:

- Il sito della filiale richiede una connettività telefonica superstite, ad esempio se la rete WAN viene rimandata. Questo requisito deve essere analizzato per ogni sito filiale; alcune delle branche potrebbero richiedere ridondanza e failover, mentre altre potrebbero non essere disponibili.

- La resilienza è necessaria tra due siti centrali. È necessario assicurarsi che un trunk SIP termini in ogni sito centrale. Se ad esempio sono presenti i siti centrali Dublin e Tukwila ed entrambi usano solo il trunk SIP di un sito, se il trunk scende, gli utenti dell'altro sito non possono effettuare chiamate PSTN.

- Il sito della filiale e il sito centrale si trovano in paesi/aree geografiche diverse. Per motivi di compatibilità e legali, è necessario almeno un trunk SIP per paese/area geografica. Ad esempio, nell'Unione europea le comunicazioni non possono uscire da un paese/area geografica senza terminare localmente in un punto centralizzato.

A seconda della posizione geografica dei siti e della quantità di traffico che anticipi all'interno dell'organizzazione, potresti non voler instradare tutti gli utenti tramite il trunk SIP centrale oppure scegliere di instradare alcuni utenti attraverso un trunk SIP presso il proprio sito di succursale. Per analizzare le proprie esigenze, rispondere alle domande seguenti:

- Quanto è grande ogni sito, ovvero il numero di utenti abilitati per VoIP aziendale?

- Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?

La decisione di distribuire il trunking SIP centralizzato o distribuito richiede un'analisi costi/benefici. In alcuni casi, può essere vantaggioso optare per il modello di distribuzione distribuita anche se non è obbligatorio. In una distribuzione completamente centralizzata, tutto il traffico del sito della filiale viene instradato su collegamenti WAN. Invece di pagare la larghezza di banda necessaria per il collegamento WAN, è consigliabile usare il trunking SIP distribuito. Ad esempio, potresti voler distribuire un server standard in un sito di succursale con la Federazione al sito centrale oppure vuoi distribuire un Survivable Branch Appliance o un Survivable Branch Server con un piccolo gateway.

> [!NOTE]
> Per informazioni dettagliate sul trunking SIP distribuito, vedere [trunking SIP del sito di succursale in Skype for Business Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione di trunking SIP supportati

Skype for Business Server supporta i tipi di connessione seguenti per il trunking SIP:

- Il cambio di etichetta Multiprotocol (MPLS) è una rete privata che indirizza e trasporta i dati da un nodo di rete a quello successivo. La larghezza di banda in una rete MPLS viene condivisa con altri abbonati e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un utente da un altro. Questo tipo di connessione non richiede una rete privata virtuale (VPN). Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP, a meno che non venga data priorità al traffico VoIP.

- Una connessione privata senza altro traffico, ad esempio una connessione in fibra ottica affittata o una linea T1, è in genere il tipo di connessione più affidabile e sicuro. Questo tipo di connessione offre la maggiore capacità di trasporto delle chiamate, ma in genere è la più costosa. La VPN non è obbligatoria. Le connessioni private sono appropriate per le organizzazioni con elevati volumi di chiamate o requisiti di sicurezza e disponibilità severi.

- Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile. Connessione Internet è l'unico tipo di connessione trunking SIP di Skype for Business Server che richiede VPN.

#### <a name="selecting-a-connection-type"></a>Selezione di un tipo di connessione

Il tipo di connessione di trunking SIP più appropriato per l'azienda dipende dalle esigenze e dal budget.

- Per un'azienda di medie dimensioni o più grande, una rete MPLS offre in genere il valore più grande. Può specificare la larghezza di banda necessaria a una tariffa più economica rispetto a una rete privata specializzata.

- Le grandi imprese possono richiedere una connessione a fibre ottiche, T1, T3 o superiore privata (E1, E3 o superiore nell'Unione europea).

- Per una piccola impresa o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore. Questo tipo di connessione non è consigliato per i siti di medie dimensioni o più grandi.

### <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

La quantità di larghezza di banda necessaria per l'implementazione dipende dalla capacità delle chiamate (il numero di chiamate simultanee che è necessario supportare). È necessario prendere in considerazione la disponibilità della larghezza di banda, in modo da poter sfruttare al massimo la capacità di picco pagata. Usare la formula seguente per calcolare il fabbisogno di larghezza di banda Peak del trunk SIP:

Larghezza di banda massima del trunk SIP = chiamate simultanee max x (64 kbps + Dimensione intestazione)

> [!NOTE]
> La dimensione dell'intestazione è massima di 20 byte.

### <a name="codec-support"></a>Supporto per codec

Skype for Business Server supporta solo i codec seguenti:

- G. 711 a-Law (usato principalmente al di fuori del Nord America)

- G. 711 µ-Law (usato in Nord America)

### <a name="internet-telephony-service-provider"></a>Provider di servizi di telefonia Internet

Il modo in cui implementare il lato provider di servizi di una connessione trunk SIP varia da un ITSP a un altro. Per informazioni sulla distribuzione, contattare il provider di servizi. Per un elenco dei provider di servizi di trunking SIP certificati, vedere [sito Web Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?LinkId=287029).

Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il proprio rappresentante Microsoft.

> [!IMPORTANT]
> Devi usare un provider di Servizi certificati Microsoft per assicurarti che ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi. Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati. Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usare il provider come ISP e usare un provider certificato da Microsoft per il trunking SIP.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologie e componenti per il trunking SIP

La figura seguente descrive la topologia di trunking SIP in Skype for Business Server.

**Topologia di trunking SIP**

![Topologia basata sul trunking SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Come illustrato nel diagramma, per la connettività tra la rete aziendale e il provider di servizi PSTN (Public Switched Telephone Network) viene usata una rete privata virtuale IP (VPN). Lo scopo di questa rete privata è offrire connettività IP, migliorare la sicurezza e, facoltativamente, ottenere garanzie di qualità del servizio (QoS). A causa della natura di una VPN, non è necessario usare Transport Layer Security (TLS) per il traffico di segnalazione SIP o il protocollo di trasporto in tempo reale (SRTP) sicuro per il traffico multimediale. Le connessioni tra l'organizzazione e il provider di servizi sono quindi costituite da connessioni TCP semplici per SIP e per il protocollo RTP (Plain Real-Time Transport Protocol) (tramite UDP) per i contenuti multimediali tramite una rete VPN IP. Assicurarsi che tutti i firewall tra i router VPN dispongano delle porte aperte per consentire ai router VPN di comunicare e che gli indirizzi IP sui bordi esterni dei router VPN siano instradabili pubblicamente.

> [!IMPORTANT]
> Contattare il provider di servizi per determinare se fornisce il supporto per l'elevata disponibilità, incluso il failover. In caso affermativo, dovrai determinare le procedure per configurarlo. Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP in ogni Mediation Server oppure è necessario configurare più trunk SIP in ogni Mediation Server? > se si hanno più siti centrali, chiedere anche se il provider di servizi ha la possibilità di abilitare le connessioni da e verso un altro sito centrale.

> [!NOTE]
> Per il trunking SIP consigliamo vivamente di distribuire server di mediazione autonomi. Per informazioni dettagliate, vedere [distribuzione di Mediation Server e definizione di peer](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) nella documentazione relativa alla distribuzione.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Protezione del server Mediation per il trunking SIP

Per motivi di sicurezza, è necessario configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN. Il processo effettivo per la configurazione di una VLAN varia da un produttore di router a un altro. Per informazioni dettagliate, contattare il fornitore del router.

Ti consigliamo di seguire queste linee guida:

- Configurare una LAN virtuale (VLAN) tra il Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).

- Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.

- Bloccare le regole di routing che instradano il traffico dal router a un punto qualsiasi ma al Mediation Server.

Se si usa un server VPN, è consigliabile seguire queste linee guida:

- Configurare una VLAN tra il server VPN e il Mediation Server.

- Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.

- Bloccare qualsiasi regola di routing che instrada il traffico del server VPN ovunque, eccetto il Mediation Server.

- Crittografare i dati nella rete VPN usando Generic Routing Encapsulation (GRE).

## <a name="see-also"></a>Vedere anche

[Trunking SIP del sito della filiale in Skype for Business Server](branch-site.md)

