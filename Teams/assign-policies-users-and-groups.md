---
title: Assegnare criteri a utenti e gruppi
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Scopri i diversi modi per assegnare criteri a utenti e gruppi in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: a57c038242c06f4305410e68cff907aef6889841
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396650"
---
# <a name="assign-policies-to-users-and-groups"></a>Assegnare criteri a utenti e gruppi

Questo articolo esamina i diversi modi per assegnare criteri a utenti e gruppi in Microsoft Teams. Prima di leggere, assicurarsi di aver letto [Assegna criteri in Teams per iniziare](policy-assignment-overview.md).

## <a name="assign-a-policy-to-individual-users"></a>Assegnare un criterio ai singoli utenti

Seguire questa procedura per assegnare un criterio a un singolo utente o a pochi utenti alla volta.

### <a name="use-the-microsoft-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Microsoft Teams

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro [dell'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) passare a **Gestisci utenti.** > 
2. Selezionare l'utente facendo clic a sinistra del nome utente e quindi selezionare **Modifica impostazioni**.
3. Selezionare il criterio da assegnare e quindi selezionare **Applica**.

    :::image type="content" source="media/assign-policies-users-edit-settings.png"  alt-text="Screenshot del riquadro Modifica impostazioni in Gestisci utenti." lightbox="media/assign-policies-users-edit-settings-expanded.png":::

> [!NOTE]
> Per annullare l'assegnazione di criteri specializzati da un utente, è possibile impostare ogni criterio su **Globale (impostazione predefinita a livello di organizzazione).** È anche possibile rimuovere le assegnazioni dei criteri in blocco per tutti gli utenti assegnati direttamente a un criterio. Per altre informazioni, vedere [Annullare l'assegnazione di criteri in blocco](#unassign-policies-in-bulk).

È anche possibile eseguire le operazioni seguenti per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare alla pagina dei criteri.
2. Selezionare il criterio da assegnare facendo clic a sinistra del nome del criterio.
3. Selezionare **Assegna utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo aver aggiunto tutti gli utenti, selezionare **Applica**.

    :::image type="content" source="media/assign-policies-user-example.png" alt-text="Screenshot che mostra come assegnare un criterio a un utente nell'interfaccia di amministrazione di Teams tramite un secondo metodo." lightbox="media/assign-policies-user-example-expanded.png":::

### <a name="use-powershell"></a>Usare PowerShell

Ogni tipo di criterio ha un proprio set di cmdlet per gestirlo. Usare il `Grant-` cmdlet per un determinato tipo di criterio per assegnare il criterio. Ad esempio, usare il `Grant-CsTeamsMeetingPolicy` cmdlet per assegnare un criterio riunione di Teams agli utenti. Questi cmdlet sono inclusi nel modulo di Teams PowerShell e sono documentati nel [riferimento ai cmdlet di Skype for Business](/powershell/skype).

 Scarica e installa la [versione pubblica di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (se non l'hai già fatto) e quindi esegui quanto segue per connetterti.

> [!NOTE]
> Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare Skype for Business Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

In questo esempio viene assegnato un criterio riunione di Teams denominato Criterio riunione studente a un utente denominato Rosso.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Per altre informazioni, vedere [Gestire i criteri tramite PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

L'assegnazione di criteri ai gruppi consente di assegnare criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza, un'unità organizzativa o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione dei criteri ai gruppi è consigliata per gruppi con un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegnano i criteri, questi vengono immediatamente assegnati al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e potrebbe richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

Le assegnazioni di Criteri di gruppo vengono propagate solo agli utenti che sono membri diretti del gruppo. Le assegnazioni non vengono propagate ai membri dei gruppi annidati.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Informazioni utili sull'assegnazione dei criteri ai gruppi

Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni di gruppo.

#### <a name="precedence-rules"></a>Regole di precedenza

Per un determinato tipo di criterio, i criteri efficaci di un utente vengono determinati in base ai criteri seguenti:

- Un criterio assegnato direttamente a un utente ha la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo. In altre parole, se a un utente viene assegnato direttamente un criterio di un determinato tipo, tale utente non erediterà un criterio dello stesso tipo da un gruppo. Questo significa anche che se un utente ha un criterio di un determinato tipo a cui è stato assegnato direttamente, è necessario rimuoverlo dall'utente prima che possa ereditare un criterio dello stesso tipo da un gruppo.
- Se a un utente non sono assegnati criteri direttamente ed è membro di due o più gruppi a cui è assegnato un criterio dello stesso tipo, l'utente eredita il criterio dell'assegnazione di gruppo con la classificazione più alta.
- Se un utente non è membro di alcun gruppo a cui è assegnato un criterio, il criterio globale (predefinito a livello di organizzazione) per quel tipo di criterio si applica all'utente.

I criteri efficaci di un utente vengono aggiornati in base alle regole seguenti:

- quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio.
- un criterio non è assegnato da un gruppo.
- un criterio assegnato direttamente all'utente viene rimosso.

#### <a name="group-assignment-ranking"></a>Classificazione delle assegnazioni di gruppo

> [!NOTE]
> Un determinato tipo di criterio può essere assegnato a un massimo di 64 gruppi tra istanze di criteri per quel tipo.

Quando si assegnano criteri a un gruppo, si specifica una classificazione per l'assegnazione di gruppo. Questa classificazione viene usata per determinare i criteri che un utente deve ereditare come criteri efficaci se l'utente è membro di due o più gruppi e a ogni gruppo viene assegnato un criterio dello stesso tipo.

La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo. Ad esempio, se si assegna un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 come classificazione più alta. La classificazione delle assegnazioni di gruppo indica quali appartenenze ai gruppi sono più importanti o più rilevanti rispetto ad altre appartenenze ai gruppi per quanto riguarda l'ereditarietà.

Supponiamo, ad esempio, di avere due gruppi, Dipendenti negozio e Responsabili negozio. A entrambi i gruppi viene assegnato un criterio per le chiamate di Teams, rispettivamente i criteri per le chiamate dei dipendenti dello Store e i criteri per le chiamate dei responsabili dello Store. Per un responsabile dello Store che fa parte di entrambi i gruppi, il suo ruolo di responsabile è più rilevante del suo ruolo di dipendente, quindi i criteri per le chiamate assegnati al gruppo di responsabili dello Store dovrebbero avere una classificazione più alta.

|Gruppo |Nome del criterio di chiamata di Teams  |Rango|
|---------|---------|---|
|Responsabili store   |Criteri per le chiamate dei responsabili dello store         |1|
|Dipendenti negozio    |Criteri per le chiamate dei dipendenti dello Store      |2|

Se non si specifica una classificazione, all'assegnazione dei criteri viene assegnata la classificazione più bassa.

### <a name="in-the-teams-admin-center"></a>Nell'interfaccia di amministrazione di Teams

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi tramite l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri per le chiamate di Teams, i criteri per i parchi chiamate di Teams, i criteri per gli eventi live di Teams, i criteri per le riunioni di Teams e i criteri di messaggistica di Teams. Per altri tipi di criteri, usare PowerShell.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare alla pagina del tipo di criterio. Ad esempio, passare a **Criteri****riunione riunioni** > .
2. Selezionare la scheda **Assegnazione Criteri di gruppo** .
3. Selezionare **Aggiungi gruppo** e quindi nel riquadro **Assegna criteri a gruppo** eseguire le operazioni seguenti:
    1. Cercare e aggiungere il gruppo a cui assegnare il criterio.
    2. Impostare la classificazione per l'assegnazione di gruppo.
    3. Selezionare il criterio da assegnare.
    4. Selezionare **Applica**.

        :::image type="content" source="media/assign-policies-groups-messaging.png" alt-text="Screenshot che mostra come assegnare un criterio a un gruppo nell'interfaccia di amministrazione di Teams." lightbox="media/assign-policies-groups-messaging-expanded.png":::

Per rimuovere un'assegnazione di Criteri di gruppo, nella scheda **Assegnazione criteri di gruppo** della pagina dei criteri selezionare l'assegnazione di gruppo e quindi **selezionare Rimuovi**.

Per modificare la classificazione di un'assegnazione di gruppo, è necessario rimuovere prima l'assegnazione di Criteri di gruppo. Quindi, seguire la procedura precedente per assegnare i criteri a un gruppo.

Questo video mostra la procedura per creare e assegnare criteri di riunione personalizzati a un gruppo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53Ws0?autoplay=false]

### <a name="use-the-powershell-option"></a>Usare l'opzione PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti i tipi di criteri di Teams. Vedi [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo PowerShell di Microsoft Teams

Per indicazioni dettagliate, vedere [Installare PowerShell di Teams](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Assegnare criteri a un gruppo di utenti

Usa il cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) per assegnare un criterio a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio viene assegnato un criterio riunione di Teams denominato Criteri riunione responsabili vendita al dettaglio a un gruppo con una classificazione di assegnazione di 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Ottenere le assegnazioni dei criteri per un gruppo

Usa il cmdlet [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) per ottenere tutti i criteri assegnati a un gruppo. I gruppi sono sempre elencati in base all'ID del gruppo anche se per assegnare i criteri è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio vengono recuperati tutti i criteri assegnati a un gruppo specifico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In questo esempio vengono restituiti tutti i gruppi a cui sono stati assegnati criteri per le riunioni di Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Rimuovere un criterio da un gruppo

Utilizzare il cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) per rimuovere un criterio da un gruppo. Quando si rimuove un criterio da un gruppo, vengono aggiornate le priorità degli altri criteri dello stesso tipo assegnati al gruppo e con una classificazione inferiore. Ad esempio, se si rimuove un criterio con classificazione 2, i criteri con classificazione 3 e 4 vengono aggiornati in modo da riflettere la nuova classificazione. Le due tabelle seguenti illustrano questo esempio.

Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri delle riunioni di Teams.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Area ovest     |Politica della regione occidentale         |2         |
|Divisione    |Criteri di divisione         |3         |
|Filiale   |Criteri per le filiali        |4         |

Se rimuoviamo i criteri area ovest dal gruppo Area ovest, le assegnazioni dei criteri e le priorità vengono aggiornate come segue.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Divisione    |Criteri di divisione         |2         |
|Filiale   |Criteri per le filiali        |3        |

In questo esempio i criteri di riunione di Teams vengono rimossi da un gruppo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Modificare un'assegnazione di criteri per un gruppo

> [!NOTE]
> Il cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) sarà disponibile a breve. Nel frattempo, per modificare un'assegnazione di Criteri di gruppo, è possibile rimuovere l'assegnazione di criteri corrente dal gruppo e quindi aggiungere una nuova assegnazione di criteri.

Dopo aver assegnato un criterio a un gruppo, puoi utilizzare il cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) per modificare l'assegnazione dei criteri del gruppo come segue:

