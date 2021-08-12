---
title: Configurare Microsoft Teams nell'azienda
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Configurare Teams nell'azienda per consentire agli utenti di collaborare tramite chat e condivisione di file, configurare e partecipare a riunioni di piccole e grandi dimensioni e parlare tramite chiamate video e vocali.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ce51b1768422a5780dbeae5b89f1285d26f18e524d3aae8bc710c127ee5af33
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280919"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>Configurare Microsoft Teams nell'azienda

Usare le informazioni di questo articolo come guida per la distribuzione di Teams nell'organizzazione.

> [!NOTE]
> Se è già stato fatto, è consigliabile iniziare la distribuzione di Teams con una distribuzione pilota. Una distribuzione pilota consentirà all’utente e agli early adopter di acquisire familiarità con Teams e le sue funzionalità prima della pianificazione e della distribuzione finale. Per altre informazioni su come avviare la distribuzione pilota, vedere [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md).

Prima di implementare Teams su larga scala, assicurarsi che l'organizzazione sia pronta esaminando gli elementi in [Assicurarsi di essere pronti](get-started-with-teams-quick-start.md#make-sure-youre-ready).

## <a name="plan-your-deployment"></a>Pianificare la distribuzione

Prima di iniziare la distribuzione di Teams, assicurarsi di aver completato il processo di pianificazione. Il processo di pianificazione deve includere:

- Comprensione dell'architettura di Teams
- Analisi e comprensione dei carichi di lavoro di Teams e di come funzionano con Microsoft 365
- Calcolo dei requisiti di rete e verifica che la rete e la connessione Internet dispongano dell'hardware e della capacità necessari per supportare requisiti critici, come le comunicazioni in tempo reale
- Comprensione dei requisiti normativi e di conformità per le informazioni archiviate in Teams e altri servizi di Microsoft 365
- Creazione di un piano di adozione che aiuti gli utenti a comprendere i vantaggi dell'uso di Teams

Si consiglia vivamente di usare l'[Assistente per Teams](https://admin.teams.microsoft.com/teams-deployment) come ausilio per la distribuzione. Per informazioni dettagliate sul funzionamento dell'Assistente per Teams, vedere [Usare Assistente per Teams per distribuire Microsoft Teams](use-advisor-teams-roll-out.md).

> [!TIP]
> Per informazioni su come usare l'Assistente per Teams per pianificare la distribuzione, completare il modulo di Microsoft Learn [Implementare Teams con l'Assistente per Teams](/learn/modules/m365-teams-rollout-using-advisor/).

Per informazioni sulla pianificazione per Teams, vedere [Panoramica della distribuzione aziendale di Teams](deploy-enterprise-overview.md).

## <a name="workloads"></a>Carichi di lavoro

È possibile personalizzare Teams in diversi modi. Le sezioni seguenti illustrano come configurare ogni carico di lavoro di Teams: **chat, team e canali**, **riunioni e conferenze** e **sistema telefonico**. L'ordine in cui si configura ciascun carico di lavoro dipende dall’utente. Anche se è consigliabile configurare prima il carico di lavoro di chat, team e canali, è possibile iniziare con le riunioni e le conferenze o anche con il sistema telefonico.

#### <a name="chat-teams-and-channels"></a>[Chat, team e canali](#tab/ChatTeamsChannels)

Chat, team e canali sono gli elementi essenziali di Teams. La **chat** consente agli utenti di parlare tra di loro, condividere file e di collegarsi in modo privato con altri. **Teams**, che può essere visibile a tutti gli utenti dell'organizzazione o solo a quelli del team, consente di collaborare con le persone giuste su qualsiasi attività o in qualsiasi occasione, che si tratti di un progetto a lungo termine o di una festa di compleanno. I **canali** nei team consentono di suddividere argomenti, progetti, reparti e altro per il team. Per informazioni dettagliate su chat, team e canali, vedere la [Panoramica su team e canali](teams-channels-overview.md).

> [!TIP]
> Per informazioni su come gestire i ruoli del team, l'accesso e i criteri di messaggistica, completare il modulo [Gestire Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) in Microsoft Learn.

### <a name="administration-and-team-ownership"></a>Amministrazione e proprietà dei team

