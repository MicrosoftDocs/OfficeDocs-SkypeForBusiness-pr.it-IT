---
title: Trunking SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Informazioni sul trunking SIP in Skype for Business Server VoIP aziendale
ms.openlocfilehash: a27967f322db816285db100696fa061f339e9f71
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634200"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Trunking SIP in Skype for Business Server

Informazioni sul trunking SIP in Skype for Business Server VoIP aziendale

Il protocollo SIP (Session Initiation Protocol) viene utilizzato per avviare e gestire sessioni di comunicazioni Voice over IP (VoIP) per servizi telefonici di base e per altri servizi di comunicazione in tempo reale, ad esempio messaggistica istantanea, conferenze, informazioni sulla presenza e sessioni multimediali. In questa sezione vengono fornite informazioni sulla pianificazione per l'implementazione di trunk SIP, un tipo di connessione SIP che si estende oltre i confini della rete locale.

## <a name="what-is-sip-trunking"></a>Cos'è il trunking SIP?

Un trunk SIP è una connessione IP che consente di stabilire un collegamento di comunicazione SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall. In genere, un trunk SIP viene utilizzato per connettere il sito centrale dell'organizzazione a un PROVIDER ITSP. In alcuni casi, è anche possibile scegliere di utilizzare il trunking SIP per connettere un sito derivato a un ITSP.

La distribuzione del trunking SIP può essere un grande passo verso la semplificazione delle telecomunicazioni dell'organizzazione e la preparazione per i miglioramenti aggiornati alle comunicazioni in tempo reale. Uno dei principali vantaggi del trunking SIP è che è possibile consolidare le connessioni dell'organizzazione alla rete PSTN (Public Switched Telephone Network) in un sito centrale, anziché al trunking TDM (Time Division Multiplexing) predecessore, che in genere richiede un trunk separato da ogni sito di succursale.

### <a name="cost-savings"></a>Risparmi sui costi

I risparmi sui costi associati al trunking SIP possono essere significativi:

- Le chiamate interurbane in genere sono molto meno costose tramite un trunk SIP.

- È possibile tagliare i costi di gestione e ridurre la complessità della distribuzione.

- Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al provider di servizi di telefonia Internet (ITSP) con un costo significativamente inferiore. Nel trunking TDM i provider di servizi applicano alle chiamate una tariffa al minuto. Il costo del trunking SIP può basarsi sull'utilizzo della larghezza di banda, che può essere acquistato con incrementi inferiori, più economici. Il costo effettivo dipende dal modello di servizio dell'ITSP scelto.

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Confronto tra trunking SIP e hosting di un gateway PSTN o di un sistema IP-PBX

Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN con relativa complessità e con i costi di gestione a essi associati. L'utilizzo di un trunk SIP può determinare significativi risparmi sui costi grazie a una riduzione delle attività di manutenzione e amministrazione.

### <a name="expanded-voip-services"></a>Servizi VoIP estesi

Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio. Con il trunking SIP, è possibile estendere le funzionalità VoIP e Skype for Business Server offrire un set di servizi più ricco. Ad esempio:

- Il rilevamento della presenza avanzato per i dispositivi che non eseguono Skype for Business Server può offrire una migliore integrazione con i telefoni cellulari, consentendoti di vedere quando un utente è in una chiamata tramite cellulare.

- Le chiamate di emergenza E9-1-1 consentono alle autorità che rispondono alle chiamate 911 di determinare la posizione del chiamante dal suo numero di telefono.

> [!NOTE]
> Contattare il provider di servizi Internet per un elenco dei servizi supportati e che possono essere abilitati per la propria organizzazione.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Confronto tra trunk SIP e connessioni SIP dirette

Il termine trunk deriva dalla tecnologia a commutazione di circuito. Si riferisce a una linea fisica dedicata che collega le apparecchiature di commutazione telefonica. Analogamente ai trunk TDM (Time Division Multiplexing) predecessore, i trunk SIP sono connessioni tra due reti SIP separate, ovvero Skype for Business Server enterprise e ITSP. A differenza dei trunk a commutazione di circuito, i trunk SIP sono connessioni virtuali che possono essere stabilite su uno qualsiasi dei tipi di connessione di trunking SIP supportati.