- Modificare la classificazione
- Modificare il criterio di un determinato tipo di criterio
- Modificare il criterio di un determinato tipo di criterio e la classificazione

In questo esempio, i criteri del parco chiamate di Teams di un gruppo vengono modificati in un criterio denominato SupportCallPark e la classificazione delle assegnazioni su 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Modificare i criteri efficaci per un utente

Ecco un esempio di come modificare i criteri efficaci per un utente a cui è assegnato direttamente un criterio.

Innanzitutto, usiamo il cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) insieme al `PolicySource` parametro per ottenere i dettagli dei criteri di trasmissione delle riunioni di Teams associati all'utente.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

L'output mostra che all'utente è stato assegnato direttamente un criterio di trasmissione riunione di Teams denominato **Eventi dipendenti**, che ha la precedenza sul criterio denominato **Vendor Live Events** assegnato a un gruppo a cui appartiene l'utente.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ora rimuoviamo i criteri Eventi dipendente dall'utente. Ciò significa che l'utente non ha più un criterio di trasmissione riunione di Teams direttamente assegnato e erediterà il criterio Eventi live fornitore assegnato al gruppo a cui appartiene l'utente.

A questo scopo, usare il cmdlet seguente nel modulo di Skype for Business PowerShell.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Usare il cmdlet seguente nel modulo PowerShell di Teams per eseguire questa operazione in scala attraverso un'assegnazione di criteri batch, dove $users è un elenco di utenti specificato.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare un criterio a un batch di utenti

