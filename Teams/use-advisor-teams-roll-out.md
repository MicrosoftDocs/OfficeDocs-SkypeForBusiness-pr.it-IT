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
ms.openlocfilehash: 13c76c61a99869459c0dabcffedc45e06f6fd42e
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931814"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Usare Advisor per Teams per distribuire Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor per Teams (anteprima) guida l'implementazione di Microsoft Teams. Valuta l’ambiente tenant di Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams. Quindi, Advisor per Teams crea un team di gestione dei servizi (in Teams) con canali per ogni carico di lavoro che si vuole distribuire. Ogni carico di lavoro del team di gestione dei servizi include un piano di Planner completo che include tutte le attività di implementazione per ogni carico di lavoro.  Con questo piano di Planner, si possono assegnare attività alle persone responsabili di ogni fase dell'implementazione, tra cui il project manager, gli amministratori di Teams e di Office 365, le persone di supporto e il team di adozione e conformità degli utenti. Ogni attività di implementazione contiene tutte le indicazioni e le risorse necessarie per completare correttamente l'attività.

Advisor per Teams fa parte dell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com). Per usare Advisor per Teams per la prima volta, fare clic sul pulsante **Avvia** nel widget **Distribuzione del carico di lavoro di Teams** nel Dashboard. In alternativa, passare a **Pianificazione** > **Advisor**.

> [!IMPORTANT]
> Advisor per Teams non è disponibile per le distribuzioni di Microsoft 365 Government - GCC High o DoD.

## <a name="using-advisor-for-teams-preview"></a>Usare Advisor per Teams (anteprima)

Non è necessario essere un amministratore di Teams per usare Advisor per Teams: chiunque nell'organizzazione può usarlo. Sono state configurate autorizzazioni speciali in modo che gli utenti non amministratori possano accedere ad Advisor per Teams, anche se questo si trova nell'interfaccia di amministrazione di Teams. È necessario essere un amministratore Teams, un amministratore del servizio Teams o un amministratore globale per aprire le valutazioni di conformità del tenant.

La prima volta che si usa Advisor per Teams, viene creato un team di gestione dei servizi in Teams. Aggiunge canali per ogni carico di lavoro che si vuole implementare. 


## <a name="available-advisor-for-teams-plans"></a>Advisor disponibile per i piani di Teams

Durante la fase di anteprima di Advisor per Teams, vengono forniti questi due piani:

1. Chat, team, canali e app
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms
1. Riunioni e conferenze
    - Valutazione del tenant
    - Piano di Planner, incluse le attività di adozione
    - Sondaggio utenti con Forms

È consigliabile iniziare con il piano Chat, team, canali e app. Dopo aver completato la distribuzione del carico di lavoro, tornare in Advisor e fare clic su **Aggiungi canale** per avviare il carico di lavoro successivo. 

## <a name="tenant-assessment"></a>Valutazione del tenant
Ogni piano include una valutazione di conformità del tenant che è possibile usare per identificare e correggere le eventuali carenze nell'ambiente prima di implementare Teams. Ecco cosa viene verificato a ogni valutazione:

### <a name="chat-teams-channels-and-apps"></a>Chat, team, canali e app


|Valutazione  |Cosa indica  |
|---------|---------|
|Licenze di Teams     |Se si dispone di un abbonamento attivo con licenze Teams disponibili |
|Licenze di Exchange     |Se si dispone di un abbonamento attivo con licenze Exchange Online disponibili. Anche se Exchange non è necessario per la funzionalità di base di Teams, l'integrazione con Exchange offre un'esperienza di Teams ottimale.         |
|Licenze di SharePoint Online     | Se si dispone di un abbonamento attivo con licenze SharePoint Online disponibili. È necessaria una licenza di SharePoint Online per ogni utente per l'archiviazione dei file, la collaborazione nei canali e le chat. 
|Accesso guest abilitato     |Se l'accesso guest è abilitato in Teams. Le impostazioni di Azure Active Directory per l'accesso guest non vengono riesaminate.   |
|Dominio con reindirizzamento a microsito configurato     |Se è stato configurato un dominio non @onmicrosoft.com per il tenant  |
|Standard di denominazione del gruppo di Office 365 configurato     | Se sono stati configurati standard di denominazione per i Gruppi di Office 365        |
|Criteri di scadenza dei Gruppi di Office 365 configurati     |  Se i criteri di scadenza di un gruppo sono stati definiti per i Gruppi di Office 365. In caso negativo, il valore è impostato su mai.        |
|Accesso esterno configurato     |Se l'accesso esterno è attivato, in modo da poter comunicare con organizzazioni esterne in Teams.          |

### <a name="meetings-and-conferencing"></a>Riunioni e conferenze


|Valutazione  |Cosa indica  |
|---------|---------|
|Licenze di Teams     |Se si dispone di un abbonamento attivo con licenze Teams disponibili |
|Licenze di Exchange     |Se si dispone di un abbonamento attivo con licenze Exchange Online disponibili. Anche se Exchange non è necessario per la funzionalità di base di Teams, l'integrazione con Exchange offre un'esperienza di Teams ottimale. |
|Licenze di audioconferenza    |Se si dispone di un abbonamento attivo con licenze di audioconferenza |
|Licenze di streaming     |Se si dispone di un abbonamento attivo con le licenze di streaming, che possono essere usate per la registrazione delle riunioni. |
|Accesso guest     |Se l'accesso guest è abilitato in Teams. Le impostazioni di Azure Active Directory per l'accesso guest non vengono riesaminate.|
|Dominio con reindirizzamento a microsito     |Se è stato configurato un dominio non @onmicrosoft.com per il tenant.  |
|Accesso esterno     |Se l'accesso esterno è attivato, in modo da poter comunicare con organizzazioni esterne in Teams. |


