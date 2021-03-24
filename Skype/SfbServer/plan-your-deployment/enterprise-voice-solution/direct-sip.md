---
title: Connessioni SIP dirette in Skype for Business Server
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Le connessioni SIP dirette sono supportate tra Skype for Business Server ed entrambi i gateway PSTN e IP-PBX in VoIP aziendale.
ms.openlocfilehash: 7a70a6f3afd303ef5847993240b26b47d1b4ceac
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096416"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Connessioni SIP dirette in Skype for Business Server

Le connessioni SIP dirette sono supportate tra Skype for Business Server ed entrambi i gateway PSTN e IP-PBX in VoIP aziendale.

È possibile utilizzare connessioni SIP dirette per connettere Skype for Business Server a uno dei seguenti:

- IP-PBX

- Gateway PSTN

Per implementare una connessione SIP diretta, è fondamentalmente necessario eseguire gli stessi passaggi di distribuzione previsti per l'implementazione di un trunk SIP. In entrambi i casi, la connessione viene implementata utilizzando l'interfaccia esterna di un Mediation Server. L'unica differenza è rappresentata dal fatto che i trunk SIP vengono connessi a un'entità esterna, quale un gateway ITSP, mentre le connessioni SIP dirette vengono connesse a un'entità interna nella rete locale, ad esempio un sistema IP-PBX o un gateway PSTN (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Opzioni di distribuzione SIP diretto

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se l'organizzazione usa una delle distribuzioni descritte in questa sezione, è possibile utilizzare Skype for Business Server come unica soluzione di telefonia per parte o per tutta l'organizzazione. In questa sezione vengono descritte in dettaglio le distribuzioni seguenti:

- **Distribuzione incrementale:** Questa opzione presuppone che tu abbia un'infrastruttura PBX (Private Branch Exchange) esistente e che intendi introdurre VoIP aziendale in modo incrementale a gruppi o team più piccoli all'interno dell'organizzazione.

- **Distribuzione solo VoIP:** questa opzione presuppone che si consideri la distribuzione di VoIP aziendale in un sito che non dispone di un'infrastruttura di telefonia tradizionale.

#### <a name="incremental-deployment"></a>Distribuzione incrementale

Nella distribuzione incrementale, Skype for Business Server è l'unica soluzione di telefonia per singoli team o reparti, mentre il resto degli utenti di un'organizzazione continua a utilizzare un SISTEMA PBX. Questa strategia di distribuzione incrementale consente di introdurre la telefonia IP nell'organizzazione tramite programmi pilota controllati. I gruppi di lavoro le cui esigenze di comunicazione sono meglio servite da Microsoft Unified Communications vengono spostati in VoIP aziendale, mentre altri utenti rimangono nel PBX esistente. È possibile eseguire la migrazione di gruppi di lavoro aggiuntivi VoIP aziendale, in base alle esigenze.

L'opzione incrementale è consigliata se si dispone di gruppi di utenti chiaramente definiti che hanno requisiti di comunicazione in comune e che si prestano alla gestione centralizzata. Questa opzione è efficace anche se si dispone di team o reparti distribuiti in aree geografiche ampie, in cui il risparmio in costi a lunga distanza può essere significativo. In realtà, questa opzione è utile per creare team virtuali i cui membri potrebbero essere sparsi in tutto il mondo. È possibile creare, modificare o eliminare tali team in rapida risposta ai cambiamenti dei requisiti aziendali.

Nella figura seguente viene illustrata la topologia generica per la distribuzione di VoIP aziendale dietro un SISTEMA PBX. Questa è la topologia consigliata per la distribuzione incrementale.

**Opzione di distribuzione incrementale**

