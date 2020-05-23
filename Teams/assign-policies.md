---
title: Assegnare i criteri agli utenti in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Scopri i diversi modi per assegnare i criteri agli utenti in Microsoft teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: aa63a0cc7ce24390228cc9d87adf054348c6522d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350040"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Assegnare i criteri agli utenti in Microsoft Teams

> [!NOTE]
> **Una delle caratteristiche di Microsoft teams discusse in questo articolo, [assegnazione dei criteri ai gruppi](#assign-a-policy-to-a-group), è attualmente disponibile solo in anteprima privata. I cmdlet di PowerShell per questa funzionalità si trovano nel modulo di PowerShell per i team pre-release.** Per rimanere in primo piano sullo stato di rilascio di questa funzionalità, vedere la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).

Come amministratore, puoi usare i criteri per controllare le caratteristiche dei team disponibili per gli utenti dell'organizzazione. Ad esempio, esistono criteri per la chiamata, criteri per le riunioni e criteri di messaggistica, per citarne solo alcuni.

Le organizzazioni hanno diversi tipi di utenti con esigenze esclusive e criteri personalizzati creati e assegnati consentono di adattare le impostazioni dei criteri a diversi set di utenti in base a tali esigenze.

Per semplificare la gestione dei criteri nell'organizzazione, teams offre diversi modi per assegnare i criteri agli utenti. È possibile assegnare un criterio direttamente agli utenti, singolarmente o in scala, tramite un'assegnazione batch o a un gruppo di cui l'utente è membro. Puoi anche usare i pacchetti di criteri per assegnare una raccolta preimpostata di criteri agli utenti dell'organizzazione che hanno ruoli simili. L'opzione scelta dipende dal numero di criteri che si stanno gestendo e dal numero di utenti a cui si sta assegnando.

In questo articolo vengono illustrati i diversi modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per quando usare cosa.

## <a name="which-policy-takes-precedence"></a>Quali criteri hanno la precedenza?

Un utente ha un criterio effettivo per ogni tipo di criterio. È possibile o anche probabile che a un utente venga assegnato direttamente un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo. In questi tipi di scenari, quali criteri hanno la precedenza?  I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.

Se a un utente viene assegnato direttamente un criterio (individualmente o tramite un'assegnazione batch), tale criterio avrà la precedenza. Nell'esempio seguente, il criterio effettivo dell'utente è il criterio riunione di Lincoln Square, che viene direttamente assegnato all'utente.

![Diagramma che mostra il modo in cui un criterio assegnato direttamente ha la precedenza](media/assign-policies-example-directly-assigned.png)

Se un utente non viene assegnato direttamente a un criterio di un tipo specificato, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza. Se un utente è un membro di più gruppi, il criterio con la classificazione delle [assegnazioni di gruppo](#group-assignment-ranking) più alta per il tipo di criteri specifico ha la precedenza.

In questo esempio, i criteri effettivi dell'utente sono i team Exec e i criteri HD, che hanno il ranking di assegnazione più alto rispetto ad altri gruppi a cui l'utente fa parte e a cui sono assegnati anche i criteri dello stesso tipo di criteri.  

![Diagramma che mostra il modo in cui un criterio ereditato dal gruppo ha la precedenza](media/assign-policies-example-group.png)

Se a un utente non viene assegnato un criterio o non è un membro di un gruppo a cui è assegnato un criterio, l'utente otterrà il criterio globale (a livello di organizzazione) per il tipo di criteri. Ecco un esempio.

![Diagramma che mostra il modo in cui prevale un criterio globale](media/assign-policies-example-global.png)

Per altre informazioni, Vedi [regole di precedenza](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Modalità di assegnazione di criteri

Ecco una panoramica dei modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per ognuno. Fare clic sui collegamenti per altre informazioni.

|Operazione da eseguire  |Se...  | Uso di...
|---------|---------|----|
|[Assegnare un criterio a singoli utenti](#assign-a-policy-to-individual-users)    | Si è nuovi team e si è appena iniziato o si deve solo assegnare uno o due criteri a un numero limitato di utenti. |L'interfaccia di amministrazione di Microsoft teams o i cmdlet di PowerShell nel modulo di PowerShell Skype for business online
| [Assegnare un pacchetto di criteri](#assign-a-policy-package)   | È necessario assegnare più criteri a specifici set di utenti dell'organizzazione che hanno ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (Teacher) agli insegnanti della scuola per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e al pacchetto di criteri per l'istruzione (studente della scuola secondaria) agli studenti secondari per limitare alcune funzionalità come le chiamate private.  |Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams|
|[Assegnare un criterio a un gruppo di utenti](#assign-a-policy-to-a-batch-of-users)   | È necessario assegnare criteri a set di utenti di grandi dimensioni. Ad esempio, si vuole assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione alla volta.  |Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams|
|[Assegnare un criterio a un gruppo](#assign-a-policy-to-a-group) (in anteprima)   |È necessario assegnare criteri in base all'appartenenza al gruppo di un utente. Ad esempio, si vuole assegnare un criterio a tutti gli utenti in un gruppo di sicurezza o in un'unità organizzativa.| Cmdlet di PowerShell nel modulo di PowerShell Teams|
| [Assegnare un pacchetto di criteri a un gruppo di utenti](#assign-a-policy-package-to-a-batch-of-users)|È necessario assegnare più criteri a un gruppo di utenti dell'organizzazione che hanno ruoli uguali o simili. Ad esempio, assegna il pacchetto di criteri Education (Teacher) a tutti gli insegnanti dell'Istituto di istruzione usando l'assegnazione batch per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e assegnare il pacchetto di criteri per l'istruzione (studente di scuola secondaria) a un gruppo di studenti secondari per limitare alcune funzionalità come le chiamate private.|Cmdlet di PowerShell nel modulo di PowerShell Teams|
| Assegnare un pacchetto di criteri a un gruppo (disponibile a breve)   | ||

## <a name="assign-a-policy-to-individual-users"></a>Assegnare un criterio a singoli utenti

Seguire questa procedura per assegnare un criterio a un singolo utente o a un numero limitato di utenti alla volta.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Selezionare il criterio che si vuole assegnare e quindi fare clic su **applica**.

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa alla pagina dei criteri.
2. Selezionare il criterio che si vuole assegnare facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Al termine dell'aggiunta di utenti, selezionare **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Ogni tipo di criterio include il proprio set di cmdlet per la gestione. Usa il ```Grant-``` cmdlet per un tipo di criteri specifico per assegnare i criteri. Ad esempio, usa il ```Grant-CsTeamsMeetingPolicy``` cmdlet per assegnare un criterio di riunione teams agli utenti. Questi cmdlet sono inclusi nel modulo di PowerShell per Skype for business online e sono documentati nella Guida di [riferimento ai cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

 Scaricare e installare il [modulo di PowerShell per Skype for business online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (se non è già stato fatto), quindi eseguire le operazioni seguenti per connettersi a Skype for business online e avviare una sessione.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

In questo esempio, assegniamo un criterio riunione teams denominato criteri riunione studenti a un utente di nome Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Per altre informazioni, vedere [gestione dei criteri tramite PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).

## <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

Un pacchetto di criteri in teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli uguali o simili nell'organizzazione. Ogni pacchetto di criteri è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche di tale ruolo. Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Worker clinico).

Quando si assegna un pacchetto di criteri agli utenti, i criteri del pacchetto vengono creati e quindi è possibile personalizzare le impostazioni di ogni criterio nel pacchetto per soddisfare le esigenze degli utenti.

Per altre informazioni sui pacchetti di criteri, tra cui indicazioni dettagliate su come assegnarle e gestirle, vedere gestire i [pacchetti di criteri in teams](manage-policy-packages.md).

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare un criterio a un gruppo di utenti

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

Per assegnare un criterio agli utenti in blocco:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**.
2. Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per mostrare gli utenti desiderati.
3. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
4. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.

Per visualizzare lo stato dell'assegnazione dei criteri, nell'intestazione visualizzata nella parte superiore della pagina **utenti** dopo aver fatto clic su **applica** per inviare l'assegnazione di criteri, fare clic su **Registro attività**. Oppure, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard**e quindi in **Registro attività**fare clic su **Visualizza dettagli**. Il registro attività Mostra le assegnazioni dei criteri ai batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams degli ultimi 30 giorni. Per altre informazioni, vedere [visualizzare le assegnazioni dei criteri nel registro attività](activity-log.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell
 
Con l'assegnazione di criteri batch è possibile assegnare un criterio a set di utenti di grandi dimensioni alla volta senza dover usare uno script. Puoi usare il ```New-CsBatchPolicyAssignmentOperationd``` cmdlet per inviare un batch di utenti e i criteri che vuoi assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. Puoi quindi usare il ```Get-CsBatchPolicyAssignmentOperation``` cmdlet per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.

Un batch può contenere fino a 20.000 utenti. È possibile specificare gli utenti in base all'ID oggetto, al nome dell'entità utente (UPN), all'indirizzo SIP (Session Initiation Protocol) o all'indirizzo di posta elettronica.

> [!IMPORTANT]
> Attualmente consigliamo di assegnare criteri in batch di utenti di 5.000 alla volta. Durante questi periodi di maggiore domanda, potresti riscontrare ritardi nei tempi di elaborazione. Per ridurre al minimo l'impatto di questi tempi di elaborazione più elevati, ti consigliamo di inviare dimensioni batch più piccole fino a utenti di 5.000 e inviare ogni batch solo dopo il completamento di quello precedente. L'invio di batch all'esterno dell'orario di lavoro normale può anche essere utile.

> [!NOTE]
> Attualmente, l'assegnazione di criteri batch non è disponibile per tutti i tipi di criteri teams. Vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

Eseguire la procedura seguente per installare il [modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando viene richiesto, accedere con le credenziali di amministratore.

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installare e connettersi a Azure AD PowerShell per modulo grafico (facoltativo)

Puoi anche [scaricare e installare Azure ad PowerShell per il modulo grafico](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se non lo hai già fatto) e connetterti AD Azure ad in modo da poter recuperare un elenco di utenti nell'organizzazione.

Eseguire la procedura seguente per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ai team.

### <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare un criterio a un gruppo di utenti

In questo esempio usiamo il ```New-CsBatchPolicyAssignmentOperation``` cmdlet per assegnare un criterio di configurazione dell'app denominato criteri di configurazione dell'app HR a un batch di utenti elencati nel file Users_ids. Text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In questo esempio, ci connettiamo ad Azure AD per recuperare una raccolta di utenti e quindi assegnare un criterio di messaggistica denominato nuovi criteri di messaggistica di noleggio a un batch di utenti specificato tramite il proprio UPN.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

Per altre informazioni, vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Ottenere lo stato di un'assegnazione batch

Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

**L'assegnazione dei criteri ai gruppi è attualmente disponibile solo in anteprima privata. I cmdlet per questa funzionalità si trovano nel modulo di PowerShell per i team pre-release.**

L'assegnazione dei criteri a gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o un'unità organizzativa. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando i membri vengono aggiunti o rimossi da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

Puoi usare il ```New-CsGroupPolicyAssignment``` cmdlet per assegnare un criterio a un gruppo. Puoi specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.

Quando si assegna il criterio, viene immediatamente assegnato al gruppo. Si noti tuttavia che la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non viene assegnato da un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi non è disponibile per tutti i tipi di criteri teams. Vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Informazioni utili sull'assegnazione dei criteri ai gruppi

Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni di gruppo.

#### <a name="precedence-rules"></a>Regole di precedenza

Per un determinato tipo di criteri, il criterio effettivo di un utente viene determinato in base alle condizioni seguenti:

- Un criterio assegnato direttamente a un utente ha la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo. In altre parole, se a un utente viene assegnato direttamente un criterio di un tipo specifico, l'utente non erediterà un criterio dello stesso tipo da un gruppo. Ciò significa anche che, se un utente ha un criterio di un tipo specifico a cui è stato assegnato direttamente, è necessario rimuovere i criteri dall'utente prima che possano ereditare un criterio dello stesso tipo da un gruppo.
- Se un utente non ha un criterio direttamente assegnato ed è un membro di due o più gruppi e ogni gruppo ha un criterio dello stesso tipo assegnato, l'utente eredita i criteri dell'assegnazione del gruppo con la classificazione più alta.
- Se un utente non è un membro di tutti i gruppi a cui è assegnato un criterio, il criterio globale (a livello di organizzazione predefinita) per tale tipo di criteri si applica all'utente.

I criteri effettivi di un utente vengono aggiornati in base a queste regole quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio, un criterio non è assegnato da un gruppo o viene rimosso un criterio direttamente assegnato all'utente.

#### <a name="group-assignment-ranking"></a>Classificazione delle assegnazioni di gruppo
 
Quando si assegna un criterio a un gruppo, è necessario specificare una classificazione per l'assegnazione del gruppo. Viene usato per determinare i criteri che un utente deve ereditare come criterio effettivo se l'utente è un membro di due o più gruppi e a ogni gruppo viene assegnato un criterio dello stesso tipo.

La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo. Ad esempio, se si sta assegnando un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 che è la classificazione più alta. La classificazione delle assegnazioni di gruppo indica l'appartenenza a un gruppo più importante o più pertinente rispetto alle altre appartenenze ai gruppi per quanto riguarda l'ereditarietà.
 
Supponiamo, ad esempio, di avere due gruppi, i dipendenti dello Store e i responsabili dello Store. A entrambi i gruppi viene assegnato un criterio di chiamata per i team, rispettivamente i criteri di chiamata dei dipendenti e i responsabili dello Store. Per un responsabile dello Store che si trova in entrambi i gruppi, il loro ruolo di Manager è più pertinente del loro ruolo di dipendente, quindi il criterio di chiamata assegnato al gruppo responsabili dello Store dovrebbe avere una classificazione più alta.

|Gruppo |Nome dei criteri di chiamata dei team  |Rango|
|---------|---------|---|
|Responsabili dello Store   |Criteri di chiamata per i responsabili dello Store         |1|
|Archiviare i dipendenti    |Criteri di chiamata dei dipendenti dello Store      |2|

Se non specifichi una classificazione, all'assegnazione dei criteri viene assegnata la classificazione più bassa.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

> [!NOTE]
> I cmdlet si trovano nella versione preliminare del modulo di PowerShell teams. Seguire questa procedura per disinstallare prima di tutto la versione in genere disponibile del modulo di PowerShell Teams (se è installato) e quindi installare la versione più recente di pre-rilascio del modulo dalla raccolta di test di PowerShell.

Se non è già stato eseguito, eseguire la procedura seguente per registrare la raccolta di test di PowerShell come origine attendibile.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Se è installata la versione in genere disponibile del modulo di PowerShell teams, eseguire la procedura seguente per disinstallarlo.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Eseguire la procedura seguente per installare il modulo di PowerShell Microsoft Teams più recente dalla raccolta di test di PowerShell.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando viene richiesto, accedere con le credenziali di amministratore.

### <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

In questo esempio, usiamo il ```New-CsGroupPolicyAssignment``` cmdlet per assegnare un criterio riunione teams denominato criteri di riunione per i responsabili delle riunioni a un gruppo con una classificazione di assegnazione di 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

Per altre informazioni, vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).

### <a name="get-policy-assignments-for-a-group"></a>Ottenere le assegnazioni dei criteri per un gruppo

Usa il ```Get-CsGroupPolicyAssignment``` cmdlet per ottenere tutti i criteri assegnati a un gruppo. Tieni presente che i gruppi sono sempre elencati dall'ID del gruppo, anche se l'indirizzo SIP o l'indirizzo di posta elettronica è stato usato per assegnare il criterio.

In questo esempio recuperiamo tutti i criteri assegnati a un gruppo specifico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In questo esempio vengono restituiti tutti i gruppi a cui è stato assegnato un criterio di riunione teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

Per altre informazioni, vedere [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).

### <a name="remove-a-policy-from-a-group"></a>Rimuovere un criterio da un gruppo

Utilizzare il ```Remove-CsGroupPolicyAssignment``` cmdlet per rimuovere un criterio da un gruppo. Quando si rimuove un criterio da un gruppo, vengono aggiornate le priorità di altri criteri dello stesso tipo assegnati al gruppo e con una classificazione inferiore. Se ad esempio si rimuove un criterio con una classificazione 2, i criteri che hanno una classificazione 3 e 4 vengono aggiornati per riflettere la nuova classificazione. Le due tabelle seguenti mostrano questo esempio.

Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri di riunione di teams.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Regione occidentale     |Criteri per la regione occidentale         |2         |
|Divisione    |Criteri di divisione         |3         |
|Filiale nel   |Criteri sussidiari        |4         |

Se rimuoviamo i criteri per l'area ovest dal gruppo area occidentale, le assegnazioni dei criteri e le priorità vengono aggiornate come indicato di seguito.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Divisione    |Criteri di divisione         |2         |
|Filiale nel   |Criteri sussidiari        |3        |

In questo esempio rimuoviamo i criteri riunione Teams da un gruppo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

Per altre informazioni, vedere [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).

### <a name="change-a-policy-assignment-for-a-group"></a>Modificare un'assegnazione di criteri per un gruppo

Dopo aver assegnato un criterio a un gruppo, è possibile usare il ```Set-CsGroupPolicyAssignmentd``` cmdlet per modificare l'assegnazione dei criteri del gruppo, come indicato di seguito:

- Modificare la classificazione
- Modificare i criteri di un tipo di criterio specifico
- Modificare i criteri di un tipo di criteri specifico e la classificazione

In questo esempio modifichiamo i criteri di parcheggio per le chiamate di team di un gruppo in un criterio denominato SupportCallPark e la classificazione delle assegnazioni su 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

Per altre informazioni, vedere [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).

### <a name="change-the-effective-policy-for-a-user"></a>Modificare i criteri effettivi per un utente

Ecco un esempio di come modificare i criteri effettivi per un utente a cui è assegnato direttamente un criterio.

Prima di tutto, usiamo il ```Get-CsUserPolicyAssignment``` cmdlet insieme al ```PolicySource``` parametro per ottenere informazioni dettagliate sui criteri di trasmissione delle riunioni dei team associati all'utente. Per altre informazioni, vedere [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Nell'output viene indicato che all'utente sono stati assegnati direttamente i criteri di riunione per le riunioni di teams denominati eventi dei dipendenti, che hanno la precedenza sui criteri denominati fornitori di eventi live assegnati a un gruppo a cui appartiene l'utente.

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ora rimuoviamo i criteri degli eventi dei dipendenti dall'utente. Ciò significa che l'utente non ha più un criterio di riunione delle riunioni di teams direttamente assegnato e erediterà i criteri degli eventi live del fornitore assegnati al gruppo a cui appartiene l'utente. 

Per eseguire questa operazione, usare il cmdlet seguente nel modulo di PowerShell per Skype for business.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

È possibile usare i cmdlet seguenti nel modulo di PowerShell teams per eseguire questa operazione in scala anche se un'assegnazione di criteri batch, dove $users è un elenco di utenti specificati.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Assegnare un pacchetto di criteri a un gruppo di utenti

Con l'assegnazione di un pacchetto di criteri batch, puoi assegnare un pacchetto di criteri a set di grandi dimensioni di utenti alla volta senza dover usare uno script. Si usa il ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet per inviare un batch di utenti e il pacchetto di criteri che si vuole assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. Puoi quindi usare il ```Get-CsBatchPolicyAssignmentOperation``` cmdlet per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.

Un batch può contenere fino a 20.000 utenti. È possibile specificare gli utenti per l'ID oggetto, l'UPN, l'indirizzo SIP o l'indirizzo di posta elettronica.

> [!IMPORTANT]
> Al momento consigliamo di assegnare pacchetti di criteri in batch di utenti di 5.000 alla volta. Durante questi periodi di maggiore domanda, potresti riscontrare ritardi nei tempi di elaborazione. Per ridurre al minimo l'impatto di questi tempi di elaborazione più elevati, ti consigliamo di inviare dimensioni batch più piccole fino a utenti di 5.000 e inviare ogni batch solo dopo il completamento di quello precedente. L'invio di batch all'esterno dell'orario di lavoro normale può anche essere utile.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

Eseguire la procedura seguente per installare il [modulo di PowerShell di Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già stato fatto). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando viene richiesto, accedere con le credenziali di amministratore.

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>Assegnare un pacchetto di criteri a un gruppo di utenti

In questo esempio usiamo il ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet per assegnare il pacchetto di criteri Education_PrimaryStudent a un batch di utenti.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

Per altre informazioni, vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Ottenere lo stato di un'assegnazione batch

Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation). 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)