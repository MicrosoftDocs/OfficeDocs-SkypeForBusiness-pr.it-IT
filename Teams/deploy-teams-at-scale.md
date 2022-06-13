---
title: Distribuire i team su vasta scala per gli operatori in prima linea in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come distribuire i team su vasta scala per gli operatori in prima linea nell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046025"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Distribuire i team su vasta scala per gli operatori in prima linea in Microsoft Teams

> [!NOTE]
> Questa funzionalità è attualmente in anteprima privata. Se desideri partecipare all'anteprima privata, contattaci [all'dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Panoramica
 
L'organizzazione può avere molti team che si usano per promuovere la comunicazione e la collaborazione tra la forza lavoro in prima linea, che si trovano in diversi punti vendita, sedi e ruoli. Attualmente, non esiste una soluzione semplice per distribuire, configurare e gestire questi team e utenti su vasta scala.

Stiamo creando una soluzione per consentire agli amministratori di distribuire e gestire i team su vasta scala.

Ecco una panoramica delle funzionalità attualmente disponibili per la creazione e la gestione di un numero elevato di team alla volta e di ciò che stiamo pianificando per il prossimo futuro.

||Disponibile oggi |Più tardi nel 2022  |
|---------|---------|---------|
|**Numero di team che è possibile creare per batch**|Fino a 100 |Fino a 500|
|**Numero di utenti che è possibile aggiungere per team**|Fino a 25|Fino a 25|

La distribuzione dei team su vasta scala consente di:

- Creare team usando modelli predefiniti o modelli personalizzati.
- Aggiungere utenti ai team come proprietari o membri.
- Gestire i team su vasta scala aggiungendo o rimuovendo utenti dai team esistenti.
- È possibile ricevere una notifica tramite posta elettronica, inclusi il completamento, lo stato e gli eventuali errori. È possibile scegliere di inviare una notifica a un massimo di cinque persone sullo stato di ogni batch di team distribuito. I proprietari e i membri del team ricevono automaticamente una notifica quando vengono aggiunti a un team.

## <a name="how-to-deploy-teams-at-scale"></a>Come distribuire i team su vasta scala

> [!NOTE]
> Prima di distribuire i team, assicurarsi che tutti i proprietari dei team abbiano una licenza di Teams.

Seguire questa procedura per distribuire un numero elevato di team alla volta.

### <a name="step-1-prepare-your-csv-files"></a>Passaggio 1: Preparare i file CSV

È necessario creare due file CSV per ogni batch di team da distribuire:

- **Un file CSV che definisce i team che si stanno creando**. Questo file deve contenere queste colonne obbligatorie, nell'ordine seguente, a partire dalla prima colonna:

    |Nome colonna  |Descrizione  |
    |---------|---------|
    |**Nome team**|Il nome del team.|
    |**ID team esistente**|Se si stanno aggiungendo o rimuovendo utenti da un team esistente, specificare l'ID del team.|
    |**Visibilità**|Se il team è pubblico (chiunque nell'organizzazione può partecipare) o privato (gli utenti devono ottenere l'approvazione dei proprietari del team per partecipare). Le opzioni sono **Pubblico** e **Privato**.|
    |**ID modello team**|Se si sta creando un team da un modello predefinito o personalizzato, specificare l'ID del modello di team. Per un elenco di modelli di team e ID predefiniti, vedere [Attività iniziali con i modelli di team nell'interfaccia di amministrazione di Teams](get-started-with-teams-templates-in-the-admin-console.md). Se si vuole usare il modello di team predefinito standard, lasciare vuoto questo modello.|

- **Un file CSV che associa gli utenti che si stanno aggiungendo a ogni team**. Questo file deve contenere queste colonne obbligatorie, nell'ordine seguente, a partire dalla prima colonna:

    |Nome colonna  |Descrizione  |
    |---------|---------|
    |**Nome e cognome utente**|Nome visualizzato dell'utente.|
    |**UPN o ID utente**|Nome dell'entità utente (UPN) o ID dell'utente. Ad esempio, averyh@contoso.com.|
    |**Nome team**|Il nome del team.|
    |**ActionType**|Sia che tu stia aggiungendo o rimuovendo l'utente dal team. Le opzioni sono **AggiungiMember** e **RemoveMember**.|
    |**Proprietario o membro**|Se l'utente è proprietario del team o membro del team. Le opzioni sono **Proprietario** e **Membro**.|