### <a name="use-the-admin-center"></a>Usare l'interfaccia di amministrazione

Per assegnare un criterio agli utenti in blocco:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti**.
2. Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per visualizzare gli utenti desiderati.
3. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, selezionare il &#x2713; (segno di spunta) nella parte superiore della tabella.
4. Seleziona **Modifica impostazioni**, apporta le modifiche desiderate e quindi seleziona **Applica**.

Per visualizzare lo stato dell'assegnazione dei criteri, nel banner visualizzato nella parte superiore della pagina **Utenti** dopo aver selezionato **Applica** per inviare l'assegnazione dei criteri, selezionare **Log attività**. Oppure, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Dashboard** e quindi, in **Log attività**, selezionare **Visualizza dettagli**. Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni. Per altre informazioni, vedere [Visualizzare le assegnazioni dei criteri nel log attività](activity-log.md).

### <a name="use-powershell-method"></a>Usare il metodo PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri batch con PowerShell non è disponibile per tutti i tipi di criteri di Teams. Vedi [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.

Con l'assegnazione dei criteri batch, è possibile assegnare un criterio a grandi set di utenti alla volta senza usare uno script. Utilizza il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e i criteri che vuoi assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. Puoi quindi utilizzare il cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato e dello stato delle assegnazioni in un batch.

Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio. Se un utente viene specificato usando l'UPN o la posta elettronica, ma ha un valore diverso rispetto all'indirizzo SIP, l'assegnazione dei criteri avrà esito negativo per l'utente. Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci rimanenti nel batch.

Un batch può contenere fino a 5.000 utenti. Per risultati ottimali, non inviare più di un paio di batch alla volta. Consentire ai batch di completare l'elaborazione prima di inviare altri batch.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installare e connettersi al modulo di Teams PowerShell

