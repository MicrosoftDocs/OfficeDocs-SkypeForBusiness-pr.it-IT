---
title: Pacchetti di criteri di Teams per enti pubblici
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri di Teams per l'organizzazione governativa.
ms.openlocfilehash: 891d8762a914a003e3707d8f5eab29b3d8d916c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117774"
---
# <a name="teams-policy-packages-for-government"></a>Pacchetti di criteri di Teams per enti pubblici

> [!NOTE]
> I pacchetti di criteri non sono attualmente disponibili nelle distribuzioni di Microsoft 365 Government GCC High o DoD.

## <a name="overview"></a>Panoramica

Un [Pacchetto di criteri](manage-policy-packages.md) in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza. È possibile personalizzare le impostazioni dei criteri del pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. È possibile gestire i pacchetti dei criteri tramite l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

I pacchetti di criteri predefiniscono i criteri per gli elementi seguenti, a seconda del pacchetto:

- Messaggistica
- Riunioni
- Chiamate
- Configurazione delle app
- Eventi live

Teams attualmente include i pacchetti di criteri per enti pubblici seguenti.

|Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams|Ideale per|Descrizione |
|---------|---------|---------|
|Responsabile della sicurezza pubblica  |Responsabili della sicurezza pubblica nell'organizzazione governativa  |Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione. |
|Frontline Manager  |Responsabili in prima linea nell'organizzazione governativa |Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea dell'organizzazione.|
|Operaio in prima linea  |Frontline Workers nell'organizzazione governativa |Crea un set di criteri e applica tali impostazioni ai Frontline Worker dell'organizzazione.|

![Screenshot dei pacchetti di criteri per il settore sanitario](media/policy-packages-gov.png)

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri per i funzionari della sicurezza pubblica agli utenti dell'organizzazione, viene creato un criterio denominato PublicSafety_Officer per ogni criterio nel pacchetto.

![Screenshot dei criteri nel pacchetto per gli operatori del settore sanitario](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzare

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.

Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.

### <a name="customize"></a>Personalizzare

Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft Teams selezionare il pacchetto di criteri, selezionare il nome del criterio da modificare e quindi selezionare **Modifica**.

È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione. Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Assegnare

Assegnare il pacchetto di criteri agli utenti. Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Assegnare un pacchetto di criteri a uno o più utenti

Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.  

![Screenshot che mostra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

Per altre informazioni, vedere [Assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).

Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.

#### <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

**Questa funzionalità è in anteprima privata**

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.

Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)

Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta. Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation). Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica. Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)