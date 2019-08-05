---
title: Connessioni SIP dirette in Skype for Business Server
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Le connessioni SIP dirette sono supportate tra Skype for Business Server e i gateway PSTN e IP-PBX in VoIP aziendale.
ms.openlocfilehash: d70fa72032b86251870ebaf623679dedc782fe24
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187733"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Connessioni SIP dirette in Skype for Business Server

Le connessioni SIP dirette sono supportate tra Skype for Business Server e i gateway PSTN e IP-PBX in VoIP aziendale.

È possibile usare connessioni SIP dirette per connettere Skype for Business Server a una delle opzioni seguenti:

- Un IP-PBX

- Un gateway PSTN

Per implementare una connessione SIP diretta, è necessario seguire essenzialmente gli stessi passaggi di distribuzione che si vuole implementare in un trunk SIP. In entrambi i casi, la connessione viene implementata usando l'interfaccia esterna di un Mediation Server. L'unica differenza è che si connettono trunk SIP a un'entità esterna, ad esempio un gateway ITSP, e si connettono connessioni SIP dirette a un'entità interna all'interno della rete locale, ad esempio un IP-PBX o un gateway PSTN (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Opzioni di distribuzione SIP diretta

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server autonomo
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se l'organizzazione usa una delle distribuzioni descritte in questa sezione, è possibile usare Skype for Business Server come unica soluzione per la telefonia per parte o tutta l'organizzazione. Questa sezione descrive in dettaglio le distribuzioni seguenti:

- **Distribuzione incrementale:** Questa opzione presuppone che si disponga di un'infrastruttura PBX (Private Branch Exchange) esistente e che si voglia inserire in modo incrementale la voce aziendale in gruppi o team più piccoli all'interno dell'organizzazione.

- **Distribuzione solo VoIP:** questa opzione presuppone che si stia valutando la distribuzione di Enterprise Voice in un sito che non ha un'infrastruttura di telefonia tradizionale.

#### <a name="incremental-deployment"></a>Distribuzione incrementale

Nella distribuzione incrementale, Skype for Business Server è l'unica soluzione di telefonia per singoli team o reparti, mentre gli altri utenti di un'organizzazione continuano a usare un PBX. Questa strategia di distribuzione incrementale offre un modo per introdurre la telefonia IP nella tua azienda attraverso programmi pilota controllati. I gruppi di lavoro le cui esigenze di comunicazione sono meglio serviti da Microsoft Unified Communications vengono spostati in Enterprise Voice, mentre altri utenti restano nel PBX esistente. È possibile eseguire la migrazione di altri gruppi di lavoro a VoIP aziendale, se necessario.

L'opzione incrementale è consigliata se sono presenti gruppi di utenti chiaramente definiti con requisiti di comunicazione comuni e che si prestano alla gestione centralizzata. Questa opzione è efficace anche se sono presenti team o reparti distribuiti su aree geografiche estese, in cui i risparmi in spese interurbane possono essere significativi. In realtà, questa opzione è utile per creare team virtuali i cui membri potrebbero essere sparsi in tutto il mondo. È possibile creare, modificare o sciogliere tali team in risposta rapida a requisiti aziendali mutevoli.

La figura seguente mostra la topologia generica per la distribuzione di VoIP aziendale dietro un PBX. Questa è la topologia consigliata per la distribuzione incrementale.

**Opzione di distribuzione incrementale**