Eseguire quanto segue per installare il [modulo PowerShell di Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire quanto segue per connettersi a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installare e connettersi al modulo di Azure AD PowerShell for Graph (facoltativo)

È anche possibile [scaricare e installare il modulo Di Azure AD PowerShell per Graph](/powershell/azure/active-directory/install-adv2) (se non è già stato fatto) e connettersi ad Azure AD in modo da poter recuperare un elenco di utenti nell'organizzazione.

Eseguire le operazioni seguenti per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando richiesto, accedere con le stesse credenziali di amministratore usate per connettersi a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Assegnare criteri di configurazione a un batch di utenti

In questo esempio usiamo il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare un criterio di configurazione dell'app denominato Criteri di configurazione app HR a un batch di utenti elencati nel file users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $user_ids -OperationName "Example 1 batch"
```

In questo esempio ci si connette ad Azure AD per recuperare una raccolta di utenti e quindi assegnare un criterio di messaggistica denominato Criteri di messaggistica per i nuovi assunti a un batch di utenti specificato usando il loro indirizzo SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Ottenere lo stato di un'assegnazione batch

Eseguire quanto segue per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal `New-CsBatchPolicyAssignmentOperation` cmdlet per un determinato batch.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output mostra che si è verificato un errore, eseguire quanto segue per ottenere altre informazioni sugli errori, che si trovano nella `UserState` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per ulteriori informazioni, vedi [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="unassign-policies-in-bulk"></a>Annullare l'assegnazione di criteri in blocco

Quando si annullano l'assegnazione di criteri in blocco, si rimuovono le assegnazioni dei criteri assegnate a singoli utenti tramite assegnazione diretta. Questa funzionalità è utile nei seguenti scenari:

1. **Per rendere effettive le assegnazioni globali (predefinite a livello di organizzazione) o di criteri di gruppo:** A causa [delle regole di precedenza, le assegnazioni](policy-assignment-overview.md#which-policy-takes-precedence) globali (predefinite a livello di organizzazione) o di criteri di gruppo non avranno effetto per gli utenti che hanno un'assegnazione diretta dei criteri. Gli amministratori possono annullare l'assegnazione di criteri in blocco per rimuovere le assegnazioni dirette in modo da rendere effettive le assegnazioni globali (predefinite a livello di organizzazione) o dei criteri di gruppo.
1. **Pulire le assegnazioni dei criteri dalla procedura guidata di Teams Education:** La procedura guidata dei criteri di Teams Education applica le impostazioni predefinite dei criteri globali per gli studenti e assegna un set di criteri personalizzato per un gruppo di personale tramite l'assegnazione di criteri di gruppo. Gli amministratori devono pulire i criteri individuali per studenti e personale affinché le attività globali (predefinite a livello di organizzazione) e di gruppo siano efficaci.
1. **Rimuovere assegnazioni di criteri non corrette:** Se a un gruppo di singoli utenti è stato assegnato un criterio errato tramite assegnazione diretta, è possibile usare i criteri di annullamento dell'assegnazione in blocco per rimuovere queste assegnazioni.

 È possibile annullare l'assegnazione di criteri in blocco [dall'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com).

1. Passare a **Gestione utenti** > .
2. Nell'angolo in alto a destra della pagina selezionare **Annulla assegnazione criteri in blocco** dal menu a discesa **Azioni** .

    ![Pagina Gestisci utenti nell'interfaccia di amministrazione di Teams.](media/manage-users-unassign-policies.png)

    > [!NOTE]
    > È anche possibile annullare l'assegnazione dei criteri dalle singole pagine dei criteri scegliendo un criterio e selezionando **Gestisci utenti**.

3. Selezionare un tipo di criterio.

    ![Pagina Annulla assegnazione criteri in blocco nell'interfaccia di amministrazione di Teams.](media/unassign-policies-page.png)

4. Scegliere il criterio da riassegnare e selezionare **Carica dati** per ottenere il numero di utenti attualmente assegnati al criterio.

    > [!IMPORTANT]
    > Quando si sceglie un criterio, vengono rimossi **tutti gli** utenti assegnati singolarmente da tale criterio.

5. Selezionare **Annulla assegnazione criteri**.

Dopo aver rimosso l'assegnazione dei criteri, è possibile esaminare i dettagli dell'operazione nel [log attività](https://admin.teams.microsoft.com/activity-log).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire Teams con i criteri](manage-teams-with-policies.md)
- [Panoramica di PowerShell di Teams](teams-powershell-overview.md)
- [Assegnare criteri in Teams - Guida introduttiva](policy-assignment-overview.md)
