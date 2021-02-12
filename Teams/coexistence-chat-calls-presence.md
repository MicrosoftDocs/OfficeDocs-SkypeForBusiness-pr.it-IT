---
title: Coesistenza con Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportamento di coesistenza tra Teams & Skype for Business, inclusi i parametri di routing, il routing delle chiamate della chat &, le chat & le chiamate da thread preesistnti, & presenza.
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661348"
---
# <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

La coesistenza e l'interoperabilità tra client e utenti di Skype for Business e Teams è definita dalle modalità di aggiornamento di Teams, descritte nelle indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

A un determinato utente verrà sempre assegnata una modalità di aggiornamento di Teams, per impostazione predefinita o esplicitamente dall'amministratore. Il valore predefinito è *Isole.* Gli utenti aggiornati a Teams hanno la modalità *TeamsOnly.* *Anche SfBOnly,* *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings* sono modalità possibili.


## <a name="routing-parameters"></a>Parametri di routing

La modalità di aggiornamento di Teams del destinatario è fondamentale per determinare il comportamento di chat, chiamate e presenza, sia all'interno di un tenant che tra tenant federati.

Se il mittente usa Teams, la decisione sull'instradamento viene presa quando si crea un nuovo thread di conversazione. I thread delle conversazioni esistenti in Teams mantengono sempre il metodo di routing determinato al momento della creazione del thread: Teams supporta i thread permanenti.

 I metodi di routing dei thread sono:  

- *nativo* per una conversazione da Teams a Teams nel tenant
- *interoperabilità* per una conversazione nel tenant da Teams a Skype for Business
- *federato* per una conversazione federata tra tenant

I parametri che determinano il metodo di routing del thread sono:

- Modalità di aggiornamento Teams del destinatario
- Client utilizzato dal mittente
- Se la conversazione è nuova o fa parte di un thread esistente
- Se la conversazione è nel tenant o federata
- Se la conversazione è possibile
    - *L'interoperabilità tra tenant* richiede che il tenant sia solo online o ibrido di Skype for Business. I tenant locali non possono avere l'interoperabilità in-tenant.
    - *La federazione tra tenant* richiede sempre una configurazione corretta della federazione di Skype for Business e una configurazione corretta della federazione di Teams da entrambi i tenant. Per uno dei tenant non è richiesta la distribuzione ibrida di Skype for Business.
    - Se l'account Skype for Business dell'origine è ospitata in locale, l'utente non può usare il client Teams per l'interoperabilità all'interno del tenant o per la federazione. Tale utente può utilizzare il client Skype for Business solo per l'interoperabilità e la federazione.
    - La comunicazione da Teams a Teams è sempre possibile nel tenant.

> [!NOTE]
> Se il destinatario e il mittente sono entrambi in modalità di aggiornamento di TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere [Esperienza di chat nativa per utenti esterni (federati) in Teams.](native-chat-for-external-users.md) Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con messaggi solo di testo.

## <a name="chat-and-call-routing"></a>Instradamento chat e chiamate

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routing nel tenant per nuove chat o chiamate 

Le tabelle seguenti acquisiscono il routing delle chat e delle chiamate in-tenant e sono valide per le nuove chiamate o le chat non avviate da un thread pre-esistente. Descrive quale client riceverà una nuova chiamata o una nuova chat, se originata da un utente a sinistra, a un utente del destinatario nel tenant a destra.

I messaggi inviati a utenti TeamsOnly verranno sempre indirizzati a Teams. I messaggi inviati agli utenti SfB verranno sempre indirizzati a Skype for Business, se la conversazione \* è possibile, come descritto in precedenza. I messaggi inviati agli utenti delle Isole verranno sempre indirizzati allo stesso client da cui sono stati inviati.

Le tabelle seguenti mostrano quale cliente in una determinata modalità riceverà una chiamata dall'origine (tre colonne all'estrema sinistra), a seconda della modalità di origine, scelta del cliente e della posizione del client Skype for Business (in sede o online).

Nelle tabelle seguenti: 
- **SfB \** _ rappresenta una delle modalità seguenti: _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings.*

- *Il testo in corsivo* evidenzia una conversazione di interoperabilità.

- **Non possibile** rappresenta una situazione in cui la chat o la chiamata non è possibile. In questi casi l'autore deve utilizzare Skype for Business. Questo è uno dei motivi per cui le indicazioni prescriptive di Microsoft per i clienti locali/ibridi usano una modalità diversa da Islands (in genere SfBWithTeamsCollab) come punto di partenza per il percorso di aggiornamento a Teams.

**Tabella 1a: instradamento di nuove chat o chiamate nel tenant verso un destinatario in modalità isole**

| <br/><br/> Modalità | Autore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route->| Destinatario <br/><br/> Isole  |
|--- |--- |--- |--- |--- |
| Isole | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| Online<br/> Online<br/> In un'ora e in un'ora<br/>In un'ora e in un'ora| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> In un'ora e in un'ora<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabella 1b: routing delle nuove chat o delle chiamate nel tenant a un destinatario in modalità \* SfB**

