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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri team per l'organizzazione sanitaria.
ms.openlocfilehash: e55102e07f7ffc77dc67c5d6697cb754c398cc40
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427171"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacchetti di criteri team per l'assistenza sanitaria

## <a name="overview"></a>Panoramica

Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza. È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.

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

Per iniziare a usare i pacchetti di criteri per l'assistenza sanitaria, nell'hub di amministrazione Microsoft, selezionare **nozioni di base sull'assistenza sanitaria**e quindi selezionare **Assegna impostazioni criteri per ruolo**. Quando si è pronti per iniziare, decidere i pacchetti di criteri a cui si vuole assegnare gli utenti dell'organizzazione.

Selezionare **Visualizza dettagli criteri** per altre informazioni sui criteri specifici in un pacchetto e le rispettive impostazioni. Questi dati [possono essere personalizzati](manage-policy-packages.md#customize-policies-in-a-policy-package) dopo l'assegnazione nell'interfaccia di amministrazione di teams.

Scegliere uno o più pacchetti da assegnare e quindi fare clic su **Avanti**. Puoi cercare e aggiungere persone al pacchetto di criteri più adatto per il loro ruolo. Un singolo utente non può essere assegnato contemporaneamente a più di un pacchetto di criteri.

Dopo aver aggiunto persone al pacchetto di criteri corretto, **fine** completa le selezioni. Puoi continuare a personalizzare e gestire i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzazione

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.

Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.

### <a name="customize"></a>Personalizza

Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica**.

Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri. Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Assegnare

Assegnare il pacchetto di criteri agli utenti. Per assegnare un pacchetto di criteri a uno o più utenti, fare clic su **Gestisci utenti**. È anche possibile [usare PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per assegnare un pacchetto di criteri ai batch di grandi dimensioni degli utenti. 

Per istruzioni su come assegnare un pacchetto di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.

## <a name="related-topics"></a>Argomenti correlati

[Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)

[Assegnare criteri agli utenti in teams](assign-policies.md)
