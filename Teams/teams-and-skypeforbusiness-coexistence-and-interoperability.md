---
title: Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Dettagli sulle Skype for Business e Microsoft Teams di coesistenza e sulla conseguente interoperabilità tra Skype for Business e Teams.
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
ms.openlocfilehash: f76fa8a527de5cc56d6ae1d2f6a657bf702d9b35
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824675"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità

![Diagramma percorso di aggiornamento, enfatizzando la fase Project definizione.](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase Project definizione")

Questo articolo fa parte della fase Project definizione del percorso di aggiornamento. Completare l'operazione dopo aver creato una lega di sponsorizzazione e un team di progetto e aver definito l'ambito, gli obiettivi e il piano per il progetto. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)

Se l'organizzazione usa Skype for Business oggi e si sta iniziando a usare Teams insieme a Skype for Business o si sta iniziando ad eseguire l'aggiornamento a Teams, è importante comprendere come coesisteranno le due applicazioni, quando e come interagisce e come gestire la migrazione degli utenti fino all'eventuale aggiornamento da Skype for Business a Teams.

> [!Tip]
> Guardare la sessione seguente per informazioni sulla [coesistenza e l'interoperabilità.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Inoltre, puoi unirti a noi per laboratori interattivi in tempo reale in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione degli aggiornamenti.
>
> Per [iniziare, partecipare](./upgrade-workshops-landing-page.yml) alla sessione Di pianificazione dell'aggiornamento.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Panoramica della coesistenza di Teams e Skype for Business

Le sezioni seguenti descrivono le modalità di coesistenza disponibili quando si decide di eseguire l'aggiornamento a Teams e le funzionalità offerte da ogni modalità. Viene inoltre descritta l'interoperabilità (interoperabilità) che si verifica tra gli utenti nei client Skype-for-Business e gli utenti nei client Teams e il modo in cui l'interoperabilità è influenzata dalla modalità di coesistenza scelta.

Teams offre funzionalità di collaborazione, chat, chiamate e riunioni. A seconda di come si sceglie di distribuire Teams, queste funzionalità potrebbero sovrapporsi alle funzionalità fornite da Skype for Business per un determinato utente. La modalità predefinita è l'esecuzione Teams insieme Skype for Business con le funzionalità sovrapposte. Tuttavia, a un utente può essere assegnata una delle diverse modalità di coesistenza (note anche come modalità di aggiornamento) progettate per garantire che queste funzionalità non si sovrappongano a tale utente (nel qual caso è disponibile l'interoperabilità tra Teams e Skype for Business). Ad esempio, se si hanno risorse Skype for Business Server locali significative con una distribuzione di VoIP aziendale complessa, ma si vuole che gli utenti potranno usare le riunioni moderne il più rapidamente possibile, è consigliabile valutare [Riunioni](meetings-first.md) prima come percorso alternativo.

È consigliabile esaminare le modalità di coesistenza seguenti per determinare il percorso più corretto per l'organizzazione.

> [!Important]
> Le modalità di coesistenza continuano a esistere dopo il ritiro di Skype for Business Online, tuttavia gli utenti ospitati online possono avere solo una modalità TeamsOnly. Non è più possibile assegnare una modalità diversa da TeamsOnly a un utente ospitato online.  Come nel caso precedente al ritiro di Skype for Business Online, agli utenti ospitati in locale può essere assegnata qualsiasi modalità diversa *da TeamsOnly.*

### <a name="islands-mode"></a>Modalità Isole

Per impostazione predefinita, gli utenti possono eseguire Teams insieme Skype for Business due soluzioni distinte che offrono funzionalità simili e sovrapposte. Le funzionalità includono presenza, chat, chiamate e riunioni. Teams utenti possono anche sfruttare le nuove funzionalità di collaborazione, ad esempio team e canali, l'accesso ai file in Microsoft 365 e alle applicazioni.

In questa modalità di coesistenza, denominata **Isole,** ognuna delle applicazioni client opera come isola separata. Skype for Business colloqui con Skype for Business e Teams colloqui con Teams. Gli utenti devono eseguire entrambi i client in qualsiasi momento e possono comunicare in modo nativo nel client da cui è stata avviata la comunicazione. Di conseguenza, non è necessaria l'interoperabilità in **modalità** Isole.

