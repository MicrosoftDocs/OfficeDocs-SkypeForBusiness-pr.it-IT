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
description: Le connessioni SIP dirette sono supportate tra Skype for Business Server e i gateway PSTN e IP-PBX in VoIP aziendale.
ms.openlocfilehash: 6e30a24bd4509d20a4ad19192e677e3bea21fff9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834456"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Connessioni SIP dirette in Skype for Business Server

Le connessioni SIP dirette sono supportate tra Skype for Business Server e i gateway PSTN e IP-PBX in VoIP aziendale.

È possibile utilizzare le connessioni SIP dirette per connettere Skype for Business Server a una delle seguenti operazioni:

- IP-PBX

- Gateway PSTN

Per implementare una connessione SIP diretta, è fondamentalmente necessario eseguire gli stessi passaggi di distribuzione previsti per l'implementazione di un trunk SIP. In entrambi i casi, la connessione viene implementata utilizzando l'interfaccia esterna di un Mediation Server. L'unica differenza è rappresentata dal fatto che i trunk SIP vengono connessi a un'entità esterna, quale un gateway ITSP, mentre le connessioni SIP dirette vengono connesse a un'entità interna nella rete locale, ad esempio un sistema IP-PBX o un gateway PSTN (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Opzioni di distribuzione SIP dirette

### <a name="skype-for-business-server-stand-alone"></a>Stand-Alone di Skype for Business Server
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se nell'organizzazione viene utilizzata una delle distribuzioni descritte in questa sezione, è possibile utilizzare Skype for Business Server come unica soluzione di telefonia per parte o per tutta l'organizzazione. In questa sezione vengono descritte dettagliatamente le distribuzioni seguenti:

- **Distribuzione incrementale:** Questa opzione presuppone che si disponga di un'infrastruttura PBX (Private Branch Exchange) esistente e che si desideri introdurre la voce di VoIP aziendale in modo incrementale ai gruppi o ai team più piccoli all'interno dell'organizzazione.

- **Distribuzione solo VoIP:** questa opzione presuppone che si stia valutando la possibilità di distribuire Enterprise Voice in un sito privo di un'infrastruttura di telefonia tradizionale.

#### <a name="incremental-deployment"></a>Distribuzione incrementale

Nella distribuzione incrementale, Skype for Business Server è l'unica soluzione di telefonia per singoli team o reparti, mentre gli altri utenti di un'organizzazione continuano a usare un sistema PBX. Questa strategia di distribuzione incrementale consente di introdurre telefonia IP all'interno dell'organizzazione tramite programmi pilota controllati. I gruppi di lavoro i cui bisogni di comunicazione sono meglio serviti dalle comunicazioni unificate Microsoft vengono spostati in VoIP aziendale, mentre altri utenti restano nel PBX esistente. È possibile eseguire la migrazione di altri gruppi di lavoro in VoIP aziendale, in base alle esigenze.

L'opzione incrementale è consigliata se si dispone di gruppi di utenti chiaramente definiti che dispongono di requisiti di comunicazione comuni e che si prestano alla gestione centralizzata. Questa opzione è efficace anche se si dispone di team o reparti distribuiti su aree geografiche estese, in cui il risparmio delle tariffe interurbane può essere significativo. In effetti, questa opzione è utile per creare team virtuali i cui membri possono essere sparsi in tutto il mondo. È possibile creare, modificare o sciogliere tali team in risposta rapida allo spostamento dei requisiti aziendali.

Nella figura seguente viene illustrata la topologia generica per la distribuzione di VoIP aziendale dietro un sistema PBX. Questa è la topologia consigliata per la distribuzione incrementale.

**Opzione di distribuzione incrementale**

