---
title: Interoperabilità tra Skype for Business e Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Dettagli delle opzioni di coesistenza di Skype for Business e Microsoft Teams e interoperabilità risultante tra Skype for Business e Teams.
localization_priority: Normal
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
ms.openlocfilehash: 7ffc673ade43e8acdb258c9364b3023ba21da2a7
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260348"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendere la coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business

![Diagramma percorso di aggiornamento, enfatizzando il passaggio Definizione progetto](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase definizione del progetto")

Questo articolo fa parte della fase di definizione del progetto per il percorso di aggiornamento. Completare il progetto dopo aver creato una sponsorizzazione e un team di progetto e aver definito l'ambito, gli obiettivi e il piano del progetto. Prima di procedere, verificare di aver completato le attività seguenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)

Se oggi la tua organizzazione usa Skype for Business e inizi a utilizzare Teams insieme a Skype for Business (o stai iniziando ad eseguire l'aggiornamento a Teams), è importante comprendere i seguenti elementi:

- Coesistere tra le due applicazioni.
- Quando e come interoperabilità.
- Come gestire la migrazione degli utenti fino al loro eventuale aggiornamento da Skype for Business a Teams.

> [!Tip]
> Guardare la sessione seguente per informazioni sulla [coesistenza e l'interoperabilità.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Inoltre, è possibile unirsi a noi per laboratori interattivi dal vivo in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione degli aggiornamenti.
>
> Partecipa prima [alla sessione Pianificare l'aggiornamento](https://aka.ms/SkypeToTeamsPlanning) per iniziare.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coesistenza di Teams e Skype for Business

 Teams offre funzionalità di collaborazione, chat, chiamate e riunioni. A seconda di come scegli di distribuire Teams, queste funzionalità potrebbero sovrapporsi alle funzionalità fornite da Skype for Business per un determinato utente. La modalità predefinita è di eseguire Teams insieme a Skype for Business con le funzionalità che si sovrappongono. Tuttavia, a un utente può essere assegnata una delle diverse modalità di coesistenza (note anche come modalità di aggiornamento) progettate per garantire che queste funzionalità non si sovrappongano a quell'utente (nel qual caso è disponibile l'interoperabilità tra Teams e Skype for Business). Ad esempio, se si hanno risorse significative di Skype for Business Server locale con una distribuzione di VoIP aziendale complessa, ma si vuole che gli utenti amino le riunioni moderne il più rapidamente possibile, è consigliabile valutare [Prima](meetings-first.md) riunione come percorso alternativo.

È consigliabile esaminare le modalità di coesistenza seguenti per determinare il percorso corretto per l'organizzazione.

> [!Important]
> Introdurre una nuova tecnologia o apportare modifiche all'ambiente esistente e familiare di Skype for Business, fornendo allo stesso tempo nuovi e grandi vantaggi aziendali, può essere disturbare per gli utenti. Valutare la conformità degli utenti e implementare un piano di comunicazione e formazione prima di implementare le modifiche descritte in questo articolo. Inoltre, è consigliabile eseguire una distribuzione pilota del piano con un gruppo selezionato di utenti prima di implementarlo nell'intera organizzazione.

### <a name="islands-mode"></a>Modalità Isole

Per impostazione predefinita, gli utenti possono affiancare Skype for Business come due soluzioni separate che offrono funzionalità simili e sovrapposte. Le funzionalità includono presenza, chat, chiamate e riunioni. Gli utenti di Teams possono anche sfruttare le nuove funzionalità di collaborazione, come team e canali, l'accesso ai file in Microsoft 365 o Office 365 e alle applicazioni.

In questa modalità di coesistenza, denominata **Isole,** ognuna delle applicazioni client opera come un'isola distinta. Skype for Business parla con Skype for Business e Teams parla con Teams. È previsto che gli utenti eseseguono sempre entrambi i client e possano comunicare a livello nativo nel client da cui è stata avviata la comunicazione. Di conseguenza, non è necessaria l'interoperabilità in **modalità** Isole.

Per evitare confusione o regressione nell'esperienza Skype for Business, Skype for Business gestisce le seguenti integrazioni non gestite nella modalità **Isole** Teams:

- Comunicazioni esterne (federate).
- Servizi vocali PSTN e applicazioni vocali, integrazione di Office.
- Controlli HID per dispositivi USB.
- Diverse altre integrazioni.  

Sistema telefonico non è supportato in Teams in **modalità** Isole. **La** modalità Isole non supporta VoIP aziendale client è Skype for Business.

> [!Important]
> In **modalità** Isole, tutti i messaggi e le chiamate da utenti federati (persone esterne all'organizzazione) vengono recapitati in Skype for Business. Dopo l'aggiornamento **alla modalità Solo Teams,** tutti i messaggi e le chiamate dall'esterno dell'organizzazione vengono recapitati in Teams.

> [!Tip]
> Il percorso consigliato dai clienti di Skype  for Business online è iniziare dalla modalità isole predefinita, guidare la saturazione dell'adozione di Teams nell'organizzazione e quindi passare rapidamente alla modalità Solo di **Teams.** I clienti locali e ibridi, in particolare quelli complessi, potrebbero trarre vantaggio dalla  distribuzione della modalità di collaborazione di **Skype for Business** con Teams come punto di partenza  invece che dalla modalità Isole e da lì in modalità Collaborazione e riunioni di **Teams** (ovvero Riunioni prima), se appropriato, e alla modalità Solo team quando l'organizzazione è pronta ad adottare Teams.

### <a name="teams-only"></a>Solo Teams

Un **utente solo di Teams** (detto anche utente *aggiornato)* ha accesso a tutte le funzionalità di Teams. Possono mantenere il client Skype for Business per partecipare a riunioni su Skype for Business organizzate da utenti o parti esterne non aggiornate. Un utente aggiornato può continuare a comunicare con altri utenti dell'organizzazione che utilizzano ancora Skype for Business utilizzando le funzionalità di interoperabilità tra Teams e Skype for Business (a condizione che gli utenti di Skype for Business non siano **in** modalità Isole). Tuttavia, un utente aggiornato non può avviare una chat, una chiamata o una riunione Skype for Business.

Non appena l'organizzazione è pronta per consentire ad alcuni o tutti gli utenti di usare Teams come unico strumento di comunicazione e collaborazione, aggiorna tali utenti alla modalità **Solo** teams. Se si esegue l'aggiornamento **dalla** modalità Isole, è importante saturare l'adozione di Teams nell'intera organizzazione prima di iniziare il processo di aggiornamento. Questa adozione evita scenari di comunicazione interrotti a causa **della modalità isole** che non fornisce interoperabilità.

In modalità **Solo teams,** Teams è l'app predefinita per il protocollo SIP/Tel. I collegamenti nella scheda contatto di un utente in Outlook per le chiamate o le chat verranno gestiti da Teams.

Per altre considerazioni sul passaggio alla modalità **Solo teams,** vedere considerazioni [sulla modalità Solo teams.](teams-only-mode-considerations.md)

![Schermata del messaggio di conferma di Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Client Skype for Business in esecuzione in modalità speciale dopo l'aggiornamento dell'utente come utente solo teams")

### <a name="skype-for-business-only"></a>Solo Skype for Business

In questa modalità di coesistenza, gli utenti rimangono in Skype for Business, non in Teams, per le funzionalità di chat, riunioni e chiamate e non usano Teams per team e canali. Questa modalità è attualmente disponibile; tuttavia, nell'implementazione corrente, i team e i canali non vengono automaticamente disattivati per l'utente. Questa operazione può essere ottenuta usando il criterio Configurazione app per nascondere team e file.

Questa modalità può essere usata prima di avviare una distribuzione gestita di Teams per impedire agli utenti di iniziare a usare Teams in anticipo rispetto alla preparazione. Questa modalità è anche un modo per abilitare la partecipazione autenticata alle riunioni di Teams per gli utenti di Skype for Business, a condizione che gli utenti siano concessi in licenza per Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Collaborazione in Skype for Business con Teams

Usa questa modalità per presentare Teams nel tuo ambiente mentre continui a utilizzare il tuo investimento esistente in Skype for Business. Lasciare Invariato Skype for Business per le funzionalità di chat, chiamate e riunioni. Aggiungere funzionalità di collaborazione di Teams:

- Team e canali.
- Accesso ai file in Microsoft 365 o Office 365.
- Applicazioni. Funzionalità di comunicazione di Teams: chat privata, chiamate e pianificazione delle riunioni.

In questa modalità, le chat private di Teams, le chiamate e la pianificazione delle riunioni sono disattivate per impostazione predefinita.

Le organizzazioni con un punto di partenza di Skype for Business Server  locale o ibrido devono considerare questa modalità come alternativa alla modalità Isole se vogliono fornire agli utenti interoperabilità e prevedibilità per le comunicazioni, oltre a avere una sequenza temporale prevedibile per l'aggiornamento a Teams (anziché basarsi sulla saturazione dell'adozione **nella** modalità Isole).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business con collaborazione e riunioni di Teams, noto anche come Prima riunione

Usare questa modalità di coesistenza per accelerare la disponibilità delle funzionalità di collaborazione e riunione di Teams nell'organizzazione. La modalità di coesistenza consente agli utenti di sfruttare l'esperienza superiore delle riunioni di Teams:

- Ottima qualità.
- Trascrizione e traduzione.
- Sfocatura dello sfondo.
- Esperienza utente superiore su tutte le piattaforme, compresi i dispositivi mobili e i browser.

Oltre a usare Teams per team e canali, in questa modalità, gli utenti useranno Teams per pianificare e condurre le loro riunioni. Le chiamate e le chat private rimangono su Skype for Business. Teams e Skype for Business traggono vantaggio da una gamma di funzionalità più avanzate insieme, come la riconciliazione della presenza, il blocco/annullamento della conservazione automatici e il supporto dei dispositivi HID in entrambe le applicazioni. Se necessario, è possibile nascondere team e canali usando i criteri di configurazione delle app.

Questa modalità di coesistenza è particolarmente utile per le organizzazioni con distribuzioni locali Skype for Business con VoIP aziendale. Queste organizzazioni hanno maggiori probabilità di richiedere del tempo per eseguire l'aggiornamento a Teams e vogliono trarre vantaggio dalle riunioni di Teams superiore il più presto possibile.

> [!TIP]
> Per aiutare a identificare la modalità di aggiornamento consigliata in base alle funzionalità da abilitare in Teams mentre Skype for Business è ancora in uso, sfruttare l'Aggiornamento guidato da Skype a [Teams.](https://aka.ms/SkypeToTeamsWizard)

Per ulteriori informazioni sulle modalità di coesistenza, i prerequisiti e la gestione, consulta indicazioni su migrazione e [interoperabilità](https://aka.ms/SkypeToTeams-Interop) per le organizzazioni che usano Teams insieme a Skype for Business e impostazioni di [coesistenza](https://aka.ms/SkypeToTeams-SetCoexistence)e aggiornamento.

|Icona del punto di decisione |Definizione dell'icona |Descrizione |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto di decisione|<ul><li>Quali modalità di coesistenza sono più adatte alle esigenze dell'organizzazione e degli utenti?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Passaggio successivo|<ul><li>Scegliere l'approccio migliore per il percorso di aggiornamento.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilità di Teams e Skype for Business

L'interoperabilità è la capacità degli utenti di Teams e Skype for Business nella stessa organizzazione di comunicare tra Teams e Skype for Business.

L'interoperabilità è regolata dalla modalità di coesistenza (nota anche come modalità di aggiornamento) del ricevitore. Non esiste alcuna interoperabilità quando il ricevitore è in **modalità** Isole.

> [!Note]
> Se distribuiti in modalità di coesistenza ad eccezione di **Isole,** Teams e Skype for Business possono interoperabilità, consentendo agli utenti di chattare e chiamarsi tra loro e assicurando che le comunicazioni rimangano [fluide](#interoperability-of-teams-and-skype-for-business)in tutta l'organizzazione durante il percorso di aggiornamento a Teams. Le modalità di coesistenza regolano l'interoperabilità. La modalità di coesistenza del ricevitore determina se sarà disponibile l'interoperabilità. Ad esempio, se il ricevitore è in una modalità in cui la chat è disponibile solo in un client (ad esempio Teams), l'interoperabilità della chat sarà generalmente disponibile nel caso in cui l'iniziatore usi l'altro client (in questo caso Skype for Business) per avviare la chat. Se invece il ricevitore è nella modalità in cui la chat è disponibile in entrambi i client (modalità Isole), l'interoperabilità non sarà disponibile per la chat. Il messaggio verrà ricevuto dal destinatario nello stesso client in cui l'iniziatore ha avviato la chat. Pertanto, una corretta comunicazione in **modalità Isole** richiede la saturazione dell'adozione di Teams; in altri casi, tutti gli utenti usano e monitorano attivamente entrambi i client.

> [!Note]
> **Per avere un'esperienza di coesistenza più recente, la versione client deve essere il client più recente disponibile nel canale di distribuzione di Office dell'utente.**

### <a name="native-interop-and-interop-escalation"></a>Escalation di interoperabilità e interoperabilità nativa

Esistono due tipi di esperienze di interoperabilità: riassegnazione nativa e interoperabilità.

- Si _verifica un'esperienza di interoperabilità_ nativa nel client attualmente in uso. Un utente sarà nel client Skype for Business, l'altro in Teams. Un'esperienza di interoperabilità nativa non li porta a un altro client per comunicare. Gli utenti saranno in grado di condurre la conversazione nel client attualmente in uso. Le esperienze di interoperabilità native sono chat e chiamate uno-a-uno.
- Un'esperienza di escalation di _interoperabilità_ significa che, nell'ambito di aiutare gli utenti a eseguire un'azione avanzata (ad esempio la condivisione del desktop), il client facilita la creazione di una riunione a cui gli utenti possono partecipare per continuare l'esperienza in quella riunione. La riunione viene creata nella piattaforma dell'organizzatore dell'azione. L'utente o gli utenti che non sono su quella piattaforma ricevono un collegamento per partecipare alla riunione. Quando fanno clic su questo collegamento, questi vengono aggiunti alla riunione in un client compatibile (browser, app Web o client completo, a seconda della configurazione). L'escalation di interoperabilità da Skype for Business richiede un client recente. L'escalation di interoperabilità da Teams è ora disponibile. Entrambi sono supportati nelle esperienze di interoperabilità nel tenant e per le comunicazioni federate tra tenant.

### <a name="native-interop-experiences"></a>Esperienze di interoperabilità native

A seconda delle modalità di coesistenza assegnate agli utenti (come descritto in precedenza), sono disponibili le seguenti esperienze di interoperabilità native:

Gli utenti di Skype for Business possono chattare uno-a-uno con gli utenti di Teams e viceversa. Una chat di interoperabilità deve essere attraversata da un gateway di interoperabilità che fa parte dei servizi cloud di Teams e quindi esiste solo online. Le chat di interoperabilità sono testo normale: il formato RTF e le emoticon non sono supportate. Agli utenti di Teams e Skype for Business viene notificato che la conversazione è una conversazione di interoperabilità.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Gli utenti di Skype for Business possono effettuare chiamate vocali e videochiamate uno-a-uno agli utenti di Teams, e gli utenti di Teams possono fare lo stesso.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Le esperienze di interoperabilità con una distribuzione locale di Skype for Business richiedono che l'ambiente locale sia in modalità ibrida con Microsoft 365 o Office 365 Skype for Business. Per informazioni dettagliate, vedere [Indicazioni sulla migrazione e l'interoperabilità.](https://aka.ms/SkypeToTeams-Interop)

Queste esperienze di interoperabilità sono disponibili a e tra gli utenti a cui è assegnata una delle seguenti modalità di coesistenza: Skype for Business con collaborazione **Teams,** Skype for Business con collaborazione e riunioni **teams,** **Solo Skype for Business** o **Teams.** Non esiste interoperabilità per gli utenti in **modalità** Isole.

### <a name="native-interop-experience-limitations"></a>Limitazioni dell'esperienza di interoperabilità nativa

A causa della differenza in protocolli e tecnologie, non è possibile supportare tutte le funzionalità a livello nativo. In particolare, le funzionalità seguenti non sono disponibili:

- Il markdown, il testo RTF e il set completo di emoticon non sono supportati né da Teams né da Skype for Business. Altre funzionalità native della casella di composizione nelle chat di Teams non sono supportate.
- La condivisione dello schermo (desktop o app) tra Teams e Skype for Business non è supportata a livello nativo. Tuttavia, è supportato tramite l'escalation di interoperabilità.
- Le chat di gruppo (conversazioni tra più persone) in Teams possono includere solo i partecipanti che usano Teams.
- Le conversazioni istantanee tra più persone (chat di gruppo) in Skype for Business possono includere solo partecipanti che usano Skype for Business. Tuttavia, l'escalation di interoperabilità a più utenti è disponibile da Skype for Business.
- Non è supportata l'inoltro di una chiamata vocale o videochiamata peer-to-peer in corso a una chiamata a più parti che coinvolge utenti sia di Teams che di Skype for Business.
- Il trasferimento di file per le chat tra due parti o l'allegato nelle chat di gruppo, da Teams a Skype for Business e viceversa, non sono supportati.
- Non esiste alcuna interoperabilità con Chat persistente di Skype for Business.

Per tutte queste limitazioni (ad eccezione di Chat persistente), una possibile soluzione alternativa consiste nell'avviare una riunione e invitare l'altro utente ad parteciparvi.

Questa soluzione alternativa è la base per l'escalation di interoperabilità. In particolare, la condivisione dello schermo e l'escalation a più parti non sono raggiungibili a livello nativo, ma sono supportati tramite l'escalation di interoperabilità.

### <a name="interop-escalation-experiences"></a>Esperienze di escalation di interoperabilità

L'escalation di interoperabilità consiste nel integrare le funzionalità di interoperabilità native con le riassegnazioni gestite alle riunioni. Le riunioni offrono esperienze significative a tutti gli utenti, indipendentemente dal cliente in cui hanno.

Quando l'utente di Teams attiva l'escalation di interoperabilità, viene creata una riunione di Teams. Quando viene attivato dall'utente Skype for Business, viene creata una riunione Skype for Business. In entrambi i casi, la riunione creata è **una** riunione Riunione corrente, che non si riflette nel calendario dell'utente.

L'altra parte riceve il collegamento per partecipare alla riunione tramite una chat di interoperabilità e partecipa facendo clic su tale collegamento. Se l'utente di Skype for Business ha un account di Teams e viene invitato dall'utente di Teams, verrà connesso alla riunione autenticato. In caso contrario, partecipa come partecipante anonimo. Al contrario, gli utenti di Teams hanno quasi sempre un account Skype for Business e un client Skype for Business che possono usare per partecipare a una riunione Skype for Business come partecipante autenticato, ma potrebbero anche partecipare come partecipanti anonimi, ad esempio utilizzando l'app Riunione Skype.

Una volta che le parti hanno aderito alla riunione, possono svolgere qualsiasi attività supportata nelle riunioni, come la condivisione di desktop o contenuti, la condivisione o il trasferimento di file, l'aggiunta di altri partecipanti e così via.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalation di interoperabilità da Skype for Business

L'escalation di interoperabilità e interoperabilità da Skype for Business è stata aggiornata nella build di luglio 2019 della versione C2R mensile. In precedenza, Skype for Business non aveva la consapevolezza anticipata che la parte remota usava Teams. Tale segnalazione è stata verificata solo dal segnale ricevuto dopo che è stata stabilita una sessione.

Quando il servizio di segnalazione indicava che la risposta proveniva dal gateway di interoperabilità, veniva visualizzata la barra aziendale gialla (banner) che indica che l'altra parte non usaVa Skype for Business. Con l'evoluzione del servizio, questo causava falsi positivi in cui gli utenti di Skype for Business vedevano la barra aziendale quando erano connessi al servizio Cloud Voicemail o ad altri servizi vocali cloud, invece che a un effettivo utente solo di **Teams.**

Per evitare questi falsi positivi, il servizio di presenza ora informa il client Skype for Business quando l'altra parte è un utente effettivo solo di **Teams.** Ciò consente a Skype for Business di sapere che deve creare una conversazione di interoperabilità prima della sua creazione e che la finestra di conversazione deve essere specifica per l'interoperabilità.

![Schermata del messaggio di Teams per creare una conversazione di interoperabilità con un utente di Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se ad esempio l'utente di Skype for Business vuole condividere il proprio desktop, viene informato che microsoft inizierà una riunione e guiderà l'utente attraverso le procedure.

![Schermata del messaggio di Teams per iniziare la riunione con un utente di Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Nel frattempo, l'utente di Teams riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione Skype for Business è disponibile sia per le chat e le chiamate federate tra tenant che per le chiamate federate tra tenant. È attivata per impostazione predefinita e non è necessario effettuare il provisioning dell'amministratore.

#### <a name="interop-escalation-from-teams"></a>Escalation di interoperabilità da Teams

L'escalation di interoperabilità da Teams a una riunione di Teams è ora disponibile quando l'utente di Teams seleziona il pulsante di condivisione desktop in un thread di interoperabilità in-tenant con un utente di Skype for Business o in un thread di federazione di interoperabilità tra tenant. L'escalation di interoperabilità è supportata da una conversazione chat 1:1 o da una chiamata 1:1.

Questa funzionalità è supportata nel client desktop di Teams per Windows, nel client desktop di Teams per Mac e nel client Web di Teams sui browser in cui è supportata la condivisione di contenuti, durante le comunicazioni con qualsiasi versione client di Skype for Business.

Nei thread di interoperabilità e nei thread di interoperabilità della federazione, l'utente di Teams dispone ora dei controlli (pulsante) per avviare la condivisione del contenuto. Quando l'utente di Teams seleziona il pulsante, viene visualizzato un menu aggiuntivo che lo informa che per condividere il contenuto, dovrà avviare una riunione di Teams.

Se gli utenti sono stati in una chiamata, il menu li avvisa anche che la chiamata corrente tra Teams e Skype for Business verrà terminata in una riunione di Teams. Se l'utente sceglie, potrà avvisare l'utente di Skype for Business prima di accettare.

![Schermata del messaggio di Teams per condividere una riunione con un utente Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Dopo l'accettazione, vengono inseriti nella riunione di Teams; devono iniziare a condividere dall'area di condivisione della riunione.

Nel frattempo, l'utente di Skype for Business riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione di Teams è disponibile sia per l'interoperabilità con tenant sia per le chat e le chiamate federate tra tenant. È attivata per impostazione predefinita e non è necessario effettuare il provisioning dell'amministratore. Tuttavia, viene disattivata per l'utente se l'amministratore ``-AllowPrivateMeetNow`` lo imposta su ``CsTeamsMeetingPolicy`` ``$false`` .

Dopo aver esaminato questo articolo, vedere questi articoli correlati:

- [Scegliere il percorso verso l'aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Indicazioni per la migrazione e l'interoperabilità](https://aka.ms/SkypeToTeams-Interop)
- [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md)
-  [Impostazione delle impostazioni di coesistenza e aggiornamento per](https://aka.ms/SkypeToTeams-SetCoexistence) i dettagli dell'implementazione.

## <a name="related-links"></a>Collegamenti correlati

[Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