Per evitare un'esperienza Skype for Business confusa o regredita, il Skype for Business gestisce le integrazioni seguenti che non vengono gestite in modalità Teams **isole:**

- Comunicazioni esterne (federate).
- Servizi vocali PSTN e applicazioni vocali, Office integrazione.
- Controlli HID per dispositivi USB.
- Diverse altre integrazioni.  

Sistema telefonico non è supportato in Teams in **modalità** Isole. **La** modalità Isole non supporta VoIP aziendale client è Skype for Business.

> [!Important]
> In **modalità** Isole, tutti i messaggi e le chiamate provenienti da utenti federati (persone esterne all'organizzazione) vengono recapitati Skype for Business. Dopo l'aggiornamento **alla Teams solo** messaggi, tutti i messaggi e le chiamate provenienti dall'esterno dell'organizzazione vengono recapitati Teams.

### <a name="teams-only"></a>Teams Solo

Un **Teams solo** utente (detto anche utente aggiornato) ha accesso a tutte le funzionalità di Teams.  Possono mantenere il client Skype for Business partecipare alle riunioni Skype for Business organizzate da utenti non aggiornati o da parti esterne. Un utente aggiornato può continuare a comunicare con altri utenti dell'organizzazione che usano ancora Skype for Business usando le funzionalità di interoperabilità tra Teams e Skype for Business (a condizione che gli utenti Skype for Business non siano **in** modalità Isole). Tuttavia, un utente aggiornato non può avviare una chat Skype for Business, una chiamata o una riunione.

Non appena l'organizzazione è pronta per consentire ad alcuni o a tutti gli utenti di usare Teams come unico strumento di comunicazione e collaborazione, aggiornare questi utenti alla modalità **solo** Teams. Se si esegue  l'aggiornamento dalla modalità Isole, si consiglia di saturare Teams'adozione in tutta l'organizzazione prima di iniziare il processo di aggiornamento. Questa adozione evita scenari di comunicazione interrotti a causa **della modalità Isole** che non fornisce interoperabilità.

Quando è **attiva Teams solo** messaggi, Teams è l'app predefinita per il protocollo SIP/Tel. I collegamenti nella scheda contatto di un utente in Outlook chiamate o chat verranno gestiti da Teams.

Per considerazioni aggiuntive sul passaggio **alla modalità solo Teams,** vedere considerazioni [Teams solo modalità.](teams-only-mode-considerations.md)

![Schermata del messaggio Teams conferma.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business client in esecuzione in una modalità speciale dopo l'aggiornamento dell'utente come Teams solo utenti")

### <a name="skype-for-business-only"></a>Solo Skype for Business

In questa modalità di coesistenza, gli utenti rimangono in Skype for Business, non Teams, per le funzionalità di chat, riunioni e chiamate e non usano Teams per team e canali. Questa modalità è disponibile oggi. Tuttavia, nell'implementazione corrente, i team e i canali non vengono disattivati automaticamente per l'utente. A questo scopo, è possibile usare i criteri di configurazione dell'app per nascondere team e file.

Questa modalità può essere usata prima di avviare una distribuzione gestita di Teams per impedire agli utenti di iniziare a usare Teams prima di aver creato la conformità. Questa modalità è anche un modo per abilitare la partecipazione autenticata alle riunioni Teams per gli utenti Skype for Business, a condizione che gli utenti siano concessi in licenza per Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business con Teams collaborazione

Usare questa modalità per introdurre Teams'ambiente mentre si continua a usare l'investimento esistente in Skype for Business. Lasciare Skype for Business invariate per le funzionalità di chat, chiamate e riunioni. Aggiungere Teams di collaborazione:

- Teams e canali.
- Accesso ai file in Microsoft 365 o Office 365.
- Applicazioni. Teams comunicazioni: chat privata, chiamate e pianificazione di riunioni.

Teams la chat privata, le chiamate e la pianificazione delle riunioni sono disattivate per impostazione predefinita in questa modalità.

Le organizzazioni con un punto di partenza di Skype for Business Server locale o ibrida  devono considerare questa modalità come alternativa alla modalità Isole se vogliono offrire agli utenti l'interoperabilità e la prevedibilità per le comunicazioni, oltre a avere una sequenza temporale prevedibile per l'aggiornamento a Teams (invece di affidarsi alla saturazione dell'adozione **in** modalità Isole).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business con Teams e riunioni, note anche come Riunioni per prime

Usare questa modalità di coesistenza per accelerare la disponibilità delle funzionalità Teams riunione e collaborazione nell'organizzazione. La modalità di coesistenza consente agli utenti di sfruttare l'esperienza Teams riunioni:

- Ottima qualità.
- Trascrizione e traduzione.
- Sfocatura dello sfondo.
- Esperienza utente superiore in tutte le piattaforme, inclusi i dispositivi mobili e i browser.

Oltre a usare Teams per le conversazioni basate su team e canali in questa modalità, gli utenti useranno Teams per pianificare e condurre le riunioni. Le chat private e le chiamate rimangono Skype for Business. Teams e Skype for Business possono trarre vantaggio da una gamma di funzionalità "migliori insieme", come la riconciliazione della presenza, il blocco/sblocco automatico e il supporto dei dispositivi HID in entrambe le applicazioni. Se si desidera, è possibile nascondere team e canali usando i criteri di configurazione dell'app.

Questa modalità di coesistenza è particolarmente utile per le organizzazioni Skype for Business distribuzioni locali con VoIP aziendale. È probabile che queste organizzazioni trascino del tempo per eseguire l'aggiornamento a Teams e vogliano trarre vantaggio dalle riunioni Teams più importanti al più presto.

> [!TIP]
> Per identificare la modalità di aggiornamento consigliata in base alle funzionalità da abilitare in Teams mentre Skype for Business è ancora in uso, usare Skype per Teams aggiornamento [guidato](https://aka.ms/SkypeToTeamsWizard).

Per altre informazioni sulle modalità di coesistenza, i prerequisiti e la gestione, vedere Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a [Skype for Business](./migration-interop-guidance-for-teams-with-skype.md) e Impostazione delle impostazioni di coesistenza e [aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)

|Icona del punto di decisione |Definizione dell'icona |Descrizione |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto di decisione|<ul><li>Quali modalità di coesistenza sono più adatte alle esigenze dell'organizzazione e degli utenti?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Passaggio successivo|<ul><li>Scegliere l'approccio migliore per il percorso di aggiornamento.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilità di Teams e Skype for Business

L'interoperabilità è la possibilità Teams e Skype for Business utenti della stessa organizzazione di comunicare tra Teams e Skype for Business.

L'interoperabilità è regolata dalla modalità di coesistenza (nota anche come modalità di aggiornamento) del ricevitore. Non esiste alcuna interoperabilità quando il ricevitore è in **modalità** Isole.

> [!Note]
> Quando viene distribuita in qualsiasi modalità di coesistenza ad eccezione di Isole **,** Teams e Skype for Business può interagire, consentendo agli utenti di chattare e chiamarsi tra loro e assicurando che le comunicazioni rimangano [fluide](#interoperability-of-teams-and-skype-for-business)in tutta l'organizzazione durante il percorso di aggiornamento a Teams. Le modalità di coesistenza regolano l'interoperabilità. La modalità di coesistenza del ricevitore determina se l'interoperabilità sarà disponibile. Ad esempio, se il destinatario è in una modalità in cui la chat è disponibile solo in un client (ad esempio, Teams), l'interoperabilità della chat sarà generalmente disponibile nel caso in cui l'iniziatore usi l'altro client (in questo caso, Skype for Business) per avviare la chat. D'altra parte, se il ricevitore è nella modalità in cui la chat è disponibile in entrambi i client (modalità Isole), l'interoperabilità non sarà disponibile per la chat. Il messaggio verrà ricevuto dal destinatario nello stesso client in cui l'iniziatore ha avviato la chat. Pertanto, la corretta comunicazione in **modalità** Isole richiede Teams saturazione dell'adozione; in altri casi, tutti gli utenti usano e monitorano attivamente entrambi i client.

> [!Note]
> **Per avere l'esperienza di coesistenza più recente, la versione client deve essere il client più recente disponibile nel canale di Office di distribuzione dell'utente.**

#### <a name="native-interop-and-interop-escalation"></a>Escalation dell'interoperabilità nativa e dell'interoperabilità

Esistono due tipi di esperienze di interoperabilità: l'escalation nativa e l'escalation di interoperabilità.

- Nel client _attualmente_ in uso si verifica un'esperienza di interoperabilità nativa. Un utente sarà nel client Skype for Business, l'altro in Teams. Un'esperienza di interoperabilità nativa non li porta a un altro client per comunicare. Gli utenti saranno in grado di condurre la conversazione nel client attualmente in uso. Le esperienze di interoperabilità native sono chat e chiamate uno-a-uno.
- Un'esperienza di _escalation_ dell'interoperabilità significa che, nell'ambito dell'assistenza agli utenti per l'esecuzione di un'azione avanzata, ad esempio la condivisione del desktop, il client facilita la creazione di una riunione a cui gli utenti possono partecipare per continuare l'esperienza in quella riunione. La riunione viene creata sulla piattaforma dell'iniziatore dell'azione. L'utente o gli utenti che non sono su quella piattaforma ricevono un collegamento di partecipazione alla riunione. Quando fanno clic su questo collegamento, vengono aggiunti alla riunione in un client compatibile (browser, app Web o client completo, a seconda della configurazione). L'escalation di interoperabilità Skype for Business richiede un client recente. L'escalation di interoperabilità Teams ora è disponibile. Entrambi sono supportati nelle esperienze di interoperabilità in-tenant e per le comunicazioni federate tra tenant.

#### <a name="native-interop-experiences"></a>Esperienze di interoperabilità native

A seconda delle modalità di coesistenza assegnate agli utenti (come descritto in precedenza), sono disponibili le esperienze di interoperabilità native seguenti:

Skype for Business utenti possono chattare uno a uno con Teams utenti e viceversa. Una chat di interoperabilità deve passare attraverso un gateway di interoperabilità che fa parte dei Teams cloud (e quindi esiste solo online). Le chat di interoperabilità sono testo normale: il formato RTF e le emoticon non sono supportati. Gli utenti in Teams e in Skype for Business vengono informati che la conversazione è una conversazione di interoperabilità.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business gli utenti possono effettuare chiamate vocali e videochiamate uno-a-uno agli utenti Teams e Teams utenti possono fare lo stesso.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Le esperienze di interoperabilità con una distribuzione locale di Skype for Business richiedono che l'ambiente locale sia in modalità ibrida con Teams. Per informazioni dettagliate, [configurare la connettività](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)ibrida tra Skype for Business Server e Microsoft 365 o Office 365 .

Queste esperienze di interoperabilità sono disponibili per e tra gli utenti a cui è assegnata una delle modalità di coesistenza seguenti: **Skype for Business con** collaborazione Teams , Skype for Business con collaborazione e riunioni **Teams**, **solo Skype for Business** oppure Teams **solo**. Non esiste alcuna interoperabilità per gli utenti in **modalità** Isole.

#### <a name="native-interop-experience-limitations"></a>Limitazioni dell'esperienza di interoperabilità nativa

A causa della differenza di protocolli e tecnologie, non è possibile supportare tutte le funzionalità in modo nativo. In particolare, le funzionalità seguenti non sono disponibili:

- Markdown, RTF e il set completo di emoticon non sono supportati né da Teams né Skype for Business. Altre funzionalità native della casella di composizione nelle chat Teams non sono supportate.
- La condivisione dello schermo (desktop o app) tra Teams e Skype for Business non è supportata a livello nativo. Tuttavia, è supportato tramite l'escalation di interoperabilità.
- Le chat di gruppo (conversazioni con più partecipanti) in Teams possono includere solo i partecipanti che usano Teams.
- Le conversazioni istantanee di più parti (chat di gruppo) in Skype for Business possono includere solo i partecipanti che usano Skype for Business. Tuttavia, l'escalation di interoperabilità a più parti è disponibile Skype for Business.
- L'escalation di una chiamata vocale o videochiamata peer-to-peer in corso a una chiamata a più parti che coinvolge utenti Teams e Skype for Business non è supportata.
- Il trasferimento di file per chat di due parti o file allegati nelle chat di gruppo, da Teams a Skype for Business e viceversa, non è supportato.
- Non esiste alcuna interoperabilità con Skype for Business Persistent Chat.

Per tutte queste limitazioni (ad eccezione di Chat persistente), una possibile soluzione alternativa consiste nell'avviare una riunione e invitare l'altro utente a partecipare.

Questa soluzione alternativa è la base per l'escalation dell'interoperabilità. In particolare, la condivisione dello schermo e l'escalation a più parti non sono raggiungibili in modo nativo, ma sono supportati tramite l'escalation di interoperabilità.

#### <a name="interop-escalation-experiences"></a>Esperienze di escalation di interoperabilità

L'escalation di interoperabilità consiste nell'integrare le funzionalità di interoperabilità native con le escalation gestite alle riunioni. Le riunioni offrono esperienze ricche a chiunque, indipendentemente dal cliente che ha.

Quando l'escalation di interoperabilità viene attivata dall Teams utente, viene creata Teams riunione. Quando viene attivato dall'utente Skype for Business, viene creata Skype for Business riunione. In entrambi i casi, la riunione creata **è** una riunione Riunione ora, che non si riflette nel calendario dell'utente.

L'altra parte riceve il collegamento di partecipazione alla riunione tramite chat di interoperabilità e partecipa facendo clic su tale collegamento. Se l Skype for Business utente ha un account Teams e viene invitato dall'utente Teams, partecipa alla riunione autenticata. In caso contrario, si uniranno come partecipante anonimo. Al contrario, gli utenti di Teams hanno quasi sempre un account Skype for Business e un client Skype for Business che possono usare per partecipare a una riunione di Skype for Business come partecipante autenticato, ma possono anche partecipare come partecipante anonimo, ad esempio usando l'app Riunione Skype.

Una volta che le parti hanno aderito alla riunione, possono svolgere qualsiasi attività supportata nelle riunioni, ad esempio la condivisione di desktop o di contenuti, la condivisione o il trasferimento di file, l'aggiunta di altri partecipanti e così via.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalation di interoperabilità Skype for Business

L'escalation di interoperabilità e interoperabilità Skype for Business è stata aggiornata nella build di luglio 2019 della versione mensile C2R. In precedenza, Skype for Business non aveva la consapevolezza che la parte remota usava Teams. Si è solo supporto che dalla segnalazione ricevuta dopo che è stata stabilita una sessione.

Quando la segnalazione indicava che la risposta proveniva dal gateway di interoperabilità (o attraverso), veniva visualizzata la barra commerciale gialla (banner) che indica che l'altra parte non usava Skype for Business. Con l'evoluzione del servizio, si sono prodotti falsi positivi in cui gli utenti di Skype for Business visualizzavano la barra aziendale quando erano connessi al servizio Cloud Voicemail o ad altri servizi vocali cloud, invece che a un utente **Teams Solo.**

Per evitare questi falsi positivi, il servizio presenza ora informa il client di Skype for Business quando l'altra parte è Teams **solo utente** effettivo. In questo Skype for Business essere consapevoli della necessità di creare una conversazione di interoperabilità prima che sia stata creata e che la finestra di conversazione sia specifica per l'interoperabilità.

![Screenshot del messaggio Teams per creare una conversazione di interoperabilità con un Skype for Business utente.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se l Skype for Business utente vuole condividere il proprio desktop, ad esempio, viene informato che verrà avviata una riunione e illustrata la procedura.

![Schermata del messaggio Teams per avviare la riunione con un Teams utente.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Nel frattempo, il Teams riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una riunione Skype for Business è disponibile sia per le chat e le chiamate federate in tenant che per le chat tra tenant. È attivata per impostazione predefinita e non è necessario eseguire il provisioning dell'amministratore.

#### <a name="interop-escalation-from-teams"></a>Escalation di interoperabilità Teams

L'escalation di interoperabilità da Teams a una riunione di Teams è ora disponibile quando l'utente di Teams seleziona il pulsante di condivisione desktop in un thread di interoperabilità in-tenant con un utente di Skype for Business o in un thread di federazione di interoperabilità tra tenant. L'escalation di interoperabilità è supportata da una conversazione chat 1:1 o da una chiamata 1:1.

La funzionalità è supportata nel client desktop di Teams per Windows, nel client desktop di Teams per Mac e nel client Web di Teams nei browser in cui è supportata la condivisione di contenuto, mentre è in comunicazione con qualsiasi versione client di Skype for Business.

Nei thread di interoperabilità e nei thread di interoperabilità federativi, l'utente Teams ora ha i controlli (pulsante) per avviare la condivisione del contenuto. Quando l Teams utente seleziona il pulsante, viene visualizzato un menu aggiuntivo che informa che per condividere il contenuto, dovrà avviare una riunione Teams riunione.

Se gli utenti erano in una chiamata, il menu avvisa anche che la chiamata corrente tra Teams e Skype for Business verrà terminata quando vengono inseriti in una riunione Teams riunione. Se sceglie, può avvisare l'utente Skype for Business prima di accettare.

![Schermata del messaggio Teams condividere una riunione con un Skype for Business utente.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Al momento dell'accettazione, vengono inseriti nella riunione Teams riunione; devono iniziare a condividere dal vassoio di condivisione della riunione.

Nel frattempo, l Skype for Business riceve un messaggio di chat in arrivo con il collegamento alla riunione e viene guidato per partecipare.

Questa escalation a una Teams riunione è disponibile sia per l'interoperabilità in tenant che per le chat e le chat federate tra tenant. È attivata per impostazione predefinita e non è necessario eseguire il provisioning dell'amministratore. Tuttavia, è disattivata per l'utente se l'amministratore imposta ``-AllowPrivateMeetNow`` su ``CsTeamsMeetingPolicy`` ``$false`` .

Dopo aver esaminato questo articolo, vedere Scegliere il percorso di [aggiornamento,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Indicazioni sulla migrazione e l'interoperabilità, [](./migration-interop-guidance-for-teams-with-skype.md) [Coesistenza](coexistence-chat-calls-presence.md)con Skype for Business e Impostazione delle impostazioni di [coesistenza](./setting-your-coexistence-and-upgrade-settings.md) e aggiornamento per i dettagli sull'implementazione. È anche consigliabile il video seguente: [Video: Gestire la coesistenza e l'interoperabilità tra SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Dettagli tecnici sulla Teams e Skype for Business coesistenza

Le sezioni seguenti riepilogano il comportamento che può verificarsi quando si eseguono client Teams e Skype for Business nella stessa organizzazione, indipendentemente dalla modalità e dal metodo di aggiornamento usato:

- [Riunioni](#meetings)
- [Interoperabilità](#interoperability)
- [Thread di conversazione nativi e di interoperabilità](#interop-versus-native-conversation-threads)
- [Icone di presenza](#presence)
- [Federazione](#federation)
- [Contatti](#contacts)

### <a name="meetings"></a>Riunioni

Indipendentemente dalla modalità, gli utenti possono sempre partecipare a qualsiasi tipo di riunione a cui sono invitati, che si Skype for Business o Teams.  Tuttavia, gli utenti devono partecipare alla riunione con un client corrispondente corrispondente al tipo di riunione:

- Se la riunione è una riunione Teams, tutti i partecipanti (che si tratta di utenti TeamsOnly, Islands o Skype for Business) usano il client Teams per partecipare alla riunione. Se Teams non è installato, l'utente verrà indirizzato al Web dopo aver tentato di partecipare a una riunione.

- Se la riunione è una riunione Skype for Business, tutti i partecipanti (che si tratta di utenti TeamsOnly, Islands o Skype for Business) usano il client Skype for Business per partecipare alla riunione. Se il client Skype for Business non è installato, l'utente verrà indirizzato al Web per partecipare tramite l'app Riunione Skype.

Quando si organizzano le riunioni, il tipo di riunione che viene pianificato si basa sulla modalità dell'organizzatore, come illustrato nella tabella seguente:

| Modalità di organizzazione    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Tutte le riunioni pianificate in Teams. Skype for Business componente aggiuntivo non è disponibile in Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Tutte le riunioni pianificate in Skype for Business. Teams componente aggiuntivo non è disponibile in Outlook. | 
| Isole | Per impostazione predefinita, le riunioni possono essere pianificate in Skype for Business o Teams. Entrambi i componenti aggiuntivi sono disponibili in Outlook. È tuttavia possibile richiedere agli utenti delle isole di pianificare sempre le riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interoperabilità

Come descritto in precedenza in Interoperabilità di Teams e [Skype for Business](#interoperability-of-teams-and-skype-for-business), Teams supporta l'interoperabilità con Skype for Business in determinati scenari. Per comunicazione di interoperabilità si intende una chat o una chiamata tra Skype for Business utente e un Teams utente.  La comunicazione di interoperabilità è possibile solo tra due utenti. la chat o le chiamate a più parti o l'aggiunta di altri utenti non è supportato.

Una chat o una chiamata di interoperabilità tra due utenti viene creata quando sono vere le condizioni seguenti:

- Un utente usa Teams e l'altro usa Skype for Business.

- La modalità del destinatario della comunicazione iniziale non è Isole (altrimenti la comunicazione si atterra nello stesso client) se entrambi gli utenti si trova nella stessa organizzazione. Negli scenari federati, l'utente mittente usa Teams e il destinatario non è in modalità TeamsOnly. 

- L Teams utente non ha anche un account Skype for Business locale.

All'interno della comunicazione di interoperabilità, la chat è solo testo normale. Inoltre, la condivisione di file e la condivisione dello schermo non sono possibili *nella chat di interoperabilità stessa.* Tuttavia, gli utenti di una conversazione di interoperabilità possono ottenere facilmente la condivisione di file e/o schermo creando una riunione su richiesta, dall'interno della chat di interoperabilità, come descritto di seguito:

- Se l'utente Teams prova a condividere lo schermo, viene creata automaticamente una riunione Teams su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente Skype for Business su richiesta. Dopo aver fatto clic sul collegamento, Skype for Business'utente aprirà Teams e si unirà alla riunione. Entrambi gli utenti sono ora in una riunione Teams e possono condividerli in base alle esigenze.

- Se l'utente di Skype for Business usa un client dal 2018 o versione successiva e prova a condividere qualsiasi contenuto, viene creata automaticamente una riunione Skype for Business su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente di Teams. Dopo aver fatto clic sul collegamento, Teams'utente tenterà di partecipare alla riunione Skype for Business riunione. Se l Teams utente ha installato il client di Skype for Business, verrà aperto e all'utente verrà chiesto di eseguire l'accesso (se non è già stato eseguito l'accesso).  Se l Teams non ha installato il client Skype for Business, all'utente verrà richiesto di usare la versione Web. Una volta che entrambi gli utenti hanno eseguito l'accesso, Skype for Business una riunione e possono condividerli in base alle esigenze.

### <a name="interop-versus-native-conversation-threads"></a>Thread di conversazione nativi e di interoperabilità

Poiché le comunicazioni di interoperabilità non supportano tutte le funzionalità della conversazione Teams nativa, il client di Teams mantiene thread di conversazione separati per le comunicazioni Teams-Teams e Teams-Skype for Business. Il rendering di queste conversazioni viene eseguito in modo diverso nell'interfaccia utente: i thread di interoperabilità possono essere differenziati da un normale thread Teams nativo:

- Mancanza di controlli per il formato RTF, la condivisione di file/schermo, l'impossibilità di aggiungere utenti.
- Modifica dell'icona dell'utente di destinazione, che mostra una "S" per Skype for Business.

Queste differenze sono mostrate negli screenshot seguenti:

Una conversazione Teams-to-Teams utente con User G3 Test

![Diagramma che mostra una conversazione Teams nativa tra Teams conversazione.](media/teams-upgrade-native-thread.png)

Conversazione di interoperabilità con lo stesso test G3 utente

![Diagramma che mostra una conversazione Teams tra Teams conversazione.](media/teams-upgrade-interop-thread.png)

Una volta creato un thread di conversazione, il tipo non cambia mai. Una volta creato, un thread di interoperabilità in Teams instraderà sempre al client di Skype for Business dell'utente di destinazione. Un thread nativo verrà sempre indirizzato al client Teams dell'utente di destinazione.  Se la modalità di un utente del destinatario cambia, i thread Teams esistenti per quell'utente non funzioneranno più e nella chat verrà visualizzata una nota con un collegamento per avviare una nuova conversazione nativa, come illustrato nello screenshot seguente.

![Diagramma che mostra una chat con un utente Skype for Business aggiornato.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Icone di presenza

La presenza per un determinato utente si basa sull'attività dell'utente nel servizio tramite il client. La presenza viene quindi pubblicata per consentire ad altri utenti di vedere.  Skype for Business e Teams sono servizi separati con client separati, quindi ogni servizio ha il proprio stato di presenza per un utente.   È inoltre disponibile la sincronizzazione tra i servizi di presenza in Teams e in Skype for Business Online.  In questo modo un servizio potrebbe pubblicare la presenza dell'utente dall'altro servizio, se necessario. 

Il comportamento di pubblicazione della presenza si basa sulla modalità dell'utente. Esistono tre casi di base:

- Se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono Teams presenza per quell'utente, indipendentemente dal client che usa.

- Se un utente è in una delle modalità Skype for Business, tutti gli altri utenti visualizzano Skype for Business presenza per tale utente, indipendentemente dal client che usa.

- Se un utente è in modalità Isole, la presenza pubblicata in Skype for Business e Teams è indipendente, quindi la presenza visualizzata agli utenti all'interno della stessa organizzazione dipenderà dal client dell'altro utente. Gli utenti delle organizzazioni federate potranno vedere la presenza dell'utente in base all'attività Skype for Business, perché il traffico federato verso una modalità isole viene Skype for Business.

Si supponga ad esempio che l'utente A sia in modalità Isole. Se l'utente A è attivo in Teams ma non è connesso a Skype for Business, gli altri utenti vedono l'utente A come attivo dal client Teams, ma nel client Skype for Business vedono l'utente A come offline. Si tratta di un problema di progettazione, perché l'utente A non può essere raggiunto se non esegue il client. 


### <a name="federation"></a>Federazione

La federazione da Teams a un altro utente che usa Skype for Business richiede che l Teams'utente sia ospitata online in Skype for Business. TeamsUpgradePolicy regola il routing per le chiamate e le chat federate in arrivo. Il comportamento di routing federato è uguale a quello degli scenari con lo stesso tenant, ad eccezione della modalità Isole. Quando i destinatari sono in modalità Isole:

- Chat e chiamate avviate da Teams in Skype for Business se il destinatario si trova in un tenant federato.
- Chat e chiamate avviate da Teams in Teams se il destinatario si trova nello stesso tenant.
- Le chat e le chiamate avviate da Skype for Business sempre Skype for Business.

Una chat federata può essere un thread nativo o un thread di interoperabilità. Vedere [Interoperabilità e thread di conversazione nativi.](#interop-versus-native-conversation-threads)

- Se il destinatario e il mittente sono entrambi in modalità di aggiornamento TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere Esperienza di chat nativa per [utenti esterni (federati) in Teams.](native-chat-for-external-users.md) 

- Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con i messaggi di solo testo. L'interfaccia utente espone le chat federate in modo simile ai thread di interoperabilità dello stesso tenant, ad eccezione della nota che indica che l'utente è esterno.

Per altre informazioni, vedere [Gestire l'accesso](manage-external-access.md) esterno in Microsoft Teams e l'esperienza di chat nativa per utenti esterni [(federati) in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatti

Teams e Skype for Business elenchi di contatti separati. Questo significa che le aggiunte, la rimozione e le modifiche apportate ai contatti in un sistema non vengono sincronizzate con l'altro sistema. Tuttavia, i contatti di Skype for Business vengono copiati automaticamente in Teams quando si verifica uno di due eventi specifici: 

- Per qualsiasi Skype for Business online, la prima volta che accede Teams, i contatti di Skype for Business verranno copiati in Teams.  Questo comportamento non è disponibile per gli utenti con un account locale in Skype for Business Server.  

- Dopo l'aggiornamento di un utente a TeamsOnly (tramite l'assegnazione di TeamsUpgradePolicy o tramite Move-CsUser -MoveToTeams), la volta successiva che un utente accede a Teams, i contatti esistenti in Skype for Business verranno uniti ai contatti esistenti già in Teams. Questo comportamento si verifica se l'utente è stato spostato in TeamsOnly da locale o online. 

In entrambi i casi, il trasferimento dei contatti da Skype for Business a Teams è asincrono, quindi potrebbe essere necessario qualche minuto prima che i contatti vengano visualizzati in Teams. I due eventi precedenti sono l'attivazione della copia.  

### <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
