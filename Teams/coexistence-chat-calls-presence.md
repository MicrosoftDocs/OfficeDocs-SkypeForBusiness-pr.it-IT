---
title: Coesistenza con Skype for Business
author: kenwith
ms.author: kenwith
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
description: Questo documento descrive il comportamento della chat, il routing delle chiamate e la presenza tra gli utenti di teams e Skype for business, sia in-tenant che federati, in base alle modalità di TeamsUpgrade assegnate. Include le ottimizzazioni del routing, il comportamento della presenza, nonché la modifica della modalità di TeamsUpgrade predefinita da *legacy* a *Islands* e l'imminente pensionamento di *legacy*.
ms.openlocfilehash: 442b4b68b9739d9d17d02e298b53c5d9ecec3c8f
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236826"
---
# <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

La coesistenza e l'interoperabilità tra client e utenti di Skype for business e teams sono definite dalle modalità TeamsUpgrade, descritte nelle [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md).

A qualsiasi utente specificato verrà sempre assegnata una modalità TeamsUpgrade, per impostazione predefinita o esplicitamente dall'amministratore. Il valore predefinito è *Islands*. Gli utenti aggiornati a teams hanno la modalità di *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*e *SfBWithTeamsCollabAndMeetings* sono anche le modalità possibili.


## <a name="routing-parameters"></a>Parametri di routing

La modalità TeamsUpgrade del destinatario è la chiave per determinare il comportamento delle chat, delle chiamate e della presenza, sia all'interno di un tenant che in tutti i tenant federati.

Se il mittente USA teams, la decisione di routing viene eseguita durante la creazione di un nuovo thread di conversazione. I thread di conversazione esistenti in teams mantengono sempre il metodo di routing determinato al momento della creazione del thread: teams supporta i thread permanenti.

 I metodi di routing dei thread sono:  

- *nativo* per un team per la conversazione in teams in-tenant
- *interoperabilità* per un team per una conversazione in Skype for business in-tenant
- *federati* per una conversazione federata tra tenant

I parametri che determinano il metodo di routing del thread sono i seguenti:

- Modalità TeamsUpgrade del destinatario
- Il client usato dal mittente
- Se la conversazione è nuova o fa parte di un thread esistente
- Indipendentemente dal fatto che la conversazione sia in-tenant o federata
- Se la conversazione è possibile
    - L'interoperabilità *in-tenant* richiede che il tenant sia online puro o Skype for business Hybrid. I tenant puramente locali non possono avere interoperabilità in-tenant.
    - La *Federazione Cross-tenant* richiede sempre la configurazione della Federazione Skype for business appropriata e la configurazione corretta della Federazione dei team da entrambi i tenant. Skype for business Hybrid non è obbligatorio né per il tenant.
    - Se l'account Skype for business dell'autore viene ospitato in locale, l'utente non può usare il client teams per l'interoperabilità in-tenant o per la Federazione. L'utente può usare solo il client Skype for business per l'interoperabilità e la Federazione.
    - La comunicazione teams to teams è sempre possibile in-tenant.

> [!NOTE]
> Attualmente, tutte le federazioni che coinvolgono teams sfruttano la pipeline della Federazione di Skype for business e teams-interoperabilità Skype for business. Stiamo pianificando team nativi-Federazione teams. Il documento presente verrà aggiornato al rilascio della Federazione nativa.

## <a name="chat-and-call-routing"></a>Chat e routing delle chiamate

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routing in-tenant per nuove chat o chiamate 

Le tabelle riportate di seguito acquisiscono il routing della chat e delle chiamate in-tenant e sono valide per le nuove chiamate o le chat non avviate da un thread preesistente. Descrive quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente del destinatario in-tenant a destra.

I messaggi inviati agli utenti di TeamsOnly saranno sempre indirizzati a teams. I messaggi inviati agli\* utenti di SFB saranno sempre indirizzati a Skype for business, se la conversazione è possibile come descritto sopra. I messaggi inviati agli utenti delle isole verranno sempre indirizzati allo stesso client da cui sono stati inviati.

Le tabelle seguenti mostrano quale client in una determinata modalità riceverà una chiamata dall'originator (tre colonne più a sinistra), a seconda della modalità di origine, del cliente scelto e della posizione in cui è ospitato il client Skype for business (on-Prem o online).

