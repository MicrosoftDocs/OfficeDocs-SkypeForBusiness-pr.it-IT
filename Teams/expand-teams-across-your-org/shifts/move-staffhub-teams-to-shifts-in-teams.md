---
title: Spostare i team di StaffHub in turni in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come spostare i team di Microsoft StaffHub e pianificare i dati in turni in Microsoft teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4060dae11ad90793c6124b1b37971b15437caf39
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825754"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Spostare i team di Microsoft StaffHub in turni in Microsoft Teams

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).

L'app turni in teams offre un approccio semplice per gestire le pianificazioni e il flusso costante di scambi di turni e di annullamenti che si verificano giornalmente. I membri del team possono accedere alle informazioni di programmazione e spostamento direttamente nell'app e in tutti i loro dispositivi per impostare le preferenze, gestire le pianificazioni e richiedere il tempo libero.

Questo articolo illustra come spostare i team di StaffHub dell'organizzazione e pianificare i dati in turni in teams. Copre:

- [Informazioni utili sul passaggio a teams](#what-you-need-to-know-about-the-move-to-teams)
- [Preparare](#prepare)
- [Eseguire un progetto pilota](#conduct-a-pilot) 
- [Andare oltre il pilota e trasferire tutti i team di StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Monitorare l'utilizzo di Teams](#monitor-teams-usage)
- [Risoluzione dei problemi](#troubleshooting)

Sia che si tratti di una piccola azienda con uno o due team di StaffHub o di una grande azienda con centinaia di team di StaffHub, qui sono disponibili le indicazioni per l'amministratore necessarie per facilitare la transizione ai team.

Per eseguire i passaggi di questo articolo, è necessario essere un amministratore globale. Se non lo si è già fatto, vedere le domande [frequenti sulla pensione StaffHub](microsoft-staffhub-to-be-retired.md) per ottenere le risposte a qualsiasi domanda possiate avere.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Informazioni utili sul passaggio a teams

### <a name="when-to-move-to-teams"></a>Quando si passa a teams

Efficace il 31 dicembre 2019 StaffHub sarà ritirato. Ti invitiamo a iniziare a usare teams oggi e iniziare a eseguire la transizione di team e utenti dell'organizzazione da StaffHub. La gestione della pianificazione è la caratteristica più usata in StaffHub, ti consigliamo di usare l'app turni in teams Moving Forward.

### <a name="what-is-moved-to-teams"></a>Elementi spostati in teams

Quando si sposta un team di StaffHub, i membri del team, i dettagli degli utenti, le pianificazioni del team e i dati della chat vengono spostati in teams. I file non vengono spostati quando si sposta un team di StaffHub. Se un team di StaffHub contiene file che si vuole anche trasferire in teams, è possibile trasferire i file in un passaggio separato.

Ogni team di StaffHub ha bisogno di un gruppo di Office 365 corrispondente. Se un team di StaffHub è associato a un gruppo di Office 365, l'impostazione della privacy del gruppo viene mantenuta quando si trasferisce il team. Se a un team di StaffHub non è associato un gruppo di Office 365, viene automaticamente creato un gruppo con l'impostazione di privacy private per supportare la transizione.  Considerata la differenza tra team e nomi di gruppo tra team e StaffHub, è possibile che venga visualizzato un nome di team diverso in teams. 

Durante la transizione da Teams da StaffHub a teams, gli utenti non avranno più accesso alle loro pianificazioni in StaffHub e verranno reindirizzati ai turni in teams. È consigliabile comunicare questo cambiamento nell'organizzazione per ridurre al minimo le interruzioni e incoraggiare gli utenti ad adottare ed esplorare team. Se si dispone di Azure AD Premium, è possibile [eseguire un report](run-report-to-show-staffhub-usage.md) per ottenere un elenco di utenti di StaffHub nell'organizzazione che devono conoscere la modifica.  

Non è possibile eseguire l'opzione rollback dopo avere spostato un team di StaffHub in teams.

### <a name="user-experience-when-you-move-a-team"></a>Esperienza utente quando si trasferisce un team

Ci sono tempi di inattività minimi (meno di un secondo, se presenti) per gli utenti quando il loro team è passato da StaffHub a turni in teams. Gli utenti possono continuare a usare StaffHub fino al completamento del passaggio a teams. Al termine dello spostamento, i membri del team vedranno un messaggio per comunicare loro che devono iniziare a usare i turni in teams per accedere alla pianificazione del team. Ecco un esempio del messaggio visualizzato dagli utenti in StaffHub dopo che il team di StaffHub è stato spostato in teams.

![Esempio di messaggio visualizzato dagli utenti.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Esempio di messaggio visualizzato dagli utenti in StaffHub dopo lo spostamento del team di StaffHub in teams")

## <a name="prepare"></a>Preparare

Ecco come prepararsi per il passaggio a teams.

### <a name="check-that-prerequisites-are-met"></a>Verificare che i prerequisiti vengano soddisfatti

Prima di trasferire un team di StaffHub in teams, verificare che:

- L'utente connesso è un amministratore globale.
- Teams è abilitato per tutti gli utenti del tenant.
- La creazione di gruppi di Office 365 è abilitata nel tenant.
- StaffHub teamId è valido.
- Il team di StaffHub ha almeno un proprietario del team.
- Il team di StaffHub contiene membri.
- Tutti i membri del team di StaffHub sono collegati a un account Azure AD.
- A tutti i membri del team di StaffHub è assegnata una licenza teams.  

Se questi prerequisiti non sono soddisfatti, la richiesta di trasferimento avrà esito negativo.

### <a name="assign-teams-licenses"></a>Assegnare licenze di Teams

Ogni utente deve avere una licenza Microsoft 365 o Office 365 attiva da [un piano idoneo](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve essere assegnata una licenza di teams. L'assegnazione di una licenza di teams agli utenti consente loro di accedere ai team.

È possibile gestire le licenze teams nell'interfaccia di amministrazione di Microsoft 365. Per altre informazioni, vedere [gestire l'accesso degli utenti ai team](../../user-access.md).

> [!NOTE]
> Se l'organizzazione usa Skype for business e non si è pronti per trasferire tutti gli utenti in teams, è possibile abilitare i team per i dipendenti di I FIRSTLINE che possono quindi eseguire teams insieme a Skype for business. In questa modalità di coesistenza, denominata *Islands*, ogni app client funziona come soluzione separata. Per altre informazioni, vedere [comprendere i team e la coesistenza e l'interoperabilità di Skype for business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>Installare la versione prerelease del modulo di PowerShell StaffHub

Se non è già stato installato, [installare la versione prerelease del modulo di PowerShell StaffHub](install-the-staffhub-powershell-module.md).

Per trasferire i team di StaffHub in teams, è necessario che sia installata la versione del modulo prerelease.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>Collegare un account di Azure AD per i membri del team di StaffHub che non ne hanno uno

Ogni membro del team di StaffHub deve essere collegato a un account di Azure Active Directory (Azure AD). Gli utenti dell'organizzazione non saranno collegati a un account di Azure AD se si applica uno degli scenari seguenti:

- Un proprietario del team ha aggiunto un utente che non dispone di un account Azure AD.
- Un proprietario del team ha invitato un utente a un team di StaffHub e l'utente non ha accettato l'invito.

Questi utenti hanno account inattivi e mostrano uno stato utente di sconosciuto, invitato o InviteRejected. Puoi collegare un account di Azure AD per questi utenti.  Ecco come fare.

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>Ottenere un elenco di tutti gli account inattivi nei team di StaffHub

Eseguire la serie di comandi seguente per ottenere un elenco di tutti gli account inattivi nei team di StaffHub ed esportare l'elenco in un file CSV. Ogni comando deve essere eseguito separatamente.

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>Collegare l'account

Esegui una delle operazioni seguenti:

- Convertire e collegare l'account.

  I proprietari e i responsabili del team di StaffHub possono convertire un account inattivo e collegarlo a un account di Azure AD in StaffHub modificando l'indirizzo di posta elettronica dell'utente in un UPN valido nella pagina delle impostazioni del team di StaffHub.

- Rimuovere l'account non collegato e quindi aggiungere di nuovo l'account usando l'UPN.
    1. Eseguire il cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) per rimuovere l'account non provisioning dal team di StaffHub.
    2. Eseguire il cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) per aggiungere di nuovo l'account al team di StaffHub usando l'UPN.

- Rimuovere l'account inattivo. Usare questa opzione se l'account utente non è più necessario.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti

Teams include un criterio di configurazione dell'app FirstlineWorker incorporato che puoi usare per personalizzare i team per evidenziare le app più importanti per gli operatori di I FIRSTLINE dell'organizzazione. Quando si assegna questo criterio agli utenti, le app del criterio vengono aggiunte alla barra dell'app in teams per un accesso rapido e semplice. Altre app aggiunte a teams possono essere trovate nella barra dell'app facendo clic su **... Altre app** nei client desktop e Web teams e scorrendo rapidamente verso l'alto nel client per dispositivi mobili teams. Per impostazione predefinita, i criteri di configurazione dell'app FirstlineWorker includono le app attività, turni, chat e chiamate.

Per istruzioni su come assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti, vedere [usare i criteri di configurazione dell'app FirstlineWorker per aggiungere i turni ai team](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Dopo aver assegnato un criterio, possono essere necessarie fino a 24 ore per avere effetto.

È consigliabile completare questo passaggio almeno una settimana prima di trasferire i team e gli utenti di StaffHub in teams. Quando gli utenti si trovano in teams, verificare che possano vedere e accedere all'app turni.

Puoi anche creare criteri di configurazione delle app personalizzati e modificare le impostazioni nel criterio di configurazione dell'app globale. Per altre informazioni, vedere [gestire i criteri di configurazione delle app in teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Utenti a bordo di Teams

Come parte della strategia di onboarding, fornisci formazione e indicazioni agli utenti per aiutarli a familiarizzare con i team. Condividere le risorse seguenti con gli utenti in modo che sappiano dove ottenere i client, la formazione e il supporto per i team:

- [Client Web di Teams](https://teams.microsoft.com)
- [Collegamenti per il download dei client desktop e per dispositivi mobili](https://teams.microsoft.com/downloads)
- [Video di formazione su Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentazione della Guida di Teams](https://support.office.com/teams)

Per istruzioni sulla distribuzione di team e sull'adozione di team di guida, vedere [come implementare](../../How-to-roll-out-teams.md) teams e [adottare teams](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Eseguire un progetto pilota

Ti consigliamo di iniziare spostando due o tre team di StaffHub per un gruppo selezionato di early adopters. L'uso di un pilota consente di affinare il piano di transizione e di essere pronti per trasferire tutti i team di StaffHub dell'organizzazione in teams. Identifica inoltre campioni che possono aiutare l'adozione delle unità nell'organizzazione. Se si è una piccola impresa che non ha bisogno di un approccio graduale, la procedura descritta in questa sezione può essere sufficiente per passare da StaffHub a teams.

### <a name="identify-pilot-teams"></a>Identificare team pilota

Individuare due o tre team pilota. Tutti i membri del team devono impegnarsi per l'uso di turni in teams per gestire le pianificazioni e comunicare e collaborare tra loro.

### <a name="identify-team-champions"></a>Identificare i campioni del team

Identificare i campioni in team pilota e arruolarli per favorire l'evangelizzazione degli spostamenti. I Team Champions sono appassionati di quello che fanno, condividono le proprie informazioni per offrire supporto e indicazioni ai membri del team. I Team Champions possono essere proprietari o responsabili del team.

I Team Champions devono garantire che i membri del team siano configurati dedicando tempo a tutti per [ottenere i clienti](../../get-clients.md)dei team, accedere a teams e verificare i loro programmi in turni e iniziare a chattare tra di loro. Gli utenti che hanno già familiarità con StaffHub saranno operativi rapidamente in turni. È anche possibile scegliere di [spostare la guida](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) per ulteriori informazioni.

### <a name="move-a-staffhub-team"></a>Trasferire un team di StaffHub

Seguire questi passaggi per trasferire un team di StaffHub alla volta. È consigliabile questo approccio per i team pilota. In seguito, quando si è pronti a trasferire tutti i team di StaffHub dell'organizzazione, vedere [trasferire i](#move-your-staffhub-teams) team di StaffHub per la procedura per la migrazione di più team alla volta.

Eseguire la procedura seguente per trasferire un team di StaffHub.

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
Esempio

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Ecco un esempio della risposta che ricevi quando invii una richiesta per trasferire un team di StaffHub in teams.

```output
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Per controllare lo stato di una richiesta di trasferimento, eseguire la procedura seguente.

```PowerShell
Get-TeamMigrationJobStatus <String>
```
Esempio

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Ecco un esempio della risposta che si ottiene quando è in corso una manovra.

```output
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Trasferire i file da un team di StaffHub a teams

Questo passaggio si applica solo se il team di StaffHub spostato in teams contiene file che si desidera spostare anche in teams. È possibile trasferire i file direttamente in SharePoint Online o usando PowerShell.

#### <a name="in-sharepoint-online"></a>In SharePoint Online

Informazioni [su come trasferire file in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Utilizzo di PowerShell

Scaricare e installare [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), se non è già stato fatto. Contiene i cmdlet necessari per trasferire i file.  

Utilizzare il cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) per connettersi al sito del team di SharePoint Online.

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Per ogni file che si vuole trasferire da StaffHub a teams, usare il cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) per trasferire il file.

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Per spostarsi di più file, eseguire il loop sui file e il secondo comando nel ciclo. Se la sessione rimane attiva, non è necessario ripetere il primo comando.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Andare oltre il pilota e trasferire tutti i team di StaffHub

### <a name="raise-awareness"></a>Aumentare la consapevolezza

Quando si è pronti per superare le squadre pilota e spostare i team di StaffHub dell'organizzazione in teams, è importante comunicare prima di tutto la modifica all'interno dell'organizzazione. Diffondere la parola sui turni e la transizione ai team per sensibilizzare, generare emozioni e guidare l'adozione.

### <a name="move-your-staffhub-teams"></a>Trasferire i team di StaffHub

Seguire questa procedura per trasferire i team di StaffHub in blocco. Puoi scegliere di trasferire tutti i team di StaffHub dell'organizzazione o di trasferire specifici team di StaffHub. Se si vuole trasferire StaffHub teams uno alla volta, vedere [trasferire un team di StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Trasferire tutti i team di StaffHub

Eseguire la procedura seguente per ottenere un elenco di tutti i team di StaffHub dell'organizzazione.

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

Eseguire quindi le operazioni seguenti per trasferire tutti i team.

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Ecco un esempio della risposta.

Per tutti i team già spostati in teams o già presenti in teams, il jobId sarà "null" perché non è necessario inviare un processo per spostare il team.

```output
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Trasferimento di team di StaffHub specifici

Eseguire la procedura seguente per ottenere un elenco di tutti gli ID del team di StaffHub nell'organizzazione.

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Nei risultati restituiti dal `Get-StaffHubteamsForTenant` cmdlet eseguito in precedenza selezionare gli ID del team che si desidera trasferire e quindi aggiungerli a un file con valori separati da virgola (CSV).

Ecco un esempio di come formattare il file CSV.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497F-a8a5-1c0708475e5f<br>TEAM_81b1f191-3E19-45ce-AB32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Dopo aver creato il file CSV, eseguire la procedura seguente per trasferire i team specificati nel file CSV.

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Verificare che i team di StaffHub siano stati spostati in teams

Eseguire la procedura seguente per ottenere un elenco di tutti i team in turni nell'organizzazione. 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Trasferire i file dai team di StaffHub in teams

Se i team di StaffHub spostati contengono file che si vuole spostare anche in teams, vedere [spostare i file da un team di StaffHub a teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Monitorare l'utilizzo di Teams

I report sull'utilizzo consentono di comprendere meglio i modelli di utilizzo e di fornire informazioni dettagliate su dove assegnare priorità agli sforzi di formazione e comunicazione nell'organizzazione. È possibile eseguire report che mostrano l'utilizzo complessivo dei team, i tipi di attività che gli utenti eseguono in team, il modo in cui gli utenti si connettono ai team e altro ancora. Per altre informazioni, vedere [segnalazione di team nell'interfaccia di amministrazione di Microsoft teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [report attività in teams nell'interfaccia di amministrazione di Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Come ottenere ulteriori informazioni sugli errori di errore**

Eseguire la procedura seguente per ottenere altre informazioni sugli errori di "errore" che si verificano quando si tenta di trasferire un team:

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

Verrà visualizzato uno degli Stati seguenti restituiti: Success, Failure, InProgress, queued.

Se viene restituito "errore", eseguire le operazioni seguenti per ottenere altre informazioni sull'errore:

```PowerShell
$res.Result.Error.Innererror
```

**Quando si prova a trasferire un team di StaffHub, lo stato viene visualizzato come "errore" e viene visualizzato il messaggio di errore "Impossibile recuperare le categorie di SKU applicabili per l'utente"**

Questo problema può verificarsi se uno o più membri del team non hanno una licenza teams. Accedere a portal.office.com, individuare il gruppo e quindi verificare che ai membri del gruppo sia assegnata una licenza teams.

**Quando si prova a trasferire un team di StaffHub, lo stato viene visualizzato come "errore" e viene visualizzato un messaggio di errore "proprietario del team non trovato"**

Questo problema può verificarsi se il gruppo associato al team di StaffHub non ha un proprietario del team. Accedere a portal.office.com, individuare il gruppo e quindi aggiungere uno o più proprietari al gruppo.

**Quando si prova a trasferire i file da StaffHub a teams, viene visualizzato il messaggio di errore "autorizzazione negata".**

Questo problema può verificarsi se si sta provando a trasferire file in un gruppo di Office 365 privato di cui non si è membri. In questo caso, usa il cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) per aggiungerti al team di StaffHub e quindi sposti i file. Dopo aver spostato i file, usare il cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) per rimuoversi dal team. 

**Quando si prova a trasferire i file da StaffHub a teams, viene visualizzato un messaggio di errore che indica che la cartella generale non esiste.**

Eseguire il comando seguente per aggiungere la cartella generale a SharePoint e riprovare:

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Argomenti correlati
- [Come implementare Microsoft Teams](../../How-to-roll-out-teams.md)
- [Ritiro di Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Gestire l'app turni per l'organizzazione in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Riferimento a PowerShell di StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
