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
description: Comportamento di coesistenza tra Teams & Skype for Business, inclusi i parametri di instradamento, il routing delle chiamate & chat, le chat & chiamate da thread preesistevi, & presenza.
ms.openlocfilehash: f85843e4f6209731ac6146ef757f5f3dc4a88644
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718027"
---
# <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

La coesistenza e l'interoperabilità tra client e utenti di Skype for Business e Teams sono definiti dalle modalità TeamsUpgrade, descritte in Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a [Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

A un determinato utente verrà sempre assegnata la modalità TeamsUpgrade, per impostazione predefinita o esplicita dall'amministratore. Il valore predefinito è *Isole.* Gli utenti aggiornati a Teams hanno la modalità *TeamsOnly*. *SfBOnly,* *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings* sono anche possibili modalità.


## <a name="routing-parameters"></a>Parametri di routing

La modalità TeamsUpgrade del destinatario è fondamentale per determinare il comportamento di chat, chiamate e presenza, sia all'interno di un tenant che tra tenant federati.

Se il mittente usa Teams, la decisione di routing viene presa quando si crea un nuovo thread di conversazione. I thread di conversazione esistenti Teams mantenere sempre il metodo di routing determinato al momento della creazione del thread: Teams supporta i thread persistenti.

 I metodi di routing dei thread sono:  

- *nativo* per un Teams di Teams conversazione in-tenant
- *interoperabilità* per un Teams di Skype per le conversazioni aziendali in-tenant
- *federato* per una conversazione federata tra tenant

I parametri che determinano il metodo di routing del thread sono:

- Modalità TeamsUpgrade del destinatario
- Client usato dal mittente
- Se la conversazione è nuova o parte di un thread esistente
- Se la conversazione è in-tenant o federata
- Se la conversazione è possibile
    - *L'interoperabilità in-tenant* richiede che il tenant sia puro online o Skype for Business ibrido. I tenant locali non possono avere l'interoperabilità in-tenant.
    - *La federazione tra tenant* richiede sempre una configurazione Skype for Business di federazione Teams corretta da entrambi i tenant. Skype for Business ibrido non è necessario per entrambi i tenant.
    - Se l Skype for Business account del mittente è ospitata in locale, l'utente non può usare il client Teams per l'interoperabilità in-tenant o per la federazione. Tale utente può usare solo il client Skype for Business per l'interoperabilità e la federazione.
    - Teams a Teams è sempre possibile comunicare in-tenant.

> [!NOTE]
> Se il destinatario e il mittente sono entrambi in modalità di aggiornamento TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere Esperienza di chat nativa per [utenti esterni (federati) in Teams](native-chat-for-external-users.md). Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con i messaggi di solo testo.

## <a name="chat-and-call-routing"></a>Routing di chat e chiamate

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routing in-tenant per nuove chat o chiamate 

Le tabelle seguenti acquisiscono il routing delle chat e delle chiamate in tenant e sono valide per le nuove chiamate o chat non avviate da un thread preesiste. Descrive quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente destinatario in-tenant a destra.

I messaggi inviati a TeamsOnly gli utenti verranno sempre indirizzati Teams. I messaggi inviati agli utenti di SfB verranno sempre indirizzati a Skype for Business, se la conversazione è possibile, come \* descritto in precedenza. I messaggi inviati agli utenti delle Isole verranno sempre indirizzati allo stesso client da cui sono stati inviati.

Le tabelle seguenti mostrano quale cliente in una determinata modalità riceverà una chiamata dall'autore (tre colonne all'estrema sinistra), a seconda della modalità dell'autore, del cliente scelto e della posizione in cui si trova il client di Skype for Business (in posizione iniziale o online).

Nelle tabelle seguenti: 
- **SfB \** _ rappresenta una delle modalità seguenti: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Il testo in corsivo* evidenzia una conversazione di interoperabilità.

- **Non possibile** rappresenta una situazione in cui la chat o la chiamata non è possibile. Il mittente deve usare Skype for Business in questi casi. Questo è uno dei motivi per cui le indicazioni prescrittive di Microsoft per i clienti ibridi/in-prem usano una modalità diversa da Isole (in genere SfBWithTeamsCollab) come punto di partenza del percorso di aggiornamento a Teams.

**Tabella 1a: routing di nuove chat o chiamate in tenant a un destinatario della modalità isole**

| <br/><br/> Modalità | Creatore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Percorso: >| Destinatario <br/><br/> Isole  |
|--- |--- |--- |--- |--- |
| Isole | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| Online<br/> Online<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> **Non possibile**<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabella 1b: in-tenant nuova chat o routing delle chiamate a un destinatario in modalità \* SfB**