### <a name="advisor-bot"></a>Bot Advisor
Quando Advisor crea il team di gestione dei servizi, il bot Advisor rilascia il messaggio seguente.

>**Benvenuti nel team di gestione dei servizi per Microsoft Teams.**
>  
>Lo scopo del team consiste nel guidare l'implementazione di Teams nell'organizzazione fornendo tutte le risorse necessarie e uno spazio di collaborazione per il team di progetto. Ogni canale creato con Advisor per Teams include un piano di Planner dettagliato e altre risorse, ad esempio un sondaggio utenti di Forms che può essere usato durante l’intero corso dell’implementazione. In qualsiasi momento è possibile tornare indietro e rivedere la valutazione di conformità del tenant o aggiungere altri piani di carico di lavoro usando l'interfaccia di amministrazione di Teams. 
> 
>**Invito all'azione** 
>- Se non si ha familiarità con Teams o con Planner, vedere la [procedura dettagliata di Teams](https://teamsdemo.office.com/) e guardare i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Passare al team di gestione dei servizi in Teams. Selezionare il canale del carico di lavoro, ad esempio Chat, team, canali e app, e selezionare la scheda **Planner** per iniziare.
> 
>Per altre informazioni su Advisor for Teams, vedere [Usare Advisor per Teams per distribuire Microsoft Teams](use-advisor-teams-roll-out.md).
>
> [!IMPORTANT]
> Il bot di Advisor per Teams viene usato solo per inviare un messaggio di benvenuto al team di gestione dei servizi. Non vengono raccolti altri dati.

> [!IMPORTANT]
> Il bot di Advisor per Teams è abilitato per impostazione predefinita. Se si usa o si prevede di usare Advisor per Teams, non disabilitarlo.


## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quali sono i requisiti di licenza per Advisor per Teams?
Non sono previsti altri requisiti di licenza oltre l'uso della licenza per Teams.

### <a name="can-i-delete-the-service-management-team"></a>È possibile eliminare il team di gestione dei servizi?
Dopo che Advisor per Teams ha creato il team di gestione dei servizi, è possibile gestire il team come qualsiasi altro team, inclusa la possibilità di eliminarlo. Tenere presente che, se non si elimina il team tramite l'interfaccia di amministrazione di Teams, il team verrà riportato come esistente.

### <a name="can-i-add-or-remove-channels-in-the-service-management-team"></a>È possibile aggiungere o rimuovere canali nel team di gestione dei servizi?
Sì, dopo aver creato il team di gestione dei servizi i canali verranno gestiti allo stesso modo di tutti gli altri team.

### <a name="can-i-add-or-remove-project-team-members-in-the-service-management-team"></a>È possibile aggiungere o rimuovere membri del team di progetto nel team di gestione del servizio?
Sì, dopo aver creato il team di gestione dei servizi, questo verrà gestito allo stesso modo di tutti gli altri team.

### <a name="can-i-modify-the-planner-plans"></a>È possibile modificare i piani di Planner?
Sì, dopo che Advisor per Teams ha creato il team di gestione dei servizi, è necessario aggiornare il piano di Planner in modo che supporti al meglio l'implementazione di Teams. È possibile modificare qualsiasi elemento, ad esempio i contenitori, le attività, i dettagli delle attività, esattamente come qualsiasi altro piano di Planner.


### <a name="can-i-modify-the-forms-survey"></a>È possibile modificare il sondaggio di Forms?
Sì, dopo che Advisor per Teams ha creato il team di gestione dei servizi, è possibile modificare il sondaggio di Forms in base alle esigenze.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quali informazioni raccoglie Advisor per Teams sull'organizzazione?
Advisor per Teams richiede il consenso per la raccolta di informazioni diverse da quelle di identificazione degli utenti finali. Le informazioni raccolte si trovano sotto forma di telemetria che fornisce un feedback a Microsoft sui risultati prodotti da Advisor per Teams e su cosa andrebbe migliorato. Questi stessi dati vengono usati per identificare opportunità per Microsoft di impegnarsi in modo proattivo con l'organizzazione in modo da facilitare la distribuzione.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>È possibile usare Advisor per Teams con FastTrack?
Sì, FastTrack supporta Advisor per Teams per tutti i clienti che vogliono distribuire Teams. Possono fornire assistenza per la configurazione iniziale del team di gestione dei servizi con Advisor per Teams, se necessario, e forniscono inoltre supporto su misura per argomenti specifici durante l'implementazione di Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>È possibile usare Advisor per Teams con un partner?
Sì, è possibile usare Advisor per Teams avendo allo stesso tempo un partner di distribuzione per la distribuzione di Teams. Se il partner è un provider di servizi di crittografia e gestisce il tenant per conto dell'utente, può usare Advisor per Teams per creare il team di gestione dei servizi e fornire assistenza nell'esecuzione del progetto nel suo complesso. Inoltre, è possibile collaborare con qualsiasi partner aggiungendo i singoli utenti come guest nel team di gestione dei servizi, per consentire loro di partecipare come membri del team del progetto nel suo complesso.

### <a name="how-do-i-use-planner"></a>Come si usa Planner?
Per altre informazioni, vedere [Guida di Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) e i [video introduttivi di Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 

### <a name="how-do-i-use-forms"></a>Come si usa Forms?
Passare al [Centro assistenza di Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Argomenti correlati

[Come implementare Teams](How-to-roll-out-teams.md)