| <br/><br/> Modalità   | Autore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route-> |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Isole |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> In un'ora e in un'ora<br/> In un'ora e in un'ora<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Non possibile** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> In un'ora e in un'ora<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabella 1c: routing delle nuove chat o delle chiamate nel tenant a un destinatario in modalità TeamsOnly**

| <br/><br/> Modalità   | Autore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route->|   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Isole   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> In un'ora e in un'ora<br/> In un'ora e in un'ora<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Team* <br/>Teams <br/>*Team*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> In un'ora e in un'ora<br/> | &boxv;<br/>&boxv; | *Team*  <br/>*Team*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Routing federato per nuove chat o chiamate
  
Le tabelle seguenti acquisiscono il routing delle chiamate e chat federate e sono valide per nuove chiamate o chat. Descrivono quale client riceverà una nuova chiamata o chat, se originato da un utente a sinistra, a un utente di destinazione federato a destra.

In sintesi, se la conversazione è possibile, come descritto in precedenza, i messaggi inviati agli utenti di TeamsOnly vengono sempre inviati a Teams; i messaggi inviati agli utenti SfB verranno sempre inviati a Skype for Business; i messaggi inviati agli utenti delle Isole verranno sempre inviati a Skype for Business, indipendentemente dal client da cui sono \* stati inviati. Il routing per le chat e le chiamate federate è diverso dal routing in-tenant in quanto gli utenti delle Isole riceveranno sempre una comunicazione federata in Skype for Business.

Questo perché non possiamo presupporre che un partner Skype for Business federato usi già Teams se è in modalità Isole. Isole è la modalità predefinita, tuttavia non è possibile presupporre che tutti gli utenti delle isole ese possano eseguire Teams. Con l'instradamento a Skype for Business ci assicuriamo che nessuna comunicazione verso un utente delle Isole fallirà. Se si è instradato a Teams, la comunicazione potrebbe essere persa se l'obiettivo non ha utilizzato Teams. L'instradamento a Skype for Business assicura che il messaggio sia sempre ricevuto.  

> [!NOTE]
> L'implementazione corrente della federazione di Teams si basa sulla federazione di Skype for Business, quindi sfrutta l'infrastruttura di interoperabilità (che richiede che il tenant dell'autore sia solo online o ibrido di Skype for Business) e offre una serie ridotta di funzionalità rispetto a un thread nativo. Ci attendono di fornire la federazione nativa di Teams a Teams in futuro, a quel punto il thread sarà nativo e fornirà funzionalità complete.

Le tabelle seguenti descrivono quale cliente riceverà una chiamata dall'origine (tre colonne all'estrema sinistra), a seconda della modalità di origine, scelta del cliente e della posizione in cui è ospitato il client Skype for Business (in sede o online).

**Tabella 2a: routing federato di nuove chat o chiamate a un destinatario delle Isole**

| <br/><br/>Modalità   | Autore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route-> | Destinatario<br/><br/> Isole |
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> In un'ora e in un'ora<br/> In un'ora e in un'ora<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Non possibile**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> In un'ora e in un'ora<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabella 2b: routing federato di nuove chat o chiamate a un destinatario in modalità \* SfB**

| <br/><br/>Modalità   | Autore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route->|  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> In un'ora e in un'ora<br/> In un'ora e in un'ora<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Non possibile** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> In un'ora e in un'ora<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabella 2c: routing federato di nuove chat o chiamate a un destinatario in modalità TeamsOnly**

| <br/><br/>Modalità | Autore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route->|  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Isole  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> In un'ora e in un'ora<br/> In un'ora e in un'ora<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Team* <br/>**Non possibile** <br/>*Team* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> In un'ora e in un'ora| &boxv;<br/>&boxv;|*Team* <br/>*Team*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chat e chiamate da thread preesistnti

### <a name="from-teams"></a>Da Teams

Le chiamate o le chat avviate da un thread persistente preesistente in Teams verranno instradati allo stesso modo del thread, se tale opzione di instradamento è ancora disponibile.

Se il thread persistente preesistente in Teams era un thread nativo (ad esempio instradato a Teams), gli altri messaggi di chat e chiamate da quel thread verranno inviati a Teams. Se si tratta di un thread di interoperabilità (ad esempio instradato a Skype for Business), ulteriori messaggi di chat e chiamate verranno inoltrati a Skype for Business (sempre che siano disponibili opzioni di routing).

> [!NOTE]
> È possibile che i thread pre-esistenti in Teams non siano più instradabili, ad esempio quando il thread era un thread di interoperabilità con un utente che ora viene aggiornato a Teams. Poiché è stato creato come thread di interoperabilità, il thread verrà instradato a Skype for Business, ma tale utente non potrà più usare Skype for Business per chat e chiamate. In questo caso, il thread verrà disabilitato e non sarà possibile ulteriori comunicazioni.