Nelle tabelle seguenti: 
- **SFB\* ** rappresenta una delle modalità seguenti: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- Il *testo in corsivo* evidenzia una conversazione di interoperabilità.

- **Non possibile** rappresenta una situazione in cui la chat o la chiamata non è possibile. In questi casi, l'autore deve usare Skype for business. Questo è uno dei motivi per cui l'orientamento prescrittivo di Microsoft per i clienti on-Prem/Hybrid consiste nell'usare una modalità diversa da Islands (in genere SfBWithTeamsCollab) come punto di partenza per il viaggio di aggiornamento in teams.

**Tabella 1a: nuova chat in-tenant o routing delle chiamate a un destinatario della modalità Isole**

| <br/><br/> Modalità | Mittente <br/><br/> Client | <br/><br/> SfB&nbsp;homed | | Destinatario <br/><br/> Isole  |
|--- |--- |--- |--- |--- |
| Isole | Teams <br/> Skype for business<br/> Teams<br/> Skype for business| Online<br/> Online<br/> On-Prem<br/>On-Prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for business<br/> Teams<br/> Skype for business|
|SfB\* <br/> | Skype for business<br/>Skype for business<br/> | Online<br/> On-Prem<br/> |&boxv;<br/>&boxv;|Skype for business<br/>Skype for business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabella 1b: nuova chat in-tenant o routing delle chiamate a un destinatario in modalità\* SFB**

| <br/><br/> Modalità   | Mittente <br/><br/> Client | <br/><br/> SfB&nbsp;homed | |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Isole |Teams<br/>Skype for business<br/>Teams <br/>Skype for business  |Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for business<br/> **Non è possibile** <br/>Skype for business<br/> |
|SfB\* <br/> | Skype for business<br/>Skype for business<br/> | Online<br/> On-Prem<br/> |&boxv;<br/>&boxv; |  Skype for business<br/>Skype for business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabella 1C: nuova chat in-tenant o routing delle chiamate a un destinatario della modalità TeamsOnly**

| <br/><br/> Modalità   | Mittente <br/><br/> Client | <br/><br/> SfB&nbsp;homed | |   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Isole   |Teams<br/>Skype for business<br/>Teams <br/>Skype for business<br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Team* <br/>Teams <br/>*Team*  |
|SfB\*  | Skype for business<br/>Skype for business<br/> | Online<br/> On-Prem<br/> | &boxv;<br/>&boxv; | *Team*  <br/>*Team*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Routing federativo per nuove chat o chiamate
  
Le tabelle seguenti acquisiscono il routing delle chiamate e delle Chat federate e sono valide per le nuove chiamate o le chat. Descrivono quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente di destinazione federato a destra.

In sintesi, se la conversazione è possibile come descritto in precedenza, i messaggi inviati agli utenti di TeamsOnly saranno sempre sbarcati in teams; i messaggi inviati agli\* utenti di SFB saranno sempre atterrati in Skype for business; i messaggi inviati agli utenti delle isole saranno sempre sbarcati in Skype for business indipendentemente dal client da cui sono stati inviati. Il routing per le chat e le chiamate federate è diverso dal routing in-tenant in cui gli utenti delle isole riceveranno sempre una comunicazione federata in Skype for business.

Questo perché non possiamo presupporre che un partner di Skype for business federativo usi già teams se si trovano in modalità isole. Islands è la modalità predefinita, ma non possiamo presupporre che tutti gli utenti delle isole eseguano team. Con il routing a Skype for business assicuriamo che nessuna comunicazione a un utente di isole non riesca. Se si instradano a teams, è possibile che le comunicazioni non vengano perse se la destinazione non usa team. Il routing a Skype for business garantisce che il messaggio venga sempre ricevuto.  

> [!NOTE]
> L'implementazione corrente della Federazione teams si basa su Skype for business Federation, quindi sfrutta l'infrastruttura di interoperabilità (che richiede che il tenant del mittente sia online puro o Skype for business Hybrid) e fornisca un set di funzionalità ridotto rispetto a un thread nativo. Prevediamo di fornirci team nativi alla Federazione teams in futuro, a questo punto il thread sarà nativo e fornirà funzionalità complete.