| Decisione | Descrizione |
|--|--|
| Chi devono essere gli amministratori di Teams? | Il ruolo di amministratore può essere usato per concedere autorizzazioni specifiche alle persone che devono amministrare Teams. Questi ruoli aggiuntivi potrebbero non essere necessari per le piccole imprese, poiché la stessa persona potrebbe essere responsabile di tutti gli aspetti di Teams. È sempre possibile aggiungere o rimuovere gli amministratori in un secondo momento.<p>[Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md). |
| Chi devono essere i proprietari e i membri del team? | I proprietari del team controllano chi può accedere a un team e ai relativi canali. Possono decidere se un team o un canale è pubblico (per l'organizzazione) o privato e possono impostare criteri come quelli per la moderazione di un canale. I membri possono accedere al team e ai relativi canali, a meno che non si tratti di un canale privato di cui non sono membri, e possono essere designati come moderatori.<p>[Assegnare proprietari e membri del team in Microsoft Teams](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>Impostazioni predefinite e criteri del ciclo di vita

| Decisione | Descrizione |
|--|--|
| Quali criteri di messaggistica devono essere applicati? | I criteri di messaggistica controllano le funzionalità di messaggistica disponibili nelle chat e nei canali per gli utenti di Teams, ad esempio chi può usare la chat, chi può modificare ed eliminare i messaggi inviati e così via. Teams ha un criterio globale che si applica a tutti gli utenti. Tutte le funzionalità nel criterio globale sono **abilitate** per impostazione predefinita.<p>Se si vuole applicare a tutti lo stesso criterio, è sufficiente modificare questo criterio globale, ad esempio disattivare il supporto dei meme nelle conversazioni.<p>Se si vogliono usare criteri diversi per gruppi di utenti diversi, ad esempio, un criterio per gli impiegati d'ufficio e un altro per gli impiegati di produzione, è possibile creare e assegnare nuovi criteri. Quando si assegna un criterio a un utente, il criterio globale non si applica più a questo utente.<p>[Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md) |
| Quali impostazioni di Teams occorre applicare? | Le impostazioni di Teams consentono di configurare i team per funzionalità come l'integrazione della posta elettronica, le opzioni di archiviazione nel cloud, la scheda Organizzazione, la configurazione dei dispositivi della sala riunioni e l'ambito di ricerca. Le modifiche apportate a queste impostazioni si applicano a tutti i team dell'organizzazione.<p>[Impostazioni di Teams](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>Accesso esterno e accesso guest

| Decisione | Descrizione |
|--|--|
| L'accesso esterno andrebbe abilitato? | L'accesso esterno consente a tutte le persone di un'altra organizzazione di comunicare con gli utenti della propria. Questa funzionalità è utile quando si ha una stretta relazione con un'altra organizzazione, ad esempio un fornitore, e si vuole che le persone di entrambe le aziende possano con la massima semplicità chattare, organizzare riunioni e così via.<p>L'accesso esterno è diverso dall'accesso guest. L'accesso esterno consente a tutte le persone di un'organizzazione di accedere e interagire con le persone di un'altra organizzazione. Con l'accesso guest si invitano persone specifiche ad accedere per interagire con le persone della propria organizzazione.<p>L'accesso esterno è **disattivato** per impostazione predefinita.<p>[Gestire l'accesso esterno in Microsoft Teams](manage-external-access.md)  |
| L'accesso guest deve essere abilitato? |L'accesso guest consente agli utenti dell'organizzazione di invitare persone esterne all'organizzazione ad accedere ai team e ai canali interni. L'accesso guest viene spesso usato per collaborare con persone esterne all'organizzazione che non hanno una relazione formale con la propria. Ad esempio, è possibile invitare un progettista a lavorare temporaneamente su un progetto.<p>L'accesso guest è diverso dall'accesso esterno. L'accesso guest invita persone specifiche ad accedere per interagire con le persone dell'organizzazione. L'accesso esterno consente a tutte le persone di un'altra organizzazione di accedere e interagire con le persone dell'organizzazione. <p>L'accesso guest è **disattivato** per impostazione predefinita. <p>[Attivare o disattivare l'accesso guest in Microsoft Teams.](set-up-guests.md)  |

#### <a name="meetings-and-audio-conferencing"></a>[Riunioni e audioconferenza](#tab/MeetingsAudioConferencing)

Le riunioni e le conferenze consentono alle persone dell'organizzazione di comunicare tra loro e con persone esterne all'organizzazione. Chiunque abbia un client Teams o Skype for Business può partecipare alle **riunioni** a cui è stato invitato. Usando il microfono, la fotocamera e lo schermo del proprio dispositivo, gli utenti possono partecipare alla conversazione senza bisogno di un telefono. I partecipanti possono chattare, effettuare chiamate vocali e condividere video e app con altri partecipanti usando un PC o un dispositivo mobile.

L'**audioconferenza** offre agli utenti la possibilità di partecipare alle riunioni usando un normale telefono, componendo il numero di telefono della conferenza e immettendo l'ID della riunione. Le audioconferenze sono utili quando un partecipante non dispone di una buona connessione Internet, se la riunione è solo vocale o in altre circostanze che impediscono di partecipare tramite il client Teams.

> [!TIP]
> Per acquisire maggiore familiarità con riunioni ed eventi, completare il modulo [Gestire riunioni, conferenze ed eventi con Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) in Microsoft Learn.

### <a name="meetings"></a>Riunioni

| Decisione | Descrizione |
|--|--|
| Quali impostazioni delle riunioni a livello di organizzazione devono essere applicate?| I criteri di riunione controllano quali funzionalità per le riunioni sono disponibili per gli organizzatori e i partecipanti. È possibile controllare se i partecipanti anonimi possono partecipare alle riunioni, personalizzare gli inviti alle riunioni, controllare come vengono gestiti i contenuti multimediali in tempo reale e altro ancora. Le modifiche apportate a queste impostazioni si applicano a tutte le riunioni dell'organizzazione. <p>[Gestire le impostazioni di riunione in Microsoft Teams](meeting-settings-in-teams.md)|
| Quali criteri di riunione devono essere applicati? | I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione. È possibile controllare se gli utenti possono pianificare riunioni private, abilitare l'opzione Riunione immediata, consentire la registrazione delle riunioni e così via. Teams ha un criterio globale che si applica a tutti gli utenti.<p> Se si vuole applicare a tutti lo stesso criterio, è sufficiente modificare questo criterio globale, ad esempio disattivare la registrazione delle riunioni. <p>Se si vogliono usare criteri diversi per gruppi di utenti diversi, ad esempio, un criterio per gli impiegati e un altro per i dirigenti, è possibile creare e assegnare nuovi criteri. Quando si assegna un criterio a un utente, il criterio globale non si applica più a questo utente.<p> [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)|
| Si vuole consentire la registrazione e l'archiviazione delle riunioni?| Gli organizzatori delle riunioni possono registrare e archiviare le riunioni nel cloud. È possibile attivare e disattivare la registrazione e l'archiviazione delle riunioni usando i criteri di riunione.<p> [Registrazione delle riunioni di Teams nel cloud](cloud-recording.md) |

### <a name="audio-conferencing"></a>Audioconferenza

| Decisione | Descrizione |
|--|--|
| Si vuole configurare l'interoperabilità video con soluzioni di terze parti?| L'interoperabilità video nel cloud consente di partecipare alle riunioni di Teams con dispositivi di telepresenza di terze parti e dispositivi video personali. Se si è già investito in dispositivi di videoconferenza e dispositivi video personali, è possibile usare l'interoperabilità video per integrarli con Teams.<p> [Interoperabilità video nel cloud per Microsoft Teams](cloud-video-interop.md).|
| Quali impostazioni di audioconferenza a livello di organizzazione devono essere applicate?| Le impostazioni di audioconferenza consentono di controllare le modalità di partecipazione alle riunioni tramite telefono. È possibile impostare la lunghezza dei PIN necessari per partecipare alle riunioni, reimpostare gli ID conferenza, abilitare o disabilitare l'invio di informazioni per l'audioconferenza ai partecipanti e così via. Le modifiche alle impostazioni di audioconferenza si applicano a tutti gli utenti dell'organizzazione.<p>[Gestire le impostazioni di audioconferenza per l'organizzazione in Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| Gli organizzatori di riunioni devono effettuare chiamate in uscita verso qualsiasi destinazione?| Quando si chiamano numeri di telefono esterni all'organizzazione da una riunione di Audioconferenza, viene usato Credito per la comunicazione. È necessario acquistare Credito per la comunicazione sufficiente per assicurarsi che non si esaurisca durante le chiamate del servizio di audioconferenza.<p>Alcuni abbonamenti al servizio di audioconferenza possono includere le chiamate in uscita. Per dettagli, controllare le informazioni sull'abbonamento.<p> [Configurare Credito per la comunicazione per la propria organizzazione](set-up-communications-credits-for-your-organization.md)|
| Quali restrizioni per le chiamate in uscita devono essere applicate?| È possibile possono usare i controlli per le chiamate in uscita per limitare il tipo di chiamate dalle audioconferenze che possono essere eseguite dagli utenti nell'organizzazione. Ad esempio, è possibile controllare se dalle riunioni si possono chiamare numeri di telefono internazionali, effettuare o meno chiamate in uscita, chiamare solo determinati paesi o aree geografiche e così via.<p>[Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente](outbound-calling-restriction-policies.md) |
| Si vuole modificare il modo in cui Teams interpreta i numeri di telefono composti? | È possibile controllare come vengono interpretati i numeri di telefono con i dial plan. Ad esempio, si può impostare il numero da comporre per raggiungere una linea telefonica esterna, controllare come vengono gestiti i numeri degli interni, impostare un prefisso in modo che un interno composto sia tradotto in un numero di telefono completo e così via.<p> [Creare e impostare dial plan](create-and-manage-dial-plans.md) |
| Si vogliono abilitare gli eventi live? | Gli eventi live consentono di trasmettere video e contenuto delle riunioni a un pubblico ampio. Se si abilitano gli eventi live, è possibile impostare criteri per controllare come vengono usati. Ad esempio, è possibile configurare l'URL che i partecipanti dovranno usare per il supporto, configurare un provider di distribuzione video di terze parti, se necessario, e così via. Teams ha un criterio globale che si applica a tutti gli utenti.<p>Se si vuole applicare a tutti lo stesso criterio, è sufficiente modificare questo criterio globale. <p>Se si vogliono usare criteri diversi per gruppi di utenti diversi, ad esempio, un criterio per gli impiegati e un altro per i dirigenti, è possibile creare e assegnare nuovi criteri. Quando si assegna un criterio a un utente, il criterio globale non si applica più a questo utente.<p> [Configurare gli eventi live in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[Sistema telefonico e connettività PSTN](#tab/PhoneSystem)

Sistema telefonico consente di sostituire il sistema di telefonia locale esistente con un set di funzionalità di Microsoft 365 strettamente integrate con l'esperienza nel cloud.

| Decisione | Descrizione |
|--|--|
| Si vuole sostituire il sistema telefonico locale? | Configurare Sistema telefonico, impostare gli operatori automatici, i piani per le chiamate, le code di chiamate e così via. <p> [Configurare Sistema telefonico nell'organizzazione](setting-up-your-phone-system.md)|
| Si vogliono impostare criteri di Cloud Voicemail?| È possibile controllare quali funzionalità di Cloud Voicemail sono disponibili per gli utenti e come funzionano. Ad esempio, è possibile abilitare o disabilitare la trascrizione dei messaggi vocali per l'intera organizzazione, abilitare o disabilitare il mascheramento del contenuto volgare per utenti specifici e così via.<p> [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md) |
| Si vogliono abilitare le chiamate di emergenza dinamiche?| Le chiamate di emergenza dinamiche consentono di configurare una mappa della posizione in base alle impostazioni di rete e ad altri metadati per determinare dove inviare il personale di emergenza nel caso in cui un utente effettui una chiamata di emergenza. È possibile configurare le impostazioni di rete, assegnare indirizzi di emergenza a posizioni e così via.<p>[Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) |
| Si vuole personalizzare il comportamento dell'ID chiamante? | Per impostazione predefinita, il numero di telefono visualizzato quando un utente di Teams effettua una chiamata è il numero di telefono dell'utente. Si può modificare questa impostazione in modo che sia il numero principale della società o un altro numero del servizio, bloccare il numero di telefono o rendere il numero anonimo. Teams ha un criterio globale che si applica a tutti gli utenti.<p>Se si vuole applicare a tutti lo stesso criterio, è sufficiente modificare questo criterio globale. <p>Se si vogliono usare criteri diversi per gruppi di utenti diversi, ad esempio, un criterio per gli impiegati e un altro per i dirigenti, è possibile creare e assegnare nuovi criteri. Quando si assegna un criterio a un utente, il criterio globale non si applica più a questo utente.<p> [Gestire i criteri dell'ID chiamante in Microsoft Teams](caller-id-policies.md) |

---

## <a name="security"></a>Sicurezza

Teams è progettato e sviluppato in conformità con il [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). Per essere conforme a SDL, Teams incorpora le tecnologie di sicurezza standard di settore come elementi essenziali dell'architettura, tra cui:

- Progettazione di modelli di minacce con cui vengono poi testate le funzionalità
- Integrazione dei miglioramenti relativi alla sicurezza durante il processo e le procedure di codifica
- Creazione di strumenti della fase di compilazione che rilevano sovraccarichi del buffer e altre potenziali minacce alla sicurezza prima dell'inserimento del codice nel prodotto finale.

Anche se Teams segue una metodologia basata sull'affidabilità da progettazione (Trustworthy by Design), è impossibile progettare un prodotto che sia al sicuro dalle minacce per la sicurezza sconosciute. Per questo motivo, è importante come funziona Teams e come interagisce con altri sistemi. È anche importante comprendere come funzionano le minacce comuni, ad esempio lo spoofing dell'indirizzo IP, gli attacchi Denial of Service, gli attacchi man-in-the-middle e così via, così da poter progettare la configurazione di rete e di Teams in un modo che consenta di ridurre la probabilità che si verifichino questi attacchi.

Per informazioni sul modo in cui Teams integra i fondamenti della sicurezza nella progettazione e per altre informazioni sulle minacce comuni, vedere [Sicurezza e Microsoft Teams](teams-security-guide.md).

## <a name="compliance"></a>Conformità

Teams e Microsoft 365 offrono molti strumenti che semplificano la conformità ai requisiti normativi del paese in cui si trovano l'azienda e gli utenti. Vedere gli articoli seguenti per informazioni su come configurare ogni singola funzionalità di conformità in Teams:

| Funzionalità | Descrizione|
|-|-|
| [Barriere informative](information-barriers-in-teams.md)| Impedisce a singoli utenti o gruppi di comunicare tra loro o di trovarsi tra loro nell'elenco di selezione utenti.|
| [Criteri di conservazione](retention-policies.md)| Consente di controllare per quanto tempo devono essere conservati i dati in Teams o se devono essere rimossi dopo un determinato periodo di tempo.|
| [Conformità delle comunicazioni](communication-compliance.md)| Contribuisce a ridurre i rischi associati alle comunicazioni identificando e prendendo misure contro il linguaggio offensivo, volgare e molesto, le immagini per adulti, audaci e cruente, oltre che contro la condivisione di informazioni riservate. |
| [Registrazione di chiamate e riunioni basata sui criteri](teams-recording-policy.md)| Consente di controllare quando e se le chiamate e le riunioni devono essere registrate e archiviate automaticamente per la successiva elaborazione, conservazione o analisi.|
| [Etichette di riservatezza](sensitivity-labels.md)| Consente di proteggere e regolare l'accesso alle informazioni sensibili creando etichette che applicano opzioni di privacy selezionate.|
| [Prevenzione della perdita dei dati](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| Consente di creare regole che determinano la modalità di gestione di determinate informazioni, ad esempio codici fiscali, numeri di carta di credito e così via. È possibile impedire l'invio di determinate informazioni, impedirne l'uscita dall'organizzazione e così via.|
| [eDiscovery](eDiscovery-investigation.md)| Consente di cercare e recuperare contenuto all'interno dell'organizzazione quando l'organizzazione riceve richieste di individuazione nell'ambito di procedimenti legali. |
| [Blocco a fini giudiziari](legal-hold.md)| Consente di conservare informazioni nell'organizzazione, anche se vengono eliminate da un utente, quando necessario durante procedimenti legali, in modo che possano essere individuate durante le indagini di eDiscovery. |
| [Ricerca contenuto](content-search.md)| Consente di eseguire query sulle informazioni di Teams su Exchange, SharePoint Online e OneDrive for Business.|
| [Auditing](audit-log-events.md)| Consente di visualizzare informazioni su un'azione specificata, tra cui l'utente che ha eseguito l'azione, la data e l'ora in cui è stata eseguita, l'indirizzo IP usato e così via. Le azioni includono la creazione o l'eliminazione di team, la creazione di canali, la modifica di impostazioni in Teams e così via.|
| [Customer Key](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| Consente di creare criteri di crittografia dei dati con le chiavi di crittografia fornite.|

## <a name="clients"></a>Client

Quando gli utenti iniziano a usare Teams possono installare il client Teams sul proprio PC Windows, Mac o Linux o sul proprio dispositivo Android o iOS. Gli utenti possono scaricare il client Teams direttamente da <https://teams.microsoft.com/downloads>.

Assicurarsi che tutti gli utenti che usano Teams abbiano una licenza di Teams. Per altre informazioni sull'assegnazione di una licenza di Teams, vedere [Gestire l'accesso degli utenti a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> È possibile ottenere suggerimenti su come pianificare la distribuzione client di Teams completando il modulo [Distribuire i client di Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) in Microsoft Learn.

Se l'organizzazione usa Microsoft Endpoint Configuration Manager, i criteri di gruppo o un meccanismo di distribuzione di terze parti per distribuire i software nei computer degli utenti, vedere [Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager](msi-deployment.md).

Per informazioni dettagliate sulla distribuzione dei client Teams, vedere [Ottenere i client per Microsoft Teams](get-clients.md).

## <a name="training"></a>Formazione

Per informazioni su come formare gli utenti e gli amministratori all'uso di Teams, vedere [Formazione su Microsoft Teams](training-microsoft-teams-landing-page.md).