---
title: Comprendere la coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business
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
ms.openlocfilehash: 60ed33e1bbafe7fe5600edfa85c9f9d5a13432db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681427"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendere la coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business

![Diagramma percorso di aggiornamento, enfatizzando la fase di definizione Project.](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di definizione Project")

Questo articolo fa parte della fase di definizione Project del percorso di aggiornamento. Completare il progetto dopo aver creato una coalizione di sponsorizzazioni e un team di progetto e aver definito l'ambito, gli obiettivi e il piano per il progetto. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)

Se attualmente l'organizzazione usa Skype for Business e si inizia a usare Teams insieme a Skype for Business o si inizia ad eseguire l'aggiornamento a Teams, è importante capire come coesistono le due applicazioni, quando e come interagiscono e come gestire la migrazione degli utenti fino all'eventuale aggiornamento da Skype for Business a Teams.

> [!Tip]
> Guardare la sessione seguente per informazioni sulla [coesistenza e l'interoperabilità](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Inoltre, puoi unirti a noi per workshop interattivi dal vivo in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione dell'aggiornamento.
>
> Partecipa prima alla pianificazione della sessione [di aggiornamento](./upgrade-workshops-landing-page.yml) per iniziare.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coesistenza di Teams e Skype for Business panoramica

Le sezioni seguenti descrivono le modalità di coesistenza disponibili quando si decide di eseguire l'aggiornamento a Teams e le funzionalità offerte da ogni modalità. Inoltre, descriviamo l'interoperabilità (interoperabilità) che si verifica tra gli utenti dei client Skype-for-Business e gli utenti su client Teams e come l'interoperabilità è influenzato dalla modalità di coesistenza scelta.

Teams offre funzionalità di collaborazione, chat, chiamate e riunioni. A seconda di come si sceglie di distribuire Teams, queste funzionalità potrebbero sovrapporsi alle funzionalità fornite da Skype for Business per un determinato utente. La modalità predefinita consiste nell'eseguire Teams insieme a Skype for Business con le funzionalità sovrapposte. Tuttavia, a un utente può essere assegnata una delle diverse modalità di coesistenza (note anche come modalità di aggiornamento) progettate per garantire che queste funzionalità non si sovrappongano per l'utente, nel qual caso è disponibile l'interoperabilità tra Teams e Skype for Business. Ad esempio, se si hanno risorse Skype for Business Server locali significative con una distribuzione VoIP aziendale complessa, ma si vuole che gli utenti possano usare le riunioni moderne il più rapidamente possibile, è consigliabile valutare [Riunioni prima](meetings-first.md) come percorso alternativo.

È consigliabile rivedere le seguenti modalità di coesistenza per determinare il percorso più adatto alla propria organizzazione.

> [!Important]
> Le modalità di coesistenza continuano a esistere dopo il ritiro di Skype for Business Online, tuttavia gli utenti ospitati online possono avere solo una modalità TeamsOnly. Non è più possibile assegnare una modalità diversa da TeamsOnly a un utente ospitato online.  Come è stato fatto prima del ritiro di Skype for Business Online, agli utenti ospitati localmente può essere assegnata qualsiasi modalità *diversa da TeamsOnly*.

### <a name="islands-mode"></a>Modalità Isole

Per impostazione predefinita, gli utenti possono eseguire Teams insieme a Skype for Business come due soluzioni separate che offrono funzionalità simili e sovrapposte. Le funzionalità includono presenza, chat, chiamate e riunioni. Teams gli utenti possono anche sfruttare le nuove funzionalità di collaborazione come team e canali, l'accesso ai file in Microsoft 365 e le applicazioni.

In questa modalità di coesistenza, denominata **Isole**, ognuna delle applicazioni client funziona come un'isola separata. Skype for Business parla con Skype for Business e Teams parla con Teams. Gli utenti devono eseguire entrambi i client in qualsiasi momento e possono comunicare in modo nativo nel client da cui è stata avviata la comunicazione. Di conseguenza, non è necessaria l'interoperabilità nella modalità **Isole** .

Per evitare un'esperienza di Skype for Business confusione o regresso, il Skype for Business gestisce le integrazioni seguenti che non vengono gestite in modalità **Isole** Teams:

- Comunicazioni esterne (federate).
- Servizi vocali PSTN e applicazioni vocali, integrazione Office.
- Controlli HID per dispositivi USB.
- Diverse altre integrazioni.

Sistema telefonico non è supportato in Teams in modalità **Isole**. **La modalità Isole** non supporta VoIP aziendale client è Skype for Business.

> [!Important]
> In modalità **Isole**, tutti i messaggi e le chiamate provenienti da utenti federati (persone esterne all'organizzazione) vengono recapitati a Skype for Business. Dopo l'aggiornamento alla modalità **solo Teams**, tutti i messaggi e le chiamate dall'esterno dell'organizzazione vengono recapitati a Teams.

### <a name="teams-only"></a>solo Teams

Un utente **Teams (** detto anche utente *aggiornato*) ha accesso a tutte le funzionalità di Teams. Possono mantenere il client Skype for Business per partecipare alle riunioni su Skype for Business che sono state organizzate da utenti non aggiornati o da parti esterne. Un utente aggiornato può continuare a comunicare con altri utenti dell'organizzazione che usano ancora Skype for Business usando le funzionalità di interoperabilità tra Teams e Skype for Business, a condizione che gli utenti Skype for Business non siano in modalità **Isole**. Tuttavia, un utente aggiornato non può avviare una Skype for Business chat, una chiamata o una riunione.

Non appena l'organizzazione è pronta per l'uso da parte di alcuni o tutti gli utenti di Teams come unico strumento di comunicazione e collaborazione, aggiornare tali utenti alla modalità **solo Teams**. Se stai effettuando l'aggiornamento dalla modalità **Isole**, ti consigliamo di saturare Teams adozione in tutta l'organizzazione prima di iniziare il processo di aggiornamento. Questa adozione evita scenari di comunicazione interrotti a causa della modalità **Isole** che non fornisce interoperabilità.

In modalità **solo Teams**, Teams è l'app predefinita per il protocollo SIP/Tel. I collegamenti nella scheda contatto di un utente in Outlook per le chiamate o la chat verranno gestiti da Teams.

Per altre considerazioni sul passaggio alla modalità **solo Teams**, vedere [Considerazioni sulla modalità Teams Solo](teams-only-mode-considerations.md).

![Schermata del messaggio di conferma di Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business client in esecuzione in modalità speciale dopo l'aggiornamento dell'utente come utente solo Teams")

### <a name="skype-for-business-only"></a>Solo Skype for Business

In questa modalità di coesistenza, gli utenti rimangono in Skype for Business, non Teams, per le funzionalità di chat, riunione e chiamata e non usano Teams per team e canali. Questa modalità è disponibile oggi; tuttavia, nell'implementazione corrente, i team e i canali non vengono automaticamente disattivati per l'utente. Ciò può essere ottenuto usando il criterio di configurazione delle app per nascondere team e file.

Questa modalità può essere usata prima di avviare una distribuzione gestita di Teams per impedire agli utenti di iniziare a usare Teams prima di aver creato la conformità. Questa modalità è anche un modo per abilitare la partecipazione autenticata a riunioni Teams per Skype for Business utenti, a condizione che gli utenti dispongano di una licenza per Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business con collaborazione Teams

Usare questa modalità per introdurre Teams nell'ambiente mentre si continua a usare l'investimento esistente in Skype for Business. Lasciare Skype for Business invariato per le funzionalità di chat, chiamate e riunioni. Aggiungere funzionalità di collaborazione Teams:

- Teams e canali.
- Accesso ai file in Microsoft 365 o Office 365.
- Applicazioni. Teams funzionalità di comunicazione: chat private, chiamate e pianificazione delle riunioni.

Teams chat privata, le chiamate e la pianificazione delle riunioni sono disattivate per impostazione predefinita in questa modalità.

Le organizzazioni con un punto di partenza per Skype for Business Server locale o ibrido devono considerare questa modalità come un'alternativa alla modalità **Islands** se vogliono offrire agli utenti interoperabilità e prevedibilità per le loro comunicazioni, oltre ad avere una sequenza temporale prevedibile per l'aggiornamento a Teams (a differenza di affidarsi alla saturazione dell'adozione in modalità **Islands**).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business con Teams collaborazione e riunioni, note anche come Riunioni

Usare questa modalità di coesistenza per accelerare la disponibilità di Teams funzionalità di riunione e collaborazione nell'organizzazione. La modalità di coesistenza consente agli utenti di sfruttare l'esperienza di riunione di Teams superiore:

- Ottima qualità.
- Trascrizione e traduzione.
- Sfocatura dello sfondo.
- Esperienza utente superiore su tutte le piattaforme, inclusi i dispositivi mobili e i browser.

Oltre a usare Teams per i team e le conversazioni basate sui canali in questa modalità, gli utenti useranno Teams per pianificare e condurre le loro riunioni. Le chat private e le chiamate rimangono Skype for Business. Teams e Skype for Business beneficiare di una serie di funzionalità "migliori insieme", come la riconciliazione della presenza, il blocco/annullamento automatico e il supporto per dispositivi HID in entrambe le applicazioni. È possibile nascondere team e canali, se lo si desidera, usando i criteri di configurazione delle app.

Questa modalità di coesistenza è particolarmente utile per le organizzazioni con Skype for Business distribuzioni locali con VoIP aziendale. È probabile che queste organizzazioni impiegano del tempo per eseguire l'aggiornamento a Teams e vogliono trarre vantaggio dalle riunioni di Teams superiori il prima possibile.

> [!TIP]
> Per identificare la modalità di aggiornamento consigliata in base alle funzionalità da abilitare in Teams mentre Skype for Business è ancora in uso, usare la [Skype per Teams l'Aggiornamento guidato](https://aka.ms/SkypeToTeamsWizard).

Per altre informazioni sulle modalità di coesistenza, i prerequisiti e la gestione, vedere [Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md) e [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md).

|Icona punto di decisione |Definizione dell'icona |Descrizione |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto di decisione|<ul><li>Quali modalità di coesistenza sono più adatte alle esigenze dell'organizzazione e degli utenti?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Passaggio successivo|<ul><li>Scegli l'approccio migliore per il tuo percorso di aggiornamento.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilità di Teams e Skype for Business

L'interoperabilità consente a Teams e Skype for Business utenti della stessa organizzazione di comunicare tra Teams e Skype for Business.

L'interoperabilità è disciplinata dalla modalità di coesistenza (nota anche come modalità di aggiornamento) del ricevitore. Non esiste interoperabilità quando il ricevitore è in modalità **Islands** .

> [!Note]
> Quando viene distribuita in qualsiasi modalità di coesistenza tranne **Isole**, Teams e Skype for Business possono interagire, consentendo agli utenti di comunicare e chiamarsi e garantire che le comunicazioni rimangano [fluide](#interoperability-of-teams-and-skype-for-business) all'interno dell'organizzazione durante il percorso di aggiornamento verso Teams. Le modalità di coesistenza regolano l'interoperabilità. La modalità di coesistenza del ricevitore determina se sarà disponibile l'interoperabilità. Ad esempio, se il ricevitore è in una modalità in cui la chat è disponibile solo in un client (ad esempio, Teams), l'interoperabilità della chat sarà generalmente disponibile nel caso in cui l'iniziatore usi l'altro client (in questo caso, Skype for Business) per avviare la chat. D'altra parte, se il ricevitore è nella modalità in cui la chat è disponibile in entrambi i client (modalità Isole), l'interoperabilità non sarà disponibile per la chat. Il messaggio verrà ricevuto dal destinatario nello stesso client in cui l'iniziatore ha avviato la chat. Pertanto, una comunicazione corretta in modalità **Isole** richiede Teams saturazione dell'adozione, vale a dire, tutti gli utenti usano attivamente e monitorano entrambi i client.

> [!Note]
> **Per avere l'esperienza di coesistenza più recente, la versione client deve essere il client più recente disponibile nel canale di distribuzione Office dell'utente.**

#### <a name="native-interop-and-interop-escalation"></a>Escalation a interoperabilità e interoperabilità nativi

Esistono due tipi di esperienze di interoperabilità: escalation nativa e di interoperabilità.

- Nel client attualmente in uso si verifica un'esperienza di _interoperabilità nativa_ . Un utente sarà nel client Skype for Business, l'altro in Teams. Un'esperienza di interoperabilità nativa non li porterà a un altro client per comunicare. Gli utenti saranno in grado di condurre la conversazione nel client in uso. Le esperienze di interoperabilità native sono chat e chiamate uno-a-uno.
- Un'esperienza di _escalation dell'interoperabilità_ significa che, nell'ambito di aiutare gli utenti a eseguire un'azione avanzata (come la condivisione del desktop), il client facilita la creazione di una riunione a cui gli utenti possono partecipare per continuare l'esperienza nella riunione. La riunione viene creata sulla piattaforma dell'iniziatore dell'azione. L'utente o gli utenti che non sono su quella piattaforma ricevono un collegamento di partecipazione alla riunione. Facendo clic su questo collegamento, vengono aggiunti alla riunione in un client compatibile (browser, app Web o client completo, a seconda della configurazione). L'escalation di interoperabilità da Skype for Business richiede un client recente. L'escalation di interoperabilità da Teams è ora disponibile. Entrambi sono supportati nelle esperienze di interoperabilità nel tenant e per le comunicazioni federate tra tenant.

#### <a name="native-interop-experiences"></a>Esperienze di interoperabilità native

A seconda delle modalità di coesistenza assegnate agli utenti (come descritto in precedenza), sono disponibili le seguenti esperienze di interoperabilità native:

Skype for Business gli utenti possono chattare uno-a-uno con Teams utenti e viceversa. Una chat di interoperabilità deve essere attraversata da un gateway di interoperabilità che fa parte di Teams servizi cloud (e quindi esiste solo online). Le chat di interoperabilità sono testo normale: testo RTF ed emoticon non sono supportate. Gli utenti in Teams e in Skype for Business ricevono una notifica che la conversazione è una conversazione interoperativo.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business utenti possono effettuare chiamate vocali e videochiamate uno-a-uno agli utenti Teams e Teams utenti possono fare lo stesso.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Le esperienze di interoperabilità con una distribuzione locale di Skype for Business richiedono che l'ambiente locale sia in modalità ibrida con Teams. Per informazioni dettagliate, [vedere Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Queste esperienze di interoperabilità sono disponibili per e tra gli utenti a cui è assegnata una delle seguenti modalità di coesistenza: **Skype for Business con la collaborazione Teams**, **Skype for Business con Teams Collaborazione e riunioni****, Skype for Business Solo** o **solo Teams**. Non esiste interoperabilità per gli utenti nella modalità **Isole** .

#### <a name="native-interop-experience-limitations"></a>Limitazioni dell'esperienza di interoperabilità nativo

A causa della differenza di protocolli e tecnologie, non è possibile supportare tutte le funzionalità in modo nativo. In particolare, le funzionalità seguenti non sono disponibili:

- Il markdown, il testo RTF e il set di emoticon completo non sono supportati da Teams o Skype for Business. Altre funzionalità native della casella di composizione in Teams chat non sono supportate.
- La condivisione dello schermo (condivisione desktop o app) tra Teams e Skype for Business non è supportata in modo nativo. Tuttavia, è supportato tramite escalation di interoperabilità.
- Le chat di gruppo (conversazioni tra più persone) in Teams possono includere solo i partecipanti che usano Teams.
- Le conversazioni istantanee a più parti (chat di gruppo) in Skype for Business possono includere solo i partecipanti che usano Skype for Business. Tuttavia, l'escalation di interoperabilità a più parti è disponibile da Skype for Business.
- L'escalation di una chiamata vocale o video peer-to-peer in corso a una chiamata a più parti che coinvolge Teams e Skype for Business utenti non è supportata.
- Il trasferimento di file per chat con due parti o file allegato nelle chat di gruppo, da Teams a Skype for Business e viceversa, non è supportato.
- Non esiste interoperabilità con Skype for Business Persistent Chat.

Per tutte queste limitazioni (ad eccezione di Persistent Chat), una possibile soluzione alternativa consiste nell'avviare una riunione e invitare l'altro utente a parteciparvi.

Questa soluzione alternativa è la base per l'escalation di interoperabilità. In particolare, la condivisione dello schermo e l'escalation a multiparty non sono raggiungibili in modo nativo, ma sono supportati tramite escalation di interoperabilità.

#### <a name="interop-escalation-experiences"></a>Esperienze di escalation di interoperabilità

L'escalation dell'interoperabilità consiste nell'integrare le funzionalità di interoperabilità native con escalation gestite alle riunioni. Le riunioni offrono esperienze avanzate a disposizione di chiunque, indipendentemente dal cliente di cui dispongono.

Quando l'escalation di interoperabilità viene attivata dall'utente Teams, viene creata una riunione Teams. Quando viene attivata dall'utente Skype for Business, viene creata una riunione Skype for Business. In entrambi i casi, la riunione creata è una riunione **Riunione** immediata, che non viene riportata nel calendario dell'utente.

L'altra parte riceve il collegamento di partecipazione alla riunione tramite chat di interoperabilità e partecipa facendo clic su tale collegamento. Se l'utente Skype for Business ha un account di Teams ed è invitato dall'utente Teams, accederà alla riunione autenticato. In caso contrario, parteciperanno come partecipanti anonimi. Al contrario, Teams utenti hanno quasi sempre un account Skype for Business e un client Skype for Business che possono usare per partecipare a una riunione Skype for Business come partecipante autenticato, ma potrebbero anche partecipare come partecipanti anonimi, ad esempio utilizzando il Riunione Skype App.

Una volta che le parti hanno aderito alla riunione, possono condurre qualsiasi attività supportata nelle riunioni, come la condivisione di desktop o contenuti, la condivisione o il trasferimento di file, l'aggiunta di altri partecipanti e così via.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalation di interoperabilità da Skype for Business

L'escalation di interoperabilità e interoperabilità da Skype for Business è stata aggiornata nella build mensile del C2R di luglio 2019. In precedenza, Skype for Business non avevano la consapevolezza avanzata che la parte remota stava usando Teams. Ha ipotizzato che dalla segnalazione ricevuta dopo una sessione è stata stabilita.

Quando la segnalazione indicava che la risposta proviene (o attraverso) dal gateway di interoperabilità, veniva visualizzata la barra (banner) di colore giallo che indicava che l'altra parte non utilizzava Skype for Business. Con l'evoluzione del nostro servizio, ciò ha portato a falsi positivi in cui Skype for Business utenti vedevano la barra aziendale quando erano connessi al servizio Cloud Voicemail o ad altri servizi vocali cloud, piuttosto che a un effettivo **utente Teams Solo**.

Per evitare questi falsi positivi, il servizio presenza informa ora il client Skype for Business quando l'altra parte è un **Teams Solo** utente effettivo. In questo modo Skype for Business di essere consapevoli della necessità di creare una conversazione interoperativo prima che sia stata creata e che la finestra di conversazione deve essere specifica per l'interoperabilità.

![Screenshot di Teams messaggio per creare una conversazione interoperativo con un utente Skype for Business.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se ad esempio l'utente Skype for Business vuole condividere il proprio desktop, viene informato che microsoft avvierà una riunione e ne verrà illustrata la procedura.

![Screenshot di Teams messaggio per avviare una riunione con un utente Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Nel frattempo, l'utente Teams riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione Skype for Business è disponibile sia per le chiamate e le chat federate in-tenant che tra tenant. È attivata per impostazione predefinita e non esiste alcuna impostazione di cui l'amministratore deve eseguire il provisioning.

#### <a name="interop-escalation-from-teams"></a>Escalation di interoperabilità da Teams

L'escalation dell'interoperabilità da Teams a una riunione di Teams è ora disponibile quando l'utente Teams seleziona il pulsante condivisione desktop in un thread di interoperabilità in-tenant con un utente Skype for Business o in un thread di federazione di interoperabilità tra tenant. L'escalation interoperabilità è supportata da una conversazione in chat 1:1 o da una chiamata 1:1.

Questa funzionalità è supportata nel client desktop Teams per Windows, nel client desktop Teams per Mac e nel client Web Teams nei browser in cui è supportata la condivisione del contenuto, durante le comunicazioni con qualsiasi versione client Skype for Business.

Nei thread di interoperabilità e nei thread di interoperabilità federativo, l'utente Teams dispone ora dei controlli (pulsante) per avviare la condivisione del contenuto. Quando l'utente Teams seleziona il pulsante, viene visualizzato un menu aggiuntivo che informa che per condividere il contenuto, dovrà avviare una riunione Teams.

Se gli utenti erano in una chiamata, il menu li avvisa anche che la chiamata corrente tra Teams e Skype for Business verrà terminata in una riunione Teams. Se lo desiderano, possono avvisare l'utente Skype for Business prima di accettare.

![Screenshot di Teams messaggio per condividere una riunione con un utente Skype for Business.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Una volta accettati, vengono inseriti nella riunione Teams; devono iniziare a condividere dall'area di condivisione della riunione.

Nel frattempo, l'utente Skype for Business riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione Teams è disponibile sia per le chiamate e le chat federate in-tenant che tra tenant. È attivata per impostazione predefinita e non esiste alcuna impostazione di cui l'amministratore deve eseguire il provisioning. Tuttavia, viene disattivata per l'utente se l'amministratore imposta su ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false``.

Dopo aver esaminato questo articolo, vedere [Scegliere il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [indicazioni sulla migrazione e l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md), [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) e [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md) per dettagli sull'implementazione. Consigliamo anche il seguente video: [Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Dettagli tecnici sulla coesistenza di Teams e Skype for Business

Le sezioni seguenti riepilogano il comportamento che può verificarsi durante l'esecuzione di client Teams e Skype for Business nella stessa organizzazione, indipendentemente dalla modalità e dal metodo di aggiornamento usato:

- [Riunioni](#meetings)
- [Interoperabilità](#interoperability)
- [Confronto tra thread di conversazione nativi e interoperabilità](#interop-versus-native-conversation-threads)
- [Icone di presenza](#presence)
- [Federazione](#federation)
- [Contatti](#contacts)

### <a name="meetings"></a>Riunioni

Indipendentemente dalla modalità, gli utenti possono sempre partecipare a qualsiasi tipo di riunione a cui sono invitati, che si tratti di Skype for Business o Teams.  Tuttavia, gli utenti devono partecipare alla riunione con un client corrispondente che corrisponde al tipo di riunione:

- Se la riunione è una riunione Teams, tutti i partecipanti (che si tratti di utenti di TeamsOnly, Islands o Skype for Business) usano il client Teams per partecipare alla riunione. Se Teams non è installato, l'utente verrà indirizzato al Web quando tenta di partecipare a una riunione.

- Se la riunione è una riunione Skype for Business, tutti i partecipanti (che si tratti di utenti di TeamsOnly, Islands o Skype for Business) usano il client Skype for Business per partecipare alla riunione. Se il client Skype for Business non è installato, l'utente verrà indirizzato al Web per partecipare tramite l'app Riunione Skype.

Durante l'organizzazione delle riunioni, il tipo di riunione pianificato si basa sulla modalità dell'organizzatore, come illustrato nella tabella seguente:

| Modalità di organizzatore    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Tutte le riunioni pianificate in Teams. Skype for Business componente aggiuntivo non è disponibile in Outlook. |
| SfbWithTeamsCollab, SfbOnly | Tutte le riunioni pianificate in Skype for Business. Teams componente aggiuntivo non è disponibile in Outlook. |
| Isole | Per impostazione predefinita, le riunioni possono essere pianificate in Skype for Business o Teams. Entrambi i componenti aggiuntivi sono disponibili in Outlook. Tuttavia, facoltativamente, è possibile richiedere agli utenti di Islands di pianificare sempre le riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interoperabilità

Come descritto in precedenza in [Interoperability of Teams and Skype for Business](#interoperability-of-teams-and-skype-for-business), Teams supporta l'interoperabilità con Skype for Business in determinati scenari. Comunicazione di interoperabilità fa riferimento a una chat o chiamata tra un utente Skype for Business e un utente Teams.  La comunicazione di interoperabilità è possibile solo tra due utenti; non è supportata la chat o le chiamate multi-party o l'aggiunta di altri utenti.

Una chiamata o una chat di interoperabilità tra due utenti viene creata quando si verificano le condizioni seguenti:

- Un utente usa Teams e l'altro Skype for Business.

- La modalità del destinatario della comunicazione iniziale non è Isole (altrimenti la comunicazione sarirebbe nello stesso cliente) se entrambi gli utenti fanno parte della stessa organizzazione. Negli scenari federati, l'utente mittente usa Teams e il destinatario non è in modalità TeamsOnly.

- L'utente Teams NON ha anche un account Skype for Business ospitato in locale.

All'interno della comunicazione di interoperabilità, la chat è solo testo normale. Inoltre, la condivisione di file e la condivisione dello schermo non sono possibili *nella chat di interoperabilità stessa*. Tuttavia, gli utenti in una conversazione interoperativo possono raggiungere facilmente la condivisione di file e/o schermo creando una riunione su richiesta, dall'interno della chat di interoperabilità, come descritto di seguito:

- Se l'utente Teams prova a condividere lo schermo, viene creata automaticamente una riunione di Teams su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente Skype for Business. Facendo clic sul collegamento, l'utente Skype for Business aprirà Teams e parteciperà alla riunione. Entrambi gli utenti sono ora in una riunione Teams e possono condividerli in base alle esigenze.

- Se l'utente Skype for Business usa un client dal 2018 o versione successiva e prova a condividere qualsiasi contenuto, viene creata automaticamente una riunione su richiesta Skype for Business e viene inviato un collegamento di invito alla riunione al client dell'utente Teams. Facendo clic sul collegamento, l'utente Teams tenterà di partecipare alla riunione Skype for Business. Se l'utente Teams ha installato il client Skype for Business, verrà aperto e all'utente verrà chiesto di accedere (se non ha già eseguito l'accesso).  Se l'utente Teams non ha installato il client Skype for Business, all'utente verrà richiesto di usare la versione Web. Dopo aver eseguito l'accesso, entrambi gli utenti partecipano a una riunione Skype for Business e possono condividerli in base alle esigenze.

### <a name="interop-versus-native-conversation-threads"></a>Confronto tra thread di conversazione nativi e interoperabilità

Poiché le comunicazioni di interoperabilità non supportano tutte le caratteristiche delle conversazioni Teams native, il client Teams gestisce thread di conversazione separati per la comunicazione tra Teams-Teams e Teams-a-Skype for Business. Il rendering di queste conversazioni è diverso nell'interfaccia utente: i thread di interoperabilità possono essere differenziati da un normale thread Teams nativo da:

- Mancanza di controlli per RTF, condivisione di file/schermo, impossibilità di aggiungere utenti.
- Modifica dell'icona dell'utente di destinazione, con una "S" per Skype for Business.

Queste differenze sono mostrate negli screenshot seguenti:

Una conversazione Teams-a-Teams nativa con test G3 dell'utente

![Diagramma che mostra una conversazione Teams-a-Teams nativa.](media/teams-upgrade-native-thread.png)

Una conversazione interoperativo con lo stesso test G3 utente

![Diagramma che mostra una conversazione di interoperabilità Teams-a-Teams.](media/teams-upgrade-interop-thread.png)

Dopo aver creato un thread di conversazione, il suo tipo non cambia mai. Una volta creato, un thread di interoperabilità in Teams verrà sempre instradato al client Skype for Business dell'utente di destinazione. Un thread nativo verrà sempre instradato al client Teams dell'utente di destinazione.  Se cambia la modalità di un utente destinatario, i thread di Teams esistenti a tale utente non funzioneranno più e verrà visualizzata una nota in quella chat con un collegamento per avviare una nuova conversazione nativa, come illustrato nello screenshot seguente.

![Diagramma che mostra una chat con un utente aggiornato Skype for Business.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Icone di presenza

La presenza per un determinato utente si basa sull'attività dell'utente nel servizio tramite il client. La presenza viene quindi pubblicata per consentire ad altri utenti di visualizzarla.  Skype for Business e Teams sono servizi separati con client separati, quindi ogni servizio ha il proprio stato presenza per un utente.   È anche possibile sincronizzare i servizi presenza in Teams e in Skype for Business Online.  In questo modo un servizio può potenzialmente pubblicare la presenza dell'utente dall'altro servizio, se necessario.

Il comportamento di pubblicazione della presenza si basa sulla modalità dell'utente. Esistono tre casi di base:

- Se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono Teams presenza per quell'utente, indipendentemente dal client che usa.

- Se un utente usa una delle modalità Skype for Business, tutti gli altri utenti vedranno Skype for Business presenza per tale utente, indipendentemente dal client che usa.

- Se un utente è in modalità Isole, la presenza pubblicata in Skype for Business e Teams sono indipendenti, quindi la presenza mostrata agli utenti all'interno della stessa organizzazione dipenderà dal client dell'altro utente. Gli utenti delle organizzazioni federate vedranno la presenza dell'utente in base all'attività di Skype for Business, poiché il traffico federato verso un utente in modalità Isole passa in Skype for Business.

Si supponga, ad esempio, che l'utente A sia in modalità Isole. Se l'utente A è attivo in Teams ma non ha eseguito l'accesso a Skype for Business, gli altri utenti vedranno l'utente A come attivo dal client Teams, ma nel client Skype for Business vedrebbe l'utente A come offline. Si tratta di un'operazione da progettazione, poiché l'utente A non può essere raggiunto se non esegue il client.


### <a name="federation"></a>Federazione

La federazione da Teams a un altro utente che usa Skype for Business richiede che l'utente Teams sia ospitato online in Skype for Business. TeamsUpgradePolicy regola il routing per le chat e le chiamate federate in arrivo. Il comportamento di routing federato è lo stesso degli scenari con lo stesso tenant, tranne che per la modalità Isole. Quando i destinatari sono in modalità Isole:

- Le chat e le chiamate avviate da Teams vengono Skype for Business se il destinatario si trova in un tenant federato.
- Le chat e le chiamate avviate da Teams atterrano in Teams se il destinatario si trova nello stesso tenant.
- Le chat e le chiamate avviate da Skype for Business atterrano sempre in Skype for Business.

Una chat federata può essere un thread nativo o un thread di interoperabilità. Vedere [Confronto tra thread di conversazione nativi e interoperabili](#interop-versus-native-conversation-threads).

- Se il destinatario e il mittente sono entrambi in modalità di aggiornamento di TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere [Esperienza di chat nativa per utenti esterni (federati) in Teams](native-chat-for-external-users.md).

- Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con i messaggi di sola lettura. L'interfaccia utente espone le chat federate in modo simile ai thread di interoperabilità dello stesso tenant, con la differenza che esiste una nota che indica che l'utente è esterno.

Per altre informazioni, vedere [Gestire l'accesso esterno in Microsoft Teams](manage-external-access.md) e [l'esperienza di chat nativa per gli utenti esterni (federati) in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatti

Teams e Skype for Business hanno elenchi di contatti separati. Ciò significa che le aggiunte ai contatti, la rimozione e le modifiche apportate in un sistema non vengono sincronizzate con l'altro sistema. Tuttavia, i contatti di Skype for Business vengono copiati automaticamente in Teams quando si verifica uno dei due eventi specifici:

- Per qualsiasi utente Skype for Business Online, la prima volta che accede a Teams, i contatti di Skype for Business verranno copiati in Teams.  Questo comportamento non è disponibile per gli utenti con un account locale in Skype for Business Server.

- Dopo l'aggiornamento di un utente a TeamsOnly (tramite l'assegnazione di TeamsUpgradePolicy o tramite Move-CsUser -MoveToTeams), la volta successiva che un utente accede a Teams, i contatti esistenti in Skype for Business verranno uniti ai contatti esistenti già presenti in Teams. Questo comportamento si verifica se l'utente è stato spostato in TeamsOnly da locale o online.

In entrambi i casi, il trasferimento dei contatti da Skype for Business a Teams è asincrono, quindi potrebbe essere necessario qualche minuto prima che i contatti vengano visualizzati in Teams. I due eventi precedenti sono ciò che attiva la copia.

### <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