Le tabelle seguenti descrivono il client che riceverà una chiamata dall'originator (tre colonne più a sinistra), a seconda della modalità di origine, del cliente scelto e della posizione in cui è ospitato il client Skype for business (on-Prem o online).

**Tabella 2a: nuova chat federata o routing delle chiamate a un destinatario delle isole**

| <br/><br/>Modalità   | Mittente<br/><br/> Client| <br/><br/>SfB homed| | Destinatario<br/><br/> Isole |
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for business <br/>Teams <br/>Skype for business  |Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for business <br/> **Non è possibile**   <br/> Skype for business |
| SfB\* |Skype for business <br/>Skype for business |Online<br/> On-Prem<br/> | &boxv;<br/>&boxv;|Skype for business <br/>Skype for business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabella 2b: nuova chat federata o routing delle chiamate a un destinatario in modalità\* SFB**

| <br/><br/>Modalità   | Mittente<br/><br/> Client| <br/><br/>SfB homed| |  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Isole |Teams<br/>Skype for business <br/>Teams <br/>Skype for business <br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for business <br/> **Non è possibile** <br/>Skype for business <br/> |  
| SfB\* |Skype for business <br/>Skype for business  |Online<br/> On-Prem<br/>  |&boxv;<br/>&boxv; | Skype for business <br/>Skype for business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabella 2C: nuova chat federata o routing delle chiamate a un destinatario della modalità TeamsOnly**

| <br/><br/>Modalità | Mittente<br/><br/> Client| <br/><br/>SfB homed| |  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Isole  |Teams<br/>Skype for business <br/>Teams <br/>Skype for business <br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Team* <br/>**Non è possibile** <br/>*Team* |
| SfB\* |Skype for business <br/>Skype for business  | Online<br/> On-Prem| &boxv;<br/>&boxv;|*Team* <br/>*Team*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chat e chiamate da thread preesistenti

### <a name="from-teams"></a>Da teams

Le chiamate o le chat avviate da un thread persistente preesistente in team verranno instradate allo stesso modo del thread, se l'opzione di routing è ancora disponibile.

Se il thread persistente preesistente in teams era un thread nativo, ovvero instradato a teams, altri messaggi di chat e chiamate da tale thread andranno in teams. Se si trattava di un thread di interoperabilità (indirizzato a Skype for business), altri messaggi di chat e chiamate andranno a Skype for business (di nuovo presupponendo che le opzioni di routing siano disponibili).

> [!NOTE]
> È possibile che i thread preesistenti nei team non siano più instradabili, ad esempio quando il thread è stato un thread di interoperabilità per un utente che ora è stato aggiornato a teams. Dato che è stato creato come thread di interoperabilità, il thread verrà indirizzato a Skype for business, ma l'utente non potrà più usare Skype for business per la chat e le chiamate. In questo caso, il thread verrà disabilitato e non consentirà ulteriori comunicazioni.

### <a name="from-skype-for-business"></a>Da Skype for business

I thread di Skype for business non vengono mantenuti oltre il timeout della sessione SIP di 10 minuti. Le chat e le chiamate da un thread esistente in Skype for business prima della scadenza della sessione SIP verranno instradate allo stesso modo del thread. Le chiamate e le chat da un thread esistente in Skype for business oltre il timeout della sessione SIP verranno indirizzate a Skype for business della parte remota, indipendentemente da quale client il thread originale proveniva dall'altra parte.

### <a name="availability"></a>Disponibilità

Sono disponibili sia i comportamenti in-tenant che quelli federati descritti in precedenza, con le limitazioni seguenti:

- Partecipanti esterni i cui inquilini si trovano in una distribuzione o in una geografia diversa di GoLocal non vedranno la chat di messaggistica istantanea durante una riunione "federata"
- La Federazione e l'interoperabilità tra Office 365 multitenant e nubi sovrane non sono supportate

## <a name="presence"></a>Icone di presenza

Quando si ha una situazione in cui alcuni utenti usano il client teams e altri ancora usano il client Skype for business, è possibile che si disponga di un numero di utenti che usano entrambi i client. Si vuole comunque che gli Stati di presenza vengano condivisi con tutti gli utenti, indipendentemente dal client che ha un singolo utente. Quando questa operazione viene condivisa nell'organizzazione, gli utenti possono determinare meglio se è appropriato avviare una chat o effettuare una chiamata.

