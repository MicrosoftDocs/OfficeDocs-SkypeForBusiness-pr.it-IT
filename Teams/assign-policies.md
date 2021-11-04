---
title: Assegnare i criteri agli utenti in Microsoft Teams
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sui diversi modi per assegnare criteri agli utenti in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e29ee61183b0c831fc6d638bf20e6edaab050e8e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760554"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Assegnare i criteri agli utenti in Microsoft Teams

Gli amministratori usano i criteri per controllare le Teams disponibili per gli utenti dell'organizzazione. Ad esempio, ci sono criteri di chiamata, criteri riunione e criteri di messaggistica, per cita solo alcuni.

Le organizzazioni hanno diversi tipi di utenti con esigenze specifiche. I criteri personalizzati creati e assegnati consentono di personalizzare le impostazioni dei criteri per diversi set di utenti in base a tali esigenze.

Per gestire facilmente i criteri nell'organizzazione, Teams diversi modi per assegnare criteri agli utenti. Assegnare un criterio direttamente agli utenti, singolarmente o su scala tramite un'assegnazione batch o a un gruppo di cui gli utenti sono membri. È anche possibile usare i pacchetti di criteri per assegnare una raccolta predefinita di criteri agli utenti dell'organizzazione con ruoli simili. L'opzione scelta dipende dal numero di criteri che si stanno gestendo e dal numero di utenti a cui si stanno assegnando i criteri. I criteri globali (predefiniti a livello di organizzazione) si applicano al maggior numero di utenti dell'organizzazione. È necessario assegnare criteri solo agli utenti che richiedono criteri specializzati.

Questo articolo descrive i diversi modi in cui è possibile assegnare criteri agli utenti e gli scenari consigliati per l'uso.

## <a name="which-policy-takes-precedence"></a>Quali criteri hanno la precedenza?

Un utente ha un criterio efficace per ogni tipo di criterio. È possibile, o anche probabile, che a un utente sia assegnato direttamente un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo. In questi tipi di scenari, quali criteri hanno la precedenza? I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.

Se a un utente viene assegnato direttamente un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza. Nell'esempio visivo seguente, i criteri effettivi dell'utente sono i criteri di riunione di Lincoln Square, assegnati direttamente all'utente.

![Diagramma che mostra come ha la precedenza un criterio assegnato direttamente.](media/assign-policies-example-directly-assigned.png)

