---
title: Pacchetti di criteri di Teams per il settore sanitario
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
description: Informazioni su come usare e gestire i pacchetti di criteri di Teams per l'organizzazione sanitaria.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812856"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacchetti di criteri di Teams per il settore sanitario

## <a name="overview"></a>Panoramica

Un [pacchetto di](manage-policy-packages.md) criteri in Microsoft Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza. È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti dei criteri utilizzando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Criteri predefiniti per i pacchetti di criteri per i seguenti, a seconda del pacchetto:

- Messaggistica
- Riunioni
- Chiamate
- Configurazione dell'app
- Eventi live

Teams attualmente include i pacchetti di criteri sanitari seguenti.

|Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams|Ideale per|Descrizione |
|---------|---------|---------|
|Operatore medico  |Operatori clinici nell'organizzazione sanitaria  |Crea un set di criteri e impostazioni dei criteri che conferiranno a operatori clinici come infermieri specializzati, infermieri con addebito, medici e social worker l'accesso completo a chat, chiamate, gestione dei turni e riunioni. |
|Information Worker sanitario  |Information worker nell'organizzazione sanitaria |Crea un set di criteri e impostazioni dei criteri che forniscono a information worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo a chat, chiamate e riunioni.|
|Sala pazienti sanitaria  |Dispositivi per la sala pazienti|Crea un set di criteri e impostazioni dei criteri che si applicano alle sale pazienti dell'organizzazione sanitaria.|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-healthcare.png)

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri per operatori clinici sanitari a un medico dell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio nel pacchetto.

![Screenshot dei criteri nel pacchetto di operatori clinici sanitari](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Introduzione ai pacchetti di criteri

Per iniziare a usare i pacchetti di criteri sanitari, nell'hub di onboarding dell'interfaccia di amministrazione Microsoft selezionare **Sanità** e quindi Assegnare le impostazioni dei criteri in base **al ruolo.** Quando sei pronto per iniziare, decidi a quali pacchetti di criteri vuoi assegnare i singoli utenti nell'organizzazione.

Selezionare **Visualizza dettagli sui criteri** per altre informazioni sui criteri specifici in un pacchetto e sulle relative impostazioni. Possono [essere personalizzate dopo l'attività](manage-policy-packages.md#customize-policies-in-a-policy-package) nell'interfaccia di amministrazione di Teams.

Scegli uno o più pacchetti da assegnare e quindi fai clic su **Avanti.** È possibile cercare e aggiungere persone al pacchetto di criteri più adatto per il loro ruolo. Non è possibile assegnare una persona a più di un pacchetto di criteri contemporaneamente.

Dopo aver aggiunto persone al pacchetto di criteri giusto, **completare** le selezioni. Puoi continuare a personalizzare e gestire i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzare

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a Pacchetti **criteri,** seleziona il nome del pacchetto e quindi seleziona il nome del criterio.

Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.

### <a name="customize"></a>Personalizzare

Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams vai a Pacchetti **criteri,** seleziona il pacchetto di criteri, seleziona il nome del criterio che vuoi modificare e quindi seleziona **Modifica.**

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

Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta. Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation). Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica. Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
