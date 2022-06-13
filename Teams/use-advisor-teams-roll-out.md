---
title: Usare Advisor per Teams per distribuire Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: Usare Advisor per Teams per pianificare e completare la distribuzione di Microsoft Teams.
ms.openlocfilehash: b05567eb17d878d297be1900425e51760341389a
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045595"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Usare Advisor per Teams per distribuire Microsoft Teams

Advisor per Teams fornisce una guida per l'implementazione di Microsoft Teams. Valuta l’ambiente dell’organizzazione di Microsoft 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams. Quindi, Advisor per Teams crea un team di distribuzione (in Teams) con canali per ogni carico di lavoro che si vuole distribuire. Ogni carico di lavoro del team di distribuzione include un piano di Planner completo che include tutte le attività di implementazione per ogni carico di lavoro.  Con questo piano di Planner, si possono assegnare attività alle persone responsabili di ogni fase dell'implementazione, tra cui il project manager, gli amministratori di Teams, il personale di supporto e il team di adozione e conformità degli utenti. Ogni attività di implementazione contiene tutte le indicazioni e le risorse necessarie per completare correttamente l'attività.

Advisor per Teams fa parte dell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com). Per sfruttare al meglio l'integrazione di Advisor per Teams con Forms e Planner, è necessaria almeno una licenza di Microsoft 365 Business Basic. Per iniziare a usare Advisor per Teams, fare clic sul pulsante **Avvia** nel widget **Distribuzione del carico di lavoro di Teams** nel dashboard. In alternativa, passare a **Pianificazione** > **Assistente per Teams**.

> [!IMPORTANT]
> Advisor per Teams non è disponibile per le distribuzioni di Microsoft 365 Government - GCC High o DoD.

Per una panoramica guidata dell'esperienza di Advisor per Teams, vedere il video di Microsoft Mechanics [Distribuire e configurare Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50).

## <a name="using-advisor-for-teams"></a>Usare Advisor per Teams

**Per usare Assistente per Teams sono necessarie le licenze di Teams, Forms e Planner.** Non è tuttavia necessario essere un amministratore di Teams per usare Assistente per Teams: chiunque nell'organizzazione può usarlo. Sono state configurate autorizzazioni speciali in modo che gli utenti non amministratori possano accedere ad Advisor per Teams, anche se questo si trova nell'interfaccia di amministrazione di Teams. È necessario essere un amministratore di Teams, un amministratore di Teams oppure un amministratore globale per aprire le valutazioni di conformità del tenant, perché i ruoli speciali senza privilegi di amministratore non hanno accesso alle API Microsoft Graph alla base delle valutazioni.

> [!IMPORTANT]
> Se la voce **Assistente per Teams** non è presente in **Pianificazione** nell'interfaccia di amministrazione di Teams, l'utente non ha la licenza per Teams.

La prima volta che si usa Assistente per Teams viene creato un team di distribuzione in Teams. Viene inoltre aggiunto un canale per ogni carico di lavoro selezionato.

> [!IMPORTANT]
> Se è già stato creato un team di distribuzione e un altro utente prova a crearlo, viene visualizzato un messaggio di errore che informa che è necessario contattare il proprio team di supporto. Questo impedirà a Teams di rivelare inavvertitamente informazioni relative al team e ai membri esistenti. Rivolgersi al proprietario del team di distribuzione per essere aggiunti oppure contattare il supporto tecnico per ottenere assistenza.

## <a name="available-advisor-for-teams-plans"></a>Advisor disponibile per i piani di Teams

Advisor per Teams attualmente prevede i seguenti piani:

1. Chat, team, canali e app
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms
    - Bot Advisor per Teams
1. Riunioni e conferenze
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms
    - Bot Advisor per Teams
