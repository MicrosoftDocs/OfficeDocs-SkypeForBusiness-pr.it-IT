---
title: Assegnare criteri a grandi gruppi di utenti nella tua scuola
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Informazioni su come usare l'assegnazione di criteri batch per assegnare i criteri a set di grandi dimensioni degli utenti nell'Istituto di istruzione in blocco per scopi scolastici remoti (Teleschool, tele-scuola).
f1keywords: ''
ms.openlocfilehash: e95c6b035298ce583a0ad34a030f2086b7c12ff3
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583339"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Assegnare criteri a grandi gruppi di utenti nella tua scuola

È necessario offrire agli studenti e agli insegnanti l'accesso a funzionalità diverse in Microsoft Teams? È possibile identificare rapidamente gli utenti dell'organizzazione per tipo di licenza e quindi assegnare il criterio appropriato. In questa esercitazione viene illustrato come usare l' [assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare un criterio di riunione agli utenti in blocco.

Tenere presente che in teams gli utenti ottengono automaticamente il criterio globale (org-Wide default) per un tipo di criteri teams, a meno che non si creino e si assegnano criteri personalizzati. Poiché la popolazione studente è spesso il più grande insieme di utenti e spesso riceve le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:

- Modificare e applicare il criterio globale (predefinito a livello di organizzazione) per limitare le funzionalità per gli studenti. 
- Creare criteri personalizzati che consentano funzionalità di base, ad esempio la chat privata e la pianificazione delle riunioni, e assegnare i criteri al personale e agli insegnanti.

Tieni presente che il criterio globale verrà applicato a tutti gli utenti dell'Istituto di istruzione fino a quando non creerai un criterio personalizzato e lo assegnerò al personale e agli insegnanti.

In questa esercitazione gli studenti otterranno i criteri riunione globale e usiamo PowerShell per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti in blocco. Supponiamo che tu abbia modificato il criterio globale per adattare le impostazioni delle riunioni per gli studenti e creato un criterio personalizzato che definisce l'esperienza di riunione per il personale e gli educatori.

![Screenshot della pagina criteri riunione nell'interfaccia di amministrazione di Teams](media/edu-batch-policy-assignment.png)

Seguire questa procedura per assegnare un criterio di riunione personalizzato al personale e agli insegnanti in blocco.

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Connettersi al modulo di Azure AD PowerShell per il grafico e al modulo di PowerShell Teams

Prima di eseguire la procedura descritta in questo articolo, è necessario installare e connettersi a Azure AD PowerShell per modulo grafico (per identificare gli utenti in base alle licenze assegnate) e alla versione preliminare del modulo di PowerShell di Microsoft Teams (per assegnare i criteri a tali utenti).

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installare e connettersi al modulo di Azure AD PowerShell per il grafico

Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire le operazioni seguenti per installare il modulo di PowerShell per il grafico di Azure Active Directory.

```powershell
Install-Module AzureAD
```

Eseguire la procedura seguente per connettersi ad Azure AD.

```powershell
Connect-AzureAD
```

Quando viene richiesto, accedere con le credenziali di amministratore.

Per altre informazioni, vedere [connettersi con il modulo di PowerShell per il grafico di Azure Active Directory](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="install-and-connect-to-the-pre-release-version-of-the-teams-powershell-module"></a>Installare e connettersi alla versione non definitiva del modulo di PowerShell Teams

I cmdlet necessari sono disponibili nella versione precedente del modulo di PowerShell teams. Seguire la procedura descritta in [installare e connettersi al modulo di PowerShell per Microsoft teams](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) per disinstallare prima la versione in generale disponibile del modulo di PowerShell Teams (se è installato) e quindi installare la versione più recente di pre-rilascio del modulo dalla raccolta di test di PowerShell.

Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.

```powershell
Connect-MicrosoftTeams
```
Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.

## <a name="identify-your-users"></a>Identificare gli utenti

Prima di tutto, Esegui le operazioni seguenti per identificare il personale e gli educatori per tipo di licenza. Questo spiega quali SKU sono in uso nell'organizzazione. È quindi possibile identificare il personale e gli insegnanti che hanno un SKU di facoltà assegnato.

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

Che restituisce:

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

In questo esempio l'output mostra che la licenza di facoltà SkuId è "e97c048c-37a4-45fb-AB50-922fbf07a370".

> [!NOTE]
> Per visualizzare un elenco di SKU per l'istruzione e ID SKU, vedere informazioni di [riferimento su SKU per l'](sku-reference-edu.md)istruzione.

Eseguiamo quindi le operazioni seguenti per identificare gli utenti con questa licenza e raccoglierli tutti insieme.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains “e97c048c-37a4-45fb-ab50-922fbf07a370”)
```

## <a name="assign-a-policy-in-bulk"></a>Assegnare un criterio in blocco

A questo punto, assegniamo i criteri appropriati agli utenti in blocco. Il numero massimo di utenti per cui è possibile assegnare o aggiornare i criteri è 20.000 alla volta. Ad esempio, se si hanno più di 20.000 personale ed educatori, è necessario inviare più batch.

Eseguire la procedura seguente per assegnare il criterio della riunione denominato EducatorMeetingPolicy al personale e agli insegnanti.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare ```PolicyType``` al criterio che si sta assegnando e ```PolicyName``` al nome del criterio.

## <a name="get-the-status-of-a-bulk-assignment"></a>Ottenere lo stato di un'assegnazione in blocco

Ogni assegnazione in blocco restituisce un ID operazione, che può essere usato per tenere traccia dell'avanzamento delle assegnazioni dei criteri o per identificare eventuali errori che potrebbero verificarsi. Ad esempio, eseguire le operazioni seguenti:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Per visualizzare lo stato di assegnazione di ogni utente nell'operazione batch, eseguire la procedura seguente. I ```UserState``` dettagli di ogni utente si trovano nella proprietà.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>Assegnare un criterio in blocco se si hanno più di 20.000 utenti

Prima di tutto, eseguire le operazioni seguenti per verificare il numero di membri del personale e gli insegnanti:

```powershell
$faculty.count
```

Invece di fornire l'intero elenco di ID utente, eseguire la procedura seguente per specificare il primo 20.000 e quindi il successivo 20.000 e così via.

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

Puoi modificare l'intervallo di ID utente fino a raggiungere l'elenco completo degli utenti. Ad esempio, immetti ```$faculty[0..19999``` per il primo batch, ```$faculty[20000..39999``` USA per il secondo batch, ```$faculty[40000..59999``` Immetti per il terzo batch e così via.

## <a name="get-the-policies-assigned-to-a-user"></a>Ottenere i criteri assegnati a un utente

Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico. L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Domande frequenti

**Voglio assicurarmi che tutti gli utenti che sono studenti, personale ed educatori ottengano automaticamente le licenze assegnate. Come è possibile eseguire questa operazione?**

Il team del prodotto teams sta lavorando per supportare l'assegnazione di criteri ai gruppi di sicurezza. A questo punto è possibile creare gruppi per studenti e docenti e quindi i criteri appropriati per i gruppi. Tieni presente che le assegnazioni degli utenti esplicite, ad esempio i criteri assegnati con questa esercitazione, sostituiranno i criteri ereditati da un gruppo. Quando questa funzionalità è supportata, verranno fornite altre istruzioni su come usare l'assegnazione dei criteri per raggruppare e aggiornare gli utenti per assicurarsi che vengano assegnati i criteri di gruppo ereditati.

**Non si ha familiarità con PowerShell per Teams. Dove è possibile ottenere altre informazioni?**

Vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)
- [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)