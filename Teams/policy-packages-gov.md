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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804028"
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

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.

Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.

### <a name="customize"></a>Personalizza

Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica**.

Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri. Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Assegnare

Assegnare il pacchetto di criteri agli utenti. Per assegnare un pacchetto di criteri a uno o più utenti, fare clic su **Gestisci utenti**. È anche possibile [usare PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per assegnare un pacchetto di criteri ai batch di grandi dimensioni degli utenti. 

Per istruzioni su come assegnare un pacchetto di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-gov-assign.png)

Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.

## <a name="related-topics"></a>Argomenti correlati

[Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)

[Assegnare criteri agli utenti in teams](assign-policies.md) 