| <br/><br/> Modalità   | Creatore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Percorso: > |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Isole |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Non possibile** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabella 1c: in-tenant nuova chat o routing delle chiamate a un destinatario della modalità TeamsOnly**

| <br/><br/> Modalità   | Creatore <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Percorso: >|   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Isole   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>**Non possibile** <br/>*Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Routing federato per nuove chat o chiamate
  
Le tabelle seguenti acquisiscono il routing delle chiamate federate e delle chat e sono valide per nuove chiamate o chat. Descrivono quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente di destinazione federato a destra.

In sintesi, se la conversazione è possibile come descritto in precedenza, i messaggi inviati a TeamsOnly gli utenti saranno sempre Teams; I messaggi inviati agli utenti sfB vengono sempre inviati Skype for Business; i messaggi inviati agli utenti delle Isole verranno sempre inviati Skype for Business Skype for Business dipendentemente dal client da cui sono \* stati inviati. Il routing per le chat e le chiamate federate è diverso dal routing in-tenant, in quanto gli utenti delle Isole riceveranno sempre una comunicazione federata Skype for Business.

Questo è dovuto al fatto che non è possibile presupporre che un partner Skype for Business federato usi già Teams se si trova in modalità Isole. Isole è la modalità predefinita, ma non è possibile presupporre che tutti gli utenti di Isole ese Teams. Con l'instradamento Skype for Business ci assicuriamo che nessuna comunicazione a un utente delle Isole non riesca. Se è stato instradato a Teams, la comunicazione potrebbe non essere persa se la destinazione non usava Teams. Il routing Skype for Business assicura che il messaggio sia sempre ricevuto.  

> [!NOTE]
> L'implementazione corrente della federazione di Teams si basa sulla federazione di Skype for Business, quindi sfrutta l'infrastruttura di interoperabilità ,che richiede che il tenant dell'iniziatore sia puro online o ibrido Skype for Business) e fornisce un set ridotto di funzionalità rispetto a un thread nativo. Ci aspettiamo di fornire Teams nativa Teams federazione in futuro, a quel punto il thread sarà nativo e fornirà funzionalità complete.

Le tabelle seguenti descrivono quale cliente riceverà una chiamata dall'iniziatore (tre colonne all'estrema sinistra), a seconda della modalità dell'autore, del cliente scelto e della posizione in cui si trova il client Skype for Business (in modalità provvisoria o online).

**Tabella 2a: routing federato di nuove chat o chiamate a un destinatario delle Isole**

| <br/><br/>Modalità   | Creatore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Percorso: > | Destinatario<br/><br/> Isole |
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Non possibile**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> On-prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabella 2b: routing federato di nuove chat o chiamate a un destinatario in modalità \* SfB**

| <br/><br/>Modalità   | Creatore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Percorso: >|  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Non possibile** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> On-prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabella 2c: routing federato di nuove chat o chiamate a un destinatario in modalità TeamsOnly**

| <br/><br/>Modalità | Creatore<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Percorso: >|  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Isole  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**Non possibile** <br/>*Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> On-prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chat e chiamate da thread preesistnti

### <a name="from-teams"></a>Da Teams

Le chiamate o le chat avviate da un thread persistente preesistente in Teams verranno instradati nello stesso modo del thread, se tale opzione di routing è ancora disponibile.

Se il thread persistente preesistente in Teams era un thread nativo,ad esempio instradato a Teams, altri messaggi di chat e chiamate da quel thread verranno indirizzati a Teams. Se si tratta di un thread di interoperabilità,ad esempio instradato a Skype for Business, altri messaggi di chat e chiamate verranno indirizzati a Skype for Business (presupponendo di nuovo che siano disponibili opzioni di routing).

> [!NOTE]
> È possibile che i thread preesistevi in Teams non siano più instradabili, ad esempio quando il thread era un thread di interoperabilità per un utente che ora viene aggiornato a Teams. Poiché è stato creato come thread di interoperabilità, il thread instraderebbe a Skype for Business, ma quell'utente non potrà più usare Skype for Business per chat e chiamate. In questo caso, il thread verrà disabilitato e non sarà possibile comunicare ulteriormente.

### <a name="from-skype-for-business"></a>Da Skype for Business

Skype for Business thread non vengono mantenuti oltre i 10 minuti. Timeout della sessione SIP. Le chat e le chiamate provenienti da un thread esistente Skype for Business prima della scadenza della sessione SIP verranno instradati nello stesso modo del thread. Le chiamate e le chat provenienti da un thread esistente in Skype for Business oltre il timeout della sessione SIP verranno instradati al Skype for Business della parte remota, indipendentemente dal client da cui proveniva il thread originale dall'altra parte.