![Diagramma dell'opzione di migrazione del reparto](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se si connette la distribuzione di Skype for Business Server a un partner Direct SIP certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra mediation server e PBX. Per un elenco dei partner Direct SIP certificati, vedere [Microsoft Unified Communications Open Interoperability Program.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)

> [!NOTE]
> Il percorso multimediale mostrato in questa figura ha il bypass multimediale abilitato (configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

In questa topologia, i reparti o i gruppi di lavoro selezionati sono abilitati per VoIP aziendale. Un gateway PSTN collega il gruppo di lavoro abilitato al protocollo VoIP (Voice over Internet Protocol) al PBX. Gli utenti abilitati per VoIP aziendale, inclusi i lavoratori remoti, comunicano attraverso la rete IP. Le chiamate VoIP aziendale utenti alla rete PSTN e ai colleghi non abilitati per VoIP aziendale vengono instradati al gateway PSTN appropriato. Le chiamate provenienti da colleghi ancora nel sistema PBX o da chiamanti sulla rete PSTN vengono instradati al gateway PSTN, che inoltra le chiamate a Skype for Business Server per il routing.

Esistono due configurazioni consigliate per la VoIP aziendale a un'infrastruttura PBX esistente per l'interoperabilità: VoIP aziendale dietro il PBX e VoIP aziendale davanti al PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>VoIP aziendale dietro il PBX

Quando VoIP aziendale viene distribuito dietro il SISTEMA PBX, tutte le chiamate dalla rete PSTN arrivano al SISTEMA PBX, che instrada le chiamate agli utenti di VoIP aziendale a un gateway PSTN e le chiamate agli utenti PBX al PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>VoIP aziendale davanti al PBX

Quando VoIP aziendale viene distribuito davanti al PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Skype for Business Server e le chiamate per gli utenti PBX al PBX. Le chiamate alla rete PSTN da utenti VoIP aziendale e PBX vengono instradati attraverso la rete IP al gateway PSTN più efficiente in termini di costi. Nella tabella seguente vengono illustrati i vantaggi e gli svantaggi di questa configurazione.

**Vantaggi e svantaggi della distribuzione di VoIP aziendale front-of-PBX**

|**Vantaggi**|**Svantaggi**|
|:-----|:-----|
|Pbx serve ancora gli utenti non abilitati per VoIP aziendale.  <br/> |I gateway esistenti potrebbero non supportare le funzionalità o la capacità desiderate.  <br/> |
|Pbx gestisce tutti i dispositivi precedenti.  <br/> |Richiede un trunk dal gateway al PBX e dal gateway al Mediation Server. Potrebbero essere necessari più trunk dal provider di servizi.  <br/> |
|VoIP aziendale utenti mantengono gli stessi numeri di telefono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only distribuzione

VoIP aziendale offre alle nuove aziende, e anche ai nuovi siti di ufficio per le aziende esistenti, l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione PBX o sostenere i costi sostanziali di distribuzione e manutenzione di un'infrastruttura IP-PBX. Questa soluzione supporta sia i lavoratori locali che i lavoratori remoti.

In questa distribuzione tutte le chiamate vengono instradati sulla rete IP. Le chiamate alla rete PSTN vengono instradati al gateway PSTN appropriato. Skype for Business o Lync Phone Edition funge da softphone. Il controllo delle chiamate remote non è disponibile e non è necessario perché non sono disponibili telefoni PBX che gli utenti possono controllare. I servizi di segreteria telefonica e operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.

> [!NOTE]
> Oltre all'infrastruttura di rete necessaria per supportare Skype for Business Server, una distribuzione solo VoIP può utilizzare un gateway qualificato di piccole dimensioni per supportare i fax e i dispositivi analogici.

Nella figura seguente viene illustrata una topologia tipica per una distribuzione solo VoIP.

**Opzione di distribuzione solo VoIP**

![Opzione di distribuzione Greenfidle](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Il percorso multimediale mostrato in questa figura ha il bypass multimediale abilitato (configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

## <a name="pstn-gateway-deployment-options"></a>Opzioni di distribuzione del gateway PSTN

### <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che convertono i segnali e i dati multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN direttamente o mediante connessione a trunk SIP. In entrambe le topologie, il gateway termina la rete PSTN. Il gateway è isolato nella propria subnet ed è connesso alla rete aziendale tramite Mediation Server.

Un'organizzazione con più siti distribuisce in genere uno o più gateway in ogni sito. I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in un'unica casella. Se i siti di succursale utilizzano un gateway, nel sito sono necessari sia una funzione di registrazione che un Mediation Server, a meno che il collegamento WAN non sia resiliente. Uno o più Mediation Server, collocati nei Front End Server, possono instradare le chiamate per uno o più gateway in ogni sito. È consigliabile distribuire la funzione di registrazione, il Mediation Server e il gateway necessari nel sito come Survivable Branch Appliance.

Determinare il numero, le dimensioni e la posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario prendere durante la pianificazione dell'VoIP aziendale aziendale.

Ecco le principali domande da considerare. Tenere presente che le risposte a queste domande sono tutte interdipendenti

- Quanti gateway PSTN sono necessari? La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico di traffico) e dal numero di siti (ogni sito ne richiede uno).

- Quali dimensioni devono essere i gateway? La risposta dipende dal numero di utenti nel sito e dal carico di traffico.

- Dove devono trovarsi i gateway? La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.

  È inoltre consigliabile considerare le opzioni di topologia del gateway (per informazioni dettagliate, vedere Topologie gateway più avanti in questo argomento).

#### <a name="mn-trunk-support"></a>Supporto dei trunk M:N

I Mediation Server possono instradare le chiamate attraverso più gateway, session border controller (SBC) forniti dai provider di servizi di telefonia Internet o una combinazione dei due. Inoltre, più Mediation Server nel pool possono interagire con più gateway. La route logica definita tra un Mediation Server e un gateway è denominata trunk. Quando un utente interno esegue una chiamata PSTN, la logica di routing in uscita nel pool Front End sceglie il trunk da instradare al di fuori di tutte le possibili combinazioni disponibili per il routing di quella particolare chiamata. Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un Mediation Server specifico nel pool, la chiamata verrà ritentata a un Mediation Server alternativo nel pool.

Per informazioni dettagliate sulla pianificazione di più gateway, vedere [Trunk M:N in Skype for Business Server.](m-n-trunk.md)

Per informazioni dettagliate su altri miglioramenti del routing in uscita, vedere [Call Routes.](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes)

#### <a name="gateway-topologies"></a>Topologie gateway

Quando si considerano le domande fondamentali della distribuzione del gateway, attenersi alla seguente procedura:

1. Contare i siti in cui si desidera fornire la connettività PSTN utilizzando VoIP aziendale.

2. Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate all'ora per utente).

3. Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.

Con questa topologia, le chiamate tra i dipendenti di ogni sito e tra siti vengono tutte instradati sulla rete Intranet. Le chiamate alla rete PSTN vengono instradati attraverso la rete IP aziendale ai gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o persino migliaia di siti distribuiti in uno o più continenti, come fanno molti istituti finanziari e altre grandi imprese? In questi casi, la distribuzione di un gateway separato in ogni sito non è pratica.

Per risolvere questo problema, molte aziende di grandi dimensioni preferiscono distribuire uno o pochi siti centrali di telefonia di grandi dimensioni.

In questa topologia, in ogni sito centrale vengono distribuiti diversi gateway di grandi dimensioni sufficienti per supportare il carico previsto per gli utenti. Tutte le chiamate agli utenti dell'organizzazione vengono inoltrate dal provider di servizi telefonici dell'azienda a un sito centrale. La logica di routing nel sito centrale determina se la chiamata deve essere instradata sulla Rete Intranet o sulla rete PSTN.

#### <a name="gateway-location"></a>Posizione gateway

La posizione del gateway può anche determinare i tipi di gateway che si sceglie e la modalità di configurazione. Esistono decine di protocolli PSTN, nessuno dei quali è uno standard mondiale. Se tutti i gateway si trovano in un singolo paese/area geografica, non si tratta di un problema, ma se si individuano gateway in diversi paesi/aree geografiche, ognuno di essi deve essere configurato in base agli standard PSTN di quel paese/area geografica. Inoltre, i gateway certificati per il funzionamento in Canada, ad esempio, potrebbero non essere certificati in India, Brasile o Unione Europea.

#### <a name="gateway-size-and-number"></a>Dimensioni e numero gateway

I gateway PSTN che la maggior parte delle organizzazioni considereranno la distribuzione di un intervallo di dimensioni compreso tra 2 e fino a 960 porte. Esistono gateway ancora più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia. Quando si stima il numero di porte richieste dall'organizzazione, utilizzare le linee guida seguenti:

- Le organizzazioni con utilizzo di telefonia leggera (una chiamata PSTN per utente all'ora) devono allocare una porta ogni 15 utenti. Ad esempio, se si dispone di 20 utenti, sarà necessario un gateway con due porte.

- Le organizzazioni con un utilizzo di telefonia moderato (due chiamate PSTN per utente all'ora) devono allocare una porta ogni 10 utenti. Ad esempio, se si dispone di 100 utenti, sarà necessario un totale di 10 porte allocate tra uno o più gateway.

- Le organizzazioni con un utilizzo elevato della telefonia (tre o più chiamate PSTN per utente all'ora) devono allocare una porta ogni cinque utenti. Ad esempio, se si dispone di 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.

- È possibile acquisire porte aggiuntive con l'aumentare del numero di utenti o della quantità di traffico nell'organizzazione.

Per un determinato numero di utenti che è necessario supportare, è possibile scegliere di distribuire un numero minore di gateway più grandi o più piccoli. Di norma, è consigliabile utilizzare almeno due gateway per un'organizzazione per mantenere la disponibilità in caso di errore di un gateway.

Ogni gateway PSTN distribuito deve disporre di almeno un Mediation Server corrispondente.