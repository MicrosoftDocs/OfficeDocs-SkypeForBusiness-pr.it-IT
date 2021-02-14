---
title: Assegnare criteri a grandi set di utenti dell'istituto di istruzione
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come assegnare criteri a grandi set di utenti dell'istituto di istruzione in base all'appartenenza ai gruppi o direttamente tramite un'assegnazione in batch per scopi scolastici remoti (teleschool o telescuola).
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616940"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Assegnare criteri a grandi set di utenti dell'istituto di istruzione

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Per informazioni più esaustivo sull'assegnazione di criteri in Microsoft Teams, vedere [Assegnare criteri agli utenti in Teams.](assign-policies.md)

## <a name="overview"></a>Panoramica

È necessario concedere a studenti e docenti l'accesso a diverse funzionalità di Microsoft Teams? È possibile identificare rapidamente gli utenti dell'organizzazione per tipo di licenza e quindi assegnare loro i criteri appropriati. Questa esercitazione illustra come assegnare criteri di riunione a grandi set di utenti dell'istituto di istruzione. È possibile assegnare criteri usando l'interfaccia di amministrazione di Microsoft Teams e PowerShell, come illustrato in entrambi i modi.

È possibile assegnare criteri di riunione a un gruppo di sicurezza di cui gli utenti sono membri o direttamente agli utenti su scala attraverso un'assegnazione di criteri batch. Si imparerà a:

- **Usare [l'assegnazione dei criteri ai](#assign-a-policy-to-a-group) gruppi per assegnare criteri di riunione a un gruppo di sicurezza (scelta consigliata).** Questo metodo consente di assegnare un criterio in base all'appartenenza ai gruppi. È possibile assegnare criteri a un gruppo di sicurezza o a una lista di distribuzione. Quando i membri vengono aggiunti o rimossi dal gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. È consigliabile usare questo metodo perché riduce il tempo necessario per gestire i criteri per i nuovi utenti o quando cambiano i ruoli degli utenti. Questo metodo è ottimale per gruppi di massimo 50.000 utenti, ma funziona anche con gruppi più grandi.

- **Usare [l'assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare criteri di riunione direttamente agli utenti in blocco.** È possibile assegnare criteri a un massimo di 5.000 utenti alla volta. Se gli utenti sono più di 5.000, è possibile inviare più batch. Con questo metodo, quando si hanno nuovi utenti, è necessario eseguire di nuovo l'assegnazione batch per assegnare i criteri a questi nuovi utenti.

Tenere presente che in Teams gli utenti ottengono automaticamente il criterio globale (impostazione predefinita a livello di organizzazione) per un tipo di criterio di Teams, a meno che non si crei e assegni un criterio personalizzato. Poiché la popolazione studente è spesso il set più grande di utenti e spesso riceve le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:

- Creare un criterio personalizzato che consente funzionalità di base come la chat privata e la pianificazione delle riunioni e assegnare i criteri a personale e docenti.
- Assegnare criteri personalizzati a personale e docenti.
- Modificare e applicare il criterio globale (impostazione predefinita a livello di organizzazione) per limitare le funzionalità per gli studenti.

Tenere presente che i criteri globali verranno applicati a tutti gli utenti dell'istituto di istruzione finché non si crea un criterio personalizzato e lo si assegna a personale e docenti.

In questa esercitazione gli studenti riceveranno il criterio di riunione globale e gli studenti riceveranno un criterio di riunione personalizzato denominato EducatorMeetingPolicy a personale e docenti. Si suppone che il criterio globale sia stato modificato [](policy-packages-edu.md) per personalizzare le impostazioni delle riunioni per gli studenti e che sia stato creato un criterio personalizzato che definiva l'esperienza della riunione per personale e docenti.

![Screenshot della pagina Criteri riunione nell'interfaccia di amministrazione di Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

Seguire questa procedura per creare un gruppo di sicurezza per il personale e i docenti e quindi assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy a tale gruppo di sicurezza.

### <a name="before-you-get-started"></a>Nozioni preliminari

> [!IMPORTANT]
> Quando si assegna un criterio a un gruppo, l'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Ad esempio, se a un utente viene assegnato direttamente un criterio (singolarmente o tramite un'assegnazione di batch), tale criterio ha la precedenza su un criterio ereditato da un gruppo. Questo significa anche che se un utente ha un criterio di riunione che gli è stato assegnato direttamente, sarà necessario rimuoverlo dall'utente prima di ereditare un criterio di riunione da un gruppo di sicurezza.

Prima di iniziare, è importante comprendere le regole di precedenza e la [classificazione](assign-policies.md#precedence-rules) [delle assegnazioni dei gruppi.](assign-policies.md#group-assignment-ranking) Assicurarsi di leggere e comprendere i concetti illustrati in Informazioni importanti sull'assegnazione **[dei criteri ai gruppi.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**

È necessario completare tutti questi passaggi perché il personale e i docenti ereditino i criteri di riunione da un gruppo di sicurezza.

1. [Creare gruppi di sicurezza.](#create-security-groups)
2. [Assegnare un criterio a un gruppo di sicurezza.](#assign-a-policy-to-a-security-group)
3. [Rimuovere un criterio assegnato direttamente agli utenti.](#remove-a-policy-that-was-directly-assigned-to-users)

### <a name="create-security-groups"></a>Creare gruppi di sicurezza

Prima di tutto, creare un gruppo di sicurezza per personale e docenti.

Con [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) è possibile creare facilmente gruppi di sicurezza come docenti e [studenti](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) nell'istituto di istruzione. È consigliabile usare SDS per creare i gruppi di sicurezza necessari per gestire i criteri per l'istituto di istruzione.

Se non si riesce a distribuire SDS all'interno dell'ambiente, usare questo script di [PowerShell](scripts/powershell-script-security-groups-edu.md) per creare due gruppi di sicurezza, uno per tutti i membri del personale e gli educatori a cui è assegnata una licenza per istituti di istruzione e un altro per tutti gli studenti a cui è assegnata una licenza per studenti. È necessario eseguire regolarmente questo script per mantenere i gruppi aggiornati.

### <a name="assign-a-policy-to-a-security-group"></a>Assegnare un criterio a un gruppo di sicurezza

#### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi tramite l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri di chiamata di Teams, i criteri del parco chiamate di Teams, i criteri di Teams, i criteri per gli eventi live di Teams, i criteri delle riunioni di Teams e i criteri di messaggistica di Teams. Per altri tipi di criteri, usare PowerShell.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Selezionare la scheda **di assegnazione di Criteri di** gruppo.
3. Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna **criteri** a gruppo eseguire le operazioni seguenti:

    ![Screenshot del riquadro Modifica impostazioni con il criterio di riunione](media/batch-group-policy-assignment-edu-group.png)
    1. Nella casella **Selezionare un gruppo** cercare e aggiungere il gruppo di sicurezza che contiene il personale e i docenti.
    2. Nella casella **Seleziona classificazione** immettere **1.**
    3. Nella casella **Seleziona un criterio** selezionare **EducatorMeetingPolicy.**
    4. Selezionare **Applica.**

Per rimuovere un'assegnazione di  Criteri di gruppo, nella scheda Assegnazione di Criteri di gruppo della pagina criteri selezionare l'assegnazione del gruppo e quindi **scegliere Rimuovi.**

Per modificare la classificazione di un'assegnazione di gruppo, è necessario prima rimuovere l'assegnazione di Criteri di gruppo. Quindi, seguire la procedura precedente per assegnare i criteri a un gruppo.

#### <a name="using-powershell"></a>Utilizzo di PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti i tipi di criteri di Teams. Per [l'elenco dei tipi di criteri supportati, vedere New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo Microsoft Teams PowerShell

Eseguire la procedura seguente per installare il [modulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Esegui quanto segue per connetterti a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le credenziali di amministratore.

##### <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

Eseguire la procedura seguente per assegnare il criterio di riunione denominato EducatorMeetingPolicy al gruppo di sicurezza che contiene il personale e i docenti e impostare la classificazione delle assegnazioni su 1. È possibile specificare un gruppo di sicurezza usando l'ID oggetto, l'indirizzo SIP (Session Initiation Protocol) o l'indirizzo di posta elettronica. In questo esempio viene utilizzato un indirizzo di posta elettronica (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Rimuovere un criterio assegnato direttamente agli utenti

Tenere presente che se a un utente è stato assegnato direttamente un criterio (singolarmente o tramite un'assegnazione di batch), tale criterio ha la precedenza. Questo significa che se un utente ha un criterio di riunione che gli è stato assegnato direttamente, sarà necessario rimuoverlo dall'utente prima di ereditare un criterio di riunione da un gruppo di sicurezza.

Per altre informazioni, vedere [Informazioni necessarie sull'assegnazione dei criteri ai gruppi.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)

Seguire questa procedura per rimuovere il criterio di riunione che è stato assegnato direttamente al personale e ai docenti.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo Microsoft Teams PowerShell

Eseguire la procedura seguente per installare il [modulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Esegui quanto segue per connetterti a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Annullare l'assegnazione di un criterio assegnato direttamente agli utenti

Eseguire la procedura seguente per rimuovere un criterio di riunione dagli utenti a cui è stato assegnato direttamente tale criterio. È possibile specificare gli utenti in base all'indirizzo di posta elettronica o all'ID oggetto.

In questo esempio il criterio di riunione viene rimosso dagli utenti specificati dal loro indirizzo di posta elettronica.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

In questo esempio il criterio di riunione viene rimosso dall'elenco di utenti in un file di testo denominato user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Ottenere assegnazioni dei criteri per un gruppo

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un gruppo di sicurezza specifico. Tenere presente che i gruppi sono sempre elencati in base all'ID gruppo anche se per assegnare i criteri è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Ottenere i criteri assegnati a un utente

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico. L'esempio seguente mostra come ottenere i criteri assegnati a reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare criteri a un batch di utenti

Seguire questa procedura per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy direttamente al personale e ai docenti in blocco.

### <a name="using-powershell"></a>Utilizzo di PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Connettersi al modulo Azure AD PowerShell per Graph e al modulo Di PowerShell di Teams

Prima di eseguire i passaggi descritti in questo articolo, è necessario installare e connettersi al modulo Azure AD PowerShell per Graph (per identificare gli utenti in base alle licenze assegnate) e al modulo Microsoft Teams PowerShell (per assegnare i criteri a tali utenti).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installare e connettersi al modulo Azure AD PowerShell per Graph

Aprire un prompt dei Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire quanto segue per installare il modulo Azure Active Directory PowerShell for Graph.

```powershell
Install-Module -Name AzureAD
```

Eseguire la procedura seguente per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando richiesto, accedere con le credenziali di amministratore.

Per altre informazioni, vedere [Connettersi con il modulo Azure Active Directory PowerShell for Graph.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo Microsoft Teams PowerShell

Eseguire la procedura seguente per installare il [modulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Esegui quanto segue per connetterti a Teams e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.

#### <a name="identify-your-users"></a>Identificare gli utenti

Eseguire prima di tutto quanto segue per identificare il personale e i docenti in base al tipo di licenza. Questo indica quali SKU sono in uso nell'organizzazione. Sarà quindi possibile identificare il personale e i docenti a cui è assegnato uno SKU per istituti di docente.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Che restituisce:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

In questo esempio l'output mostra che SKUId della licenza per istituti di docente è "e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Per visualizzare un elenco di SKU Education e ID SKU, vedere informazioni di riferimento [su Education SKU.](sku-reference-edu.md)

Esegui quindi la procedura seguente per identificare gli utenti che hanno questa licenza e raccoglierli tutti insieme.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Assegnare un criterio in blocco

A questo punto, gli utenti vengono assegnati in blocco agli utenti. Il numero massimo di utenti per cui è possibile assegnare o aggiornare i criteri è 5.000 alla volta. Ad esempio, se si hanno più di 5.000 membri del personale e docenti, è necessario inviare più batch.

Eseguire la procedura seguente per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy a personale e docenti.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare al criterio da assegnare e al ```PolicyType``` ```PolicyName``` nome del criterio.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Ottenere lo stato di un'assegnazione in blocco

Ogni assegnazione in blocco restituisce un ID operazione, che è possibile usare per tenere traccia dello stato delle assegnazioni dei criteri o identificare gli eventuali errori. Ad esempio, eseguire:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Per visualizzare lo stato dell'assegnazione di ogni utente nell'operazione batch, eseguire quanto segue. I dettagli di ogni utente sono nella ```UserState``` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Assegnare un criterio in blocco se si hanno più di 5.000 utenti

Eseguire prima di tutto quanto segue per determinare il numero di membri del personale e dei docenti disponibili:

```powershell
$faculty.count
```

Invece di fornire l'intero elenco di ID utente, eseguire la procedura seguente per specificare i primi 5.000 e i successivi 5.000 e così via.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

È possibile modificare l'intervallo di ID utente fino a raggiungere l'elenco completo di utenti. Ad esempio, immettere ```$faculty[0..4999``` per il primo batch, usare per il ```$faculty[5000..9999``` secondo batch, immettere per il terzo batch ```$faculty[10000..14999``` e così via.

#### <a name="get-the-policies-assigned-to-a-user"></a>Ottenere i criteri assegnati a un utente

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico. L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Domande frequenti

**Non ho familiarità con PowerShell per Teams. Dove è possibile trovare altre informazioni?**

Per una panoramica sull'uso di PowerShell per gestire Teams, vedere La panoramica [di Teams su PowerShell.](teams-powershell-overview.md) Per altre informazioni sui cmdlet usati in questo articolo, vedere:

- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)
- [Criteri e pacchetti di criteri di Teams per l'istruzione](policy-packages-edu.md)
- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