### <a name="availability"></a>Disponibilità

Sono disponibili sia i comportamenti in-tenant che quelli federati descritti in precedenza, con le limitazioni seguenti:

- I partecipanti esterni i cui tenant risiedono in una distribuzione golocale o geografica diversa non vedono la chat di messaggistica istantanea durante una riunione "federata"
- La federazione e l'interoperabilità tra Multitenant O365 e Sovereign Clouds non sono supportate

## <a name="presence"></a>Icone di presenza

In una situazione in cui alcuni utenti usano il client Teams e altri ancora usano il client Skype for Business, è possibile che siano presenti diversi utenti che usano entrambi i client. Si vuole comunque che gli stati presenza siano condivisi con tutti gli utenti indipendentemente dal client di un singolo utente. Quando questo viene condiviso nell'intera organizzazione, gli utenti possono determinare meglio se è appropriato avviare una chat o effettuare una chiamata.

Ad esempio, se la chat o la chiamata di un mittente deve atterrare sul client Skype for Business di destinazione, è la presenza del cliente di Skype for Business che dovrebbe essere visualizzata al mittente. Se deve essere visualizzato nel client di Teams di destinazione, è la presenza del Teams del cliente di destinazione.

Per sapere quale comportamento aspettarsi, è necessario comprendere che la presenza è condivisa in base alla modalità di coesistenza di un utente:

* Se un utente è in modalità TeamsOnly, qualsiasi altro utente (in Teams o Skype for Business) vede che la presenza dell'utente TeamsOnly Teams
* Se un utente è in una delle modalità SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualsiasi altro utente (in Teams o Skype for Business) vede che la presenza Skype for Business \* dell'utente SfB
* Se un utente è in modalità Isole (o Legacy), la presenza in Teams e presenza in Skype for Business sono indipendenti (i valori non devono corrispondere) e gli altri utenti potranno vedere una o l'altra presenza dell'utente isole, a seconda che si trova nello stesso tenant o in un tenant federato e quale client usi
    * Da Teams, qualsiasi altro utente all'interno dello stesso tenant visualizza la presenza Teams dell'utente isole; questo è allineato con la tabella di routing in-tenant precedente
    * Da Teams, qualsiasi altro utente in un tenant federato visualizza la presenza Skype for Business dell'utente isole. questo è allineato con la tabella di routing federata precedente
    * Da Skype for Business, qualsiasi altro utente visualizza la presenza Skype for Business dell'utente isole (sia in-tenant che federato); questo è allineato con le tabelle di routing precedenti


### <a name="in-tenant-presence"></a>Presenza in tenant

I messaggi inviati a TeamsSolo gli utenti vengono sempre inviati Teams. I messaggi inviati agli utenti sfB verranno sempre inviati Skype for Business, se la conversazione è possibile, come \* descritto sopra. I messaggi inviati agli utenti delle Isole verranno sempre inviati al client da cui sono stati originati.

La tabella descrive la presenza del Publisher che verrà visualizzato da un watcher, a seconda della modalità del Publisher e del client di Watcher (per un nuovo thread).

**Tabella 3: presenza in-tenant (nuovo thread)**

|Watcher <br/><br/>Client|<br/><br/>Percorso: > |<br/><br/>Isole |Publisher <br/><br/>SfB\* |<br/>Teams Solo|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Presenza federata

La presenza federata si basa sulla raggiungibilità federata illustrata nella tabella 2.

La tabella seguente descrive la presenza del Publisher che verrà visualizzato da un watcher, a seconda della modalità del Publisher e del client di Watcher (per un nuovo thread). In pratica il cliente del Watcher non fa alcuna differenza nella federazione in questa fase.

**Tabella 4: presenza federata (nuovo thread)**

|Watcher <br/><br/> Client |<br/><br/>Percorso: >|<br/><br/> Isole  |Publisher <br/><br/> SfB\* |<br/><br/> Teams Solo |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presenza nei thread preesistevi

Per allineare la presenza e la raggiungibilità nei thread preesistevi, la presenza della destinazione esposta in tale thread deve essere allineata al routing del thread, presupponendo che il routing sia possibile.

In particolare, se un destinatario con cui in precedenza si era avuto un thread di conversazione di interoperabilità persistente è stato aggiornato a Teams, il thread non rifletterà più la presenza accurata e non sarà più instradabile. È consigliabile avviare un nuovo thread.

## <a name="related-links"></a>Collegamenti correlati
[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)