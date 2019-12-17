---
title: Usare Advisor per Teams (anteprima) per distribuire Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Usare Advisor per Teams (anteprima) per pianificare e completare la distribuzione di Microsoft Teams.
ms.openlocfilehash: 22b38da39ff0649077a8f4b388e4ffb39272824c
ms.sourcegitcommit: da1327ce289afee32585dc2c7e7ac81823379975
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2019
ms.locfileid: "40032821"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Usare Advisor per Teams per distribuire Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor per Teams (anteprima) guida l'implementazione di Microsoft Teams. Valuta l’ambiente tenant di Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams. Quindi, Advisor per Teams crea un team di distribuzione (in Teams) con canali per ogni carico di lavoro che si vuole distribuire. Ogni carico di lavoro del team di distribuzione include un piano di Planner completo che include tutte le attività di implementazione per ogni carico di lavoro.  Con questo piano di Planner, si possono assegnare attività alle persone responsabili di ogni fase dell'implementazione, tra cui il project manager, gli amministratori di Teams e di Office 365, le persone di supporto e il team di adozione e conformità degli utenti. Ogni attività di implementazione contiene tutte le indicazioni e le risorse necessarie per completare correttamente l'attività.

Advisor per Teams fa parte dell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com). Per sfruttare al meglio l'integrazione di Advisor per Teams con Forms e Planner, è necessaria almeno una licenza di Office 365 Business Essentials. Per iniziare a usare Advisor per Teams, fare clic sul pulsante **Avvia** nel widget **Distribuzione del carico di lavoro di Teams** nel dashboard. In alternativa, passare a **Pianificazione** > **Advisor**.

> [!IMPORTANT]
> Advisor per Teams non è disponibile per le distribuzioni di Microsoft 365 Government - GCC High o DoD.

Per una panoramica guidata dell'esperienza di Advisor per Teams, vedere il video di Microsoft Mechanics [Distribuire e configurare Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50).

## <a name="using-advisor-for-teams-preview"></a>Usare Advisor per Teams (anteprima)

Non è necessario essere un amministratore di Teams per usare Advisor per Teams: chiunque nell'organizzazione può usarlo. Sono state configurate autorizzazioni speciali in modo che gli utenti non amministratori possano accedere ad Advisor per Teams, anche se questo si trova nell'interfaccia di amministrazione di Teams. È necessario essere un amministratore di Teams, un amministratore del servizio Teams oppure un amministratore globale per aprire le valutazioni di conformità del tenant, poiché i ruoli speciali senza privilegi di amministratore non hanno accesso alle API Microsoft Graph alla base delle valutazioni.

La prima volta che si usa Advisor per Teams viene creato un team di distribuzione in Teams. Viene inoltre aggiunto un canale per ogni carico di lavoro selezionato.

> [!IMPORTANT]
> Se è già stato creato un team di distribuzione e un altro utente prova a crearlo, viene visualizzato un messaggio di errore che informa che è necessario contattare il team di supporto. Questo impedirà a Teams di rivelare inavvertitamente informazioni relative al team e ai membri esistenti. Rivolgersi al proprietario del team di distribuzione per essere aggiunti oppure contattare il supporto tecnico per ottenere assistenza.

## <a name="available-advisor-for-teams-plans"></a>Advisor disponibile per i piani di Teams

Durante la fase di anteprima di Advisor per Teams, vengono forniti i due piani seguenti:

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

È consigliabile iniziare con il piano Chat, team, canali e app. Dopo aver completato la distribuzione del carico di lavoro, tornare in Advisor per Teams e fare clic su **Aggiungi canale** per avviare il carico di lavoro successivo.

## <a name="tenant-assessment"></a>Valutazione del tenant
Ogni piano include una valutazione di conformità del tenant che è possibile usare per identificare rapidamente gli aspetti dell'ambiente che è necessario correggere prima di implementare Teams. Nelle valutazioni sono inclusi i prerequisiti e le procedure consigliate. Ogni test di valutazione avrà un segno di spunta verde o un triangolo di avviso arancione. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Un segno di spunta verde indica che il tenant ha superato il test specifico. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Un triangolo di avviso arancione indica che è consigliabile eseguire azioni di follow-up per determinare se è necessaria un'azione, ad esempio un criterio di scadenza del Gruppo di Office 365 è consigliabile ma non obbligatorio.

> [!IMPORTANT]
> Dopo che un utente con un ruolo con privilegi di amministratore avvia Advisor per Teams, tutte le valutazioni vengono eseguite in background. Se si aggiorna o corregge un elemento, è possibile che non si rifletta nelle valutazioni fino a 24 ore. Si tratta di una situazione temporanea: non appena Advisor per Teams non sarà più in anteprima ma disponibile a livello generale, le valutazioni verranno aggiornate in tempo reale.

Le sezioni seguenti descrivono le singole valutazioni, tra cui se un elemento è un prerequisito o una procedura consigliata, il modo in cui vengono eseguiti i controlli e il motivo della valutazione, nonché le indicazioni per la correzione se necessaria.

