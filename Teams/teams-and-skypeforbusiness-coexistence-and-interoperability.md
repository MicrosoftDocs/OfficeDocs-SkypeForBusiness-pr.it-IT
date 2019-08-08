---
title: Microsoft Teams | Aggiornamento, modalità isole, criteri di interoperabilità, solo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Informazioni dettagliate sulle opzioni di coesistenza di Skype for business e Microsoft teams e sull'interoperabilità tra Skype for business e teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ba7ae0613bbab87f09a6c290d191d711d583c24
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237529"
---
![Aggiornare il diagramma di viaggio, enfatizzando la fase di definizione del progetto] (media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di definizione del progetto")

Questo articolo fa parte della fase di definizione del progetto del viaggio di aggiornamento, un'attività completa dopo aver creato una coalizione di sponsorizzazione e un team di progetto e definito l'ambito, gli obiettivi e la visione per il progetto. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Informazioni sulla coesistenza e l'interoperabilità di Microsoft teams e Skype for business

Se l'organizzazione usa Skype for business oggi e si inizia a usare teams insieme a Skype for business, oppure si inizia a eseguire l'aggiornamento a teams, è importante capire come coesistono le due applicazioni, quando e come interagiscono e come gestire migrazione degli utenti fino al loro eventuale aggiornamento da Skype for business a teams.

> [!Tip]
> Per informazioni sulla coesistenza e l'interoperabilità [,](https://aka.ms/teams-upgrade-coexistence-interop)vedere la sessione seguente.
>
> Inoltre, puoi unirti a noi per laboratori dinamici e interattivi in cui condivideremo le indicazioni, le procedure consigliate e le risorse progettate per avviare la pianificazione e l'implementazione dell'aggiornamento.
>
> Prima di tutto, partecipa al piano della sessione di [aggiornamento](https://aka.ms/SkypeToTeamsPlanning) per iniziare.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coesistenza di teams e Skype for business

Oltre alle funzionalità di collaborazione, teams offre funzionalità di chat, chiamate e riunioni. A seconda di come si sceglie di distribuire Team, queste funzionalità potrebbero sovrapporsi alle funzionalità fornite da Skype for business per un utente specifico. La modalità predefinita consiste nell'eseguire teams insieme a Skype for business con le funzionalità sovrapposte; a un utente può tuttavia essere assegnata una delle diverse modalità di coesistenza progettate per garantire che queste funzionalità non vengano sovrapposte per tale utente (in questo caso è disponibile l'interoperabilità tra team e Skype for business).

È consigliabile esaminare le modalità di coesistenza descritte di seguito per determinare il percorso appropriato per l'organizzazione.

> [!Important]
> L'introduzione di nuove tecnologie o l'adozione di modifiche nell'ambiente esistente e familiare di Skype for business, offrendo così nuovi vantaggi per le aziende, possono essere di disturbo per gli utenti. Richiedere tempo per valutare la disponibilità degli utenti e implementare un piano di comunicazione e formazione prima di implementare le modifiche descritte in questo articolo. Inoltre, consigliamo vivamente di pilotare il piano con un gruppo di utenti selezionato prima di implementarlo nell'organizzazione.

### <a name="islands-mode"></a>Modalità Isole

Per impostazione predefinita, gli utenti possono eseguire teams insieme a Skype for business come due soluzioni separate che garantiscono funzionalità simili e sovrapposte, ad esempio presenza, chat, chiamate e riunioni. Gli utenti di teams possono anche sfruttare le nuove funzionalità di collaborazione come team e canali, accedere ai file in Office 365 e applicazioni.

In questa modalità di coesistenza, denominata **Islands**, ognuna delle applicazioni client funziona come un'isola separata. I colloqui di Skype for business con Skype for business e i colloqui di teams con teams. Gli utenti eseguono entrambi i client in qualsiasi momento e possono comunicare in modo nativo nel client da cui è stata avviata la comunicazione. Di conseguenza, non c'è bisogno di interoperabilità in modalità **isole** .

Per evitare un'esperienza di Skype for business confusa o regressione, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione di Office e molte altre integrazioni continuano a essere gestite da Skype for business.

> [!Important]
> In modalità **isole** tutti i messaggi provenienti da utenti federati (persone esterne all'organizzazione) vengono recapitati a Skype for business. Dopo il passaggio alla modalità **solo teams** , tutti i messaggi esterni all'organizzazione vengono recapitati a teams.

> [!Tip]
> Il percorso consigliato per i clienti di Skype for business online è iniziare con la modalità **isole** predefinite, guidare la saturazione delle adozioni teams nell'organizzazione e quindi procedere rapidamente alla modalità **solo teams** . I clienti locali e ibridi possono trarre vantaggio dalla distribuzione della modalità di **collaborazione di Skype for business con teams** come punto di partenza invece che da Islands e da lì per passare a **Skype for business con la modalità di collaborazione e riunione** in teams, Se necessario, e alla modalità **solo teams** quando l'organizzazione è pronta per l'adozione di team.

### <a name="skype-for-business-only"></a>Solo Skype for business

In questa modalità di coesistenza gli utenti rimangono in Skype for business, non in team, per le funzionalità di chat, riunioni e chiamate e non usano team per team e canali. Questa modalità è oggi disponibile; Tuttavia, nell'implementazione corrente i team e i canali non vengono disattivati automaticamente per l'utente. Questa operazione può essere eseguita usando i criteri delle autorizzazioni dell'app per nascondere team e canali.

### <a name="teams-only"></a>Solo Teams

Un utente **solo teams** (detto anche utente *aggiornato* ) ha accesso a tutte le funzionalità in teams. Possono mantenere il client Skype for business per partecipare a riunioni su Skype for business organizzati da utenti non aggiornati o da parti esterne. Un utente aggiornato può continuare a comunicare con altri utenti dell'organizzazione che usano ancora Skype for business usando le funzionalità di interoperabilità tra teams e Skype for business (purché gli utenti di Skype for business non siano in modalità isole) ; Tuttavia, un utente aggiornato non può avviare una chat, una chiamata o una riunione Skype for business.

Non appena l'organizzazione è pronta per consentire ad alcuni o a tutti gli utenti di usare teams come unico strumento di comunicazione e collaborazione, è possibile aggiornare gli utenti alla modalità **solo teams** . Se si esegue l'aggiornamento dalla modalità isole, è consigliabile saturare prima di tutto l'adozione di team in tutta l'organizzazione prima di iniziare il processo di aggiornamento. In questo modo si evitano scenari di comunicazione interrotti a causa della modalità Islands che non offre interoperabilità.

Per altre considerazioni su come passare alla modalità solo teams, vedere [considerazioni sulla modalità solo teams](teams-only-mode-considerations.md).

Screenshot ![del messaggio di conferma del team] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Client Skype for business eseguito in una modalità speciale dopo che l'utente è stato aggiornato come utente di solo teams")

### <a name="skype-for-business-with-teams-collaboration"></a>Collaborazione tra Skype for business e teams

Usa questa modalità per introdurre team nell'ambiente mentre continui a sfruttare gli investimenti esistenti in Skype for business. In questa modalità si lascia invariati Skype for business per le funzionalità di chat, chiamate e riunioni e si aggiungono le funzionalità di collaborazione dei team, ovvero team e canali, l'accesso ai file in Office 365 e le applicazioni. Le funzionalità di comunicazione di teams: chat privata, chiamate e riunioni di programmazione sono disattivate per impostazione predefinita in questa modalità. Le organizzazioni con un punto di partenza di Skype for Business Server in locale o ibrido dovrebbero considerare questa modalità come alternativa alla modalità isole, se vogliono dare agli utenti l'interoperabilità e la prevedibilità per le comunicazioni.

### <a name="skype-for-business-with-teams-collaboration-and-meetings"></a>Skype for business con la collaborazione e le riunioni di Teams

Usa questa modalità di coesistenza per accelerare la disponibilità delle funzionalità di riunione dei team nella tua organizzazione, oltre alle sue funzionalità di collaborazione, consentendo agli utenti di sfruttare l'esperienza di riunioni superiori di teams-grande qualità, funzionalità innovative come la trascrizione e la traduzione o la sfocatura dello sfondo e un'esperienza utente superiore in tutte le piattaforme, inclusi i dispositivi mobili e i browser.

Insieme all'uso di team per le conversazioni basate su team e canali in questa modalità, gli utenti useranno team per pianificare e condurre le riunioni. Chat e chiamate private restano in Skype for business. I team e Skype for business traggono vantaggio da un'ampia gamma di funzionalità di "migliore collaborazione", come la riconciliazione della presenza, il supporto automatico di blocco/sospensione e la gestione dei dispositivi HID in entrambe le applicazioni. 

Questa modalità di coesistenza è particolarmente utile per gli utenti nelle distribuzioni locali di Skype for business con Enterprise Voice, che probabilmente richiederà del tempo per l'aggiornamento a teams e vuole trarre vantaggio dalle riunioni di Team superiori il prima possibile.

> [!Note]
> Una volta distribuite in modalità di coesistenza specifiche, teams e Skype for business possono [interagire](#interoperability-of-teams-and-skype-for-business), consentendo agli utenti di chattare e chiamarsi a vicenda e garantire che le comunicazioni rimangano fluide nell'organizzazione durante il viaggio di aggiornamento in teams. La modalità di coesistenza regola l'interoperabilità. La modalità di coesistenza del destinatario determina se l'interoperabilità sarà disponibile. Ad esempio, se il destinatario si trova in una modalità in cui la chat è disponibile solo in un solo client (ad affermare Team), l'interoperabilità della chat sarà in genere disponibile nel caso in cui l'iniziatore usi l'altro client (in questo caso Skype for business) per avviare la chat. Se invece il destinatario si trova in una modalità in cui la chat è disponibile in entrambi i client (modalità isole), l'interoperabilità non sarà disponibile per la chat. Il messaggio verrà ricevuto dal destinatario nello stesso client in cui l'initiator ha avviato la chat. Di conseguenza, la comunicazione corretta in modalità isole richiede la saturazione dell'adozione di Teams; ovvero tutti gli utenti che usano e controllano attivamente entrambi i client.

> [!TIP]
> Per identificare la modalità di aggiornamento consigliata in base alle funzionalità che si vogliono abilitare in teams mentre Skype for business è ancora in uso, sfruttare la [procedura guidata di aggiornamento di Skype to teams](https://aka.ms/SkypeToTeamsWizard).

Per altre informazioni sulle modalità di coesistenza, sui prerequisiti e sulla gestione, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://aka.ms/SkypeToTeams-Interop) e per [impostare le impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto decisionale|<ul><li>Quali modalità di coesistenza si adattano meglio alle esigenze dell'organizzazione e degli utenti?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Passaggio successivo|<ul><li>Scegliere l'approccio migliore per il viaggio di aggiornamento.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilità di teams e Skype for business

L'interoperabilità è la possibilità per gli utenti di team e Skype for business nella stessa organizzazione di comunicare tra team e Skype for business.

### <a name="native-interop-and-interop-escalation"></a>Interoperabilità nativa e escalation di interoperabilità

Esistono due tipi di esperienze di interoperabilità, ad escalation nativo e di interoperabilità.

- Un'esperienza di interoperabilità _nativa_ si verifica nel client che l'utente sta attualmente usando. Un utente sarà nel client Skype for business, l'altro in teams. Un'esperienza di interoperabilità nativa non li porterà in un altro client per comunicare, ma gli utenti potranno eseguire la conversazione nel client che sta usando. Le esperienze di interoperabilità native sono chat e chiamate uno-a-uno.
- Un' __ esperienza di escalation di interoperabilità significa che, nell'aiutare gli utenti a eseguire un'azione avanzata, ad esempio la condivisione del desktop, il client facilita la creazione di una riunione a cui gli utenti possono partecipare per continuare l'esperienza di tale riunione. La riunione viene creata sulla piattaforma dell'iniziatore dell'azione. L'utente o gli utenti che non fanno parte della piattaforma ricevono un collegamento a una riunione. Mentre fanno clic su questo collegamento, vengono uniti alla riunione in un client compatibile (browser, app Web o client completo, a seconda della configurazione). L'escalation di interoperabilità da Skype for business richiede un client recente. L'escalation di interoperabilità da teams sarà disponibile a breve.

### <a name="native-interop-experiences"></a>Esperienze di interoperabilità Native

A seconda delle modalità di coesistenza assegnate agli utenti, come descritto in precedenza, sono disponibili le seguenti esperienze di interoperabilità Native:

- Gli utenti di Skype for business possono chattare uno-a-uno con gli utenti di teams e viceversa. Una chat di interoperabilità deve passare attraverso un gateway di interoperabilità che fa parte dei servizi cloud di Teams (e quindi esiste solo online). Le chat di interoperabilità sono di testo normale: testo RTF ed emoticon non sono supportate. Gli utenti in teams e in Skype for Business ricevono una notifica che la conversazione è una conversazione di interoperabilità.

    Screenshot ![dell'esperienza di interoperabilità chat] di Teams (media/Interop_chat_experience_from_Teams.png "Esperienza di interoperabilità chat da teams")

- Gli utenti di Skype for business possono effettuare chiamate vocali e video uno-a-uno agli utenti di teams e viceversa.

    Screenshot ![dell'esperienza di interoperabilità delle chiamate] di Teams (media/Interop_calling_experience_from_Teams.png "Esperienza di chiamata di interoperabilità da teams")

> [!Important]
> Le esperienze di interoperabilità con una distribuzione locale di Skype for business richiedono che l'ambiente locale sia in modalità ibrida con Office 365 Skype for business. Per informazioni dettagliate, vedi indicazioni per la [migrazione e](https://aka.ms/SkypeToTeams-Interop)l'interoperabilità.

Queste esperienze di interoperabilità sono disponibili per e tra gli utenti che hanno una delle seguenti modalità di coesistenza assegnate: **Skype for business con collaborazione teams**, **Skype for business con la collaborazione e le riunioni**di teams, **Skype for **Solo per le aziende o solo per i **Team**. Non c'è interoperabilità per gli utenti in modalità isole.

### <a name="native-interop-experience-limitations"></a>Limitazioni dell'esperienza di interoperabilità Native

Alcune funzionalità non sono disponibili per l'esperienza di interoperabilità e la chiamata di interoperabilità tra team e Skype for business:

- Markdown, Rich Text e il set completo di emoticon non sono supportati da teams o Skype for business. Altre caratteristiche native della casella di composizione nelle chat di teams non sono supportate.
- La condivisione dello schermo (condivisione di desktop o app) tra team e Skype for business non è supportata.
- Le chat di gruppo (conversazioni a più parti) in teams possono includere solo i partecipanti che usano team.
- Le conversazioni di messaggistica istantanea a più parti (chat di gruppo) in Skype for business possono includere solo i partecipanti che usano Skype for business.
- L'escalation di una chiamata vocale o video peer-to-peer in corso a una chiamata a più parti che coinvolge sia i team che gli utenti di Skype for business non è supportata.
- Non sono supportati i trasferimenti di file per le chat di due parti o l'allegato di file in chat di gruppo, da team a Skype for business e viceversa.
- Non c'è interoperabilità con la chat persistente di Skype for business.

Per tutte queste limitazioni (ad eccezione della chat persistente), una possibile soluzione alternativa consiste nel fatto che un utente avvii una riunione e inviti l'altro utente a partecipare. Questa soluzione alternativa è la base per l'escalation di interoperabilità.

Dopo aver esaminato questo articolo, vedere [scegliere il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), le [linee guida per la migrazione e](https://aka.ms/SkypeToTeams-Interop)l'interoperabilità, la coesistenza [con Skype for business](coexistence-chat-calls-presence.md)e impostare le impostazioni di coesistenza [e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) per l'implementazione Dettagli.

## <a name="related-links"></a>Collegamenti correlati

[Video: gestire la coesistenza e l'interoperabilità tra SfB e teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
