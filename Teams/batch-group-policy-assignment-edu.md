---
title: Assegnare criteri a grandi gruppi di utenti nella tua scuola
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come assegnare criteri a grandi insiemi di utenti nell'Istituto di istruzione in base all'appartenenza al gruppo o direttamente tramite un'assegnazione batch per scopi scolastici remoti (Teleschool, tele-School).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534102"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Assegnare criteri a grandi gruppi di utenti nella tua scuola

> [!NOTE]
> Per una storia più ampia sull'assegnazione di criteri in Microsoft teams, vedere [assegnare criteri agli utenti in teams](assign-policies.md).

## <a name="overview"></a>Panoramica

È necessario offrire agli studenti e agli insegnanti l'accesso a funzionalità diverse in Microsoft Teams? È possibile identificare rapidamente gli utenti dell'organizzazione per tipo di licenza e quindi assegnare il criterio appropriato. In questa esercitazione viene illustrato come assegnare un criterio di riunione a set di utenti di grandi dimensioni nell'Istituto di istruzione. Puoi assegnare criteri usando l'interfaccia di amministrazione di Microsoft teams e PowerShell e ti mostreremo entrambi i modi.

È possibile assegnare un criterio di riunione a un gruppo di sicurezza che gli utenti sono membri o direttamente agli utenti in scala tramite un'assegnazione di criteri batch. Imparerai a:

- **Usare l' [assegnazione dei criteri per i gruppi](#assign-a-policy-to-a-group) per assegnare un criterio di riunione a un gruppo di sicurezza (scelta consigliata)**. Questo metodo consente di assegnare un criterio in base all'appartenenza al gruppo. È possibile assegnare un criterio a un gruppo di sicurezza o a una lista di distribuzione. Quando i membri vengono aggiunti o rimossi dal gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. Ti consigliamo di usare questo metodo perché riduce il tempo necessario per gestire i criteri per i nuovi utenti o quando cambiano i ruoli degli utenti. Questo metodo funziona meglio per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.

- **Usare l' [assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare un criterio di riunione direttamente agli utenti in blocco**. È possibile assegnare un criterio per un massimo di 5.000 utenti alla volta. Se si hanno più di 5.000 utenti, è possibile inviare più batch. Con questo metodo, quando si hanno nuovi utenti, è necessario eseguire di nuovo l'assegnazione batch per assegnare i criteri a tali nuovi utenti.

Tenere presente che in teams gli utenti ottengono automaticamente il criterio globale (org-Wide default) per un tipo di criteri teams, a meno che non si creino e si assegnano criteri personalizzati. Poiché la popolazione studente è spesso il più grande insieme di utenti e spesso riceve le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:

- Creare criteri personalizzati che consentano funzionalità di base, ad esempio la chat privata e la pianificazione delle riunioni, e assegnare i criteri al personale e agli insegnanti.
- Assegnare i criteri personalizzati al personale e agli educatori.
- Modificare e applicare il criterio globale (predefinito a livello di organizzazione) per limitare le funzionalità per gli studenti.

Tieni presente che il criterio globale verrà applicato a tutti gli utenti dell'Istituto di istruzione fino a quando non creerai un criterio personalizzato e lo assegnerò al personale e agli insegnanti.

In questa esercitazione gli studenti otterranno i criteri globali per le riunioni e assegnerò un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti. Supponiamo che tu abbia modificato il criterio globale per adattare le impostazioni delle riunioni per gli studenti e [creato un criterio personalizzato](policy-packages-edu.md) che definisce l'esperienza di riunione per il personale e gli educatori.

![Screenshot della pagina criteri riunione nell'interfaccia di amministrazione di Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

Seguire questa procedura per creare un gruppo di sicurezza per il personale e gli educatori e quindi assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al gruppo di sicurezza.

### <a name="before-you-get-started"></a>Nozioni preliminari

> [!IMPORTANT]
> Quando si assegna un criterio a un gruppo, l'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Ad esempio, se un utente ha direttamente assegnato un criterio (individualmente o tramite un'assegnazione batch), tale criterio ha la precedenza su un criterio ereditato da un gruppo. Ciò significa anche che, se un utente ha un criterio di riunione direttamente assegnato a tali criteri, sarà necessario rimuovere i criteri della riunione dall'utente prima che possano ereditare i criteri di una riunione da un gruppo di sicurezza.