Le connessioni SIP dirette sono invece connessioni SIP che non oltrepassano il confine di rete locale, ovvero si connettono a un gateway PSTN o un PBX nella rete interna. Per informazioni dettagliate su come utilizzare connessioni SIP dirette con Skype for Business Server, vedere [Connessioni SIP dirette in Skype for Business Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Come si implementa il trunking SIP?

Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra i client Skype for Business Server e il provider di servizi e transcodifica i supporti, se necessario.

Ogni Mediation Server dispone di un'interfaccia di rete interna e di un'interfaccia di rete esterna. L'interfaccia interna si connette ai Front End Server. L'interfaccia esterna è comunemente chiamata interfaccia gateway perché è tradizionalmente utilizzata per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX. Per implementare un trunk SIP, connettere l'interfaccia esterna del Mediation Server al componente perimetrale esterno del provider ITSP. Il componente perimetrale esterno dell'ITSP potrebbe essere un servizio Session Border Controller (SBC), un router o un gateway.

Per informazioni dettagliate sui Mediation Server, vedere [Mediation Server component in Skype for Business Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Trunking SIP centralizzato o distribuito

Il trunking SIP centralizzato instrada tutto il traffico VoIP, incluso il traffico del sito di succursale, attraverso il sito centrale. Il modello di distribuzione centralizzata è semplice, conveniente ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Skype for Business Server.

Il trunking SIP distribuito è un modello di distribuzione in cui vengono implementati trunk SIP locali in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare attraverso il sito centrale.

Il trunking SIP distribuito è necessario solo nei casi seguenti:

- Il sito di succursale richiede una connettività telefonica survivable(ad esempio, se la rete WAN non è più in linea). Questo requisito deve essere analizzato per ogni sito di succursale. alcuni rami potrebbero richiedere ridondanza e failover, mentre altri potrebbero non essere necessari.

- La resilienza è necessaria tra due siti centrali. È necessario assicurarsi che un trunk SIP termini in ogni sito centrale. Ad esempio, se si dispone di siti centrali di Dublino e Tukwila ed entrambi utilizzano solo il trunk SIP di un sito, se il trunk si insedia, gli utenti dell'altro sito non possono effettuare chiamate PSTN.

- Il sito di succursale e il sito centrale sono in diversi paesi/aree geografiche. Per motivi legali e di compatibilità, è necessario almeno un trunk SIP per paese. Nell'Unione Europea ad esempio le comunicazioni non possono uscire da un paese senza terminare localmente in un punto centralizzato.

A seconda della posizione geografica dei siti e del traffico previsto all'interno dell'organizzazione, è possibile che non si desideri instradare tutti gli utenti attraverso il trunk SIP centrale oppure scegliere di instradare alcuni utenti tramite un trunk SIP nel proprio sito di succursale. Per valutare le proprie esigenze, analizzare gli aspetti seguenti:

- Quanto è grande ogni sito (ovvero quanti utenti sono abilitati per VoIP aziendale)?

- Numeri DID (Direct Inward Dialing) presso ogni sito che ricevono più telefonate

Per scegliere se distribuire il trunking SIP centralizzato o distribuito, è necessaria un'analisi costi-benefici. In alcuni casi può essere vantaggioso scegliere il modello di trunking SIP distribuito, anche quando non è obbligatorio. In una distribuzione completamente centralizzata, tutto il traffico dei siti di succursale viene instradato su collegamenti WAN. Per non incorrere nei costi della larghezza di banda necessaria per i collegamenti WAN, può essere preferibile utilizzare il trunking SIP distribuito. È ad esempio possibile distribuire un server edizione Standard in un sito di succursale con federazione nel sito centrale oppure un Survivable Branch Appliance o un Survivable Branch Server con un gateway di piccole dimensioni.

> [!NOTE]
> Per informazioni dettagliate sul trunking SIP distribuito, vedere [Branch site SIP trunking in Skype for Business Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Tipi di connessione supportati per il trunking SIP

Skype for Business Server supporta i seguenti tipi di connessione per il trunking SIP:

- MPLS (Multiprotocol Label Switching) è una rete privata che indirizza e trasferisce i dati da un nodo di rete al successivo. La larghezza di banda in una rete MPLS viene condivisa con altri sottoscrittori e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un sottoscrittore da quello di un altro. Questo tipo di connessione non richiede una rete privata virtuale (VPN). Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP a meno che non abbai priorità.

- Una connessione privata senza altro traffico, ad esempio una connessione su fibra ottica dedicata o linea T1. Questo tipo di connessione è in genere il più affidabile e sicuro. Garantisce un'elevata capacità di trasporto delle chiamate, ma è anche il più costoso. Non è richiesta una VPN. Le connessioni private sono appropriate per le organizzazioni con un elevato volume di chiamate o con requisiti di disponibilità e sicurezza rigorosi.

- Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile. La connessione Internet è l'Skype for Business Server di connessione trunking SIP che richiede VPN.

#### <a name="selecting-a-connection-type"></a>Scelta di un tipo di connessione

Il tipo di connessione per il trunking SIP più appropriato per la propria azienda dipende dalle diverse esigenze e dal budget a disposizione.

- Per un'azienda di medie o grandi dimensioni, una rete MPLS in genere è la soluzione più appropriata, poiché offre la larghezza di banda necessaria a una tariffa più conveniente rispetto a una rete privata specializzata.

- Per le aziende di dimensioni maggiori può essere necessaria una connessione su fibra ottica privata, T1, T3 o superiore (E1, E3 o superiore nell'Unione Europea).

- Per un'azienda di piccole dimensioni o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore. Questo tipo di connessione non è consigliato per siti di medie o grandi dimensioni.

### <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

La larghezza di banda richiesta da un'implementazione dipende dalla capacità di chiamata, ovvero dal numero di chiamate simultanee che devono essere supportate. È necessario tenere conto della disponibilità della larghezza di banda in modo da poter usufruire pienamente della capacità di picco per cui si paga. Usare la formula seguente per calcolare il requisito di larghezza di banda di picco di un trunk SIP:

Larghezza di banda di picco di trunk SIP = Numero massimo di chiamate simultanee x (64 kbps + dimensioni delle intestazioni)

> [!NOTE]
> Le dimensioni massime delle intestazioni corrispondono a 20 byte.

### <a name="codec-support"></a>Supporto di codec

Skype for Business Server supporta solo i codec seguenti:

- G.711 a-law (utilizzato principalmente al di fuori dell'America del Nord)

- G.711 µ-law (utilizzato nell'America del Nord)

### <a name="internet-telephony-service-provider"></a>Provider di servizi di telefonia Internet

La modalità di implementazione del lato provider di servizi di una connessione trunk SIP varia da un ITSP all'altro. Per informazioni sulla distribuzione, contattare il provider di servizi. Per un elenco dei provider di servizi di trunking SIP certificati, vedere [Sito Web Microsoft Unified Communications Open Interoperability Program](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).

Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il rappresentante Microsoft.

> [!IMPORTANT]
> È necessario usare un provider di servizi certificato Microsoft per garantire che il provider ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi. Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati. Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usarlo come ISP, passando a un provider certificato Microsoft per il trunking SIP.


### <a name="topologies-and-components-for-sip-trunking"></a>Topologie e componenti per il trunking SIP

Nella figura seguente viene illustrata la topologia di trunking SIP in Skype for Business Server.

**Topologia di trunking SIP**

![Topologia trunking SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Come illustrato nella figura, una rete privata virtuale (VPN, Virtual Private Network) IP viene utilizzata per la connettività tra l'azienda e il provider di servizi PSTN. Lo scopo di questa rete privata è quello di fornire connettività IP, migliorare la protezione e, facoltativamente, ottenere garanzie relative alla qualità del servizio. Data la natura delle VPN, non è necessario utilizzare TLS per il traffico di segnalazione SIP o SRTP per il traffico multimediale. Le connessioni tra l'azienda e il provider di servizi sono pertanto normali connessioni TCP per SIP e RTP (tramite UDP) per i contenuti multimediali potenzialmente inviati tramite una rete VPN IP. Accertarsi che le porte di tutti i firewall tra i router VPN siano aperte per consentire ai router VPN di comunicare e che gli indirizzi IP nei perimetri esterni dei router VPN consentano l'esecuzione del routing pubblicamente.

> [!IMPORTANT]
> Contattare il provider di servizi per determinare se fornisce supporto per la disponibilità elevata, incluso il failover. In tal caso, sarà necessario determinare le procedure per la configurazione. Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP in ogni Mediation Server oppure è necessario configurare più trunk SIP in ogni Mediation Server? > Se si dispone di più siti centrali, chiedere anche se il provider di servizi è in grado di abilitare le connessioni da e verso un altro sito centrale.

> [!NOTE]
> Per il trunking SIP, è consigliabile distribuire Mediation Server autonomi. Per informazioni dettagliate, vedere [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) nella documentazione relativa alla distribuzione.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Protezione del Mediation Server per il trunking SIP

Per motivi di sicurezza è opportuno configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN. La procedura per la configurazione di una VLAN varia in base al produttore del router. Per informazioni dettagliate, rivolgersi al fornitore del router.

È consigliabile attenersi alle linee guida seguenti:

- Configurare una rete LAN virtuale (VLAN) tra Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).

- Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.

- Bloccare tutte le regole di routing che instradino il traffico dal router a qualsiasi posizione, ad esempio il Mediation Server.

Se si utilizza un server VPN, è consigliabile attenersi alle linee guida seguenti:

- Configurare una VLAN tra il server VPN e il Mediation Server.

- Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.

- Bloccare qualsiasi regola di routing che instrada il traffico del server VPN verso qualsiasi posizione, ad esempio il Mediation Server.

- Crittografare i dati sulla VPN utilizzando Generic Routing Encapsulation (GRE).

## <a name="see-also"></a>Vedere anche

[Trunking SIP del sito di succursale in Skype for Business Server](branch-site.md)