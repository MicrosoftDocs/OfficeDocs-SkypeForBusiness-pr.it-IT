---
title: Coesistenza con Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
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
ms.openlocfilehash: 1ed59546d871a7ac375061714ceedd67086818d1
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911830"
---
# <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

La coesistenza e l'interoperabilità tra Skype for Business e Teams client sono controllate dalle modalità di coesistenza. Per altre informazioni, vedere Indicazioni sulla migrazione e [l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)per le organizzazioni che usano Teams insieme a Skype for Business . Dopo il ritiro di Skype for Business Online il 31 luglio 2021, gli utenti ospitati nel cloud sono sempre utenti TeamsOnly. Non è più possibile assegnare una modalità di coesistenza diversa da TeamsOnly a un utente online. Le modalità di coesistenza diverse da TeamsOnly sono pertinenti solo per le organizzazioni con distribuzioni locali di Skype for Business Server o Lync Server 2013. In questo articolo, qualsiasi riferimento a "Skype for Business Server" si applica anche a Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinazione della modalità di coesistenza di un utente
Tutti gli utenti delle organizzazioni senza alcuna distribuzione locale di Skype for Business Server sono in modalità TeamsOnly e anche la modalità effettiva del tenant è TeamsOnly. Questo può essere confermato esaminando la proprietà TeamsUpgradeEffectiveMode nel tenant o l'utente che usa Teams PowerShell.   Prima del ritiro di Skype for Business Online il 31 luglio 2021, le organizzazioni hanno avuto la possibilità di cambiare la modalità di coesistenza per l'utente o il tenant. Questo non è più possibile se non per le organizzazioni con una distribuzione locale di Skype for Business Server, che non devono avere la modalità teamsOnly a livello di tenant. È possibile confermare che la modalità di coesistenza non può più essere modificata se TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" nell'utente o nel tenant.  TeamsUpgradePolicyIsReadOnly per qualsiasi utente avrà lo stesso valore del valore del tenant.  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

In un'organizzazione con una distribuzione locale di Skype for Business Server, i criteri globali tenant per TeamsUpgradePolicy possono avere qualsiasi modalità diversa *da TeamsOnly*. Le modalità consentite sono *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings*. Agli utenti può anche essere assegnata direttamente un'istanza di TeamsUpgradePolicy, che sostituisce i criteri globali del tenant.  Gli utenti ospitati nel cloud devono essere TeamsOnly e gli utenti ospitati in locale devono essere in qualsiasi modalità diversa da TeamsOnly.  Se a un utente non è assegnata un'istanza di TeamsUpgradePolicy, l'utente riceve il valore dai criteri globali del tenant. 

## <a name="routing-parameters"></a>Parametri di routing

La modalità di coesistenza del destinatario determina il comportamento di chat, chiamate e presenza, sia all'interno di un tenant che tra tenant federati. Se il mittente usa Teams, la decisione di routing viene presa quando si crea un nuovo thread di conversazione. Una volta creato un thread di conversazione, il routing non cambia e mantiene il metodo di routing determinato al momento della creazione del thread.

I metodi di routing dei thread sono:

- *nativo* per un Teams di Teams conversazione in-tenant
- *interoperabilità* per un Teams per Skype for Business conversazione in-tenant
- *federato nativo per* una conversazione federata tra tenant quando entrambi gli utenti hanno la modalità TeamsOnly. 
- *interoperabilità federata* per una conversazione federata tra tenant che si basa sull'interoperabilità tra Skype for Business e Teams.

> [! NOTE]
> - Le conversazioni native, sia nello stesso tenant che negli scenari federati, si verificano quando sia il destinatario che il mittente hanno la modalità TeamsOnly. La conversazione sarà un'esperienza di chat nativa, che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere Esperienza di chat nativa per [utenti esterni (federati) in Teams](native-chat-for-external-users.md). 
> - Se uno dei partecipanti alla conversazione NON ha la modalità TeamsOnly, la conversazione è un'esperienza di interoperabilità con messaggi di solo testo.
> - Le comunicazioni federate tra gli utenti di TeamsOnly in cloud multi-tenant e ambienti cloud speciali (ad esempio, cloud governativi) verranno visualizzate come chat federate di interoperabilità.


