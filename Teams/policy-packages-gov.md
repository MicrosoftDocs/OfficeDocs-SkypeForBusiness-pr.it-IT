---
title: Pacchetti di criteri per le squadre per enti pubblici
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come usare e gestire i pacchetti di criteri per le squadre per l'organizzazione pubblica.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908595"
---
# <a name="teams-policy-packages-for-government"></a>Pacchetti di criteri per le squadre per enti pubblici

> [!NOTE]
> I pacchetti di criteri non sono attualmente disponibili nelle distribuzioni governative GCC High o DoD di Microsoft 365.

## <a name="overview"></a>Panoramica

Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza. È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.

I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:

- Messaggistica
- Riunioni
- Chiamate
- Configurazione dell'app
- Eventi live

I team attualmente includono i pacchetti di criteri seguenti per il governo.

|Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams|Ideale per|Descrizione |
|---------|---------|---------|
|Addetto alla sicurezza pubblica  |Responsabili della sicurezza pubblica nella propria organizzazione governativa  |Crea un set di criteri e impostazioni dei criteri applicabili agli addetti alla sicurezza pubblica dell'organizzazione. |
|Gestione i FIRSTLINE  |Responsabili di i FIRSTLINE nella propria organizzazione pubblica |Crea un set di criteri e applica tali impostazioni ai responsabili di I FIRSTLINE dell'organizzazione.|
|Lavoratore i FIRSTLINE  |I FIRSTLINE lavoratori dell'organizzazione governativa |Crea un set di criteri e applica tali impostazioni agli operatori I FIRSTLINE dell'organizzazione.|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-gov.png)

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri per gli agenti di sicurezza pubblica agli utenti dell'organizzazione, viene creato un criterio denominato PublicSafety_Officer per ogni criterio nel pacchetto.

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzazione

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri** , selezionare il nome del pacchetto e quindi selezionare il nome del criterio.

Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.

### <a name="customize"></a>Personalizza

Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica**.

Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri. Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Assegnare

Assegnare il pacchetto di criteri agli utenti. Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Assegnare un pacchetto di criteri a uno o più utenti

Per assegnare un pacchetto di criteri a uno o più utenti, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri** e quindi seleziona **Gestisci utenti**.  

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

Per altre informazioni, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).

Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.

#### <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

**Questa funzionalità è in anteprima privata**

L'assegnazione di un pacchetto di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando i membri vengono aggiunti o rimossi da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. Questo metodo è consigliato per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.

Per altre informazioni, vedere [assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assegnare un pacchetto di criteri a un set di grandi dimensioni (batch) di utenti

USA assegnazione pacchetto criteri batch per assegnare un pacchetto di criteri a set di grandi dimensioni di utenti alla volta. Si usa il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri che si vuole assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti per l'ID oggetto, l'UPN, l'indirizzo SIP o l'indirizzo di posta elettronica. Per altre informazioni, vedere [assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)

[Assegnare criteri agli utenti in teams](assign-policies.md) 