Prima di iniziare, è importante comprendere [le regole di precedenza](assign-policies.md#precedence-rules) e la [classificazione delle assegnazioni di gruppo](assign-policies.md#group-assignment-ranking). Verificare di **aver letto e compreso i concetti che [occorre sapere sull'assegnazione dei criteri ai gruppi](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

È necessario completare tutti questi passaggi per il personale e gli educatori per ereditare i criteri di una riunione da un gruppo di sicurezza.

1. [Creare gruppi di sicurezza](#create-security-groups).
2. [Assegnare un criterio a un gruppo di sicurezza](#assign-a-policy-to-a-security-group).
3. [Rimuovere un criterio direttamente assegnato agli utenti](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Creare gruppi di sicurezza

Prima di tutto, crea un gruppo di sicurezza per il personale e gli educatori.

Con [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), puoi [facilmente creare gruppi di sicurezza per educatori e studenti](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) nella tua scuola. Ti consigliamo di usare SDS per creare i gruppi di sicurezza necessari per gestire i criteri per la tua scuola.

Se non si riesce a distribuire SDS nell'ambiente, usare [questo script di PowerShell](scripts/powershell-script-security-groups-edu.md) per creare due gruppi di sicurezza, uno per tutti i membri del personale e gli educatori che hanno una licenza di facoltà e un altro per tutti gli studenti a cui è assegnata una licenza per studenti. È necessario eseguire questo script in modo sistematico per aggiornare i gruppi.

### <a name="assign-a-policy-to-a-security-group"></a>Assegnare un criterio a un gruppo di sicurezza

#### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft teams è disponibile solo per i criteri di chiamata dei team, i criteri di parcheggio per i team, i criteri per i team, i criteri per le riunioni dei team e i criteri di messaggistica di team. Per altri tipi di criteri, usare PowerShell.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Selezionare la scheda **assegnazione criteri di gruppo** .
3. Selezionare **Aggiungi gruppo**e quindi nel riquadro **Assegna criteri a gruppo** eseguire le operazioni seguenti:

    ![Screenshot del riquadro Modifica impostazioni che mostra i criteri delle riunioni](media/batch-group-policy-assignment-edu-group.png)
    1. Nella casella **selezionare un gruppo** cercare e aggiungere il gruppo di sicurezza che contiene il personale e gli insegnanti.
    2. Nella casella **Seleziona rango** immettere **1**.
    3. Nella casella **selezionare un criterio** selezionare **EducatorMeetingPolicy**.
    4. Selezionare **applica**.

Per rimuovere un'assegnazione di criteri di gruppo, nella scheda assegnazione criteri di **gruppo** della pagina Criteri selezionare l'assegnazione del gruppo e quindi scegliere **Rimuovi**.

Per modificare la classificazione di un'assegnazione di gruppo, è necessario rimuovere prima di tutto l'assegnazione dei criteri di gruppo. Seguire quindi la procedura descritta in precedenza per assegnare i criteri a un gruppo.

#### <a name="using-powershell"></a>Utilizzo di PowerShell

> [!NOTE]
> Attualmente, l'assegnazione dei criteri ai gruppi che usano PowerShell non è disponibile per tutti i tipi di criteri teams. Vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```

Quando viene richiesto, accedere con le credenziali di amministratore.

##### <a name="assign-a-policy-to-a-group"></a>Assegnare un criterio a un gruppo

Eseguire la procedura seguente per assegnare il criterio della riunione denominato EducatorMeetingPolicy al gruppo di sicurezza che contiene il personale e gli insegnanti e impostare la classificazione delle assegnazioni su 1. Puoi specificare un gruppo di sicurezza usando l'ID oggetto, l'indirizzo SIP (Session Initiation Protocol) o l'indirizzo di posta elettronica. In questo esempio usiamo un indirizzo di posta elettronica (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Rimuovere un criterio assegnato direttamente agli utenti

Tenere presente che se all'utente è stato assegnato un criterio direttamente (individualmente o tramite un'assegnazione batch), tale criterio ha la precedenza. Ciò significa che se un utente ha un criterio di riunione direttamente assegnato a tali criteri, sarà necessario rimuovere i criteri della riunione dall'utente prima che possano ereditare i criteri di una riunione da un gruppo di sicurezza.

Per altre informazioni, vedere [cosa occorre sapere sull'assegnazione dei criteri ai gruppi](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).

Seguire questa procedura per rimuovere i criteri della riunione direttamente assegnati al personale e agli insegnanti.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```
Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Annullare l'assegnazione di un criterio assegnato direttamente agli utenti

Eseguire la procedura seguente per rimuovere un criterio della riunione dagli utenti a cui è stato assegnato direttamente il criterio. Puoi specificare gli utenti tramite l'indirizzo di posta elettronica o l'ID oggetto.

In questo esempio, il criterio della riunione viene rimosso dagli utenti specificati dall'indirizzo di posta elettronica.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

In questo esempio, il criterio della riunione viene rimosso dall'elenco di utenti in un file di testo denominato user_ids.txt. 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Ottenere le assegnazioni dei criteri per un gruppo

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un gruppo di sicurezza specifico. Tieni presente che i gruppi sono sempre elencati dall'ID del gruppo, anche se l'indirizzo SIP o l'indirizzo di posta elettronica è stato usato per assegnare il criterio.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Ottenere i criteri assegnati a un utente

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico. L'esempio seguente mostra come ottenere i criteri assegnati a reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Assegnare un criterio a un gruppo di utenti

Seguire questa procedura per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy direttamente al personale e agli insegnanti in blocco.

### <a name="using-powershell"></a>Utilizzo di PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Connettersi al modulo di Azure AD PowerShell per il grafico e al modulo di PowerShell Teams

Prima di eseguire la procedura descritta in questo articolo, è necessario installare e connettersi a Azure AD PowerShell per il modulo grafico (per identificare gli utenti tramite le licenze assegnate) e il modulo di PowerShell di Microsoft Teams (per assegnare i criteri a tali utenti).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installare e connettersi al modulo di Azure AD PowerShell per il grafico

Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire le operazioni seguenti per installare il modulo di PowerShell per il grafico di Azure Active Directory.

```powershell
Install-Module -Name AzureAD
```

Eseguire la procedura seguente per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando viene richiesto, accedere con le credenziali di amministratore.

Per altre informazioni, vedere [connettersi con il modulo di PowerShell per il grafico di Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installare e connettersi al modulo di PowerShell di Microsoft Teams

Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato). Assicurarsi di installare la versione 1.0.5 o successiva.

```powershell
Install-Module -Name MicrosoftTeams
```

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```
Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.

#### <a name="identify-your-users"></a>Identificare gli utenti

Prima di tutto, Esegui le operazioni seguenti per identificare il personale e gli educatori per tipo di licenza. Questo spiega quali SKU sono in uso nell'organizzazione. È quindi possibile identificare il personale e gli insegnanti che hanno un SKU di facoltà assegnato.

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

In questo esempio l'output mostra che la licenza di facoltà SkuId è "e97c048c-37a4-45fb-AB50-922fbf07a370".

> [!NOTE]
> Per visualizzare un elenco di SKU per l'istruzione e ID SKU, vedere informazioni di [riferimento su SKU per l'](sku-reference-edu.md)istruzione.

Eseguiamo quindi le operazioni seguenti per identificare gli utenti con questa licenza e raccoglierli tutti insieme.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Assegnare un criterio in blocco

A questo punto, assegniamo i criteri appropriati agli utenti in blocco. Il numero massimo di utenti per cui è possibile assegnare o aggiornare i criteri è 5.000 alla volta. Ad esempio, se si hanno più di 5.000 personale ed educatori, è necessario inviare più batch.

Eseguire la procedura seguente per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare ```PolicyType``` al criterio che si sta assegnando e ```PolicyName``` al nome del criterio.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Ottenere lo stato di un'assegnazione in blocco

Ogni assegnazione in blocco restituisce un ID operazione, che può essere usato per tenere traccia dell'avanzamento delle assegnazioni dei criteri o per identificare eventuali errori che potrebbero verificarsi. Ad esempio, eseguire le operazioni seguenti:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Per visualizzare lo stato di assegnazione di ogni utente nell'operazione batch, eseguire la procedura seguente. I dettagli di ogni utente si trovano nella ```UserState``` Proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Assegnare un criterio in blocco se si hanno più di 5.000 utenti

Prima di tutto, eseguire le operazioni seguenti per verificare il numero di membri del personale e gli insegnanti:

```powershell
$faculty.count
```

Invece di fornire l'intero elenco di ID utente, eseguire la procedura seguente per specificare il primo 5.000 e quindi il successivo 5.000 e così via.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Puoi modificare l'intervallo di ID utente fino a raggiungere l'elenco completo degli utenti. Ad esempio, immetti ```$faculty[0..4999``` per il primo batch, USA ```$faculty[5000..9999``` per il secondo batch, immetti ```$faculty[10000..14999``` per il terzo batch e così via.

#### <a name="get-the-policies-assigned-to-a-user"></a>Ottenere i criteri assegnati a un utente

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico. L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Domande frequenti

**Non si ha familiarità con PowerShell per Teams. Dove è possibile ottenere altre informazioni?**

Per una panoramica sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md). Per altre informazioni sui cmdlet usati in questo articolo, vedere:

- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)
- [Criteri per i team e pacchetti di criteri per l'istruzione](policy-packages-edu.md)
- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