Quando si crea una nuova conversazione, i fattori che determinano il modo in cui viene instradato il thread sono:

- Modalità di coesistenza del destinatario
- Client usato dal mittente
- Se la conversazione è in-tenant o federata
- Se la conversazione è possibile. Se un utente ha un account Skype for Business locale, non può usare il client Teams per l'interoperabilità in-tenant o per la federazione. Tale utente può usare solo il client Skype for Business per l'interoperabilità e la federazione. Tenere presente che Teams comunicazioni Teams in tenant è sempre possibile.

## <a name="chat-and-call-routing"></a>Routing di chat e chiamate
Le tabelle seguenti mostrano quale cliente in una determinata modalità riceverà una chiamata dall'autore (tre colonne all'estrema sinistra). Il mittente che riceve la chiamata dipende dalla modalità del mittente, dal cliente scelto e dalla posizione in cui si trova l'account Skype for Business (locale o online).

Nelle tabelle seguenti:

- **Skype for Business** _ rappresenta una delle modalità seguenti: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *Il testo in corsivo* evidenzia una conversazione di interoperabilità.
- **Non possibile** rappresenta una situazione in cui la chat o la chiamata non è possibile. Il mittente deve usare Skype for Business in questi casi. Questo è uno dei motivi per cui le indicazioni prescrittive di Microsoft per i clienti locali e ibridi usano una modalità diversa da Isole (in genere SfBWithTeamsCollab) come punto di partenza per il percorso di aggiornamento a Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routing in-tenant per nuove chat o chiamate

Le tabelle seguenti acquisiscono il routing delle chat e delle chiamate in tenant e sono valide per le nuove chiamate o chat non avviate da un thread preesiste. Descrive quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente destinatario in-tenant a destra.  I messaggi inviati a TeamsOnly gli utenti verranno sempre indirizzati Teams. I messaggi inviati Skype for Business utenti instraderanno sempre a Skype for Business. I messaggi inviati agli utenti delle Isole verranno sempre indirizzati allo stesso client da cui sono stati inviati.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabella 1a: routing della nuova chat o delle chiamate nel tenant a un destinatario della modalità TeamsOnly

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>&nbsp;Skype for Business homed|<br><br>Percorso: >|Destinatario TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;|Teams <br> *Team*|
|Skype for Business | Skype for Business | Locale|&boxv;|*Team*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabella 1b: in-tenant nuovo instradamento di chat o chiamate a un destinatario della modalità isole

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>&nbsp;Skype for Business homed|<br><br>Percorso: >|Destinatario isole|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole| Teams <br> Skype for Business|Locale<br>Locale|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Locale|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabella 1c: nuova chat o instradamento delle chiamate in tenant a un destinatario in modalità Skype for Business posta elettronica

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>&nbsp;Skype for Business homed|<br><br>Percorso: >|Skype for Business Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;| **Non possibile** <br> Skype for Business|
|Skype for Business | Skype for Business| Locale|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Routing federato per nuove chat o chiamate

Le tabelle seguenti acquisiscono il routing delle chiamate federate e delle chat e sono valide per nuove chiamate o chat. Descrivono quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente di destinazione federato a destra. In sintesi, se la conversazione è possibile come descritto in precedenza, i messaggi inviati a TeamsOnly verranno sempre inviati a Teams; i messaggi inviati a Skype for Business utenti verranno sempre inviati in Skype for Business; I messaggi inviati alle isole verranno sempre inviati Skype for Business indipendentemente dal client da cui sono stati inviati. 