1. Aggiornamento di Skype for Business
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms
    - Bot Advisor per Teams
    - Progettato per i clienti che attualmente utilizzano ambienti locali Skype for Business online o Skype for Business, il piano di aggiornamento di Skype for Business consentirà un aggiornamento pianificato in ogni minimo dettaglio. Sfruttando un efficiente framework comprovato per l'implementazione del cambiamento, il piano farà da guida attraverso una procedura dettagliata, sia che si abbia appena iniziato a usare Teams, che già lo si utilizzi insieme a Skype for Business o che si sia pronti per l'aggiornamento. Il piano mette a disposizione anche [materiale sussidiario e procedure consigliate online](./upgrade-start-here.md), [risorse scaricabili](https://aka.ms/UpgradeSuccessKit), [workshop di pianificazione di gruppo](./upgrade-workshops-landing-page.yml) e risorse aggiuntive a supporto del raggiungimento dei risultati.
1. Education (visibile solo alle organizzazioni educative)
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms
    - Bot Advisor per Teams
    - Progettato per le organizzazioni educative, il piano Education ti aiuterà a distribuire, adottare e gestire i team nel tuo istituto formativo.

Per le organizzazioni commerciali, è consigliabile iniziare con il piano Chat, team, canali e app. Per le organizzazioni educative, ti consigliamo di iniziare con il piano Education. Dopo aver completato la distribuzione del carico di lavoro, tornare in Assistente per Teams e selezionare **Aggiungi canale** per avviare il carico di lavoro successivo.



## <a name="tenant-assessment"></a>Valutazione del tenant

Ogni piano include una valutazione di conformità del tenant che è possibile usare per identificare rapidamente gli aspetti dell'ambiente che è necessario correggere prima di implementare Teams. Nelle valutazioni sono inclusi i prerequisiti e le procedure consigliate. Ogni test di valutazione avrà un segno di spunta verde o un triangolo di avviso arancione.

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Un segno di spunta verde indica che il tenant ha superato il test specifico.
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Un triangolo di avviso arancione indica che è consigliabile eseguire azioni di follow-up per determinare se è necessaria un'azione, ad esempio un criterio di scadenza del gruppo di Microsoft 365 è consigliabile ma non obbligatorio.

> [!IMPORTANT]
> Dopo che un utente con un ruolo con privilegi di amministratore avvia Advisor per Teams, tutte le valutazioni vengono eseguite in background. Se si aggiorna o corregge un elemento, è possibile che non si rifletta nelle valutazioni fino a 24 ore.

Le sezioni seguenti descrivono le singole valutazioni, tra cui se un elemento è un prerequisito o una procedura consigliata, il modo in cui vengono eseguiti i controlli e il motivo della valutazione, nonché le indicazioni per la correzione se necessaria.

### <a name="assessment-tests-for-all-workloads"></a>Test di valutazione per i carichi di lavoro

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Dominio con reindirizzamento a microsito configurato     |Se è stato configurato un dominio non @onmicrosoft.com per il tenant, ad esempio @contoso.onmicrosoft.com. Naturalmente è possibile usare il dominio @onmicrosoft. com oppure configurare dominio con reindirizzamento a microsito, secondo l'opzione desiderata. Per altre informazioni, leggere [Aggiungere un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain). |
|Licenze di Teams     |Si tratta di un prerequisito: **è necessario** avere licenze di Teams per poter distribuire Teams. Eseguire una query in Microsoft Graph per verificare se si hanno licenze di Teams e almeno una licenza disponibile da assegnare. Per altre informazioni, leggere la [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).    |
|Licenze di Exchange Online     |Se si dispone di un abbonamento attivo con licenze Exchange Online disponibili. Anche se Exchange non è necessario per la funzionalità di base di Teams, l'integrazione con Exchange offre un'esperienza di Teams ottimale. Eseguire una query in Microsoft Graph per analizzare le sottoscrizioni associate al tenant e verificare se si hanno sottoscrizioni con una licenza di Exchange Online idonea e almeno una licenza disponibile da assegnare. Per altre informazioni, vedere [Modalità di interazione tra Exchange e Teams](exchange-teams-interact.md).    |
|Licenze di SharePoint Online     |Se si dispone di un abbonamento attivo con licenze SharePoint Online disponibili. È consigliabile usare le licenze SharePoint Online per utente per disporre di OneDrive for Business per l'archiviazione dei file nelle chat. Eseguire una query in Microsoft Graph per verificare se si hanno licenze di SharePoint Online e almeno una licenza disponibile da assegnare. Per altre informazioni, leggere [Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](./sharepoint-onedrive-interact.md).    |
|Accesso guest abilitato     |Se l'[accesso guest](guest-access.md) è abilitato. L'accesso guest consente di invitare utenti esterni a partecipare al proprio team. Vedere [Collaborare con gli ospiti in un team](/microsoft-365/solutions/collaborate-as-team) per scoprire come attivare l'accesso ospite in Teams; l'elenco di controllo include le configurazioni di Azure AD richieste. |
|Accesso esterno configurato     |Se l'[accesso esterno](manage-external-access.md) è disattivato. Per impostazione predefinita, l'opzione è attivata con la federazione aperta. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Valutazioni per Chat, team, canali e app.

Oltre ai [test di valutazione per i carichi di lavoro](#assessment-tests-for-all-workloads), vengono eseguite le seguenti valutazioni aggiuntive per il carico di lavoro Chat, team, canali e app:

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Criteri di denominazione dei gruppi di Microsoft 365 configurati     |Se sono stati configurati gli standard di denominazione per i Gruppi di Microsoft 365. I criteri di denominazione per i Gruppi di Microsoft 365 consentono all'organizzazione di applicare una strategia di denominazione coerente con i team creati dall'utente e si applica anche ad altri carichi di lavoro dei Gruppi, tra cui Outlook, SharePoint, Planner e Yammer. Questo test esegue una query in Azure AD tramite Microsoft Graph per verificare l'esistenza di criteri di denominazione validi per i Gruppi di Microsoft 365. Per altre informazioni, leggere [Criterio di denominazione dei gruppi](/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Criteri di scadenza dei gruppi di Microsoft 365 configurati     |Se i criteri di scadenza di un Gruppo sono stati definiti per i Gruppi di Microsoft 365. Questo consente all'organizzazione di rimuovere automaticamente Teams inattivi. Per impostazione predefinita l'opzione è disattivata. Questo test esegue una query in Azure AD tramite Microsoft Graph e indica se un valore è stato modificato rispetto all'impostazione predefinita. Per altre informazioni, leggere [Criteri di scadenza del gruppo Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Valutazioni per messaggistica istantanea, riunioni e conferenze

Oltre ai [test di valutazione per i carichi di lavoro](#assessment-tests-for-all-workloads), vengono eseguite le seguenti valutazioni aggiuntive per il carico di lavoro della messaggistica istantanea, riunioni e conferenze:

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Licenze di audioconferenza    |Se si dispone di un abbonamento attivo con licenze di audioconferenza. Si tratta di un prerequisito per la distribuzione di bridge di audioconferenza. Eseguire una query in Microsoft Graph per verificare se sono presenti licenze di audioconferenza, con almeno una licenza disponibile da assegnare. Per altre informazioni, leggere [ Licenze per i componenti aggiuntivi di Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licenze di streaming     |Se si dispone di un abbonamento attivo con licenze di Microsoft Stream. Si tratta di un prerequisito per attivare la registrazione di una riunione. Eseguire una query in Microsoft Graph per verificare se sono presenti licenze di Microsoft Stream e almeno una licenza disponibile da assegnare. Per altre informazioni su Stream e su come attivarlo, leggere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Valutazioni per l'aggiornamento di Skype for Business

Oltre ai [test di valutazione per i carichi di lavoro](#assessment-tests-for-all-workloads), l'aggiornamento di Skype for Business include anche le valutazioni utilizzate nelle riunioni e nei piani per le conferenze.

### <a name="advisor-for-teams-bot"></a>Bot Advisor per Teams

Quando Advisor per Teams crea il team di distribuzione, il relativo bot consegna il messaggio seguente nel canale Generale:

>**Benvenuti nel team di distribuzione per Microsoft Teams.**
>  
>Lo scopo del team consiste nel guidare l'implementazione di Teams nell'organizzazione fornendo tutte le risorse necessarie e uno spazio di collaborazione per il team di progetto. Ogni canale creato con Advisor per Teams include un piano di Planner dettagliato e altre risorse, ad esempio un sondaggio utenti di Forms che può essere usato durante l’intero corso dell’implementazione. In qualsiasi momento, è possibile tornare indietro e rivedere la valutazione di conformità del tenant o aggiungere altri piani di carico di lavoro usando l'interfaccia di amministrazione di Teams.
>
>**Invito all'azione**
>
>- Se non si ha familiarità con Teams o con Planner, vedere la [procedura dettagliata di Teams](https://teamsdemo.office.com/) e guardare i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).
>- Passare al team di distribuzione in Teams. Selezionare il canale del carico di lavoro, ad esempio Chat, team, canali e app, e selezionare la scheda **Planner** per iniziare.
>
>Per altre informazioni su Advisor for Teams, vedere [Usare Advisor per Teams per distribuire Microsoft Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> Il bot di Advisor per Teams viene usato solo per inviare un messaggio di benvenuto al team di distribuzione. Non vengono raccolti altri dati.

> [!IMPORTANT]
> Il bot Advisor per Teams è attivato per impostazione predefinita. Se si usa o si prevede di usare Advisor per Teams, non disattivarlo.

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Percorsi di apprendimento di Assistente per Teams e Microsoft 365

[I percorsi di apprendimento di Microsoft 365](/office365/customlearning/) rappresentano una soluzione su richiesta che è possibile personalizzare per formare gli utenti e incrementare l'utilizzo di Teams nell'organizzazione. Usare i percorsi di apprendimento insieme ad Assistente per Teams per aiutare gli utenti e favorire una rapida adozione.

I percorsi di apprendimento forniscono un modello di sito di SharePoint Online e la possibilità di creare facilmente un sito di apprendimento per gli utenti. È possibile personalizzare il portale di formazione dei percorsi di apprendimento per fare in modo che includa contenuti di formazione e supporto specifici per le esigenze degli utenti. Usare le playlist di Teams dal catalogo online di Microsoft e aggiungere la propria.

È possibile creare un sito di apprendimento nei percorsi di apprendimento, quindi aggiungerlo come scheda a un canale in Teams per un accesso facile e veloce da parte degli utenti.

Ad esempio, è possibile usare Assistente per Teams insieme ai percorsi di apprendimento per formare l'help desk e i promotori e fare in modo che gli utenti finali ricevano la formazione tramite i percorsi di apprendimento. È possibile inoltre creare un sito di apprendimento per favorire l'onboarding dell'help desk e dei promotori in Teams e aggiungerlo come scheda a ogni canale del carico di lavoro che viene distribuito. L'help desk e i promotori potranno quindi creare una pagina di supporto sul portale di formazione dei percorsi di apprendimento con collegamenti e playlist personalizzati per supportare gli utenti su Teams. Questa pagina di supporto può essere aggiunta a un canale in qualsiasi team per favorire la formazione degli utenti finali.

Segue una panoramica su come usare Assistente per Teams insieme ai percorsi di apprendimento.

### <a name="get-started-in-learning-pathways"></a>Introduzione ai percorsi di apprendimento

Per iniziare a usare i percorsi di apprendimento, consultare [Introduzione ai percorsi di apprendimento](/office365/customlearning/).

Per configurare una nuova soluzione di percorsi di apprendimento, nel proprio ambiente, vedere [Effettuare il provisioning di una nuova soluzione di percorsi di formazione](/office365/customlearning/custom_provision).

### <a name="create-a-learning-plan"></a>Creare un piano di apprendimento

#### <a name="plan-your-learning-content"></a>Pianificare i contenuti di apprendimento

Prima di creare il sito nei percorsi di apprendimento, assicurarsi di rivedere e raccogliere le risorse di apprendimento e le funzionalità disponibili. Con i percorsi di apprendimento, è possibile usare i contenuti dalla pagina di formazione per Microsoft 365 e aggiungere i contenuti creati per adattarsi alle esigenze specifiche del sito.

Per ulteriori informazioni, vedere [Pianificare i contenuti dei percorsi di apprendimento](/office365/customlearning/custom_plancontent) e [Risorse per supportare il personale remoto](/office365/customlearning/custom_plancontent_remoteresources).

#### <a name="explore-teams-content-in-learning-pathways"></a>Esplorare i contenuti di Teams nei percorsi di apprendimento

I percorsi di apprendimento forniscono un sito SharePoint con una web part connessa a un catalogo online. La pagina di formazione per Microsoft 365, che ospita la web part, mostra tutta la formazione disponibile nei percorsi di apprendimento. Rivedere il materiale disponibile per acquisire familiarità e scoprire come sono stati organizzati i contenuti.

[Andare al sito dei percorsi di apprendimento](/office365/customlearning/custom_goto), selezionare **Formazione per Microsoft 365**, quindi **Microsoft Teams** per vedere tutte le playlist di formazione per Teams nel catalogo online. Selezionare una playlist, quindi i pulsanti **Avanti** e **Indietro** per spostarsi. È anche possibile fare clic su freccia GIÙ per visualizzare l'indice delle playlist e passare a un argomento specifico.

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>Fare un inventario delle risorse di apprendimento di Teams nell'organizzazione

Rivedere i contenuti di apprendimento di Teams già disponibili nell'organizzazione. Ad esempio, si potrebbe aver già sviluppato onboarding, formazione e contenuti di supporto per Teams. Le risorse esistenti di SharePoint possono essere unite ai contenuti di Microsoft in una playlist per creare una playlist ideata appositamente per la propria organizzazione.

#### <a name="build-your-site-in-learning-pathways"></a>Creare il sito nei percorsi di apprendimento

L'[Admin Success Center](/office365/customlearning/custom_successcenter) nei percorsi di apprendimento fornisce le linee guida e le risorse necessarie per agevolare la pianificazione e la personalizzazione dei percorsi di apprendimento dell'organizzazione. Ulteriori informazioni su come [personalizzare il sito](/office365/customlearning/custom_overview), mostrare e nascondere i contenuti, creare playlist personalizzate e molto altro.

Per accedere all'Admin Success Center nella home page dei percorsi di apprendimento, selezionare **Admin Success Center**.

#### <a name="add-your-site-to-teams"></a>Aggiungere il proprio sito a Teams

Una volta pronto, sarà possibile aggiungere il sito a un canale in qualsiasi team per un accesso rapido e semplice.

1. In Teams, andare al team e selezionare un canale.
2. Nella parte superiore della pagina del canale, selezionare **+** (**Aggiungi una scheda**).
3. Selezionare **Pagine di SharePoint** e selezionare **Aggiungi una pagina da qualsiasi sito di SharePoint**.
4. Incollare l'URL del sito dei percorsi di apprendimento e selezionare **Salva**.

Per ulteriori informazioni, vedere [Aggiungere una pagina o un elenco di SharePoint a un canale in Teams](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).

### <a name="train-your-support-team"></a>Formare il team di assistenza

Usare le risorse nel sito dei percorsi di apprendimento per eseguire l'onboarding dell'help desk e dei promotori in Teams. Sarà possibile fare in modo che siano tutti pronti grazie agli strumenti e le informazioni di cui necessitano per supportare gli utenti in Teams.

Per ottenere linee guida e risorse su come preparare l'help desk e i promotori per Teams, vedere [Formare la propria organizzazione](https://adoption.microsoft.com/microsoft-teams/#train-your-org) e [Creare promotori](https://adoption.microsoft.com/microsoft-teams/#build-champions).

Come contatto per le domande pratiche degli utenti, l'help desk e i promotori possono usare il sito dei percorsi di apprendimento per formare gli utenti e come alternativa alla creazione dei ticket di supporto. Incoraggiare l'help desk e i promotori a [personalizzare il sito dei percorsi di apprendimento](/office365/customlearning/) creando una pagina di formazione e supporto e [aggiungerla come scheda a un canale](#add-your-site-to-teams) in un team, così che gli utenti possano usarla in autonomia.

### <a name="drive-adoption"></a>Favorire l'adozione

Dopo aver personalizzato il sito e riunito i piani di apprendimento, prendere in considerazione come favorire la consapevolezza tra gli utenti per incoraggiarli a usare i percorsi di apprendimento per un apprendimento continuo.

Usare i canali di comunicazione per promuovere il sito e generare consapevolezza. Ad esempio, includere uno slogan standard come "Consulta il sito di formazione e supporto per scoprire come ottimizzare la produttività con Teams" nelle comunicazioni con gli utenti.

Coinvolgere gli utenti mettendo in evidenza le modalità di collaborazione in Teams e indirizzarli verso il sito dei percorsi di apprendimento per scoprire come.

Controllare queste risorse, che includono linee guida, kit di adozione, best practice e molto altro per favorire l'implementazione di un piano di adozione di successo.  

- [Favorire l'adozione dei percorsi di apprendimento](/office365/customlearning/driveadoption)
- [Adottare Teams](adopt-microsoft-teams-landing-page.md)
- [Risorse di adozione per Teams](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Requisiti di licenza per Assistente per Teams

Per sfruttare al meglio l'integrazione di Advisor per Teams con Forms e Planner, è necessario almeno Microsoft 365 Business Basic.

### <a name="can-i-delete-the-deployment-team"></a>È possibile eliminare il team di distribuzione?

Dopo che Advisor per Teams ha creato il team di distribuzione, è possibile gestire il team come qualsiasi altro team, inclusa la possibilità di eliminarlo. Tenere presente che se non si elimina il team tramite l'interfaccia di amministrazione di Teams, il team verrà visualizzato come ancora esistente nell'interfaccia di amministrazione.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>È possibile aggiungere o rimuovere canali nel team di distribuzione?

Sì, dopo aver creato il team di distribuzione i canali verranno gestiti allo stesso modo di tutti gli altri team.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>È possibile aggiungere o rimuovere membri del team di progetto nel team di distribuzione?

Sì, dopo aver creato il team di distribuzione, questo verrà gestito allo stesso modo di tutti gli altri team.

### <a name="can-i-modify-the-planner-plans"></a>È possibile modificare i piani di Planner?

Sì, dopo che Advisor per Teams ha creato il team di distribuzione, è necessario aggiornare il piano di Planner in modo che supporti al meglio l'implementazione di Teams. È possibile modificare qualsiasi elemento, ad esempio i contenitori, le attività, i dettagli delle attività, esattamente come qualsiasi altro piano di Planner.

### <a name="can-i-modify-the-forms-survey"></a>È possibile modificare il sondaggio di Forms?

Sì, dopo che Advisor per Teams ha creato il team di distribuzione, è possibile modificare il sondaggio di Forms in base alle esigenze.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>Esiste una differenza con l'Assistente per Teams in GCC?

Sì, vengono creati sondaggi di Forms per utenti ma non vengono aggiunti ai canali del piano poiché l'app Teams di Forms non è attualmente disponibile in GCC.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quali informazioni raccoglie Assistente per Teams sull'organizzazione?

Advisor per Teams richiede il consenso per la raccolta di informazioni diverse da quelle di identificazione degli utenti finali. Le informazioni raccolte si trovano sotto forma di telemetria che fornisce un feedback a Microsoft sui risultati prodotti da Advisor per Teams e su cosa andrebbe migliorato. Questi stessi dati vengono usati per identificare opportunità per Microsoft di impegnarsi in modo proattivo con l'organizzazione in modo da facilitare la distribuzione.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>È possibile usare Assistente per Teams con FastTrack?

Sì, FastTrack supporta Advisor per Teams per tutti i clienti che vogliono distribuire Teams. Possono fornire assistenza per la configurazione iniziale del team di distribuzione con Advisor per Teams, se necessario, e forniscono inoltre supporto su misura per argomenti specifici durante l'implementazione di Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>È possibile usare Assistente per Teams con un partner?

Sì, è possibile usare Advisor per Teams avendo allo stesso tempo un partner di distribuzione per la distribuzione di Teams. Se il partner è un provider di servizi di crittografia e gestisce il tenant per conto dell'utente, può usare Advisor per Teams per creare il team di distribuzione e fornire assistenza nell'esecuzione del progetto nel suo complesso. Inoltre, è possibile collaborare con qualsiasi partner aggiungendo i singoli utenti come guest nel team di distribuzione, per consentire loro di partecipare come membri del team del progetto nel suo complesso.

### <a name="how-do-i-use-planner"></a>Come usare Planner

Per altre informazioni, vedere [Guida di Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) e i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).

### <a name="how-do-i-use-forms"></a>Come usare Forms

Passare al [Centro assistenza di Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Argomenti correlati

[Personalizzare l'Assistente per Teams](/office365/customlearning/custom_teamsadvisor)

[Come implementare Teams](./deploy-overview.md)

[Procedure consigliate per l'organizzazione dei team in Teams](best-practices-organizing.md)

[Nomi dei prodotti e identificatori dei piani di servizio per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