![Diagramma dell'opzione di migrazione dipartimentale (di reparto)](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se si connette la distribuzione di Skype for Business Server a un partner SIP diretto certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra il Mediation Server e il PBX. Per un elenco dei partner SIP diretti certificati, vedere il [programma Microsoft Unified Communications Open Interoperability](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

In questa topologia sono abilitati i reparti o i gruppi di lavoro selezionati per VoIP aziendale. Un gateway PSTN collega il gruppo di lavoro abilitato VoIP (Voice over Internet Protocol) al PBX. Gli utenti abilitati per VoIP aziendale, inclusi i dipendenti remoti, comunicano tramite la rete IP. Le chiamate effettuate dagli utenti di VoIP aziendale alla rete PSTN e ai colleghi che non sono abilitate per VoIP aziendale vengono instradate al gateway PSTN appropriato. Le chiamate di colleghi che si trovano ancora nel sistema PBX o dai chiamanti della rete PSTN vengono instradate al gateway PSTN, che inoltra le chiamate a Skype for Business Server per il routing.

Esistono due configurazioni consigliate per connettere Enterprise Voice a un'infrastruttura PBX esistente per l'interoperabilità: VoIP aziendale dietro il PBX e VoIP aziendale davanti al PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>VoIP aziendale dietro il PBX

Quando Enterprise Voice viene distribuita dietro il PBX, tutte le chiamate dalla rete PSTN arrivano al PBX, che instrada le chiamate agli utenti di VoIP aziendale a un gateway PSTN e chiama gli utenti PBX al PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>VoIP aziendale davanti al PBX

Quando Enterprise Voice viene distribuita davanti al PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Skype for Business Server e chiama gli utenti PBX al PBX. Le chiamate alla rete PSTN sia dagli utenti VoIP aziendali che da quelli PBX vengono instradate tramite il network IP al gateway PSTN più efficiente rispetto ai costi. La tabella seguente mostra i vantaggi e gli svantaggi di questa configurazione.

**Vantaggi e svantaggi della distribuzione di VoIP aziendale davanti al PBX**

|**Vantaggi**|**Svantaggi**|
|:-----|:-----|
|Il PBX serve ancora agli utenti non abilitati per VoIP aziendale.  <br/> |I gateway esistenti potrebbero non supportare le caratteristiche o le capacità desiderate.  <br/> |
|PBX gestisce tutti i dispositivi precedenti.  <br/> |Richiede un trunk dal gateway al PBX e dal gateway al server Mediation. Potrebbe essere necessario un numero maggiore di Trunks dal provider di servizi.  <br/> |
|Gli utenti di VoIP aziendale mantengono gli stessi numeri di telefono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Distribuzione solo VoIP

Enterprise Voice offre nuove aziende e nuovi siti di Office per le aziende esistenti, con l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione PBX o di incorrere in una sostanziale distribuzione e manutenzione costi di un'infrastruttura IP-PBX. Questa soluzione supporta sia i lavoratori in loco che i dipendenti remoti.

In questa distribuzione tutte le chiamate vengono instradate tramite la rete IP. Le chiamate alla rete PSTN vengono instradate al gateway PSTN appropriato. Skype for business o Lync Phone Edition funge da softphone. Il controllo delle chiamate remote non è disponibile e non è necessario perché non ci sono telefoni PBX da controllare dagli utenti. I servizi di segreteria telefonica e di operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.

> [!NOTE]
> Oltre all'infrastruttura di rete necessaria per supportare Skype for Business Server, una distribuzione solo VoIP può usare un piccolo gateway qualificato per il supporto di fax e dispositivi analogici.

La figura seguente mostra una topologia tipica per una distribuzione solo VoIP.

**Opzione di distribuzione solo VoIP**

![Opzione di distribuzione vergine](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

## <a name="pstn-gateway-deployment-options"></a>Opzioni di distribuzione del gateway PSTN

### <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che traducono segnalazioni e elementi multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN, direttamente o tramite connessione ai trunk SIP. In entrambe le topologie il gateway termina la rete PSTN. Il gateway è isolato nella relativa subnet ed è connesso alla rete aziendale tramite il server Mediation.

Un'organizzazione con più siti in genere distribuisce uno o più gateway in ogni sito. I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in una singola casella. Se i siti di succursale usano un gateway, è necessario che il registrar e Mediation Server sia obbligatorio nel sito, a meno che il collegamento WAN non sia resiliente. Uno o più server di mediazione, che sono collocati nei server front-end, possono instradare le chiamate per uno o più gateway in ogni sito. È consigliabile che il registrar, il Mediation Server e il gateway richiesto nel sito vengano distribuiti come Survivable Branch Appliance.

La determinazione del numero, delle dimensioni e della posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario apportare quando si pianifica l'infrastruttura VoIP aziendale.

Ecco le principali domande da prendere in considerazione. Tieni presente che le risposte a queste domande sono tutte interdipendenti

- Quanti gateway PSTN sono necessari? La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico di traffico) e dal numero di siti (ogni sito ne ha bisogno).

- Quali sono le dimensioni dei gateway? La risposta dipende dal numero di utenti nel sito e dal carico di traffico.

- Dove devono essere ubicati i gateway? La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.

  Dovresti anche prendere in considerazione le opzioni della topologia del gateway (per informazioni dettagliate, Vedi topologie del gateway più avanti in questo argomento).

#### <a name="mn-trunk-support"></a>Supporto di M:N trunk

I Mediation Server possono instradare le chiamate attraverso più gateway, Session Border Controller (SBCs) forniti da provider di servizi di telefonia Internet o una combinazione dei due. Inoltre, più server di mediazione nel pool possono interagire con più gateway. La route logica definita tra un Mediation Server e un gateway viene chiamata trunk. Quando un utente interno inserisce una chiamata PSTN, la logica di routing in uscita nel pool Front-End sceglie quale trunk per instradare oltre tutte le possibili combinazioni che potrebbero essere disponibili per il routing di quella particolare chiamata. Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un determinato Mediation Server nel pool, la chiamata verrà riprovata in un server di mediazione alternativo nel pool.

Per informazioni dettagliate sulla pianificazione di più gateway, vedere [trunk di M:N in Skype for Business Server](m-n-trunk.md).

Per informazioni dettagliate sugli altri miglioramenti del routing in uscita, vedere [Route di chiamata](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologie del gateway

Quando si considerano le domande fondamentali della distribuzione di gateway, eseguire le operazioni seguenti:

1. Contare i siti in cui si vuole specificare la connettività PSTN tramite VoIP aziendale.

2. Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate per ora per utente).

3. Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.

Con questa topologia, le chiamate tra i dipendenti di ogni sito e tra i siti sono tutte instradate sulla Intranet. Le chiamate a PSTN vengono instradate tramite la rete IP aziendale verso i gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o anche migliaia di siti distribuiti in uno o più continenti, come fanno molti istituti finanziari e altre imprese di grandi dimensioni? In questi casi, la distribuzione di un gateway separato in ogni sito non è pratica.

Per risolvere questo problema, molte aziende di grandi dimensioni preferiscono distribuire uno o più siti centrali di telefonia di grandi dimensioni.

In questa topologia, diversi gateway di grandi dimensioni sufficienti per supportare il caricamento previsto dell'utente vengono distribuiti in ogni sito centrale. Tutte le chiamate agli utenti dell'organizzazione vengono inoltrate dal provider di servizi telefonici della società a un sito centrale. La logica di routing nel sito centrale determina se la chiamata deve essere instradata tramite Intranet o PSTN.

#### <a name="gateway-location"></a>Posizione del gateway

La posizione del gateway può anche determinare i tipi di gateway scelti e il modo in cui vengono configurati. Esistono decine di protocolli PSTN, nessuno dei quali è uno standard mondiale. Se tutti i gateway si trovano in un singolo paese/area geografica, questo non è un problema, ma se si individuano i gateway in più paesi/aree geografiche, ognuno deve essere configurato in base agli standard PSTN di tale paese/area geografica. Inoltre, i gateway certificati per l'operazione, ad esempio Canada, potrebbero non essere certificati in India, Brasile o Unione europea.

#### <a name="gateway-size-and-number"></a>Dimensioni e numero del gateway

Gateway PSTN che la maggior parte delle organizzazioni valuterà la distribuzione di intervalli di dimensioni da 2 a fino a un massimo di 960 porte. (Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi telefonici). Per valutare il numero di porte richieste dall'organizzazione, usare le linee guida seguenti:

- Le organizzazioni con utilizzo della telefonia leggera (una chiamata PSTN per utente per ora) devono allocare una sola porta per ogni 15 utenti. Se ad esempio sono presenti 20 utenti, sarà necessario un gateway con due porte.

- Le organizzazioni con un utilizzo moderato della telefonia (due chiamate PSTN per utente per ora) devono allocare una sola porta per ogni 10 utenti. Ad esempio, se si hanno 100 utenti, è necessario un totale di 10 porte allocate tra uno o più gateway.

- Le organizzazioni con uso di telefonia pesante (tre o più chiamate PSTN per utente per ora) devono allocare una porta per ogni cinque utenti. Ad esempio, se si hanno 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.

- Le porte aggiuntive possono essere acquisite Man mano che aumenta il numero di utenti o la quantità di traffico nell'organizzazione.

Per qualsiasi numero di utenti che è necessario supportare, è possibile scegliere di distribuire meno, gateway più grandi o quelli più piccoli. Di norma, è consigliabile un minimo di due gateway per un'organizzazione per mantenere la disponibilità se un gateway non riesce.

Ogni gateway PSTN distribuito deve avere almeno un Mediation Server corrispondente.