Il routing per le chat e le chiamate federate è diverso dal routing in-tenant, in quanto gli utenti delle Isole riceveranno sempre una comunicazione federata in Skype for Business. Questo perché il partner federato potrebbe non usare ancora Teams. L'instradamento Skype for Business per qualsiasi ricetta in modalità isole assicura che i messaggi siano sempre ricevuti.  L'instradamento Teams potrebbe comportare la mancata comunicazione se il destinatario previsto non usa Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabella 2a: routing federato di nuove chat o chiamate a un destinatario in modalità TeamsOnly

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>Skype for Business ospitata|<br><br>Percorso: >|Destinatario TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole|Teams <br> Skype for Business|Locale <br> Locale|&boxv;<br>&boxv;|**Non possibile** <br> *Team*|
|Skype for Business |Skype for Business|Locale|&boxv;| *Team*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabella 2b: routing federato di nuove chat o chiamate a un destinatario delle Isole

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>Skype for Business ospitata|<br><br>Percorso: >|Destinatario isole|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;| **Non possibile** <br> Skype for Business|
|Skype for Business |Skype for Business| Locale|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabella 2c: routing federato di nuove chat o chiamate a un destinatario in modalità Skype for Business messaggi

<br>

|<br><br>Modalità|Creatore<br><br>Client|<br><br>Skype for Business ospitata|<br><br>Percorso: >|Skype for Business Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;|**Non possibile** <br> Skype for Business|
|Skype for Business |Skype for Business|Locale|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chat e chiamate da thread preesistnti

### <a name="from-teams"></a>Da Teams

Le chiamate o le chat avviate da un thread di conversazione Teams vengono instradati nello stesso modo del thread. Se il thread preesistente in Teams era un thread nativo, ad esempio instradato a Teams, altri messaggi di chat e chiamate da quel thread verranno indirizzati a Teams. Se si tratta di un thread di interoperabilità,ad esempio instradato a Skype for Business, altri messaggi di chat e chiamate verranno indirizzati a Skype for Business (presupponendo che siano disponibili opzioni di routing).

> [!NOTE]
> È possibile che i thread preesistevi in Teams non siano più instradabili, ad esempio quando il thread era un thread di interoperabilità per un utente che è stato aggiornato a Teams. Poiché è stato creato come thread di interoperabilità, il thread instraderebbe a Skype for Business, ma quell'utente non potrà più usare Skype for Business per chat e chiamate. In questo caso, il thread verrà disabilitato e non sarà possibile comunicare ulteriormente.

### <a name="from-skype-for-business"></a>Da Skype for Business

Skype for Business thread sip non vengono mantenuti oltre il timeout della sessione SIP di 10 minuti. Le chat e le chiamate provenienti da un thread esistente Skype for Business prima della scadenza della sessione SIP verranno instradati nello stesso modo del thread. Le chiamate e le chat provenienti da un thread esistente in Skype for Business oltre il timeout della sessione SIP verranno instradati al Skype for Business della parte remota, indipendentemente dal client da cui proveniva il thread originale dall'altra parte.

## <a name="presence"></a>Icone di presenza

Nelle situazioni in cui alcuni utenti usano il client Teams e altri usano il client Skype for Business, è possibile che alcuni di questi utenti utilizzino entrambi i client. È importante comprendere che la presenza viene pubblicata in base alla modalità di coesistenza di un utente. Ad esempio, se la chat o la chiamata di un mittente deve atterrare sul client Skype for Business di destinazione, è la presenza del cliente di Skype for Business che dovrebbe essere visualizzata all'autore. Se deve essere visualizzato nel client di Teams di destinazione, è la presenza del Teams del client di destinazione.

La presenza viene condivisa in base alla modalità di coesistenza di un utente, come descritto di seguito:

- Se un utente è in modalità TeamsOnly, qualsiasi altro utente (in Teams o Skype for Business) vede che la presenza dell'utente TeamsOnly Teams
- Se un utente è in una delle modalità di Skype for Business (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualsiasi altro utente (in Teams o Skype for Business) vede che la presenza Skype for Business dell'utente Skype for Business
- Se un utente è in modalità Isole, la presenza in Teams e la presenza in Skype for Business sono indipendenti (i valori non devono corrispondere) e gli altri utenti vedono una o l'altra presenza dell'utente isole, a seconda che si trova nello stesso tenant o in un tenant federato e quale client usi
  - Da Teams, qualsiasi altro utente all'interno dello stesso tenant visualizza la presenza Teams utente isole; questo è allineato con la tabella di routing in-tenant precedente
  - Da Teams, qualsiasi altro utente in un tenant federato visualizza la presenza Skype for Business'utente delle isole; questo è allineato con la tabella di routing federata precedente
  - Da Skype for Business, qualsiasi altro utente vede la presenza Skype for Business dell'utente isole (sia in-tenant che federata); questo è allineato con le tabelle di routing precedenti

### <a name="in-tenant-presence"></a>Presenza in tenant

I messaggi inviati a TeamsSolo gli utenti vengono sempre inviati Teams. I messaggi inviati Skype for Business in modalità utente verranno sempre Skype for Business, se la conversazione è possibile, come descritto in precedenza. I messaggi inviati agli utenti delle Isole verranno sempre inviati al client da cui sono stati originati.

La tabella descrive la presenza dell'Publisher che verrà vista da un watcher, a seconda della modalità del Publisher e del client di Watcher (per un nuovo thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabella 3: presenza in-tenant (nuovo thread)

<br>

|Watcher<br><br>Client|<br><br>Percorso: >|<br><br>Isole|Publisher<br><br>Skype for Business|<br>Teams Solo|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Presenza federata

La presenza federata si basa sulla raggiungibilità federata illustrata nella tabella 2.  La tabella seguente descrive la presenza del Publisher che verrà visualizzato da un watcher, a seconda della modalità del Publisher e del client di Watcher (per un nuovo thread). In pratica il cliente del Watcher non fa alcuna differenza nella federazione in questa fase.

#### <a name="table-4-federated-presence-new-thread"></a>Tabella 4: presenza federata (nuovo thread)

<br>

|Watcher<br><br>Client|<br><br>Percorso: >|<br><br>Isole|Publisher<br><br>Skype for Business|<br><br>Teams Solo|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presenza nei thread preesiste

Per allineare la presenza e la raggiungibilità nei thread preesistevi, la presenza della destinazione esposta in tale thread deve essere allineata al routing del thread, presupponendo che il routing sia possibile.  In particolare, se un destinatario con cui in precedenza si era avuto un thread di conversazione di interoperabilità persistente è stato aggiornato a Teams, il thread non rifletterà più la presenza accurata e non sarà più instradabile. È consigliabile avviare un nuovo thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federazione e interoperabilità con Office 365 gestiti da 21Vianet

La federazione e l'interoperabilità tra Office 365 multi-tenant e Office 365 gestiti da 21Vianet sono supportati quando gli utenti Office 365 multi-tenant sono in modalità solo Teams multi-tenant. In questo scenario, gli utenti di Skype for Business Online in Office 365 gestiti da 21Vianet saranno in grado di comunicare con Teams Solo gli utenti in Office 365 multi-tenant tramite chat e chiamate. La tabella seguente mostra gli scenari supportati in questa configurazione:
 
|Scenario|Origine|Destinatario|Supportata?|
|---|---|---|---|
|Icone di presenza|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì<br>Sì|
|Chat|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì(solo 1:1)|
|Chiamate audio|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì (solo 1:1)|
|Videochiamate|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì (solo 1:1)|
|Condivisione dello schermo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Sì (tramite una riunione Teams alzata di livello)<br>Sì (tramite una riunione Skype for Business alzata di livello)|
|||||


## <a name="related-links"></a>Collegamenti correlati
[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams con Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Gestire la coesistenza e l'interoperabilità tra Skype for Business e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
