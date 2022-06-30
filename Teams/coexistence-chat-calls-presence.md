---
title: Coesistenza con Skype for Business
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Comportamento di coesistenza tra & Skype for Business di Teams, inclusi parametri di routing, routing delle chiamate & chat, chat & chiamate da thread preesistenti, presenza &.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562395"
---
# <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

La coesistenza e l'interoperabilità tra client Skype for Business e Teams è controllata dalle modalità di coesistenza. Per altre informazioni, vedere [Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md). Dopo il ritiro di Skype for Business Online il 31 luglio 2021, gli utenti ospitati nel cloud sono sempre utenti di TeamsOnly. Non è più possibile assegnare una modalità di coesistenza diversa da TeamsOnly a un utente online. Modalità di coesistenza diverse da TeamsOnly sono rilevanti solo per le organizzazioni con distribuzioni locali di Skype for Business Server o Lync Server 2013. In questo articolo qualsiasi riferimento a "Skype for Business Server" si applica anche a Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinazione della modalità di coesistenza di un utente
Tutti gli utenti nelle organizzazioni senza alcuna distribuzione locale di Skype for Business Server sono in modalità TeamsOnly e anche la modalità effettiva del tenant è TeamsOnly. Ciò può essere confermato esaminando la proprietà TeamsUpgradeEffectiveMode nel tenant o l'utente che usa Teams PowerShell.   Prima del ritiro di Skype for Business Online il 31 luglio 2021, le organizzazioni avevano la possibilità di modificare la modalità di coesistenza per l'utente o il tenant. Ciò non è più possibile se non per le organizzazioni con una distribuzione locale di Skype for Business Server, che non devono avere la modalità a livello di tenant di TeamsOnly. È possibile confermare che la modalità di coesistenza non può più essere modificata se TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" nell'utente o nel tenant.  TeamsUpgradePolicyIsReadOnly su qualsiasi utente avrà lo stesso valore del valore del tenant.  


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

In un'organizzazione con una distribuzione locale di Skype for Business Server, i criteri globali del tenant per TeamsUpgradePolicy possono avere una modalità *diversa da TeamsOnly*. Le modalità consentite sono *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings*. Agli utenti può anche essere assegnata direttamente un'istanza di TeamsUpgradePolicy, che sostituiscono i criteri globali del tenant.  Gli utenti ospitati nel cloud devono essere TeamsOnly e gli utenti ospitati in locale devono essere una modalità diversa da TeamsOnly.  Se a un utente non è assegnata un'istanza di TeamsUpgradePolicy, l'utente riceve il valore dal criterio globale tenant. 

## <a name="routing-parameters"></a>Parametri routing

La modalità di coesistenza del destinatario determina il comportamento di chat, chiamate e presenza, sia all'interno di un tenant che tra tenant federati. Se il mittente usa Teams, la decisione di routing viene presa durante la creazione di un nuovo thread di conversazione. Dopo aver creato un thread di conversazione, il routing non cambia e mantiene il metodo di routing determinato quando è stato creato il thread.

I metodi di routing dei thread sono:

- *nativo* per una conversazione da Teams a Teams nel tenant
- *interagire* per una conversazione di Teams Skype for Business nel tenant
- *federato nativo* per una conversazione federata tra tenant quando entrambi gli utenti hanno la modalità TeamsOnly. 
- *interoperabilità federato* per una conversazione federata tra tenant che si basa sull'interoperabilità tra Skype for Business e Teams.

> [!NOTE]
> - Le conversazioni native, sia nello stesso tenant che negli scenari federati, si verificano quando sia il destinatario che il mittente hanno la modalità TeamsOnly. La conversazione sarà un'esperienza di chat nativa, che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere [Esperienza di chat nativa per utenti esterni (federati) in Teams](native-chat-for-external-users.md). 
> - Se uno dei partecipanti alla conversazione NON dispone della modalità TeamsOnly, la conversazione è un'esperienza di interoperabilità con i messaggi di sola lettura.
> - Le comunicazioni federate tra TeamsSolo gli utenti in cloud multi-tenant e ambienti cloud speciali (ad esempio i cloud governativi) appariranno come chat federate interoperabili.


