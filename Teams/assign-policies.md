---
title: Assegnare i criteri agli utenti in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Informazioni sui diversi modi per assegnare criteri agli utenti in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196295"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Assegnare i criteri agli utenti in Microsoft Teams

Gli amministratori possono utilizzare i criteri per controllare le funzionalità di Teams disponibili per gli utenti dell'organizzazione. Ad esempio, ci sono criteri per le chiamate, criteri per le riunioni e criteri di messaggistica, solo per cita ne alcuni.

Le organizzazioni hanno diversi tipi di utenti con esigenze specifiche. I criteri personalizzati creati e assegnati consentono di personalizzare le impostazioni dei criteri per diversi set di utenti in base a queste esigenze.

Per gestire facilmente i criteri nell'organizzazione, Teams offre diversi modi per assegnare i criteri agli utenti. Assegnare criteri direttamente agli utenti, singolarmente o su scala nel processo di assegnazione di un batch, oppure a un gruppo di cui gli utenti sono membri. È anche possibile usare pacchetti di criteri per assegnare una raccolta predefinita di criteri agli utenti dell'organizzazione con ruoli simili. L'opzione scelta dipende dal numero di criteri da gestire e dal numero di utenti a cui si stanno assegnando criteri. I criteri globali (impostazione predefinita a livello di organizzazione) si applicano al maggior numero di utenti dell'organizzazione. È necessario assegnare criteri solo agli utenti che richiedono criteri specifici.

Questo articolo descrive i diversi modi in cui è possibile assegnare criteri agli utenti e gli scenari consigliati per l'uso.

## <a name="which-policy-takes-precedence"></a>Quali criteri hanno la precedenza?

Un utente ha un criterio effettivo per ogni tipo di criterio. È possibile, o addirittura probabile, che un utente sia assegnato direttamente a un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo. In questi tipi di scenari, quali criteri hanno la precedenza? I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.

Se a un utente viene direttamente assegnato un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza. Nell'esempio visivo seguente, il criterio effettivo dell'utente è il criterio di riunione Square Square, assegnato direttamente all'utente.

![Diagramma che illustra in che modo un criterio assegnato direttamente ha la precedenza](media/assign-policies-example-directly-assigned.png)

