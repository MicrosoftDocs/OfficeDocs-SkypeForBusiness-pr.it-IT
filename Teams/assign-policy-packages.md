---
title: Assegnare pacchetti di criteri a utenti e gruppi
author: KarliStites
ms.author: kastites
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
description: Informazioni sui diversi modi per assegnare pacchetti di criteri a utenti e gruppi in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 553e30fa694403b2ad5e2edfd86b53fe8231eed3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015070"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Assegnare pacchetti di criteri a utenti e gruppi

Questo articolo illustra i diversi modi per assegnare pacchetti di criteri a utenti e gruppi in Microsoft Teams. Prima di leggere, assicurarsi di aver letto [Assegnare criteri in Teams - Guida introduttiva](policy-assignment-overview.md).

> [!NOTE]
> Ogni utente richiederà il componente aggiuntivo Comunicazioni avanzate per ricevere un'assegnazione del pacchetto di criteri personalizzata. Per ulteriori informazioni, vedere [Componente aggiuntivo per comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Assegnare un pacchetto di criteri agli utenti

Un pacchetto di criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli uguali o simili nell'organizzazione. Ogni pacchetto di criteri è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche del ruolo. Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Clinical worker). Per altre informazioni, vedere [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Assegnare un pacchetto di criteri a un utente

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Utenti** e quindi selezionare l'utente.

2. Nella pagina dell'utente selezionare **Criteri** e quindi accanto a Pacchetto **criteri** selezionare **Modifica.**

3. Nel riquadro **Assegna pacchetto di** criteri selezionare il pacchetto da assegnare e quindi scegliere **Salva**.

![Teams screenshot dell'interfaccia di amministrazione per l'assegnazione di pacchetti di criteri a un utente.](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Assegnare un pacchetto di criteri a più utenti

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a Pacchetti criteri **e** quindi selezionare il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.

2. Scegliere **Gestisci utenti**.

3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.

4. Dopo aver aggiunto gli utenti, selezionare **Salva**.


![Teams screenshot dell'interfaccia di amministrazione per l'assegnazione di pacchetti di criteri a più utenti.](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.

L'assegnazione di pacchetti di criteri ai gruppi è consigliata per gruppi con un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.

Quando si assegna il pacchetto di criteri, questo viene immediatamente assegnato al gruppo. Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo. Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.

> [!IMPORTANT]
> Prima di iniziare, è importante comprendere[(](assign-policies-users-and-groups.md#precedence-rules)regole di precedenza ) e ([classificazione assegnazione gruppo](assign-policies-users-and-groups.md#group-assignment-ranking)). Leggere e comprendere i concetti descritti in[(](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)Informazioni necessarie sull'assegnazione dei criteri ai gruppi ) più indietro in questo articolo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Assegnare un pacchetto di criteri a un gruppo di utenti nell'interfaccia di amministrazione

1. Passare all'interfaccia di amministrazione di Teams.

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

Usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo. È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica. Quando si assegna il pacchetto di criteri, specificare una ( classificazione[assegnazione gruppo](assign-policies-users-and-groups.md#group-assignment-ranking)) per ogni tipo di criterio nel pacchetto di criteri.

In questo esempio il pacchetto di criteri Education_Teacher viene assegnato a un gruppo con una classificazione delle assegnazioni di 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione 2 per TeamsMeetingPolicy.

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
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se l'output indica che si è verificato un errore, eseguire le operazioni seguenti per ottenere altre informazioni sugli errori presenti nella `UserState` proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire Teams con i criteri](manage-teams-with-policies.md)
- [Gestire i pacchetti di criteri in Microsoft Teams](manage-policy-packages.md)
- [Teams Panoramica di PowerShell](teams-powershell-overview.md)
- [Assegnare criteri in Teams - Guida introduttiva](policy-assignment-overview.md)