Se a un utente non è assegnato direttamente un criterio di un determinato tipo, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza. Se un utente è membro di più gruppi, [](#group-assignment-ranking) ha la precedenza il criterio con la classificazione di assegnazione di gruppo più alta per il tipo di criterio specificato.

In questo esempio visivo, i criteri effettivi dell'utente sono i criteri Exec Teams e HD, che hanno la classificazione di assegnazione più alta rispetto ad altri gruppi di cui l'utente è membro e a cui è assegnato anche un criterio dello stesso tipo di criteri.  

![Diagramma che mostra come ha la precedenza un criterio ereditato dal gruppo.](media/assign-policies-example-group.png)

Se a un utente non è assegnato direttamente un criterio o non è membro di alcun gruppo a cui è assegnato un criterio, l'utente ottiene il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio. Ecco un esempio visivo.

![Diagramma che mostra la precedenza di un criterio globale.](media/assign-policies-example-global.png)

Per altre informazioni, vedere [Regole di precedenza.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Modi per assegnare criteri

Ecco una panoramica dei modi in cui è possibile assegnare criteri agli utenti e degli scenari consigliati per ognuno di essi. Selezionare i collegamenti per altre informazioni.

Prima di assegnare criteri a singoli utenti o gruppi, impostare i criteri globali (predefiniti a livello di [organizzazione)](#set-the-global-policies) in modo che siano applicabili al maggior numero di utenti dell'organizzazione.  Dopo aver impostato i criteri globali, sarà necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.

|Eseguire questa operazione  |Se...  | Uso in corso...
|---------|---------|----|
|[Assegnare un criterio a singoli utenti](#assign-a-policy-to-individual-users)    | Non si ha la Teams per iniziare o è sufficiente assegnare uno o un paio di criteri a un numero limitato di utenti. |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell
|[Assegnare un criterio a un gruppo](#assign-a-policy-to-a-group) |Assegnare criteri in base all'appartenenza al gruppo di un utente. Ad esempio, assegnare un criterio a tutti gli utenti di un gruppo di sicurezza o di una lista di distribuzione.| L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
|[Assegnare un criterio a un batch di utenti](#assign-a-policy-to-a-batch-of-users)   | Assegnare criteri a set di utenti di grandi dimensioni. Ad esempio, assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione contemporaneamente. |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
| [Assegnare un pacchetto di criteri agli utenti](#assign-a-policy-package-to-users)  |Assegnare più criteri a set specifici di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (Teacher) agli insegnanti dell'istituto di istruzione per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Education (Secondary school student) agli studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.  |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
| [Assegnare un pacchetto di criteri a un gruppo](#assign-a-policy-package-to-a-group) (in anteprima privata)   |Assegnare più criteri a un gruppo di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare un pacchetto di criteri a tutti gli utenti di un gruppo di sicurezza o di una lista di distribuzione. |L Microsoft Teams di amministrazione di PowerShell (disponibile a breve) o i cmdlet di PowerShell nel modulo Teams PowerShell|
| [Assegnare un pacchetto di criteri a un batch di utenti](#assign-a-policy-package-to-a-batch-of-users)|Assegnare più criteri a un batch di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (Teacher) a tutti gli insegnanti dell'istituto di istruzione usando l'assegnazione batch per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Education (Secondary school student) a un batch di studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.|Cmdlet di PowerShell nel modulo Teams PowerShell|

## <a name="set-the-global-policies"></a>Impostare i criteri globali

Seguire questa procedura per impostare i criteri globali (predefiniti a livello di organizzazione) per ogni tipo di criterio.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare alla pagina dei criteri per il tipo di criterio da aggiornare. Ad esempio, **Teams** Teams, Criteri riunioni riunioni, Criteri  >     >   **di** messaggistica o **Criteri**  >  **chiamate vocali.**
2. Selezionare il **criterio Globale (impostazione predefinita** a livello di organizzazione) per visualizzare le impostazioni correnti.
3. Aggiornare il criterio in base alle esigenze e quindi selezionare **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per impostare i criteri globali con PowerShell, usare l'identificatore globale.  Per iniziare, esaminare i criteri globali correnti per determinare l'impostazione da modificare.

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

## <a name="assign-a-policy-to-individual-users"></a>Assegnare un criterio a singoli utenti

Seguire questa procedura per assegnare un criterio a un singolo utente o a un numero limitato di utenti alla volta.

### <a name="use-the-microsoft-teams-admin-center"></a>Usare l'Microsoft Teams di amministrazione

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Utenti** e quindi selezionare l'utente.
2. Selezionare l'utente facendo clic a sinistra del nome utente e quindi selezionare **Modifica impostazioni.**
3. Selezionare il criterio da assegnare e quindi scegliere **Applica**.

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare alla pagina dei criteri.
2. Selezionare il criterio da assegnare facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo aver aggiunto gli utenti, selezionare **Applica**.

### <a name="use-powershell"></a>Usare PowerShell

Ogni tipo di criterio ha un proprio set di cmdlet per gestirlo. Usare il `Grant-` cmdlet per un determinato tipo di criterio per assegnare il criterio. Ad esempio, usare il `Grant-CsTeamsMeetingPolicy` cmdlet per assegnare un criterio Teams riunione agli utenti. Questi cmdlet sono inclusi nel modulo Teams PowerShell e sono documentati nel riferimento [Skype for Business cmdlet.](/powershell/skype/intro?view=skype-ps&preserve-view=true)

Scaricare e installare la Teams pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (se non è già stata eseguita) e quindi eseguire le operazioni seguenti per connettersi.

> [!NOTE]
> Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.
>
> Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

In questo esempio viene assegnato un criterio Teams riunione denominato Criteri riunione studente a un utente denominato Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Per altre informazioni, vedere [Gestire i criteri tramite PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

L'assegnazione dei criteri ai gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione dei criteri ai gruppi è consigliata per gruppi con un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegna il criterio, questo viene immediatamente assegnato al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

Le assegnazioni di Criteri di gruppo vengono propagate solo agli utenti che sono membri diretti del gruppo. Le assegnazioni non vengono propagate ai membri di gruppi annidati.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Informazioni necessarie sull'assegnazione dei criteri ai gruppi

Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni di gruppo.

#### <a name="precedence-rules"></a>Regole di precedenza

Per un determinato tipo di criterio, i criteri effettivi di un utente vengono determinati in base a quanto segue:

- I criteri assegnati direttamente a un utente hanno la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo. In altre parole, se a un utente viene assegnato direttamente un criterio di un determinato tipo, tale utente non erediterà un criterio dello stesso tipo da un gruppo. Questo significa anche che se un utente ha un criterio di un determinato tipo a cui è stato assegnato direttamente, è necessario rimuoverlo dall'utente prima che possa ereditare un criterio dello stesso tipo da un gruppo.

- Se a un utente non è assegnato direttamente un criterio ed è membro di due o più gruppi e a ogni gruppo è assegnato un criterio dello stesso tipo, l'utente eredita i criteri dell'assegnazione di gruppo con la classificazione più alta.

- Se un utente non è membro di alcun gruppo a cui è assegnato un criterio, il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio si applica all'utente.

I criteri effettivi di un utente vengono aggiornati in base alle regole seguenti:

- quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio.
- un criterio non è assegnato a un gruppo.
- i criteri assegnati direttamente all'utente vengono rimossi.

#### <a name="group-assignment-ranking"></a>Classificazione delle assegnazioni di gruppo

Quando si assegna un criterio a un gruppo, si specifica una classificazione per l'assegnazione del gruppo. Viene usato per determinare quali criteri un utente deve ereditare come criterio effettivo se l'utente è membro di due o più gruppi e a ogni gruppo viene assegnato un criterio dello stesso tipo.

La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo. Ad esempio, se si assegna un criterio di chiamata a due gruppi, impostare la classificazione di un'attività su 1 e l'altra su 2, con 1 come classificazione più alta. La classificazione delle assegnazioni di gruppo indica quale appartenenza al gruppo è più importante o più pertinente rispetto ad altre appartenenze ai gruppi per quanto riguarda l'ereditarietà.

Si supponga, ad esempio, di avere due gruppi, Dipendenti negozio e Responsabili negozio. A entrambi i gruppi viene assegnato un Teams di chiamata, rispettivamente criteri di chiamata dei dipendenti dello Store e criteri di chiamata dei responsabili dello store. Per un responsabile del negozio che fa parte di entrambi i gruppi, il suo ruolo di responsabile è più rilevante del suo ruolo di dipendente, quindi i criteri di chiamata assegnati al gruppo Store Manager devono avere una classificazione più alta.

|Raggruppa |Teams del criterio di chiamata  |Rango|
|---------|---------|---|
|Responsabili dello Store   |Criteri di chiamata dei responsabili dei negozi         |1|
|Dipendenti del negozio    |Criteri per le chiamate dei dipendenti dello Store      |2|

Se non si specifica una classificazione, all'assegnazione dei criteri viene assegnato il rango più basso.

### <a name="in-the-teams-admin-center"></a>Nell'Teams di amministrazione

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri di chiamata Teams, per i criteri di parcheggio di chiamata Teams, per i criteri di Teams, per gli eventi live Teams, per i criteri per le riunioni Teams e per i criteri di messaggistica Teams. Per altri tipi di criteri, usare PowerShell.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare alla pagina del tipo di criterio. Ad esempio, passare a **Criteri**  >  **riunione riunioni**.

2. Selezionare la scheda **Assegnazione criteri di** gruppo.

3. Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna criteri a **gruppo** eseguire le operazioni seguenti:
    1. Cercare e aggiungere il gruppo a cui si vuole assegnare il criterio.
    2. Impostare la classificazione per l'assegnazione di gruppo.
    3. Selezionare il criterio da assegnare.
    4. Selezionare **Applica**.

Per rimuovere un'assegnazione di  Criteri di gruppo, nella scheda Assegnazione criteri di gruppo della pagina dei criteri selezionare l'assegnazione di gruppo e quindi **scegliere Rimuovi**.

Per modificare la classificazione di un'assegnazione di gruppo, è necessario prima di tutto rimuovere l'assegnazione di Criteri di gruppo. Seguire quindi i passaggi precedenti per assegnare il criterio a un gruppo.

### <a name="use-the-powershell-option"></a>Usare l'opzione di PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti Teams tipi di criteri. Vedere [New-CsGroupPolicyAssignment per](/powershell/module/teams/new-csgrouppolicyassignment) l'elenco dei tipi di criteri supportati.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo Microsoft Teams PowerShell

Per istruzioni dettagliate, vedere Installare [Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Assegnare un criterio a un gruppo di utenti

Usare il cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) per assegnare un criterio a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio viene assegnato un criterio Teams riunione denominato Criteri riunione per i responsabili dei punti vendita al dettaglio a un gruppo con una classificazione delle assegnazioni di 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Ottenere le assegnazioni dei criteri per un gruppo

Usare il cmdlet [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) per ottenere tutti i criteri assegnati a un gruppo. Si noti che i gruppi sono sempre elencati in base all'ID gruppo, anche se per assegnare il criterio è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.

In questo esempio vengono recuperati tutti i criteri assegnati a un gruppo specifico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In questo esempio vengono restituiti tutti i gruppi a cui è assegnato un criterio Teams riunione.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Rimuovere un criterio da un gruppo

Usare il cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) per rimuovere un criterio da un gruppo. Quando si rimuove un criterio da un gruppo, vengono aggiornate le priorità di altri criteri dello stesso tipo assegnati al gruppo e con una classificazione inferiore. Ad esempio, se si rimuove un criterio con una classificazione di 2, i criteri con una classificazione di 3 e 4 vengono aggiornati in base alla nuova classificazione. Questo esempio è illustrato nelle due tabelle seguenti.

Ecco un elenco delle assegnazioni dei criteri e delle priorità per un criterio Teams riunione.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Area occidentale     |Criteri dell'area occidentale         |2         |
|Divisione    |Criteri di divisione         |3         |
|Affiliata   |Criteri affiliati        |4         |

Se il criterio Area occidentale viene rimosso dal gruppo Area ovest, le assegnazioni e le priorità dei criteri vengono aggiornate nel modo seguente.

|Nome gruppo  |Nome del criterio  |Rango|
|---------|---------|---------|
|Vendite    |Criteri di vendita       | 1        |
|Divisione    |Criteri di divisione         |2         |
|Affiliata   |Criteri affiliati        |3        |

In questo esempio vengono rimosso i criteri Teams riunione da un gruppo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Modificare un'assegnazione di criteri per un gruppo

> [!NOTE]
> Il cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) sarà disponibile a breve. Nel frattempo, per modificare un'assegnazione di criteri di gruppo, è possibile rimuovere l'assegnazione di criteri corrente dal gruppo e quindi aggiungere una nuova assegnazione di criteri.

Dopo aver assegnato un criterio a un gruppo, è possibile usare il cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) per modificare l'assegnazione dei criteri del gruppo nel modo seguente:

- Modificare la classificazione
- Modificare il criterio di un determinato tipo di criterio
- Modificare i criteri di un determinato tipo di criteri e la classificazione

In questo esempio, i criteri di Teams di un gruppo vengono 3 in un criterio denominato SupportCallPark e la classificazione delle assegnazioni viene impostata su 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Modificare i criteri effettivi per un utente

Ecco un esempio di come modificare i criteri effettivi per un utente a cui è assegnato direttamente un criterio.

Prima di tutto, viene utilizzato il cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) insieme al parametro per ottenere i dettagli dei criteri di trasmissione Teams riunione associati ```PolicySource``` all'utente.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

L'output mostra che all'utente è stato assegnato direttamente un criterio di trasmissione riunione Teams denominato Eventi dipendente, che ha la precedenza sui criteri denominati Eventi live fornitore assegnati a un gruppo a cui appartiene l'utente.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

A questo punto, il criterio Eventi dipendente viene rimosso dall'utente. Questo significa che all'utente non è più assegnato direttamente un criterio di trasmissione della riunione Teams e erediterà il criterio Eventi live fornitore assegnato al gruppo a cui appartiene l'utente.

Usare il cmdlet seguente nel modulo Skype for Business PowerShell per eseguire questa operazione.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Usare il cmdlet seguente nel modulo Teams PowerShell per eseguire questa operazione su larga scala anche se un'assegnazione di criteri batch, in cui $users è un elenco di utenti specificato dall'utente.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare un criterio a un batch di utenti

### <a name="use-the-admin-center"></a>Usare l'interfaccia di amministrazione

Per assegnare un criterio agli utenti in blocco:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione selezionare **Utenti.**

2. Cercare gli utenti a cui si vuole assegnare il criterio o filtrare la visualizzazione per visualizzare gli utenti desiderati.

3. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.

4. Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**

Per visualizzare lo stato dell'assegnazione dei criteri, nel  banner visualizzato nella  parte superiore della pagina Utenti dopo aver selezionato Applica per inviare l'assegnazione dei criteri, selezionare **Log attività.** Oppure, nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare a **Dashboard** e quindi in **Log attività** selezionare **Visualizza dettagli.** Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'Microsoft Teams di amministrazione degli ultimi 30 giorni. Per altre informazioni, vedere [Visualizzare le assegnazioni dei criteri nel log attività.](activity-log.md)

### <a name="use-powershell-method"></a>Usare il metodo di PowerShell

> [!NOTE]
> Attualmente, l'assegnazione di criteri batch con PowerShell non è disponibile per tutti Teams tipi di criteri. Per [l'elenco dei tipi di criteri supportati, vedere New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Con l'assegnazione di criteri batch, è possibile assegnare un criterio a set di utenti di grandi dimensioni alla volta senza dover usare uno script. Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e i criteri da assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato e dello stato delle assegnazioni in un batch.

Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio. Se un utente viene specificato usando l'UPN o la posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente. Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci rimanenti nel batch.

Un batch può contenere fino a 5.000 utenti. Per risultati ottimali, non inviare più di pochi batch alla volta. Consentire ai batch di completare l'elaborazione prima di inviare altri batch.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installare e connettersi al modulo Teams PowerShell

Eseguire le operazioni seguenti per installare il [Microsoft Teams di PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installare e connettersi al modulo Azure AD PowerShell per Graph (facoltativo)Install and connect to the Azure AD PowerShell for Graph module (optional)

È anche possibile scaricare e installare il modulo [di PowerShell](/powershell/azure/active-directory/install-adv2) per Graph di Azure AD (se non è già stato fatto) e connettersi a Azure AD in modo da poter recuperare un elenco di utenti nell'organizzazione.

Eseguire le operazioni seguenti per connettersi a Azure AD.

```powershell
Connect-AzureAD
```

Quando richiesto, accedere usando le stesse credenziali di amministratore usate per connettersi a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Assegnare un criterio di configurazione a un batch di utenti

In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare un criterio di configurazione dell'app denominato Criteri di configurazione app risorse umane a un batch di utenti elencati nel file Users_ids.text.

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In questo esempio ci connettiamo a Azure AD per recuperare una raccolta di utenti e quindi assegniamo un criterio di messaggistica denominato Criteri di messaggistica di nuova assunzione a un batch di utenti specificato usando l'indirizzo SIP.

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

Se l'output indica che si è verificato un errore, eseguire le operazioni seguenti per ottenere altre informazioni sugli errori presenti nella `UserState` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-package-to-users"></a>Assegnare un pacchetto di criteri agli utenti

Un pacchetto di criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli uguali o simili nell'organizzazione. Ogni pacchetto di criteri è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche del ruolo. Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Clinical Worker). Per altre informazioni, vedere [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Assegnare un pacchetto di criteri a un utente

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Utenti** e quindi selezionare l'utente.

2. Nella pagina dell'utente selezionare **Criteri** e quindi accanto a Pacchetto **criteri** selezionare **Modifica.**

3. Nel riquadro **Assegna pacchetto di** criteri selezionare il pacchetto da assegnare e quindi scegliere **Salva**.

### <a name="assign-a-policy-package-to-multiple-users"></a>Assegnare un pacchetto di criteri a più utenti

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Pacchetti criteri **e** quindi selezionare il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.

2. Scegliere **Gestisci utenti**.

3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.

4. Dopo aver aggiunto gli utenti, selezionare **Salva**.

## <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione di pacchetti di criteri ai gruppi è consigliata per gruppi con un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegna il pacchetto di criteri, questo viene immediatamente assegnato al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

> [!IMPORTANT]
> Prima di iniziare, è importante comprendere le regole di precedenza e la [classificazione](#precedence-rules) [delle assegnazioni di gruppo.](#group-assignment-ranking) Leggere e comprendere i concetti descritti [in](#what-you-need-to-know-about-policy-assignment-to-groups) Informazioni sull'assegnazione dei criteri ai gruppi più indietro in questo articolo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Assegnare un pacchetto di criteri a un gruppo di utenti nell'interfaccia di amministrazione

1. Passare all'interfaccia di amministrazione di Teams.
2. Nel riquadro di spostamento sinistro passare alla pagina del pacchetto di criteri.
3. Selezionare la scheda Raggruppa assegnazione pacchetto.
4. Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna un pacchetto di criteri al gruppo eseguire le operazioni seguenti:

   - Cercare e aggiungere il gruppo a cui si vuole assegnare il pacchetto di criteri.

2. Nel riquadro di spostamento sinistro passare alla pagina del pacchetto di criteri.

3. Selezionare la scheda Assegnazione criteri di gruppo.

4. Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna un pacchetto di criteri al gruppo eseguire le operazioni seguenti:

    1. Cercare e aggiungere il gruppo a cui si vuole assegnare il pacchetto di criteri.
    
    1. Selezionare un pacchetto di criteri.
    
    1. Impostare la classificazione per ogni tipo di criterio.
    
    1. Selezionare **Applica**.
    
    ![mostra l'assegnazione dei Criteri di gruppo.](media/group-pkg-assignment.png)

5. Per gestire la classificazione per un tipo di criterio specifico, passare alla pagina dei criteri specifica.

6. Per riassegnare un pacchetto di criteri a un gruppo, rimuovere prima l'assegnazione dei criteri di gruppo. Seguire quindi i passaggi precedenti per assegnare il pacchetto di criteri a un gruppo.

### <a name="work-with-powershell"></a>Usare PowerShell

#### <a name="get-the-teams-powershell-module"></a>Ottenere il modulo Teams PowerShell

Per istruzioni dettagliate, vedere Installare [Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Assegnare un pacchetto di criteri a un gruppo di utenti

Usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica. Quando si assegna il pacchetto di criteri, specificare una classificazione [delle assegnazioni di gruppo](#group-assignment-ranking) per ogni tipo di criterio nel pacchetto di criteri.

In questo esempio il pacchetto di criteri Education_Teacher viene assegnato a un gruppo con una classificazione delle assegnazioni 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione 2 per TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Assegnare un pacchetto di criteri a un batch di utenti

Con l'assegnazione di pacchetti di criteri batch, è possibile assegnare un pacchetto di criteri a set di utenti di grandi dimensioni alla volta senza dover usare uno script. Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri da assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch. È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato e dello stato delle assegnazioni in un batch.

Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio. Se un utente viene specificato usando l'UPN o la posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente. Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci rimanenti nel batch.

Un batch contiene fino a 5.000 utenti. Per risultati ottimali, non inviare più di pochi batch alla volta. Consentire ai batch di completare l'elaborazione prima di inviare altri batch.

### <a name="use-the-teams-powershell-module"></a>Usare il modulo Teams PowerShell

Eseguire le operazioni seguenti per installare [il Microsoft Teams di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già stato fatto). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Assegnare pacchetti di criteri a un batch di utenti

In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare il pacchetto di criteri di Education_PrimaryStudent a un batch di utenti.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Visualizzare lo stato di un'assegnazione batch

Eseguire quanto segue per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal `New-CsBatchPolicyAssignmentOperation` cmdlet per un determinato batch.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire le operazioni seguenti per ottenere altre informazioni sugli errori presenti nella `UserState` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Argomenti correlati

[Teams Panoramica di PowerShell](teams-powershell-overview.md)
