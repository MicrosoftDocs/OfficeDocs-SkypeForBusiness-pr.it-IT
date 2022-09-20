---
title: Configurare Microsoft Teams nella piccole imprese
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configurare Teams nelle piccola imprese per consentire agli utenti di collaborare tramite chat e condivisione di file, configurare e partecipare a riunioni di piccole e grandi dimensioni e parlare tramite video e chiamate vocali.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 32b55c026daad08aab22f1621190e2768e0b26e5
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808667"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurare Microsoft Teams nella piccole imprese

È possibile personalizzare Teams in diversi modi. Le sezioni seguenti mostrano come configurare ogni carico di lavoro Teams: **chat, team e canali**; **riunioni e conferenze**; e **soluzioni vocali**. L'ordine in cui si configura ciascun carico di lavoro dipende dall’utente. Anche se è consigliabile configurare prima il carico di lavoro di chat, team e canali, è possibile iniziare con le riunioni e le conferenze o anche con il cloud voice. La scelta sta all'utente.

> [!NOTE]
> Se non si è già stato fatto, è consigliabile iniziare la distribuzione di Teams attraverso una distribuzione pilota. La distribuzione pilota consentirà all’utente e agli early adopter di acquisire familiarità con Teams e le relative funzionalità prima della pianificazione e della distribuzione finale. Per altre informazioni su come avviare la distribuzione pilota, vedere [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md).

Prima di implementare Teams su larga scala, assicurarsi che l'organizzazione sia pronta esaminando gli elementi in [Assicurarsi di essere pronti](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Passare alla sezione a cui si è interessati:

- [Carichi di lavoro](#workloads)
  - [Chat, team e canali](#chat-teams-and-channels)
  - [Riunioni e conferenze](#meetings-and-conferencing)
  - [Servizi telefonici con piano per chiamate](#teams-phone-with-calling-plan)
- [Distribuire i client](#deploy-clients)
- [Formazione](#training)

## <a name="workloads"></a>Carichi di lavoro
### <a name="chat-teams-and-channels"></a>Chat, team e canali

Chat, team e canali sono la base di ogni team. La **chat** consente agli utenti di parlare tra di loro, condividere file e di collegarsi in modo privato con altri. **Teams**, che può essere visibile a tutti gli utenti dell'organizzazione o solo a quelli del team, consente di collaborare con le persone giuste su qualsiasi attività o in qualsiasi occasione, che si tratti di un progetto a lungo termine o di una festa di compleanno. I **canali** nei team consentono di suddividere argomenti, progetti, reparti e altro per il team. Per informazioni dettagliate su chat, team e canali, vedere la [Panoramica su team e canali](teams-channels-overview.md).

> [!TIP]
> Per informazioni su come gestire i ruoli del team, l'accesso e i criteri di messaggistica, completare il modulo [Gestire Microsoft Teams](/training/modules/m365-teams-collab-manage-teams/) in Microsoft Learn.

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
> Per acquisire maggiore familiarità con riunioni ed eventi, completare il modulo [Gestire riunioni, conferenze ed eventi con Microsoft Teams](/training/modules/m365-teams-collab-manage-meetings) in Microsoft Learn.

Le riunioni sono abilitate per impostazione predefinita in Teams. Tuttavia è possibile controllare l'esperienza degli organizzatori e dei partecipanti. È possibile impostare criteri per personalizzare le azioni consentite e non consentite per gli utenti prima e durante le riunioni. Per altre informazioni, vedere i seguenti articoli:

- [Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurare audioconferenze per piccole e medie imprese](audio-conferencing-smb.md)

### <a name="teams-phone-with-calling-plan"></a>Servizi telefonici con piano per chiamate

Servizi telefonici Microsoft 365 Teams con piano per chiamate è un'ottima soluzione per le aziende con meno di 300 utenti e offre tutte le funzionalità di un sistema telefonico per ufficio. Servizi telefonici Teams include la segreteria telefonica, ID chiamante, menu del sistema telefonico, numeri gratuiti e altro ancora, senza la necessità di gestire un complesso e costoso sistema telefonico locale.

Per altre informazioni su Servizi telefonici Teams con piano per chiamate per le piccole e medie imprese, vedere [Servizi telefonici Teams per le piccole e medie imprese](/microsoftteams/business-voice/whats-business-voice).

## <a name="deploy-clients"></a>Distribuire i client

Quando gli utenti sono pronti per iniziare a usare Teams, possono installare il client Teams sul proprio PC Windows, Mac o Linux o sul dispositivo Android o iOS. Gli utenti possono scaricare il client Teams direttamente da <https://teams.microsoft.com/downloads>.

Assicurarsi che tutti gli utenti che usano Teams abbiano una licenza di Teams. Per altre informazioni sull'assegnazione di una licenza di Teams, vedere [Gestire l'accesso degli utenti a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> È possibile ottenere suggerimenti su come pianificare la distribuzione client di Teams completando il modulo [Distribuire i client di Microsoft Teams](/training/modules/m365-teams-collab-deploy-clients/) in Microsoft Learn.

Se l'organizzazione usa Microsoft Endpoint Configuration Manager, i criteri di gruppo o un meccanismo di distribuzione di terze parti per distribuire i software nei computer degli utenti, vedere [Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager](msi-deployment.md).

Per informazioni dettagliate sulla distribuzione dei client Teams, vedere [Ottenere i client per Microsoft Teams](get-clients.md).

## <a name="training"></a>Formazione

Per informazioni su come formare gli utenti all’uso di Teams, vedere [Formazione su Microsoft Teams](training-microsoft-teams-landing-page.md).