Quando si crea una nuova conversazione, i fattori che determinano come viene instradato il thread sono:

- Modalità di coesistenza del destinatario
- Il client utilizzato dal mittente
- Indipendentemente dal fatto che la conversazione sia nel tenant o federata
- Se la conversazione è possibile. Se un utente ha un account di Skype for Business ospitato in locale, non può usare il client Teams per l'interoperabilità in-tenant o per la federazione. L'utente può utilizzare solo il client Skype for Business per l'interoperabilità e la federazione. Si noti che la comunicazione tra Teams e Teams è sempre possibile nel tenant.

## <a name="chat-and-call-routing"></a>Instradamento di chat e chiamate
Le tabelle seguenti mostrano quale client in una determinata modalità riceverà una chiamata dall'originatore (tre colonne all'estrema sinistra). Quale cient riceve la chiamata dipende dalla modalità dell'originatore, dal client scelto e dal posto in cui è ospitato l'account Skype for Business (locale o online).

Nelle tabelle seguenti:

- **Skype for Business** _ rappresenta una delle seguenti modalità: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *Il testo in corsivo* evidenzia una conversazione di interoperabilità.
- **Non possibile** rappresenta una situazione in cui la chat o la chiamata non è possibile. In questi casi, l'autore deve usare Skype for Business. Questo è uno dei motivi per cui le indicazioniscriptive di Microsoft per i clienti locali e ibridi sono l'uso di una modalità diversa da Islands (in genere SfBWithTeamsCollab) come punto di partenza per il loro viaggio di aggiornamento a Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routing in-tenant per nuove chat o chiamate

Le tabelle seguenti acquisiscono il routing delle chiamate e della chat nel tenant e sono valide per le nuove chiamate o chat che non vengono avviate da un thread preesistente. Descrive quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente destinatario nel tenant a destra.  I messaggi inviati a Teams Solo gli utenti verranno sempre indirizzati a Teams. I messaggi inviati agli utenti Skype for Business verranno sempre indirizzati a Skype for Business. I messaggi inviati agli utenti delle isole verranno sempre indirizzati allo stesso client da cui sono stati inviati.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabella 1a: in-tenant nuova chat o call routing a un destinatario in modalità TeamsOnly

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>&nbsp;Skype for Business sondato|<br><br>Itinerario-- >|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;|Teams <br> *Team*|
|Skype for Business | Skype for Business | Locale|&boxv;|*Team*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabella 1b: in-tenant nuova chat o call routing a un destinatario in modalità isole

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>&nbsp;Skype for Business sondato|<br><br>Itinerario-- >|Isole Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole| Teams <br> Skype for Business|Locale<br>Locale|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Locale|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabella 1c: in-tenant nuova chat o call routing a un destinatario in modalità Skype for Business

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>&nbsp;Skype for Business sondato|<br><br>Itinerario-- >|Destinatario Skype for Business|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;| **Non possibile** <br> Skype for Business|
|Skype for Business | Skype for Business| Locale|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Routing federato per nuove chat o chiamate

Le tabelle seguenti acquisiscono il routing delle chiamate e delle chat federate e sono valide per le nuove chiamate o chat. Descrivono quale client riceverà una nuova chiamata o chat, se originata da un utente a sinistra, a un utente di destinazione federato a destra. In sintesi, se la conversazione è possibile come descritto sopra, i messaggi inviati a TeamsSolo gli utenti atterrano sempre in Teams; i messaggi inviati agli utenti in modalità Skype for Business atterrano sempre in Skype for Business; i messaggi inviati agli utenti di Islands atterrano sempre in Skype for Business indipendentemente dal client da cui sono stati inviati. 