### <a name="from-skype-for-business"></a>Da Skype for Business

I thread di Skype for Business non persistono oltre i 10 min. Timeout della sessione SIP. Le chat e le chiamate da un thread esistente in Skype for Business prima della scadenza della sessione SIP verranno instradati allo stesso modo del thread. Le chiamate e le chat da un thread esistente in Skype for Business oltre il timeout della sessione SIP verranno instradati al client Skype for Business della parte remota, indipendentemente dal client di origine del thread originale.

### <a name="availability"></a>Disponibilità

Sono disponibili sia il comportamento in-tenant che quello federato descritti in precedenza, con le limitazioni seguenti:

- I partecipanti esterni i cui tenant si trovano in una diversa distribuzione GoLocal o in geografia non vedono la chat di messaggistica istantanea durante una riunione "federata"
- La federazione e l'interoperabilità tra Multitenant Office 365 e cloud sovereign non sono supportate

## <a name="presence"></a>Icone di presenza

In presenza di una situazione in cui alcuni utenti usano il client Teams, mentre altri usano ancora il client Skype for Business, è possibile che alcuni utenti utilizzino entrambi i client. Si vuole comunque che gli stati presenza siano condivisi con tutti gli utenti, indipendentemente dal client di cui dispone un singolo utente. Quando questa operazione viene condivisa all'interno dell'organizzazione, gli utenti possono stabilire meglio se è opportuno avviare una chat o effettuare una chiamata.

Ad esempio, se la chat o la chiamata di un mittente dovrebbe essere sul client Skype for Business di destinazione, la presenza del client Skype for Business dovrebbe essere mostrata all'origine. Se dovrebbe essere visualizzato nel client Teams del target, dovrebbe essere visualizzata la presenza del client Teams.

Per conoscere il comportamento previsto, è necessario sapere che la presenza è condivisa in base alla modalità di coesistenza di un utente:

* Se un utente è in modalità TeamsOnly, qualsiasi altro utente (in Teams o Skype for Business) visualizza la presenza di TeamsOnly dell'utente
* Se un utente è in una delle modalità SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualsiasi altro utente (in Teams o Skype for Business) riceverà la presenza di \* Skype for Business dell'utente SfB
* Se un utente è in modalità Isole (o Legacy), la presenza in Teams e la presenza in Skype for Business sono indipendenti (i valori non devono corrispondere) e altri utenti potranno vedere una o l'altra presenza dell'utente delle Isole, a seconda che si trova nello stesso tenant o in un tenant federato e quale client usa
    * Da Teams, qualsiasi altro utente nello stesso tenant visualizza la presenza di Teams dell'utente delle Isole; questo è allineato alla tabella di routing in-tenant riportata sopra
    * Da Teams, qualsiasi altro utente in un tenant federato visualizza la presenza di Skype for Business dell'utente delle Isole; questo è allineato alla tabella di routing federato riportata sopra
    * Da Skype for Business, qualsiasi altro utente visualizza la presenza di Skype for Business dell'utente isole (sia nel tenant che federato); questo è allineato alle tabelle di routing precedenti


### <a name="in-tenant-presence"></a>Presenza nel tenant

I messaggi inviati agli utenti di TeamsOnly verranno sempre inviati a Teams. I messaggi inviati agli utenti SfB verranno sempre inviati a Skype for Business, se la conversazione \* è possibile, come descritto in precedenza. I messaggi inviati agli utenti delle Isole verranno sempre inviati al client da cui sono stati originati.

La tabella descrive la presenza dell'autore che verrà vista da un controllore, a seconda della modalità di Publisher e del client del Watcher (per un nuovo thread).

**Tabella 3: presenza nel tenant (nuovo thread)**

|Watcher <br/><br/>Client|<br/><br/>Route-> |<br/><br/>Isole |Publisher <br/><br/>SfB\* |<br/>Solo Teams|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Presenza federata

La presenza federata si basa sulla raggiungibilità federata mostrata nella tabella 2.

La tabella seguente descrive la presenza di Publisher che verrà vista da un controllore, a seconda della modalità di Publisher e del client del Watcher (per un nuovo thread). In pratica, in questa fase il cliente del Watcher non fa differenza nella federazione.

**Tabella 4: presenza federata (nuovo thread)**

|Watcher <br/><br/> Client |<br/><br/>Route->|<br/><br/> Isole  |Publisher <br/><br/> SfB\* |<br/><br/> Solo Teams |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presenza in thread pre-esistenti

Per allineare presenza e raggiungibilità in thread pre-esistenti, la presenza del target esposta in quel thread deve essere allineata al routing del thread, presupponendo che sia possibile il routing.

In particolare, se un destinatario con cui si aveva in precedenza un thread di conversazione di interoperabilità persistente è stato aggiornato a Teams, il thread non rifletterà più la presenza accurata e non sarà più instradabile. È consigliabile iniziare un nuovo thread.

## <a name="related-links"></a>Collegamenti correlati
[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