Ad esempio, se una chat o una chiamata di un originatore deve atterrare sul client Skype for business di destinazione, è la presenza del client Skype for business che deve essere visualizzata all'originatore. Se deve atterrare sul client teams di destinazione, è la presenza del client teams che deve essere visualizzata.

Per conoscere il comportamento da prevedere, è necessario capire che la presenza è condivisa in base alla modalità di coesistenza di un utente:

* Se un utente è in modalità TeamsOnly, qualsiasi altro utente (sia in teams che in Skype for business) vedrà che la presenza di teams di TeamsOnly dell'utente
* Se un utente si trova in una delle modalità\* SFB (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualsiasi altro utente (sia in team che in Skype for business) vedrà che la presenza\* di Skype for business per l'utente di SFB
* Se un utente è in modalità Islands (o legacy), la presenza in teams e la presenza in Skype for business sono indipendenti (i valori non devono corrispondere) e altri utenti vedranno una o l'altra presenza dell'utente Islands, a seconda che si trovino nello stesso tenant o in una Federazione tenant ed il client che usano
    * Da teams, qualsiasi altro utente all'interno dello stesso tenant vedrà la presenza di Teams dell'utente Islands; Questa operazione è allineata alla tabella di routing in-tenant riportata sopra
    * Da teams, qualsiasi altro utente di un tenant federato vedrà la presenza di Skype for business dell'utente Islands; Questa operazione è allineata alla tabella di routing federata precedente
    * Da Skype for business, qualsiasi altro utente vedrà la presenza di Skype for business dell'utente Islands (sia in-tenant che federati); Questo è allineato alle tabelle di routing sopra


### <a name="in-tenant-presence"></a>Presenza in-tenant

I messaggi inviati agli utenti di TeamsOnly saranno sempre sbarcati in teams. I messaggi inviati agli\* utenti di SFB saranno sempre atterrati in Skype for business, se la conversazione è possibile come descritto sopra. I messaggi inviati agli utenti delle isole saranno sempre atterrati nel client da cui sono stati originati.

La tabella descrive la presenza dell'autore che verrà visualizzata da un osservatore, a seconda della modalità dell'autore e del client di Watcher (per un nuovo thread).

**Tabella 3: presenza in-tenant (nuovo thread)**

|Watcher <br/><br/>Client| |<br/><br/>Isole |Publisher <br/><br/>SfB\* |<br/>Solo Teams|
|--- |--- |--- |--- |---|
|Skype for business |&boxv;|Skype for business | Skype for business | Teams|
|Teams |&boxv; |Teams |Skype for business |Teams |
| | | | |

### <a name="federated-presence"></a>Presenza federata

La presenza federata si basa sulla raggiungibilità federata mostrata nella tabella 2.

La tabella seguente descrive la presenza dell'autore che verrà visualizzata da un osservatore, a seconda della modalità dell'autore e del client di Watcher (per un nuovo thread). In pratica il cliente del Watcher non fa alcuna differenza nella Federazione in questa fase.

**Tabella 4: presenza federata (nuovo thread)**

|Watcher <br/><br/> Client | |<br/><br/> Isole  |Publisher <br/><br/> SfB\* |<br/><br/> Solo Teams |
|--- |--- |--- |--- |---|
|Skype for business |&boxv; |Skype for business  | Skype for business  | Teams  |
|Teams | &boxv;|Skype for business |Skype for business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presenza nei thread preesistenti

Per allineare la presenza e la raggiungibilità nei thread preesistenti, la presenza della destinazione esposta in tale thread deve essere allineata con il routing del thread, presupponendo che il routing sia possibile.

In particolare, se un destinatario in precedenza aveva un thread di conversazione di interoperabilità persistente con l'aggiornamento a teams, il thread non rifletterà più la presenza accurata e non sarà più instradabile. È consigliabile avviare un nuovo thread.

## <a name="related-links"></a>Collegamenti correlati
[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Video: gestire la coesistenza e l'interoperabilità tra SfB e teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