### <a name="assessment-tests-for-all-workloads"></a>Test di valutazione per i carichi di lavoro

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Dominio con reindirizzamento a microsito configurato     |Se è stato configurato un dominio non @onmicrosoft.com per il tenant, ad esempio @contoso.onmicrosoft.com. Naturalmente è possibile usare il dominio @onmicrosoft. com oppure configurare dominio con reindirizzamento a microsito, secondo l'opzione desiderata. Per altre informazioni, leggere [Aggiungere un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). |
|Licenze di Teams     |Si tratta di un prerequisito: **è necessario** avere licenze di Teams per poter distribuire Teams. Eseguire una query in Microsoft Graph per verificare se si hanno licenze di Teams e almeno una licenza disponibile da assegnare. Per altre informazioni, leggere [Licenze di Office 365 per Teams](https://docs.microsoft.com/microsoftteams/office-365-licensing).    |
|Licenze di Exchange Online     |Se si dispone di un abbonamento attivo con licenze Exchange Online disponibili. Anche se Exchange non è necessario per la funzionalità di base di Teams, l'integrazione con Exchange offre un'esperienza di Teams ottimale. Eseguire una query in Microsoft Graph per analizzare le sottoscrizioni associate al tenant e verificare se si hanno sottoscrizioni con una licenza di Exchange Online idonea e almeno una licenza disponibile da assegnare. Per altre informazioni, vedere [Modalità di interazione tra Exchange e Teams](exchange-teams-interact.md).    |
|Licenze di SharePoint Online     |Se si dispone di un abbonamento attivo con licenze SharePoint Online disponibili. È consigliabile usare le licenze SharePoint Online per utente per disporre di OneDrive for Business per l'archiviazione dei file nelle chat. Eseguire una query in Microsoft Graph per verificare se si hanno licenze di SharePoint Online e almeno una licenza disponibile da assegnare. Per altre informazioni, leggere [Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact).    |
|Accesso guest abilitato     |Se l'[accesso guest](guest-access.md) è abilitato. L'accesso guest consente di invitare utenti esterni a partecipare al proprio team. Usare l'[elenco di controllo per l'accesso guest in Teams](guest-access-checklist.md) per attivare l'accesso guest. L'elenco di controllo include le configurazioni di Azure Active Directory obbligatorie. |
|Accesso esterno configurato     |Se l'[accesso esterno](manage-external-access.md) è disattivato. Per impostazione predefinita, l'opzione è attivata con la federazione aperta. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Valutazioni per Chat, team, canali e app.