#### <a name="examples"></a>Esempi

Usare gli esempi seguenti per creare i file CSV. Qui abbiamo denominato i file, Teams.csv e Users.csv.

**Teams.csv**

|Nome team|ID team esistente|Visibilità|ID modello team|
|---------|---------|---------|---------|
|Contoso Store 1||Pubblico|com.microsoft.teams.template.retailStore|
|Contoso Store 2||Pubblico|com.microsoft.teams.template.retailStore|
|Contoso Store 3||Pubblico|com.microsoft.teams.template.retailStore|
|Contoso Store 4||Pubblico|com.microsoft.teams.template.retailStore|
|Contoso Store 5||Pubblico|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||Pubblico|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||Pubblico||
|Contoso Store 8||Privato|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||Privato|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||Privato|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Nome e cognome utente |UPN o ID utente|Nome team|ActionType|Proprietario o membro|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Store 1|Aggiungi membro|Proprietario|
|Casey Jensen|caseyj@contoso.com|Contoso Store 2|Aggiungi membro|Proprietario|
|Jessie Irwin|jessiei@contoso.com|Contoso Store 3|Aggiungi membro|Proprietario|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Store 4|Aggiungi membro|Proprietario|
|Mikaela Lee|mikaelal@contoso.com|Contoso Store 5|Aggiungi membro|Proprietario|
|Morgan Conners|morganc@contoso.com|Contoso Store 6|Aggiungi membro|Membro|
|Oscar Ward|oscarw@contoso.com|Contoso Store 7|Aggiungi membro|Membro|
|Rene Pelletier|renep@contoso.com|Contoso Store 8|Aggiungi membro|Membro|
|Sydney Mattos|sydneym@contoso.com|Contoso Store 9|Aggiungi membro|Membro|
|Violet Martinez|violetm@contoso.com|Contoso Store 10|Aggiungi membro|Membro|

### <a name="step-2-deploy-your-teams"></a>Passaggio 2: Distribuire i team

Dopo aver creato i file CSV, è possibile configurare l'ambiente e distribuire i team.

Si usa il ```New-CsBatchTeamsDeployment``` cmdlet per inviare un batch di team da creare. Per ogni batch viene generato un ID di orchestrazione. È quindi possibile usare il ```Get-CsBatchTeamsDeployment``` cmdlet per tenere traccia dello stato e dello stato di ogni batch.

1. Installare PowerShell versione 7 o successiva. Per indicazioni dettagliate, vedere [Installazione di PowerShell in Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Eseguire PowerShell in modalità amministratore.
1. Eseguire le operazioni seguenti per disinstallare qualsiasi modulo di PowerShell installato in precedenza Teams.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Se viene visualizzato un messaggio di errore, l'impostazione è già stata impostato. Procedere con il passaggio successivo.
1. Scaricare e installare [l'ultima versione del modulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Eseguire le operazioni seguenti per connettersi a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando richiesto, accedere con le credenziali di amministratore.

1. Eseguire le operazioni seguenti per ottenere un elenco dei comandi nel modulo Teams PowerShell.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Verifica che e ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` siano elencati.

1. Eseguire quanto segue per distribuire un batch di team. In questo comando è possibile specificare il percorso dei file CSV e gli indirizzi di posta elettronica di un massimo di cinque destinatari per notificare la distribuzione.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Ad esempio:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    I destinatari riceveranno notifiche tramite posta elettronica sullo stato della distribuzione. Il messaggio di posta elettronica contiene l'ID di orchestrazione per il batch inviato e gli eventuali errori.

1. Eseguire le operazioni seguenti per verificare lo stato del batch inviato.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Inviaci il tuo feedback

Apprezziamo il tuo feedback. Usabilità, affidabilità, prestazioni&mdash;, benvenuto tutto!

Invia [dscale@microsoft.com](mailto:dscale@microsoft.com) e includi l'ID di orchestrazione e il file di errore, se disponibile.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica di Teams PowerShell](teams-powershell-overview.md)