![Diagramma dell'opzione di migrazione dipartimentale](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se si sta connettendo la distribuzione di Skype for Business Server a un partner SIP diretto certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra il Mediation Server e il sistema PBX. Per un elenco di partner diretti SIP certificati, vedere il  [programma Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

In questa topologia, i reparti o i gruppi di lavoro selezionati sono abilitati per VoIP aziendale. Un gateway PSTN collega il gruppo di lavoro abilitato VoIP (Voice over Internet Protocol) al sistema PBX. Gli utenti abilitati per VoIP aziendale, compresi i lavoratori remoti, comunicano tra la rete IP. Le chiamate effettuate da utenti di VoIP aziendale alla rete PSTN e ai colleghi che non sono abilitati per VoIP aziendale vengono instradate al gateway PSTN appropriato. Le chiamate provenienti da colleghi che sono ancora nel sistema PBX o dai chiamanti sulla rete PSTN vengono instradate al gateway PSTN, che inoltra le chiamate a Skype for Business Server per il routing.

Sono disponibili due configurazioni consigliate per connettere VoIP aziendale a un'infrastruttura PBX esistente per l'interoperabilità: Enterprise Voice behind the PBX and Enterprise Voice di fronte al sistema PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>VoIP aziendale dietro il sistema PBX

Quando Enterprise Voice viene distribuita dietro il sistema PBX, tutte le chiamate provenienti dalla rete PSTN giungono al PBX, che instrada le chiamate agli utenti di VoIP aziendale verso un gateway PSTN e chiama gli utenti PBX al sistema PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>VoIP aziendale di fronte al sistema PBX

Quando Enterprise Voice viene distribuita di fronte al sistema PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Skype for Business Server e chiama gli utenti PBX al sistema PBX. Le chiamate alla rete PSTN da parte di utenti di VoIP aziendale e PBX vengono instradate tramite la Network IP al gateway PSTN più conveniente. Nella tabella seguente vengono illustrati i vantaggi e gli svantaggi di questa configurazione.

**Vantaggi e svantaggi della distribuzione di VoIP aziendale davanti al PBX**

|**Vantaggi**|**Svantaggi**|
|:-----|:-----|
|Il sistema PBX serve ancora gli utenti non abilitati per VoIP aziendale.  <br/> |I gateway esistenti potrebbero non supportare le caratteristiche o la capacità desiderata.  <br/> |
|Il sistema PBX gestisce tutti i dispositivi precedenti.  <br/> |Richiede un trunk dal gateway al PBX e dal gateway al Mediation Server. Potrebbe essere necessario un numero maggiore di trunk dal provider di servizi.  <br/> |
|Gli utenti di VoIP aziendale conservano gli stessi numeri di telefono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Distribuzione di VoIP-Only

Enterprise Voice fornisce nuove aziende e nuovi siti di Office per le aziende esistenti, con l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione del PBX o di incorrere in sostanziali costi di distribuzione e manutenzione di un'infrastruttura IP-PBX. Questa soluzione supporta sia i lavoratori in sito che quelli remoti.

In questa distribuzione, tutte le chiamate vengono instradate sulla rete IP. Le chiamate alla rete PSTN vengono instradate al gateway PSTN appropriato. Skype for business o Lync Phone Edition funge da softphone. Il controllo delle chiamate remote non è disponibile e non è necessario perché non sono presenti telefoni PBX che gli utenti possono controllare. I servizi di segreteria telefonica e di operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.

> [!NOTE]
> Oltre all'infrastruttura di rete necessaria per supportare Skype for Business Server, una distribuzione solo VoIP può utilizzare un gateway piccolo e qualificato per il supporto di macchine fax e dispositivi analogici.

Nella figura seguente viene illustrata una topologia tipica per una distribuzione solo VoIP.

**Opzione di distribuzione solo VoIP**

![Opzione di distribuzione di Vergine](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.

## <a name="pstn-gateway-deployment-options"></a>Opzioni di distribuzione di gateway PSTN

### <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che convertono i segnali e i dati multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN direttamente o mediante connessione a trunk SIP. In entrambe le topologie il gateway termina la rete PSTN. Il gateway è isolato nella propria subnet ed è connesso alla rete aziendale tramite il Mediation Server.

Un'organizzazione con più siti in genere distribuisce uno o più gateway in ogni sito. I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in una singola casella. Se i siti di succursale utilizzano un gateway, è necessario che il servizio di registrazione e Mediation Server siano necessari nel sito, a meno che il collegamento WAN non sia resiliente. Uno o più Mediation Server, che sono collocati nei Front End Server, possono instradare le chiamate per uno o più gateway in ogni sito. È consigliabile che il servizio di registrazione, il Mediation Server e il gateway richiesti nel sito siano distribuiti come Survivable Branch Appliance.

Determinare il numero, le dimensioni e la posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario apportare quando si pianifica l'infrastruttura VoIP aziendale.

Di seguito sono riportate le principali domande da prendere in considerazione. Tenere presente che le risposte a queste domande sono tutte interdipendenti

- Quanti gateway PSTN sono necessari? La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico del traffico) e dal numero di siti (ogni sito ne ha bisogno).

- Quali dimensioni devono essere i gateway? La risposta dipende dal numero di utenti nel sito e dal carico di traffico.

- Dove devono essere ubicati i gateway? La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.

  È inoltre consigliabile prendere in considerazione le opzioni di topologia del gateway (per informazioni dettagliate, vedere Topologie del gateway più avanti in questo argomento).

#### <a name="mn-trunk-support"></a>Supporto dei trunk M:N

I Mediation Server possono instradare le chiamate tramite più gateway, Session Border Controller (SBCs) forniti da provider di servizi di telefonia Internet o una combinazione di due. Inoltre, più Mediation Server nel pool è in grado di interagire con più gateway. La route logica definita tra un Mediation Server e un gateway è denominata trunk. Quando un utente interno inserisce una chiamata PSTN, la logica di routing in uscita nel pool Front End sceglie il trunk da instradare oltre tutte le combinazioni possibili che potrebbero essere disponibili per il routing di quella chiamata specifica. Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un determinato Mediation Server nel pool, la chiamata verrà ritentata in un Mediation server alternativo nel pool.

Per informazioni dettagliate sulla pianificazione di più gateway, vedere [M:N trunk in Skype for Business Server](m-n-trunk.md).

Per informazioni dettagliate sull'altro miglioramento del routing in uscita, vedere [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologie di gateway

Se si considerano le questioni fondamentali della distribuzione di gateway, eseguire la procedura seguente:

1. Contare i siti in cui si desidera fornire la connettività PSTN tramite VoIP aziendale.

2. Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate all'ora per utente).

3. Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.

Con questa topologia, le chiamate tra i lavoratori di ogni sito e tra i siti vengono instradate all'interno della rete Intranet. Le chiamate alla rete PSTN vengono instradate tramite la Network IP dell'organizzazione ai gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o addirittura migliaia di siti distribuiti in uno o più continenti, come fanno molte istituzioni finanziarie e altre imprese di grandi dimensioni? In questi casi, la distribuzione di un gateway separato in ogni sito non è pratico.

Per risolvere questo problema, molte società di grandi dimensioni preferiscono distribuire uno o più siti centrali di telefonia di grandi dimensioni.

In questa topologia, numerosi gateway di grandi dimensioni sufficienti per ospitare il carico utente previsto vengono distribuiti in ogni sito centrale. Tutte le chiamate agli utenti nell'organizzazione vengono inoltrate dal provider di servizi telefonici della società a un sito centrale. La logica di routing nel sito centrale determina se la chiamata deve essere instradata attraverso la rete Intranet o la rete PSTN.

#### <a name="gateway-location"></a>Posizione del gateway

Il percorso del gateway può anche determinare i tipi di gateway scelti e il modo in cui vengono configurati. Sono disponibili dozzine di protocolli PSTN, nessuno dei quali è uno standard mondiale. Se tutti i gateway sono situati in un singolo paese/area geografica, non si tratta di un problema, ma se si individuano i gateway in diversi paesi/aree geografiche, è necessario configurarli in base agli standard PSTN di quel paese/area geografica. Inoltre, i gateway certificati per l'operazione, ad esempio il Canada, potrebbero non essere certificati in India, Brasile o nell'Unione europea.

#### <a name="gateway-size-and-number"></a>Dimensione e numero del gateway

I gateway PSTN che la maggior parte delle organizzazioni valuterà la distribuzione di un intervallo di dimensioni da 2 a fino a 960 porte. (Esistono anche gateway più grandi, ma questi sono utilizzati principalmente dai provider di servizi di telefonia). Quando si valuta il numero di porte richieste dall'organizzazione, utilizzare le linee guida seguenti:

- Le organizzazioni con utilizzo di telefonia chiaro (una chiamata PSTN per utente all'ora) devono allocare una porta per ogni 15 utenti. Ad esempio, se si dispone di 20 utenti, sarà necessario un gateway con due porte.

- Le organizzazioni con un utilizzo di telefonia moderato (due chiamate PSTN per utente all'ora) devono allocare una porta per ogni 10 utenti. Ad esempio, se si dispone di 100 utenti, sarà necessario un totale di 10 porte allocate tra uno o più gateway.

- Le organizzazioni con un utilizzo pesante della telefonia (tre o più chiamate PSTN per utente all'ora) devono allocare una porta per ogni cinque utenti. Ad esempio, se si dispone di 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.

- È possibile acquisire ulteriori porte quando aumenta il numero di utenti o la quantità di traffico nell'organizzazione.

Per un determinato numero di utenti che è necessario supportare, è possibile scegliere di distribuire meno, gateway più grandi o più piccoli. Come regola generale, è consigliabile un minimo di due gateway per un'organizzazione per mantenere la disponibilità se un gateway ha esito negativo.

Ogni gateway PSTN distribuito deve disporre di almeno un Mediation Server corrispondente.


