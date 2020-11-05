---
title: Pacchetti di criteri team per l'assistenza sanitaria
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Informazioni su come usare e gestire i pacchetti di criteri team per l'organizzazione sanitaria.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908515"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacchetti di criteri team per l'assistenza sanitaria

## <a name="overview"></a>Panoramica

Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza. È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:

- Messaggistica
- Riunioni
- Chiamate
- Configurazione dell'app
- Eventi live

I team attualmente includono i seguenti pacchetti di criteri sanitari.

|Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams|Ideale per|Descrizione |
|---------|---------|---------|
|Lavoratore clinico sanitario  |Operatori clinici nell'organizzazione sanitaria  |Crea un set di criteri e impostazioni dei criteri che conferiscono agli operatori clinici, ad esempio infermieri registrati, addebiti infermieri, medici e assistenti sociali, l'accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni. |
|Information Worker sanitari  |Information Worker nell'organizzazione sanitaria |Crea un set di criteri e impostazioni dei criteri che forniscono agli Information Worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo alla chat, alle chiamate e alle riunioni.|
|Sala paziente sanitaria  |Dispositivi per la sala paziente|Crea un set di criteri e impostazioni dei criteri applicabili alle sale del paziente nell'organizzazione sanitaria.|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-healthcare.png)

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri di lavoro clinico sanitario ai clinici dell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio nel pacchetto.

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Introduzione ai pacchetti di criteri

Per iniziare a usare i pacchetti di criteri sanitari, nell'hub dell'interfaccia di amministrazione Microsoft selezionare **assistenza sanitaria** e quindi selezionare **Assegna impostazioni criteri per ruolo**. Quando si è pronti per iniziare, decidere i pacchetti di criteri a cui si vuole assegnare gli utenti dell'organizzazione.

Selezionare **Visualizza dettagli criteri** per altre informazioni sui criteri specifici in un pacchetto e le rispettive impostazioni. Questi dati [possono essere personalizzati](manage-policy-packages.md#customize-policies-in-a-policy-package) dopo l'assegnazione nell'interfaccia di amministrazione di teams.

Scegliere uno o più pacchetti da assegnare e quindi fare clic su **Avanti**. Puoi cercare e aggiungere persone al pacchetto di criteri più adatto per il loro ruolo. Un singolo utente non può essere assegnato contemporaneamente a più di un pacchetto di criteri.

Dopo aver aggiunto persone al pacchetto di criteri corretto, **fine** completa le selezioni. Puoi continuare a personalizzare e gestire i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzazione

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **, selezionare** il nome del pacchetto e quindi selezionare il nome del criterio.

Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.

### <a name="customize"></a>Personalizza

Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri** , seleziona il pacchetto di criteri, seleziona il nome del criterio che vuoi modificare e quindi scegli **modifica**.

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