Se a un utente non viene direttamente assegnato un criterio di un determinato tipo, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza. Se un utente è membro di più gruppi, [](#group-assignment-ranking) il criterio con la classificazione di assegnazione di gruppi più alta per il tipo di criterio specificato ha la precedenza.

In questo esempio visivo, il criterio effettivo dell'utente è il criterio Exec Teams e HD, che ha la classificazione di assegnazione più alta rispetto agli altri gruppi di cui l'utente è membro e a cui è anche assegnato un criterio dello stesso tipo di criterio.  

![Diagramma che illustra in che modo un criterio ereditato dal gruppo ha la precedenza](media/assign-policies-example-group.png)

Se a un utente non viene assegnato direttamente un criterio o non è membro di alcun gruppo a cui è assegnato un criterio, l'utente ottiene il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio. Ecco un esempio visivo.

![Diagramma che illustra in che modo i criteri globali hanno la precedenza](media/assign-policies-example-global.png)

Per altre informazioni, vedere [Regole di precedenza.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Modalità di assegnazione dei criteri

Ecco una panoramica dei modi in cui è possibile assegnare criteri agli utenti e degli scenari consigliati per ognuno di essi. Selezionare i collegamenti per altre informazioni.

Prima di assegnare criteri a singoli utenti o gruppi, iniziare impostando i criteri globali (impostazione predefinita a livello di [organizzazione)](#set-the-global-policies) in modo che siano applicati al maggior numero di utenti dell'organizzazione.  Dopo aver impostato i criteri globali, è necessario assegnarli solo agli utenti che richiedono criteri specifici.

|Operazione da eseguire  |Se...  | Uso di...
|---------|---------|----|
|[Assegnare criteri a singoli utenti](#assign-a-policy-to-individual-users)    | L'utente non ha ancora iniziato a usare Teams o ha bisogno di assegnare solo uno o un paio di criteri a un numero limitato di utenti. |Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Skype for Business Online
|[Assegnare un criterio a un gruppo](#assign-a-policy-to-a-group) |Assegnare criteri in base all'appartenenza ai gruppi di un utente. Ad esempio, assegnare un criterio a tutti gli utenti di un gruppo di sicurezza o una lista di distribuzione.| Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams|
|[Assegnare criteri a un batch di utenti](#assign-a-policy-to-a-batch-of-users)   | Assegnare criteri a grandi set di utenti. Ad esempio, assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione contemporaneamente. |Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams|
| [Assegnare un pacchetto di criteri agli utenti](#assign-a-policy-package-to-users)  |Assegnare più criteri a set specifici di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (docente) agli insegnanti dell'istituto di istruzione per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Istruzione (studenti secondari) agli studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.  |Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams|
| [Assegnare un pacchetto di criteri a un gruppo](#assign-a-policy-package-to-a-group) (in anteprima privata)   |Assegnare più criteri a un gruppo di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare un pacchetto di criteri a tutti gli utenti in un gruppo di sicurezza o una lista di distribuzione. |Interfaccia di amministrazione di Microsoft Teams (presto disponibile) o cmdlet di PowerShell nel modulo PowerShell di Teams|
| [Assegnare un pacchetto di criteri a un batch di utenti](#assign-a-policy-package-to-a-batch-of-users)|Assegnare più criteri a un batch di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (docente) a tutti gli insegnanti dell'istituto di istruzione usando l'assegnazione batch per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Education (studenti secondari) a un batch di studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.|Cmdlet di PowerShell nel modulo Teams di PowerShell|

## <a name="set-the-global-policies"></a>Impostare i criteri globali

Seguire questa procedura per impostare i criteri globali (impostazione predefinita a livello di organizzazione) per ogni tipo di criterio.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare alla pagina dei criteri per il tipo di criterio da aggiornare. Ad esempio, i **criteri di Teams**  >  **Teams,** i criteri **per** le  >  **riunioni,** i criteri di **messaggistica** o **le chiamate**  >  **vocali.**
2. Selezionare il **criterio globale (impostazione predefinita a** livello di organizzazione) per visualizzare le impostazioni correnti.
3. Aggiornare il criterio in base alle esigenze e quindi selezionare **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per impostare i criteri globali con PowerShell, usare l'identificatore globale.  Per iniziare, esaminare il criterio globale corrente per determinare l'impostazione da modificare.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Aggiornare quindi i criteri globali in base alle esigenze.  È necessario specificare solo i valori per le impostazioni da modificare.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Assegnare criteri a singoli utenti

Seguire questa procedura per assegnare criteri a un singolo utente o a un numero limitato di utenti alla volta.

### <a name="use-the-microsoft-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Microsoft Teams

Per assegnare un criterio a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Utenti e quindi seleziona l'utente.
2. Selezionare l'utente facendo clic a sinistra del nome utente e quindi **selezionando Modifica impostazioni.**
3. Selezionare il criterio da assegnare e quindi scegliere **Applica.**

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai alla pagina dei criteri.
2. Selezionare il criterio da assegnare facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo aver aggiunto gli utenti, selezionare **Applica.**

### <a name="use-powershell"></a>Usare PowerShell

Ogni tipo di criterio ha un proprio set di cmdlet per gestirlo. Usare il ```Grant-``` cmdlet per un determinato tipo di criterio per assegnare il criterio. Ad esempio, usare il ```Grant-CsTeamsMeetingPolicy``` cmdlet per assegnare criteri di riunione di Teams agli utenti. Questi cmdlet sono inclusi nel modulo PowerShell di Skype for Business Online e sono documentati nel riferimento [ai cmdlet di Skype for Business.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

 Scarica e installa il modulo [PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) di Skype for Business online (se non l'hai già fatto), quindi esegui questa procedura per connetterti a Skype for Business online e avviare una sessione.

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

In questo esempio viene assegnato un criterio di riunione di Teams denominato Criteri riunione studente a un utente denominato Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Per altre informazioni, vedere [Gestire i criteri con PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

L'assegnazione dei criteri ai gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione dei criteri ai gruppi è consigliata per gruppi di un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegnano i criteri, vengono immediatamente assegnati al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e potrebbe richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

Le assegnazioni di Criteri di gruppo vengono propagate solo agli utenti che sono membri diretti del gruppo. Le assegnazioni non vengono propagate ai membri di gruppi annidati.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Informazioni necessarie sull'assegnazione dei criteri ai gruppi

Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni dei gruppi.

#### <a name="precedence-rules"></a>Regole di precedenza

Per un determinato tipo di criterio, il criterio effettivo di un utente viene determinato in base a quanto segue:

- I criteri assegnati direttamente a un utente hanno la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo. In altre parole, se a un utente viene direttamente assegnato un criterio di un determinato tipo, l'utente non erediterà un criterio dello stesso tipo da un gruppo. Questo significa anche che se un utente ha un criterio di un determinato tipo a cui è stato assegnato direttamente, è necessario rimuoverlo dall'utente prima di ereditare un criterio dello stesso tipo da un gruppo.
- Se a un utente non sono assegnati direttamente criteri ed è membro di due o più gruppi a cui è assegnato un criterio dello stesso tipo, l'utente eredita il criterio dell'assegnazione di gruppo che ha la classificazione più alta.
- Se un utente non è membro di alcun gruppo a cui è assegnato un criterio, il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio viene applicato all'utente.

I criteri effettivi di un utente vengono aggiornati in base alle regole seguenti:

- quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio.
- Un criterio non è assegnato a un gruppo.
- I criteri assegnati direttamente all'utente vengono rimossi.

#### <a name="group-assignment-ranking"></a>Classificazione delle assegnazioni dei gruppi

Quando si assegna un criterio a un gruppo, si specifica una classificazione per l'assegnazione del gruppo. Viene usato per determinare i criteri che un utente deve ereditare come criterio effettivo se l'utente è membro di due o più gruppi a cui è assegnato un criterio dello stesso tipo.

La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo. Ad esempio, se si assegna un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 come classificazione più alta. La classificazione delle assegnazioni di gruppo indica quale appartenenza ai gruppi è più importante o più pertinente di altre appartenenze a gruppi per quanto riguarda l'ereditarietà.

Si supponga, ad esempio, di avere due gruppi, Dipendenti negozio e Responsabili negozio. A entrambi i gruppi sono assegnati, rispettivamente, un criterio di chiamata di Teams, un criterio di chiamata dei dipendenti negozio e un criterio di chiamata per i responsabili negozio. Per un responsabile negozio che fa parte di entrambi i gruppi, il suo ruolo di responsabile è più pertinente del suo ruolo di dipendente, quindi il criterio di chiamata assegnato al gruppo Di responsabili negozio dovrebbe avere una classificazione più alta.

|Raggruppa |Nome del criterio di chiamata di Teams  |Rango|
|---------|---------|---|
|Responsabili negozio   |Criteri per le chiamate dei responsabili negozio         |1|
|Dipendenti negozio    |Criteri per le chiamate dei dipendenti negozio      |2|

Se non si specifica una classificazione, all'assegnazione dei criteri viene data la classificazione più bassa.

### <a name="in-the-teams-admin-center"></a>Nell'interfaccia di amministrazione di Teams

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi tramite l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri di chiamata di Teams, i criteri del parco chiamate di Teams, i criteri di Teams, i criteri per gli eventi live di Teams, i criteri delle riunioni di Teams e i criteri di messaggistica di Teams. Per altri tipi di criteri, usare PowerShell.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai alla pagina del tipo di criterio. Ad esempio, passare a **Criteri**  >  **riunione riunioni.**
2. Selezionare la scheda **di assegnazione di Criteri di** gruppo.
3. Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna **criteri** a gruppo eseguire le operazioni seguenti:
    1. Cercare e aggiungere il gruppo a cui assegnare il criterio.
    2. Impostare la classificazione per l'assegnazione del gruppo.
    3. Selezionare il criterio da assegnare.
    4. Selezionare **Applica.**

Per rimuovere un'assegnazione di  Criteri di gruppo, nella scheda Assegnazione di Criteri di gruppo della pagina dei criteri selezionare l'assegnazione del gruppo e quindi **scegliere Rimuovi.**

Per modificare la classificazione di un'assegnazione di gruppo, è necessario prima rimuovere l'assegnazione di Criteri di gruppo. Quindi, seguire la procedura precedente per assegnare i criteri a un gruppo.

### <a name="use-the-powershell-option"></a>Usare l'opzione PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti i tipi di criteri di Teams. Per [l'elenco dei tipi di criteri supportati, vedere New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo Microsoft Teams PowerShell

Per istruzioni dettagliate, vedere Installare [PowerShell di Teams.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Assegnare un criterio a un gruppo di utenti

Usare il cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per assegnare un criterio a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio viene assegnato un criterio di riunione di Teams denominato Criterio riunione di responsabili dettaglio a un gruppo con una classificazione di assegnazione 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Ottenere assegnazioni dei criteri per un gruppo

Usare il [cmdlet Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) per ottenere tutti i criteri assegnati a un gruppo. Tenere presente che i gruppi sono sempre elencati in base all'ID gruppo anche se per assegnare i criteri è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio vengono recuperati tutti i criteri assegnati a un gruppo specifico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In questo esempio vengono restituiti tutti i gruppi a cui è assegnato un criterio di riunione di Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Rimuovere un criterio da un gruppo

Usare il cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) per rimuovere un criterio da un gruppo. Quando si rimuovono criteri da un gruppo, le priorità di altri criteri dello stesso tipo assegnate a quel gruppo e con una classificazione inferiore vengono aggiornate. Ad esempio, se si rimuove un criterio con una classificazione 2, i criteri con una classificazione 3 e 4 vengono aggiornati in modo da riflettere la nuova classificazione. Questo esempio è illustrato nelle due tabelle seguenti.

Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri delle riunioni di Teams.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Area ovest     |Criteri dell'area Ovest         |2         |
|Divisione    |Criteri di divisione         |3         |
|Affiliata   |Criteri affiliati        |4         |

Se si rimuove il criterio Area Ovest dal gruppo Area Ovest, le assegnazioni e le priorità dei criteri vengono aggiornate nel modo seguente.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Divisione    |Criteri di divisione         |2         |
|Affiliata   |Criteri affiliati        |3        |

In questo esempio il criterio di riunione di Teams viene rimosso da un gruppo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Modificare un'assegnazione di criteri per un gruppo

> [!NOTE]
> Il cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) sarà disponibile a breve. Nel frattempo, per modificare un'assegnazione di Criteri di gruppo, è possibile rimuovere l'assegnazione di criteri corrente dal gruppo e quindi aggiungere una nuova assegnazione di criteri.

Dopo aver assegnato un criterio a un gruppo, è possibile usare il cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) per modificare l'assegnazione dei criteri del gruppo come indicato di seguito:

- Modificare la classificazione
- Modificare il criterio di un determinato tipo di criterio
- Modificare il criterio di un determinato tipo di criterio e la classificazione

In questo esempio i criteri del call park di Teams di un gruppo vengono 3dati con un criterio denominato SupportCallPark e la classificazione delle assegnazioni viene impostata su 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Modificare i criteri effettivi per un utente

Ecco un esempio di come modificare il criterio effettivo per un utente a cui viene direttamente assegnato un criterio.

Prima di tutto, usiamo il cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) insieme al parametro per ottenere i dettagli dei criteri di trasmissione delle riunioni di Teams associati ```PolicySource``` all'utente.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

L'output mostra che all'utente è stato direttamente assegnato un criterio di trasmissione riunione di Teams denominato Eventi dipendente, che ha la precedenza sul criterio denominato Eventi live fornitore assegnato a un gruppo a cui appartiene l'utente.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

A questo punto, il criterio Eventi dipendenti viene rimosso dall'utente. Questo significa che l'utente non ha più un criterio di trasmissione riunione di Teams assegnato direttamente all'utente e erediterà il criterio Eventi live fornitore assegnato al gruppo a cui appartiene l'utente.

Utilizzare il cmdlet seguente nel modulo PowerShell di Skype for Business per eseguire questa operazione.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Usare il cmdlet seguente nel modulo PowerShell di Teams per eseguire questa operazione su larga scala, anche se con un'assegnazione di criteri batch, in $users è un elenco di utenti specificato dall'utente.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare criteri a un batch di utenti

### <a name="use-the-admin-center"></a>Usare l'interfaccia di amministrazione

Per assegnare un criterio agli utenti in blocco:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti.**
2. Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per mostrare gli utenti desiderati.
3. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
4. Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**

Per visualizzare lo stato dell'assegnazione dei criteri, nel  banner visualizzato nella  parte superiore della pagina Utenti dopo aver selezionato Applica per inviare l'assegnazione dei criteri, selezionare **Log attività.** Oppure, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Dashboard** e quindi, in **Log** attività, **seleziona Visualizza dettagli.** Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni. Per altre informazioni, vedi [Visualizzare le assegnazioni dei criteri nel log attività.](activity-log.md)

### <a name="use-powershell-method"></a>Usare il metodo di PowerShell

> [!NOTE]
> Attualmente, l'assegnazione di criteri batch con PowerShell non è disponibile per tutti i tipi di criteri di Teams. Vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.

Con l'assegnazione di criteri batch, è possibile assegnare un criterio a grandi set di utenti contemporaneamente senza dover usare uno script. Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il criterio da assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato delle assegnazioni in batch.

Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio. Se un utente viene specificato usando l'UPN o l'indirizzo di posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente. Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci che restano nel batch.

Un batch può contenere fino a 5.000 utenti. Per risultati ottimali, non inviare più di pochi batch alla volta. Consentire il completamento dell'elaborazione dei batch prima di inviare altri batch.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installare e connettersi al modulo Teams PowerShell

Eseguire la procedura seguente per installare il modulo [Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Esegui quanto segue per connetterti a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installare e connettersi al modulo Azure AD PowerShell per Graph (facoltativo)

È anche possibile scaricare e installare il modulo [Azure AD PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se non è già stato fatto) e connettersi ad Azure AD in modo da poter recuperare un elenco di utenti nell'organizzazione.

Eseguire la procedura seguente per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando richiesto, accedere con le stesse credenziali di amministratore usate per connettersi a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Assegnare criteri di configurazione a un batch di utenti

In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare un criterio di configurazione dell'app denominato Criteri di configurazione app risorse umane a un batch di utenti elencati nel file Users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In questo esempio ci connettiamo ad Azure AD per recuperare una raccolta di utenti e quindi assegniamo un criterio di messaggistica denominato Criterio di messaggistica di nuova assunzione a un batch di utenti specificato usando il loro indirizzo SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Ottenere lo stato di un'assegnazione batch

Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un determinato batch.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori presenti nella ```UserState``` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>Assegnare un pacchetto di criteri agli utenti

Un pacchetto di criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli uguali o simili nell'organizzazione. Ogni pacchetto di criteri è progettato in base a un ruolo utente e include criteri e impostazioni dei criteri predefiniti che supportano le attività tipiche per quel ruolo. Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e Il pacchetto Healthcare (operatore clinico). Per altre informazioni, vedere [Gestire i pacchetti di criteri in Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Assegnare un pacchetto di criteri a un utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Utenti e quindi seleziona l'utente.
2. Nella pagina dell'utente selezionare **Criteri,** quindi accanto a Pacchetto **di criteri** selezionare **Modifica.**
3. Nel riquadro **Assegna pacchetto dei** criteri seleziona il pacchetto che vuoi assegnare e quindi seleziona **Salva.**

### <a name="assign-a-policy-package-to-multiple-users"></a>Assegnare un pacchetto di criteri a più utenti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a Pacchetti **criteri,** quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, selezionare **Salva.**

## <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

**Questa funzionalità è in anteprima privata**

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione di pacchetti di criteri ai gruppi è consigliata per gruppi di un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegna il pacchetto di criteri, questo viene immediatamente assegnato al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e potrebbe richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

> [!IMPORTANT]
> Prima di iniziare, è importante comprendere le regole di precedenza e la [classificazione](#precedence-rules) [delle assegnazioni dei gruppi.](#group-assignment-ranking) Leggere e comprendere i concetti che è necessario conoscere sull'assegnazione [dei](#what-you-need-to-know-about-policy-assignment-to-groups) criteri ai gruppi in precedenza in questo articolo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Assegnare un pacchetto di criteri a un gruppo di utenti nell'interfaccia di amministrazione

1. Accedere all'interfaccia di amministrazione di Teams.
2. Nel riquadro di spostamento sinistro passare alla pagina del pacchetto di criteri.
3. Selezionare la scheda di assegnazione di Criteri di gruppo.
4. Selezionare **Aggiungi gruppo,** quindi nel riquadro Assegna un pacchetto di criteri al gruppo eseguire le operazioni seguenti:

    a. Cerca e aggiungi il gruppo a cui vuoi assegnare il pacchetto di criteri.

    b. Seleziona un pacchetto di criteri.

    c. Impostare la classificazione per ogni tipo di criterio.

    d. Selezionare **Applica.**

    ![mostra l'assegnazione di Criteri di gruppo](media/group-pkg-assignment.png)

5. Per gestire la classificazione per un tipo di criterio specifico, passare alla pagina dei criteri specifici.
6. Per riassegnare un pacchetto di criteri a un gruppo, rimuovere prima l'assegnazione di Criteri di gruppo. Seguire quindi la procedura precedente per assegnare il pacchetto di criteri a un gruppo.

### <a name="work-with-powershell"></a>Usare PowerShell

#### <a name="get-the-teams-powershell-module"></a>Ottenere il modulo Di PowerShell di Teams

Per istruzioni dettagliate, vedere Installare [PowerShell di Teams.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Assegnare un pacchetto di criteri a un gruppo di utenti

Usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica. Quando si assegna il pacchetto di criteri, specificare una classificazione [delle assegnazioni di gruppo](#group-assignment-ranking) per ogni tipo di criterio nel pacchetto di criteri.

In questo esempio il pacchetto di criteri Education_Teacher viene assegnato a un gruppo con una classificazione di assegnazione 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione 2 per TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Assegnare un pacchetto di criteri a un batch di utenti

Con l'assegnazione di pacchetti di criteri batch, è possibile assegnare un pacchetto di criteri a grandi set di utenti contemporaneamente senza dover usare uno script. Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri da assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato delle assegnazioni in batch.

Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio. Se un utente viene specificato usando l'UPN o l'indirizzo di posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente. Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci che restano nel batch.

Un batch contiene fino a 5.000 utenti. Per risultati ottimali, non inviare più di pochi batch alla volta. Consentire il completamento dell'elaborazione dei batch prima di inviare altri batch.

### <a name="use-the-teams-powershell-module"></a>Usare il modulo Teams di PowerShell

Esegui quanto segue per installare il [modulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non l'hai già fatto). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Esegui quanto segue per connetterti a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Assegnare pacchetti di criteri a un batch di utenti

In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare il pacchetto di criteri Education_PrimaryStudent a un batch di utenti.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Visualizzare lo stato di un'assegnazione batch

Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un determinato batch.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori presenti nella ```UserState``` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di Teams su PowerShell](teams-powershell-overview.md)