Oltre ai [test di valutazione per i carichi di lavoro](#assessment-tests-for-all-workloads), vengono eseguite le seguenti valutazioni aggiuntive per il carico di lavoro Chat, team, canali e app:

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Criteri di denominazione del Gruppo di Office 365 configurati     |Se sono stati configurati gli standard di denominazione per i Gruppi di Office 365. I criteri di denominazione per i Gruppi di Office 365 consentono all'organizzazione di applicare una strategia di denominazione coerente con i team creati dall'utente e si applica anche ad altri carichi di lavoro dei Gruppi, tra cui Outlook, SharePoint, Planner e Yammer. Questo test esegue una query in Azure AD tramite Microsoft Graph per verificare l'esistenza di criteri di denominazione validi per i Gruppi di Office 365. Per altre informazioni, leggere [Criteri di denominazione dei Gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy).    |
|Criteri di scadenza dei gruppi di Office 365 configurati     |Se i criteri di scadenza di un Gruppo sono stati definiti per i Gruppi di Office 365. Questo consente all'organizzazione di rimuovere automaticamente Teams inattivi. Per impostazione predefinita l'opzione è disattivata. Questo test esegue una query in Azure AD tramite Microsoft Graph e indica se un valore è stato modificato rispetto all'impostazione predefinita. Per altre informazioni, leggere [Criteri di scadenza dei Gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Valutazioni per messaggistica istantanea, riunioni e conferenze

Oltre ai [test di valutazione per i carichi di lavoro](#assessment-tests-for-all-workloads), vengono eseguite le seguenti valutazioni aggiuntive per il carico di lavoro della messaggistica istantanea, riunioni e conferenze:

|Test di valutazione  |Cosa indica  |
|---------|---------|
|Licenze di audioconferenza    |Se si dispone di un abbonamento attivo con licenze di audioconferenza. Si tratta di un prerequisito per la distribuzione di bridge di audioconferenza. Eseguire una query in Microsoft Graph per verificare se sono presenti licenze di audioconferenza, con almeno una licenza disponibile da assegnare. Per altre informazioni, leggere [ Licenze per i componenti aggiuntivi di Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licenze di streaming     |Se si dispone di un abbonamento attivo con licenze di Microsoft Stream. Si tratta di un prerequisito per attivare la registrazione di una riunione. Eseguire una query in Microsoft Graph per verificare se sono presenti licenze di Microsoft Stream e almeno una licenza disponibile da assegnare. Per altre informazioni su Stream e su come attivarlo, leggere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

### <a name="advisor-for-teams-bot"></a>Bot Advisor per Teams

Quando Advisor per Teams crea il team di distribuzione, il relativo bot consegna il messaggio seguente nel canale Generale:

>**Benvenuti nel team di distribuzione per Microsoft Teams.**
>  
>Lo scopo del team consiste nel guidare l'implementazione di Teams nell'organizzazione fornendo tutte le risorse necessarie e uno spazio di collaborazione per il team di progetto. Ogni canale creato con Advisor per Teams include un piano di Planner dettagliato e altre risorse, ad esempio un sondaggio utenti di Forms che può essere usato durante l’intero corso dell’implementazione. In qualsiasi momento è possibile tornare indietro e rivedere la valutazione di conformità del tenant o aggiungere altri piani di carico di lavoro usando l'interfaccia di amministrazione di Teams.
> 
>**Invito all'azione** 
>- Se non si ha familiarità con Teams o con Planner, vedere la [procedura dettagliata di Teams](https://teamsdemo.office.com/) e guardare i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Passare al team di distribuzione in Teams. Selezionare il canale del carico di lavoro, ad esempio Chat, team, canali e app, e selezionare la scheda **Planner** per iniziare.
> 
>Per altre informazioni su Advisor for Teams, vedere [Usare Advisor per Teams per distribuire Microsoft Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> Il bot di Advisor per Teams viene usato solo per inviare un messaggio di benvenuto al team di distribuzione. Non vengono raccolti altri dati.

> [!IMPORTANT]
> Il bot Advisor per Teams è attivato per impostazione predefinita. Se si usa o si prevede di usare Advisor per Teams, non disattivarlo.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quali sono i requisiti di licenza per Advisor per Teams?
Per sfruttare al meglio l'integrazione di Advisor per Teams con Forms e Planner, è necessario almeno Office 365 Business Essentials.

### <a name="can-i-delete-the-deployment-team"></a>È possibile eliminare il team di distribuzione?
Dopo che Advisor per Teams ha creato il team di distribuzione, è possibile gestire il team come qualsiasi altro team, inclusa la possibilità di eliminarlo. Tenere presente che se non si elimina il team tramite l'interfaccia di amministrazione di Teams, il team verrà visualizzato come ancora esistente nell'interfaccia di amministrazione. Si tratta di una situazione temporanea: verrà risolta quando Advisor per Teams non sarà più in anteprima e diventerà disponibile a livello generale.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>È possibile aggiungere o rimuovere canali nel team di distribuzione?
Sì, dopo aver creato il team di distribuzione i canali verranno gestiti allo stesso modo di tutti gli altri team.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>È possibile aggiungere o rimuovere membri del team di progetto nel team di distribuzione?
Sì, dopo aver creato il team di distribuzione, questo verrà gestito allo stesso modo di tutti gli altri team.

### <a name="can-i-modify-the-planner-plans"></a>È possibile modificare i piani di Planner?
Sì, dopo che Advisor per Teams ha creato il team di distribuzione, è necessario aggiornare il piano di Planner in modo che supporti al meglio l'implementazione di Teams. È possibile modificare qualsiasi elemento, ad esempio i contenitori, le attività, i dettagli delle attività, esattamente come qualsiasi altro piano di Planner.

### <a name="can-i-modify-the-forms-survey"></a>È possibile modificare il sondaggio di Forms?
Sì, dopo che Advisor per Teams ha creato il team di distribuzione, è possibile modificare il sondaggio di Forms in base alle esigenze.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quali informazioni raccoglie Advisor per Teams sull'organizzazione?
Advisor per Teams richiede il consenso per la raccolta di informazioni diverse da quelle di identificazione degli utenti finali. Le informazioni raccolte si trovano sotto forma di telemetria che fornisce un feedback a Microsoft sui risultati prodotti da Advisor per Teams e su cosa andrebbe migliorato. Questi stessi dati vengono usati per identificare opportunità per Microsoft di impegnarsi in modo proattivo con l'organizzazione in modo da facilitare la distribuzione.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>È possibile usare Advisor per Teams con FastTrack?
Sì, FastTrack supporta Advisor per Teams per tutti i clienti che vogliono distribuire Teams. Possono fornire assistenza per la configurazione iniziale del team di distribuzione con Advisor per Teams, se necessario, e forniscono inoltre supporto su misura per argomenti specifici durante l'implementazione di Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>È possibile usare Advisor per Teams con un partner?
Sì, è possibile usare Advisor per Teams avendo allo stesso tempo un partner di distribuzione per la distribuzione di Teams. Se il partner è un provider di servizi di crittografia e gestisce il tenant per conto dell'utente, può usare Advisor per Teams per creare il team di distribuzione e fornire assistenza nell'esecuzione del progetto nel suo complesso. Inoltre, è possibile collaborare con qualsiasi partner aggiungendo i singoli utenti come guest nel team di distribuzione, per consentire loro di partecipare come membri del team del progetto nel suo complesso.

### <a name="how-do-i-use-planner"></a>Come si usa Planner?
Per altre informazioni, vedere [Guida di Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) e i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 

### <a name="how-do-i-use-forms"></a>Come si usa Forms?
Passare al [Centro assistenza di Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Argomenti correlati

[Come implementare Teams](How-to-roll-out-teams.md)

[Nomi dei prodotti e identificatori dei piani di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
) 
