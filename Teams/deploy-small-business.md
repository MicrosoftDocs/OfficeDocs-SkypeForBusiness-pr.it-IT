---
title: Configurare Microsoft Teams nella piccole imprese
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configurare Teams nelle piccola imprese per consentire agli utenti di collaborare tramite chat e condivisione di file, configurare e partecipare a riunioni di piccole e grandi dimensioni e parlare tramite video e chiamate vocali.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fd7865823cffdfd2f2b2932a78744786c59cfd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101232"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurare Microsoft Teams nella piccole imprese

È possibile personalizzare Teams in diversi modi. Le sezioni seguenti illustrano come configurare ogni carico di lavoro di Teams: **chat, team e canali**, **riunioni e conferenze** e **cloud voice**. L'ordine in cui si configura ciascun carico di lavoro dipende dall’utente. Anche se è consigliabile configurare prima il carico di lavoro di chat, team e canali, è possibile iniziare con le riunioni e le conferenze o anche con il cloud voice. La scelta sta all'utente.

> [!NOTE]
> Se tutto ciò è già stato fatto, è consigliabile iniziare la distribuzione di Teams attraverso una distribuzione pilota. Una distribuzione pilota consentirà all’utente e agli early adopter di acquisire familiarità con Teams e le sue funzionalità prima della pianificazione e della distribuzione finale. Per altre informazioni su come avviare la distribuzione pilota, vedere [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md).

Prima di implementare totalmente Teams, assicurarsi che l'organizzazione sia pronta esaminando gli elementi in [Assicurarsi di essere pronti](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Passare alla sezione a cui si è interessati:

- [Carichi di lavoro](#workloads)
  - [Chat, team e canali](#chat-teams-and-channels)
  - [Riunioni e conferenze](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [Distribuire i client](#deploy-clients)
- [Formazione](#training)

## <a name="workloads"></a>Carichi di lavoro
### <a name="chat-teams-and-channels"></a>Chat, team e canali

Chat, team e canali sono la base di ogni team. La **chat** consente agli utenti di parlare tra di loro, condividere file e di collegarsi in modo privato con altri. **Teams**, che può essere visibile a tutti gli utenti dell'organizzazione o solo a quelli del team, consente di collaborare con le persone giuste su qualsiasi attività o in qualsiasi occasione, che si tratti di un progetto a lungo termine o di una festa di compleanno. I **canali** nei team consentono di suddividere argomenti, progetti, reparti e altro per il team. Per informazioni dettagliate su chat, team e canali, vedere la [Panoramica su team e canali](teams-channels-overview.md).

> [!TIP]
> Informazioni su come gestire i ruoli del team, l'accesso e i criteri di messaggistica completando il modulo [Gestire Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) in Microsoft Learn.

Quando si pianifica l'implementazione di team e canali, è necessario decidere chi può crearli, se gli utenti guest esterni all'organizzazione possono accedervi e così via. L'articolo [Chat, team, canali e app di Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) contiene molte informazioni sulla pianificazione di chat, team e canali. Tuttavia, ci sono alcuni aspetti chiave in questo articolo su cui è consigliabile soffermarsi. Selezionare una decisione per ottenere altre informazioni.

| Decisione | Descrizione |
|--|--|
| [Chi devono essere gli amministratori di Teams?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | Il ruolo di amministratore può essere usato per concedere autorizzazioni specifiche alle persone che devono amministrare Teams. Questi ruoli aggiuntivi potrebbero non essere necessari per le piccole imprese, poiché la stessa persona potrebbe essere responsabile di tutti gli aspetti di Teams. È sempre possibile aggiungere o rimuovere gli amministratori in un secondo momento.<br><br>[Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md). |
| [Chi devono essere i proprietari e i membri del team?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | I proprietari del team controllano chi può accedere a un team e ai relativi canali. Possono decidere se un team o un canale è pubblico (per l'organizzazione) o privato e possono impostare criteri come quelli per la moderazione di un canale. I membri possono accedere al team e ai relativi canali, a meno che non si tratti di un canale privato di cui non sono membri, e possono essere designati come moderatori.<br><br>[Assegnare proprietari e membri del team in Microsoft Teams](assign-roles-permissions.md) |
| [L'accesso guest deve essere abilitato?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |L'accesso guest consente agli utenti dell'organizzazione di invitare persone esterne all'organizzazione ad accedere ai team e ai canali dell'organizzazione. L'accesso guest viene spesso usato per collaborare con persone esterne all'organizzazione che non hanno una relazione formale con la propria. Ad esempio, è possibile invitare un progettista a lavorare temporaneamente su un progetto.<br>L'accesso guest è diverso dall'accesso esterno. L'accesso guest invita persone specifiche ad accedere per interagire con le persone dell'organizzazione.  <br>L'accesso guest è **disattivato** per impostazione predefinita. <br><br>[Attivare o disattivare l'accesso guest in Microsoft Teams.](set-up-guests.md)  |

Non sono necessarie ulteriori operazioni per consentire agli utenti di iniziare a usare chat, team e canali. Sono tuttavia disponibili numerose opzioni per controllare l'uso di Teams. È possibile apportare modifiche subito o attendere finché non sarà possibile controllare come gli utenti usano Teams. Per altre informazioni, vedere i seguenti articoli:

- [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md)
- [Impostazioni di Teams](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Riunioni e conferenze

Le riunioni e le conferenze consentono alle persone dell'organizzazione di collegarsi tra di loro e con persone esterne all'organizzazione. Chiunque abbia un client Teams o Skype for Business può partecipare alle **riunioni** a cui è stato invitato. Usando il microfono, la fotocamera e lo schermo del proprio dispositivo, gli utenti possono partecipare alla conversazione senza bisogno di un telefono. I partecipanti possono chattare, effettuare chiamate vocali e condividere video e app con altri partecipanti usando un PC o un dispositivo mobile.

L'**audioconferenza** offre agli utenti la possibilità di partecipare alle riunioni usando un normale telefono, componendo il numero di telefono della conferenza e immettendo l'ID della riunione. Le audioconferenze sono utili quando un partecipante non dispone di una buona connessione Internet, se la riunione è solo vocale o in altre circostanze che impediscono di partecipare tramite il client Teams.

> [!TIP]
> Per acquisire maggiore familiarità con riunioni ed eventi, completare il modulo [Gestire riunioni, conferenze ed eventi con Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) in Microsoft Learn.

Le riunioni sono abilitate per impostazione predefinita in Teams. Tuttavia è possibile controllare l'esperienza degli organizzatori e dei partecipanti. È possibile impostare criteri per personalizzare le azioni consentite e non consentite per gli utenti prima e durante le riunioni. Per altre informazioni, vedere i seguenti articoli:

- [Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurare audioconferenze per piccole e medie imprese](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) è una soluzione ideale per le aziende con meno di 300 utenti, in grado di offrire tutte le funzionalità di un sistema di telefonia per ufficio. Business Voice include la segreteria telefonica, ID chiamante, menu del sistema telefonico, numeri gratuiti e altro ancora, senza la necessità di gestire un complesso e costoso sistema telefonico locale.

Basato sul Sistema telefonico di Microsoft 365, Business Voice semplifica il tutto raggruppando funzionalità e componenti aggiuntivi del Sistema telefonico e fornendo una procedura guidata, facile da seguire, per configurare il sistema telefonico. Se l'organizzazione si trova in un [paese o area geografica che supporta Business Voice](business-voice/country-region-availability.md), è possibile trasferire i numeri di telefono in Microsoft 365 e lasciare a Microsoft la gestione del sistema telefonico.

Con Microsoft 365 come sistema di telefonia, è possibile trasformare qualsiasi dispositivo in un telefono installando il client Teams. Oppure, se si preferisce un telefono tradizionale da tavolo o un telefono da conferenza, sono disponibili molti dispositivi certificati Teams tra cui scegliere. In entrambi i casi, le chiamate vengono sempre indirizzate all’utente e il numero sarà sempre quello del telefono dell'ufficio.

Per maggiori informazioni sul VoIP aziendale, vedere [Cosa è necessario acquistare per usare Microsoft 365 Business Voice?](business-voice/what-to-buy.md).

## <a name="deploy-clients"></a>Distribuire i client

Quando gli utenti iniziano a usare Teams possono installare il client Teams sul proprio PC Windows, Mac o Linux o sul proprio dispositivo Android o iOS. Gli utenti possono scaricare il client Teams direttamente da <https://teams.microsoft.com/downloads>.

Assicurarsi che tutti gli utenti che usano Teams abbiano una licenza di Teams. Per altre informazioni sull'assegnazione di una licenza di Teams, vedere [Gestire l'accesso degli utenti a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> È possibile ottenere suggerimenti su come pianificare la distribuzione client di Teams completando il modulo [Distribuire i client di Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) in Microsoft Learn.

Se l'organizzazione usa Microsoft Endpoint Configuration Manager, i criteri di gruppo o un meccanismo di distribuzione di terze parti per distribuire i software nei computer degli utenti, vedere [Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager](msi-deployment.md).

Per informazioni dettagliate sulla distribuzione dei client Teams, vedere [Ottenere i client per Microsoft Teams](get-clients.md).

## <a name="training"></a>Formazione

Per informazioni su come formare gli utenti all’uso di Teams, vedere [Formazione su Microsoft Teams](training-microsoft-teams-landing-page.md).