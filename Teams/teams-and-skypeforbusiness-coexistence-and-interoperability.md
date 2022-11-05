---
title: Comprendere Microsoft Teams e coesistenza e interoperabilità di Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Dettagli sulle opzioni di coesistenza di Skype for Business e Microsoft Teams e sulla conseguente interoperabilità tra Skype for Business e Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91297a0b2fa5178195b10b61817cc11a30acfbc
ms.sourcegitcommit: 303579b3ecd4e0af43710d4b078610f63e9d0eca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2022
ms.locfileid: "68853364"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendere Microsoft Teams e coesistenza e interoperabilità di Skype for Business

![Diagramma percorso di aggiornamento, enfatizzando la fase di definizione del progetto.](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di definizione del progetto")

Questo articolo fa parte della fase di definizione del progetto del percorso di aggiornamento. Completare il progetto dopo aver creato una coalizione di sponsorizzazioni e un team di progetto e aver definito l'ambito, gli obiettivi e il piano per il progetto. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)

Se la tua organizzazione usa Skype for Business oggi e inizi a usare Teams insieme a Skype for Business - o stai iniziando ad eseguire l'aggiornamento a Teams - è importante capire come coesistono le due applicazioni, quando e come interagiscono e come gestire la migrazione degli utenti fino al loro eventuale aggiornamento da Skype for Business a Teams.

> [!Tip]
> Guardare la sessione seguente per informazioni sulla [coesistenza e l'interoperabilità](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Inoltre, puoi unirti a noi per workshop interattivi dal vivo in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione dell'aggiornamento.
>
> Partecipa prima alla pianificazione della sessione [di aggiornamento](./upgrade-workshops-landing-page.yml) per iniziare.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Panoramica sulla coesistenza di Teams e Skype for Business

Dal ritiro di Skype for Business Online, tutti gli utenti di un'organizzazione online pura (ovvero un'organizzazione che non ha una distribuzione locale di Skype for Business) hanno una modalità di coesistenza di TeamsOnly. La modalità TeamsOnly assicura agli utenti la piena funzionalità di Teams. Tuttavia, le organizzazioni con una distribuzione locale di Skype for Business Server potrebbero avere utenti che sono ancora ospitati in locale. Questi utenti non possono essere TeamsOnly. Gli utenti con un account di Skype for Business Server locale possono avere una modalità di coesistenza *diversa da TeamsOnly.* Le sezioni seguenti descrivono le modalità di coesistenza disponibili prima di decidere di eseguire l'aggiornamento di Utenti in locale Skype for Business a TeamsOnly e le funzionalità offerte da ogni modalità. Inoltre, le sezioni descrivono l'interoperabilità (interoperabilità) che si verifica tra gli utenti dei client di Skype for Business e gli utenti nei client di Teams e il modo in cui l'interoperabilità è influenzato dalla modalità di coesistenza scelta.

Teams offre funzionalità di collaborazione, chat, chiamate e riunioni.  La funzionalità chat, chiamate e riunioni era sempre disponibile in Skype for Business. A seconda della configurazione scelta quando si fornisce Teams, queste funzionalità possono sovrapporsi alle funzionalità fornite da Skype for Business per un determinato utente. La modalità di coesistenza predefinita per gli utenti locali è Isole. La modalità Isole consente all'utente di eseguire Teams insieme a Skype for Business con funzionalità simili disponibili in entrambi i client, ovvero le funzionalità si sovrappongono. Tuttavia, a un utente possono essere assegnate altre modalità di coesistenza per evitare che questa funzionalità si sovrapponga all'utente, nel qual caso è disponibile l'interoperabilità tra Teams e Skype for Business. Ad esempio, se si hanno risorse Skype for Business Server locali significative con una distribuzione VoIP aziendale complessa, ma si vuole consentire agli utenti di usare le riunioni moderne il più rapidamente possibile, è consigliabile valutare l'uso della Skype for Business con la modalità Collaborazione e riunioni di Teams, nota anche come [Riunioni prima di tutto ](meetings-first.md).

È consigliabile rivedere le seguenti modalità di coesistenza per determinare il percorso più adatto alla propria organizzazione.

> [!Important]
> Le modalità di coesistenza continuano a esistere dopo il ritiro di Skype for Business Online, tuttavia gli utenti ospitati online possono avere solo una modalità TeamsOnly. Non è più possibile assegnare una modalità diversa da TeamsOnly a un utente ospitato online.  Come è stato fatto prima del ritiro di Skype for Business Online, agli utenti ospitati localmente può essere assegnata qualsiasi modalità *diversa da TeamsOnly*.


### <a name="teams-only"></a>Solo teams

**Solo Teams** è l'unica modalità disponibile per gli utenti online. Un utente **solo di Teams** (in passato, a volte chiamato utente *aggiornato*) ha accesso a tutte le funzionalità in Teams e può continuare a comunicare con qualsiasi altro utente (nella stessa organizzazione o esterna) che usa ancora Skype for Business (a condizione che gli utenti Skype for Business non siano in modalità **Isole**). **Solo** gli utenti di Teams ricevono chat e chiamate in arrivo in Teams, oltre a pianificare riunioni in Teams. Non possono avviare chat o chiamate o pianificare riunioni in Skype for Business. 

**Solo** gli utenti di Teams possono mantenere il client Skype for Business per partecipare a qualsiasi Skype for Business riunioni che già hanno o possono ricevere in futuro, ovvero da parti esterne o eventualmente da utenti Skype for Business Server locali nella propria organizzazione. *Tuttavia, dopo che Microsoft rimuove l'infrastruttura Skype for Business Online per un determinato utente solo di Teams, gli utenti di Teams Only possono partecipare alle riunioni Skype for Business solo in forma anonima.* Dopo il 30 giugno 2022, il provisioning dei nuovi utenti di TeamsOnly non verrà più eseguito con l'infrastruttura di Skype for Business Online. Se questi utenti sono invitati a una riunione Skype for Business, dovranno partecipare in forma anonima. Dopo ottobre 2022, il provisioning degli utenti dall'ambiente locale al cloud (ovvero diventano TeamsOnly) non verrà più eseguito con l'infrastruttura di Skype for Business Online.  Se questi utenti sono invitati a una riunione di Skype for Business, dovranno partecipare anche in forma anonima.

Non appena l'organizzazione è pronta per alcuni o tutti gli utenti a usare Teams come unico strumento di comunicazione e collaborazione, aggiorna questi utenti alla modalità **Solo teams** . Se stai effettuando l'aggiornamento dalla modalità **Isole** , ti consigliamo di saturare l'adozione di Teams in tutta l'organizzazione prima di iniziare il processo di aggiornamento. Questa adozione evita scenari di comunicazione interrotti a causa della modalità **Isole** che non fornisce interoperabilità.

In modalità **Solo Teams** , Teams è l'app predefinita per il protocollo SIP/Tel. I collegamenti nella scheda contatto di un utente in Outlook per chiamate o chat verranno gestiti da Teams.

Per altre considerazioni sul passaggio alla modalità **Solo Teams** , vedere [Considerazioni sulla modalità Solo teams](teams-only-mode-considerations.md).

![Schermata del messaggio di conferma di Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business client in esecuzione in una modalità speciale dopo l'aggiornamento dell'utente come utente solo di Teams")


### <a name="islands-mode"></a>Modalità Isole

In modalità **Isole**, gli utenti possono eseguire Teams insieme a Skype for Business come due soluzioni separate che offrono funzionalità simili e sovrapposte. Le funzionalità includono presenza, chat, chiamate e riunioni. Gli utenti di Teams possono anche sfruttare le nuove funzionalità di collaborazione come team e canali, l'accesso ai file in Microsoft 365 e le applicazioni.

In questa modalità di coesistenza, ognuna delle applicazioni client funziona come un'isola separata. Skype for Business parla con Skype for Business e teams con Teams. Gli utenti devono eseguire entrambi i client in qualsiasi momento e possono comunicare in modo nativo nel client da cui è stata avviata la comunicazione. Di conseguenza, non è necessaria l'interoperabilità nella modalità **Isole** .

Per evitare un'esperienza di Skype for Business confusione o regresso, il Skype for Business gestisce le integrazioni seguenti che non vengono gestite in modalità **Isole** Teams:

- Comunicazioni esterne (federate).
- Servizi vocali PSTN e applicazioni vocali, integrazione di Office.
- Controlli HID per dispositivi USB.
- Diverse altre integrazioni.

Telefono di Microsoft Teams Sistema non è supportato in Teams in modalità **Isole**. 

> [!Important]
>  - In modalità **Isole**, tutti i messaggi e le chiamate provenienti da utenti federati (persone esterne all'organizzazione) vengono recapitati a Skype for Business. Dopo l'aggiornamento alla modalità **Solo Teams** , tutti i messaggi e le chiamate dall'esterno dell'organizzazione vengono recapitati a Teams.
>  - È consigliabile richiedere agli utenti di Islands di pianificare sempre le riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams. Ciò assicura che tutti gli utenti pianifichino le riunioni con Teams, che supporta l'accesso autenticato e la partecipazione alle riunioni per qualsiasi utente dell'organizzazione, indipendentemente dal fatto che l'utente sia TeamsOnly o che usi ancora Skype for Business Server. Al contrario, dopo che Microsoft ha ritirato l'infrastruttura legacy di Skype for Business Online per le organizzazioni ibride a partire da ottobre 2022, TeamsOnly gli utenti potranno partecipare alle riunioni Skype for Business solo in forma anonima.


### <a name="skype-for-business-only"></a>Solo Skype for Business

In questa modalità di coesistenza, gli utenti rimangono in Skype for Business, non in Teams, per le funzionalità di chat, riunione e chiamata e non usano Teams per team e canali. Questa modalità è disponibile oggi; tuttavia, nell'implementazione corrente, i team e i canali non vengono automaticamente disattivati per l'utente. Ciò può essere ottenuto usando il criterio di configurazione delle app per nascondere team e file.

Questa modalità può essere usata prima di avviare una distribuzione gestita di Teams per impedire agli utenti di iniziare a usare Teams prima di aver creato la conformità. Questa modalità è anche un modo per abilitare la partecipazione autenticata alle riunioni di Teams per Skype for Business utenti, a condizione che gli utenti siano concessi in licenza per Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business con la collaborazione in Teams

Usare questa modalità per presentare Teams nel proprio ambiente mentre si continua a usare l'investimento esistente in Skype for Business. Lasciare Skype for Business invariato per le funzionalità di chat, chiamate e riunioni. Aggiungere le funzionalità di collaborazione di Teams:

- Team e canali.
- Accesso ai file in Microsoft 365 o Office 365.
- Applicazioni. Funzionalità di comunicazione di Teams: chat private, chiamate e pianificazione delle riunioni.

Le chat private di Teams, le chiamate e la pianificazione delle riunioni sono disattivate per impostazione predefinita in questa modalità.

Le organizzazioni che iniziano con Skype for Business Server locale hanno questa modalità come alternativa alla modalità **Islands** se vogliono offrire agli utenti interoperabilità e prevedibilità per le loro comunicazioni durante la migrazione. Questa modalità fornisce anche una sequenza temporale prevedibile per l'aggiornamento a Teams (anziché affidarsi alla saturazione dell'adozione in modalità **Isole** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business con le riunioni e la collaborazione di Teams, note anche come Riunioni per prime

In questa modalità, la funzionalità di chiamata e chat privata rimane attiva Skype for Business mentre Teams viene utilizzato per pianificare e condurre riunioni, oltre che per la collaborazione tramite conversazioni basate sui canali.  Questa modalità di coesistenza consente di accelerare la disponibilità delle funzionalità di collaborazione e riunione di Teams nell'organizzazione e consente agli utenti di sfruttare l'esperienza di riunioni di Teams superiore:

- Ottima qualità.
- Trascrizione e traduzione.
- Sfocatura dello sfondo.
- Esperienza utente superiore su tutte le piattaforme, inclusi i dispositivi mobili e i browser.

Teams e Skype for Business beneficiare di una gamma di funzionalità "insieme migliori", come la riconciliazione della presenza, il blocco/annullamento automatico e il supporto per dispositivi HID in entrambe le applicazioni. È possibile nascondere team e canali, se lo si desidera, usando i criteri di configurazione delle app di Teams.

Questa modalità di coesistenza è particolarmente utile per le organizzazioni con Skype for Business distribuzioni locali con VoIP aziendale. È probabile che queste organizzazioni impiegano del tempo per eseguire l'aggiornamento a Teams e vogliono trarre vantaggio dalle riunioni superiori di Teams il prima possibile.

> [!NOTE]
> A partire da ottobre 2022, questa modalità è consigliata per tutti gli utenti locali assegnati in precedenza **Skype for Business Solo** o **Skype for Business con le modalità di collaborazione di Teams**. Questa modalità offre le stesse funzionalità delle altre due, tranne le nuove riunioni pianificate dall'utente saranno le riunioni di Teams invece di Skype for Business riunioni. Ciò assicura agli utenti di pianificare le riunioni come riunioni di Teams, che supporta l'accesso autenticato e la partecipazione alle riunioni per qualsiasi utente dell'organizzazione, indipendentemente dal fatto che l'utente sia TeamsOnly o che usi ancora Skype for Business Server.  Al contrario, quando Microsoft ritira l'infrastruttura legacy di Skype for Business Online, Gli utenti di TeamsOnly non potranno più eseguire l'autenticazione quando partecipano a riunioni Skype for Business, ma possono comunque partecipare in forma anonima. Per informazioni dettagliate, vedere [Cosa aspettarsi dopo il ritiro](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

> [!TIP]
> Per identificare la modalità di aggiornamento consigliata in base alle funzionalità che si desidera abilitare in Teams mentre Skype for Business è ancora in uso, usare [l'Aggiornamento guidato da Skype a Teams](https://aka.ms/SkypeToTeamsWizard).

Per altre informazioni sulle modalità di coesistenza, i prerequisiti e la gestione, vedere [Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md) e [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md).

|Icona punto di decisione |Definizione dell'icona |Descrizione |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto di decisione|<ul><li>Quali modalità di coesistenza sono più adatte alle esigenze dell'organizzazione e degli utenti?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Passaggio successivo|<ul><li>Scegli l'approccio migliore per il tuo percorso di aggiornamento.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilità di Teams e Skype for Business

L'interoperabilità è la possibilità per Teams e Skype for Business utenti della stessa organizzazione di comunicare tra Teams e Skype for Business.

L'interoperabilità è disciplinata dalla modalità di coesistenza (nota anche come modalità di aggiornamento) del ricevitore. Non esiste interoperabilità quando il ricevitore è in modalità **Islands** .

> [!Note]
> Quando viene distribuita in qualsiasi modalità di coesistenza tranne **Isole**, Teams e Skype for Business possono interagire, consentendo agli utenti di comunicare e chiamarsi e garantire che le comunicazioni rimangano [fluide](#interoperability-of-teams-and-skype-for-business) nell'intera organizzazione durante il percorso di aggiornamento a Teams. Le modalità di coesistenza regolano l'interoperabilità. La modalità di coesistenza del ricevitore determina se sarà disponibile l'interoperabilità. Ad esempio, se il ricevitore è in una modalità in cui la chat è disponibile solo in un client (ad esempio, Teams), l'interoperabilità della chat sarà generalmente disponibile nel caso in cui l'iniziatore usi l'altro client (in questo caso, Skype for Business) per avviare la chat. D'altra parte, se il ricevitore è nella modalità in cui la chat è disponibile in entrambi i client (modalità Isole), l'interoperabilità non sarà disponibile per la chat. Il messaggio verrà ricevuto dal destinatario nello stesso client in cui l'iniziatore ha avviato la chat. Pertanto, una comunicazione adeguata in modalità **Isole** richiede la saturazione dell'adozione di Teams; ovvero tutti gli utenti usano attivamente e monitorano entrambi i client.

> [!Note]
> **Per avere l'esperienza di coesistenza più recente, la versione client deve essere il client più recente disponibile nel canale di distribuzione di Office dell'utente.**

#### <a name="native-interop-and-interop-escalation"></a>Escalation a interoperabilità e interoperabilità nativi

Esistono due tipi di esperienze di interoperabilità: escalation nativa e di interoperabilità.

- Nel client attualmente in uso si verifica un'esperienza di _interoperabilità nativa_ . Un utente sarà nel client Skype for Business, l'altro in Teams. Un'esperienza di interoperabilità nativa non li porterà a un altro client per comunicare. Gli utenti saranno in grado di condurre la conversazione nel client in uso. Le esperienze di interoperabilità native sono chat e chiamate uno-a-uno.
- Un'esperienza di _escalation dell'interoperabilità_ significa che, nell'ambito di aiutare gli utenti a eseguire un'azione avanzata (come la condivisione del desktop), il client facilita la creazione di una riunione a cui gli utenti possono partecipare per continuare l'esperienza nella riunione. La riunione viene creata sulla piattaforma dell'iniziatore dell'azione. L'utente o gli utenti che non sono su quella piattaforma ricevono un collegamento di partecipazione alla riunione. Quando fanno clic su questo collegamento, accedono alla riunione in un client compatibile ( browser, app Web o client completo, a seconda della configurazione). L'escalation di interoperabilità da Skype for Business richiede un client recente. L'escalation di interoperabilità da Teams è ora disponibile. Entrambi sono supportati nelle esperienze di interoperabilità nel tenant e per le comunicazioni federate tra tenant.

#### <a name="native-interop-experiences"></a>Esperienze di interoperabilità native

A seconda delle modalità di coesistenza assegnate agli utenti (come descritto in precedenza), sono disponibili le seguenti esperienze di interoperabilità native:

Skype for Business gli utenti possono chattare uno-a-uno con gli utenti di Teams e viceversa. Una chat di interoperabilità deve passare attraverso un gateway di interoperabilità che fa parte dei servizi cloud di Teams (e quindi esiste solo online). Le chat di interoperabilità sono testo normale: testo RTF ed emoticon non sono supportate. Gli utenti in Teams e in Skype for Business ricevono una notifica che la conversazione è una conversazione interoperativo.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business gli utenti possono effettuare chiamate vocali e videochiamate uno-a-uno agli utenti di Teams e gli utenti di Teams possono fare lo stesso.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Le esperienze di interoperabilità con gli utenti locali di un'organizzazione con una combinazione di utenti locali e di Teams richiedono che l'ambiente locale sia in modalità ibrida con Teams. Per informazioni dettagliate, [configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Queste esperienze di interoperabilità sono disponibili per e tra gli utenti a cui è assegnata una delle seguenti modalità di coesistenza: **Skype for Business con collaborazione in Teams**, **Skype for Business con la collaborazione e le riunioni di Teams**, **solo Skype for Business** o **Solo teams**. Non esiste interoperabilità per gli utenti in modalità **Isole** .

#### <a name="native-interop-experience-limitations"></a>Limitazioni dell'esperienza di interoperabilità nativo

A causa della differenza di protocolli e tecnologie, non è possibile supportare tutte le funzionalità in modo nativo. In particolare, le funzionalità seguenti non sono disponibili:

- Markdown, RTF e il set di emoticon completo non sono supportati da Teams o da Skype for Business. Altre funzionalità native della casella di composizione nelle chat di Teams non sono supportate.
- La condivisione dello schermo (condivisione desktop o app) tra Teams e Skype for Business non è supportata in modo nativo. Tuttavia, è supportato tramite escalation di interoperabilità.
- Le chat di gruppo (conversazioni tra più persone) in Teams possono includere solo i partecipanti che usano Teams.
- Le conversazioni istantanee a più parti (chat di gruppo) in Skype for Business possono includere solo i partecipanti che usano Skype for Business. Tuttavia, l'escalation di interoperabilità a più parti è disponibile da Skype for Business.
- L'escalation di una chiamata vocale o video peer-to-peer in corso a una chiamata a più parti che coinvolge sia Teams che Skype for Business utenti non è supportata.
- Il trasferimento di file per le chat di due parti o l'allegato file nelle chat di gruppo, da Teams a Skype for Business e viceversa, non sono supportati.
- Non esiste interoperabilità con Skype for Business Persistent Chat.

Per tutte queste limitazioni (ad eccezione di Persistent Chat), una possibile soluzione alternativa consiste nell'avviare una riunione e invitare l'altro utente a parteciparvi.

Questa soluzione alternativa è la base per l'escalation di interoperabilità. In particolare, la condivisione dello schermo e l'escalation a multiparty non sono raggiungibili in modo nativo, ma sono supportati tramite escalation di interoperabilità.

#### <a name="interop-escalation-experiences"></a>Esperienze di escalation di interoperabilità

L'escalation dell'interoperabilità consiste nell'integrare le funzionalità di interoperabilità native con escalation gestite alle riunioni. Le riunioni offrono esperienze avanzate a disposizione di chiunque, indipendentemente dal cliente di cui dispongono.

Quando l'utente di Teams attiva l'escalation dell'interoperabilità, viene creata una riunione di Teams. Quando viene attivata dall'utente Skype for Business, viene creata una riunione Skype for Business. In entrambi i casi, la riunione creata è una riunione **Riunione** immediata, che non viene riportata nel calendario dell'utente.

L'altra parte riceve il collegamento di partecipazione alla riunione tramite chat di interoperabilità e partecipa facendo clic su tale collegamento. Se l'utente Skype for Business ha un account di Teams ed è invitato dall'utente di Teams, parteciperà alla riunione autenticato. In caso contrario, parteciperanno come partecipanti anonimi. Gli utenti di Teams hanno quasi sempre un account di Skype for Business e un client Skype for Business che possono usare per partecipare a una riunione Skype for Business come partecipante autenticato, ma possono anche partecipare come partecipanti anonimi, ad esempio usando l'app Riunione Skype.

Una volta che le parti hanno aderito alla riunione, possono condurre qualsiasi attività supportata nelle riunioni, come la condivisione di desktop o contenuti, la condivisione o il trasferimento di file, l'aggiunta di altri partecipanti e così via.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalation di interoperabilità da Skype for Business

L'escalation di interoperabilità e interoperabilità da Skype for Business è stata aggiornata nella build mensile del C2R di luglio 2019. In precedenza, Skype for Business non aveva la consapevolezza avanzata che la parte remota stava usando Teams. Ha ipotizzato che dalla segnalazione ricevuta dopo una sessione è stata stabilita.

Quando la segnalazione indicava che la risposta proviene (o attraverso) dal gateway di interoperabilità, veniva visualizzata la barra aziendale (banner) gialla indicante che l'altra parte non usava Skype for Business. Con l'evoluzione del nostro servizio, ciò ha portato a falsi positivi in cui Skype for Business utenti vedevano la barra aziendale quando erano connessi al servizio Cloud Voicemail o ad altri servizi vocali cloud, piuttosto che a un effettivo utente **di Teams Only**.

Per evitare falsi positivi, il servizio presenza sta informando il client Skype for Business quando l'altra parte è un utente effettivo **di Teams**. In questo modo Skype for Business di creare una conversazione interoperativo e la finestra di conversazione è specifica di interoperabilità.

![Screenshot del messaggio di Teams per creare una conversazione interoperativo con un utente Skype for Business.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se ad esempio l'utente Skype for Business vuole condividere il desktop, viene informato che verrà avviata una riunione e i passaggi sono illustrati in dettaglio.

![Schermata del messaggio di Teams per avviare una riunione con un utente di Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Nel frattempo, l'utente di Teams riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione Skype for Business è disponibile sia per le chiamate e le chat federate in-tenant che tra tenant. È attivata per impostazione predefinita e non esiste alcuna impostazione di cui l'amministratore deve eseguire il provisioning.

#### <a name="interop-escalation-from-teams"></a>Escalation di interoperabilità da Teams

L'escalation di interoperabilità da Teams a una riunione di Teams è ora disponibile quando l'utente di Teams seleziona il pulsante di condivisione desktop in un thread di interoperabilità in-tenant con un utente Skype for Business o in un thread di federazione di interoperabilità tra tenant. L'escalation interoperabilità è supportata da una conversazione in chat 1:1 o da una chiamata 1:1.

Questa funzionalità è supportata nel client desktop di Teams per Windows, nel client desktop di Teams per Mac e nel client Web di Teams nei browser in cui è supportata la condivisione di contenuti, durante le comunicazioni con qualsiasi versione client Skype for Business.

Nei thread di interoperabilità e nei thread di interoperabilità federativo, l'utente di Teams ha ora i controlli (pulsante) per avviare la condivisione del contenuto. Quando l'utente di Teams seleziona il pulsante, viene visualizzato un menu aggiuntivo che informa che per condividere contenuti, dovrà avviare una riunione di Teams.

Se gli utenti erano in una chiamata, il menu li avvisa che la chiamata corrente tra Teams e Skype for Business verrà terminata quando vengono inseriti in una riunione di Teams. Se lo desiderano, possono avvisare l'utente Skype for Business prima di accettare.

![Schermata del messaggio di Teams per condividere una riunione con un utente Skype for Business.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Una volta accettati, vengono inseriti nella riunione di Teams; devono avviare la condivisione dall'area di condivisione della riunione.

Nel frattempo, l'utente Skype for Business riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione di Teams è disponibile sia per le chiamate e le chat federate in-tenant che tra tenant. È attivata per impostazione predefinita e non esiste alcuna impostazione di cui l'amministratore deve eseguire il provisioning. Tuttavia, viene disattivata per l'utente se l'amministratore imposta su ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false``.

Dopo aver esaminato questo articolo, vedere [Scegliere il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [indicazioni sulla migrazione e l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md), [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) e [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md) per dettagli sull'implementazione. Consigliamo anche il video seguente: [Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Dettagli tecnici sulla coesistenza di Teams e Skype for Business

Le sezioni seguenti riepilogano il comportamento che può verificarsi durante l'esecuzione sia di Teams che di client Skype for Business nella stessa organizzazione, indipendentemente dalla modalità e dal metodo di aggiornamento usato:

- [Riunioni](#meetings)
- [Interoperabilità](#interoperability)
- [Confronto tra thread di conversazione nativi e interoperabilità](#interop-versus-native-conversation-threads)
- [Icone di presenza](#presence)
- [Federazione](#federation)
- [Contatti](#contacts)

### <a name="meetings"></a>Riunioni

Indipendentemente dalla modalità, gli utenti possono sempre partecipare a qualsiasi tipo di riunione a cui sono invitati, che si tratti di Skype for Business o Teams.  Tuttavia, gli utenti devono partecipare alla riunione con un client corrispondente che corrisponde al tipo di riunione:

- Se la riunione è una riunione di Teams, tutti i partecipanti (che si tratti di Utenti di TeamsOnly, Islands o Skype for Business) usano il client teams per partecipare alla riunione. Se Teams non è installato, l'utente verrà indirizzato al Web quando tenta di partecipare a una riunione.

- Se la riunione è una riunione Skype for Business, tutti i partecipanti (che si tratti di utenti di TeamsOnly, Islands o Skype for Business) usano il client Skype for Business per partecipare alla riunione. Se il client Skype for Business non è installato, l'utente verrà indirizzato al Web per partecipare tramite l'app Riunione Skype. 

  In alcuni casi, i partecipanti in modalità TeamsOnly potranno partecipare alle riunioni Skype for Business solo usando Skype for Business Web App o l'app Riunioni Skype come utente anonimo. Alla fine, questo caso sarà vero per tutti gli utenti in modalità TeamsOnly. Per altre informazioni, vedere [ritiro di Skype for Business Online](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Durante l'organizzazione delle riunioni, il tipo di riunione pianificato si basa sulla modalità dell'organizzatore, come illustrato nella tabella seguente:

| Modalità di organizzatore    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Tutte le riunioni pianificate in Teams. Skype for Business componente aggiuntivo non è disponibile in Outlook. |
| SfbWithTeamsCollab, SfbOnly | Tutte le riunioni pianificate in Skype for Business. Il componente aggiuntivo Teams non è disponibile in Outlook. È consigliabile usare SfbWithTeamsCollabAndMeetings, che consente a tutti gli utenti, sia in locale che in TeamsOnly, di usare Teams per le riunioni.|
| Isole | Per impostazione predefinita, le riunioni possono essere pianificate in Skype for Business o Teams. Entrambi i componenti aggiuntivi sono disponibili in Outlook. Tuttavia, è possibile richiedere facoltativamente che gli utenti nelle isole pianifichino sempre le riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interoperabilità

Come descritto in precedenza in [Interoperability of Teams and Skype for Business](#interoperability-of-teams-and-skype-for-business), Teams supporta l'interoperabilità con Skype for Business in determinati scenari. Comunicazione di interoperabilità si riferisce a una chat o chiamata tra un utente Skype for Business e un utente di Teams. La comunicazione di interoperabilità è possibile solo tra due utenti; non è supportata la chat o le chiamate multi-party o l'aggiunta di altri utenti.

Una chiamata o una chat di interoperabilità tra due utenti viene creata quando si verificano le condizioni seguenti:

- Un utente usa Teams e l'altro usa Skype for Business.

- La modalità del destinatario della comunicazione iniziale non è Isole (altrimenti la comunicazione sarirebbe nello stesso client) se entrambi gli utenti fanno parte della stessa organizzazione. Negli scenari federati, l'utente mittente usa Teams e il destinatario non è in modalità TeamsOnly.

- L'utente di Teams NON ha anche un account Skype for Business ospitato in locale.

All'interno della comunicazione di interoperabilità, la chat è solo testo normale. Inoltre, la condivisione di file e la condivisione dello schermo non sono possibili *nella chat di interoperabilità stessa*. Tuttavia, gli utenti in una conversazione interoperativo possono raggiungere facilmente la condivisione di file e/o schermo creando una riunione su richiesta, dall'interno della chat di interoperabilità, come descritto di seguito:

- Se l'utente di Teams prova a condividere lo schermo, viene creata automaticamente una riunione di Teams su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente Skype for Business. Facendo clic sul collegamento, l'utente Skype for Business aprirà Teams e parteciperà alla riunione. Entrambi gli utenti sono ora in una riunione di Teams e possono condividerli in base alle esigenze.

- Se l'utente Skype for Business usa un client dal 2018 o versione successiva e prova a condividere qualsiasi contenuto, viene creata automaticamente una riunione Skype for Business su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente di Teams. Dopo aver fatto clic sul collegamento, l'utente di Teams tenterà di partecipare alla riunione Skype for Business. Se l'utente di Teams ha installato il client Skype for Business, verrà aperto e all'utente viene chiesto di accedere (se non ha già eseguito l'accesso).  Se l'utente di Teams non ha installato il client Skype for Business, all'utente verrà richiesto di usare la versione Web. Dopo aver eseguito l'accesso, entrambi gli utenti partecipano a una riunione Skype for Business e possono condividerli in base alle esigenze.

### <a name="interop-versus-native-conversation-threads"></a>Confronto tra thread di conversazione nativi e interoperabilità

Poiché le comunicazioni di interoperabilità non supportano tutte le funzionalità delle conversazioni native di Teams, il client Teams mantiene thread di conversazione separati per le comunicazioni Teams-to-Teams e Teams-to-Skype for Business. Il rendering di queste conversazioni è diverso nell'interfaccia utente: i thread di interoperabilità possono essere differenziati da un normale thread nativo di Teams da:

- Mancanza di controlli per RTF, condivisione di file/schermo, impossibilità di aggiungere utenti.
- Modifica dell'icona dell'utente di destinazione, con una "S" per Skype for Business.

Queste differenze sono mostrate negli screenshot seguenti:

Una conversazione nativa di Teams-to-Teams con test G3 dell'utente

![Diagramma che mostra una conversazione nativa di Teams-a-Teams.](media/teams-upgrade-native-thread.png)

Una conversazione interoperativo con lo stesso test G3 utente

![Diagramma che mostra una conversazione teams-to-teams di interoperabilità.](media/teams-upgrade-interop-thread.png)

Dopo aver creato un thread di conversazione, il suo tipo non cambia mai. Una volta creato, un thread di interoperabilità in Teams verrà sempre indirizzato al client Skype for Business dell'utente di destinazione. Un thread nativo verrà sempre instradato al client di Teams dell'utente di destinazione.  Se la modalità di un utente del destinatario cambia, i thread di Teams esistenti a quell'utente non funzioneranno più e verrà visualizzata una nota su quella chat con un collegamento per avviare una nuova conversazione nativa, come mostrato nello screenshot seguente.

![Diagramma che mostra una chat con un utente aggiornato Skype for Business.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Icone di presenza

La presenza per un determinato utente si basa sull'attività dell'utente nel servizio tramite il client. La presenza viene quindi pubblicata per consentire ad altri utenti di visualizzarla.  Skype for Business e Teams sono servizi separati con client separati, quindi ogni servizio ha il proprio stato presenza per un utente.   C'è anche la sincronizzazione tra i servizi presenza in Teams e in Skype for Business Online.  In questo modo un servizio può potenzialmente pubblicare la presenza dell'utente dall'altro servizio, se necessario.

Il comportamento di pubblicazione della presenza si basa sulla modalità dell'utente. Esistono tre casi di base:

- Se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono la presenza di Teams per quell'utente, indipendentemente dal client che usa.

- Se un utente usa una delle modalità Skype for Business, tutti gli altri utenti vedranno Skype for Business presenza per tale utente, indipendentemente dal client che usa.

- Se un utente è in modalità Isole, la presenza pubblicata in Skype for Business e Teams sono indipendenti, quindi la presenza mostrata agli utenti all'interno della stessa organizzazione dipenderà dal client dell'altro utente. Gli utenti delle organizzazioni federate vedranno la presenza dell'utente in base all'attività di Skype for Business, poiché il traffico federato verso un utente in modalità Isole passa in Skype for Business.

Si supponga, ad esempio, che l'utente A sia in modalità Isole. Se l'utente A è attivo in Teams ma non ha eseguito l'accesso a Skype for Business, gli altri utenti vedrebbero l'utente A come attivo dal client di Teams, ma nel client Skype for Business vedrebbero l'utente A come offline. Si tratta di un'operazione da progettazione, dal momento che l'utente A non può essere raggiunto se non esegue il client.


### <a name="federation"></a>Federazione

La federazione da Teams a un altro utente che usa Skype for Business richiede che l'utente di Teams sia ospitato online in Skype for Business. TeamsUpgradePolicy regola il routing per le chat e le chiamate federate in arrivo. Il comportamento di routing federato è lo stesso degli scenari con lo stesso tenant, tranne che per la modalità Isole. Quando i destinatari sono in modalità Isole:

- Le chat e le chiamate avviate da Teams vengono Skype for Business se il destinatario si trova in un tenant federato.
- Le chat e le chiamate avviate da Teams atterrano in Teams se il destinatario si trova nello stesso tenant.
- Le chat e le chiamate avviate da Skype for Business atterrano sempre in Skype for Business.

Una chat federata può essere un thread nativo o un thread di interoperabilità. Vedere [Confronto tra thread di conversazione nativi e interoperabili](#interop-versus-native-conversation-threads).

- Se il destinatario e il mittente sono entrambi in modalità di aggiornamento di TeamsOnly, la conversazione sarà un'esperienza di chat nativa, che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere [Esperienza di chat nativa per utenti esterni (federati) in Teams](native-chat-for-external-users.md).

- Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con i messaggi di sola lettura. L'interfaccia utente espone le chat federate in modo simile ai thread di interoperabilità dello stesso tenant, con la differenza che esiste una nota che indica che l'utente è esterno.

Per altri dettagli, vedere [Gestire l'accesso esterno in Microsoft Teams](manage-external-access.md) e [l'esperienza di chat nativa per utenti esterni (federati) in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatti

Teams e Skype for Business hanno elenchi di contatti separati. Ciò significa che le aggiunte ai contatti, la rimozione e le modifiche apportate in un sistema non vengono sincronizzate con l'altro sistema. Tuttavia, i contatti di Skype for Business vengono automaticamente copiati in Teams quando si verifica uno dei due eventi specifici:

- Per qualsiasi utente Skype for Business Online, la prima volta che accede a Teams, i contatti di Skype for Business verranno copiati in Teams. Questo comportamento non è disponibile per gli utenti con un account locale in Skype for Business Server.

- Dopo l'aggiornamento di un utente a TeamsOnly (tramite l'assegnazione di TeamsUpgradePolicy o tramite Move-CsUser -MoveToTeams), la volta successiva che un utente accede a Teams, i contatti esistenti in Skype for Business verranno uniti ai contatti esistenti già presenti in Teams. Questo comportamento si verifica se l'utente è stato spostato in TeamsOnly da locale o online.

In entrambi i casi, il trasferimento dei contatti da Skype for Business a Teams è asincrono, quindi potrebbe essere necessario qualche minuto prima che i contatti vengano visualizzati in Teams. I due eventi precedenti sono ciò che attiva la copia.

### <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