Il routing per le chat e le chiamate federate è diverso dal routing nel tenant perché gli utenti di Islands riceveranno sempre una comunicazione federata in Skype for Business. Il motivo è che il partner federato potrebbe non usare ancora Teams. Il routing a Skype for Business per tutte le ricette in modalità isole assicura che i messaggi vengano sempre ricevuti.  Il routing a Teams potrebbe comportare comunicazioni perse se il destinatario previsto non usa Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabella 2a: nuova chat federata o routing delle chiamate a un destinatario in modalità TeamsOnly

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>Skype for Business ospitato|<br><br>Itinerario-- >|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Isole|Teams <br> Skype for Business|Locale <br> Locale|&boxv;<br>&boxv;|**Non possibile** <br> *Team*|
|Skype for Business |Skype for Business|Locale|&boxv;| *Team*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabella 2b: nuova chat federata o routing delle chiamate a un destinatario delle isole

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>Skype for Business ospitato|<br><br>Itinerario-- >|Isole Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;| **Non possibile** <br> Skype for Business|
|Skype for Business |Skype for Business| Locale|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabella 2c: routing federato di nuove chat o chiamate a un destinatario in modalità Skype for Business

<br>

|<br><br>Modalità|Mittente<br><br>Client|<br><br>Skype for Business ospitato|<br><br>Itinerario-- >|Destinatario Skype for Business|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Isole|Teams <br> Skype for Business| Locale <br> Locale|&boxv;<br>&boxv;|**Non possibile** <br> Skype for Business|
|Skype for Business |Skype for Business|Locale|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chat e chiamate da thread preesistenti

### <a name="from-teams"></a>Da Teams

Le chiamate o le chat avviate da un thread di conversazione preesistente in Teams vengono instradate allo stesso modo di quel thread. Se il thread preesistente in Teams era un thread nativo (ad esempio instradato a Teams), ulteriori messaggi di chat e chiamate da quel thread andranno a Teams. Se si tratta di un thread di interoperabilità (ad esempio instradato a Skype for Business), ulteriori messaggi di chat e chiamate andranno a Skype for Business (presupponendo che siano disponibili opzioni di routing).

> [!NOTE]
> È possibile che i thread preesistenti in Teams non siano più instradabili, ad esempio quando il thread era un thread di interoperabilità a un utente che da allora è stato aggiornato a Teams. Poiché è stato creato come thread interoperativo, il thread viene indirizzato a Skype for Business, ma l'utente non può più usare Skype for Business per la chat e le chiamate. In questo caso, il thread verrà disabilitato e non permetterà ulteriori comunicazioni.

### <a name="from-skype-for-business"></a>Da Skype for Business

Skype for Business thread non persistono oltre il timeout della sessione SIP di 10 minuti. Le chat e le chiamate da un thread esistente in Skype for Business prima della scadenza della sessione SIP verranno instradate allo stesso modo del thread. Le chiamate e le chat da un thread esistente in Skype for Business oltre il timeout della sessione SIP verranno instradate alla Skype for Business della parte remota, indipendentemente dal client da cui proviene il thread originale dall'altra parte.

## <a name="presence"></a>Icone di presenza

Nelle situazioni in cui alcuni utenti usano il client teams e altri usano il client Skype for Business, è possibile che alcuni di questi utenti usano entrambi i client. È importante tenere presente che la presenza viene pubblicata in base alla modalità di coesistenza di un utente. Ad esempio, se la chat o la chiamata di un originatore deve atterrare sul client Skype for Business del target, è la presenza del client di Skype for Business che deve essere mostrata all'originatore. Se viene visualizzato sul client Teams del target, è la presenza del client di Teams che dovrebbe essere visualizzata.

La presenza viene condivisa in base alla modalità di coesistenza di un utente, come descritto di seguito:

- Se un utente è in modalità TeamsOnly, qualsiasi altro utente (in Teams o Skype for Business) vedrà la presenza di Teams solo dell'utente
- Se un utente è in una delle modalità di Skype for Business (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualsiasi altro utente (in Teams o Skype for Business) vedrà che Skype for Business presenza Skype for Business dell'utente
- Se un utente è in modalità Isole, la presenza in Teams e la presenza in Skype for Business sono indipendenti (i valori non devono corrispondere) e gli altri utenti vedranno una o l'altra presenza dell'utente isole, a seconda che si trovino nello stesso tenant o in un tenant federato e quale client utilizzano
  - Da Teams, qualsiasi altro utente all'interno dello stesso tenant vedrà la presenza di Teams dell'utente isole; questo è allineato con la tabella di routing in-tenant sopra
  - Da Teams, qualsiasi altro utente in un tenant federato vedrà la presenza dell'utente Skype for Business isole; questo è allineato con la tabella di routing federata sopra riportata
  - Da Skype for Business, qualsiasi altro utente vedrà la presenza Skype for Business dell'utente Isole (sia nel tenant che federato). Questo aspetto è allineato con le tabelle di routing precedenti

### <a name="in-tenant-presence"></a>Presenza nel tenant

I messaggi inviati a TeamsSolo gli utenti atterrano sempre in Teams. I messaggi inviati agli utenti in modalità Skype for Business atterrano sempre in Skype for Business, se la conversazione è possibile come descritto in precedenza. I messaggi inviati agli utenti delle isole verranno sempre indirizzati nel client da cui sono stati originati.

La tabella descrive la presenza di Publisher che verrà visualizzata da un watcher, a seconda della modalità di Publisher e del client di Watcher (per un nuovo thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabella 3: presenza nel tenant (nuovo thread)

<br>

|Osservatore<br><br>Client|<br><br>Itinerario-- >|<br><br>Isole|Publisher<br><br>Skype for Business|<br>Solo teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Presenza federata

La presenza federata si basa sulla raggiungibilità federata mostrata nella tabella 2.  La tabella seguente descrive la presenza di Publisher che sarà visualizzata da un watcher, a seconda della modalità di Publisher e del client di Watcher (per un nuovo thread). In pratica, il cliente del Watcher non fa differenza nella federazione in questa fase.

#### <a name="table-4-federated-presence-new-thread"></a>Tabella 4: presenza federata (nuovo thread)

<br>

|Osservatore<br><br>Client|<br><br>Itinerario-- >|<br><br>Isole|Publisher<br><br>Skype for Business|<br><br>Solo teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presenza in thread preesistenti

Per allineare presenza e raggiungibilità nei thread preesistenti, la presenza della destinazione esposta in tale thread deve essere allineata al routing del thread, presupponendo che sia possibile il routing.  In particolare, se un destinatario con cui in precedenza era stato aggiornato un thread di conversazione di interoperabilità persistente a Teams, tale thread non rifletterà più una presenza accurata e non sarà più instradabile. È consigliabile iniziare un nuovo thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federazione e interoperabilità con Office 365 gestito da 21Vianet

La federazione e l'interoperabilità tra Office 365 multi-tenant e Office 365 gestiti da 21Vianet sono supportati quando gli utenti Office 365 multi-tenant sono in modalità Solo teams. In questo scenario, gli utenti di Skype for Business Online in Office 365 gestiti da 21Vianet saranno in grado di comunicare con gli utenti di Teams Only in Office 365 multi-tenant tramite chat e chiamate. La tabella seguente mostra gli scenari supportati in questa configurazione:
 
|Scenario|Origine|Destinatario|Supportati?|
|---|---|---|---|
|Icone di presenza|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì<br>Sì|
|Chat|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì(solo 1:1)|
|Chiamate audio|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì (solo 1:1)|
|Videochiamate|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sì (solo 1:1)<br>Sì (solo 1:1)|
|Condivisione dello schermo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Sì (tramite una riunione di Teams alzata di livello)<br>Sì (tramite una riunione Skype for Business alzata di livello)|
|||||


## <a name="related-links"></a>Collegamenti correlati
[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Gestire la coesistenza e l'interoperabilità tra Skype for Business e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
