---
title: Pacchetti di criteri di Teams per il personale in prima linea
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: conceptual
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: Informazioni su come usare e gestire i pacchetti di criteri di Teams per il personale in prima linea nell'organizzazione.
ms.openlocfilehash: 790d9bf7dbf90fadf48c9e5e0818d3eddeac4b75
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131215"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>Pacchetti di criteri di Teams per il personale in prima linea

## <a name="overview"></a>Panoramica

Un [Pacchetto di criteri](manage-policy-packages.md) in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione. I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.

È possibile personalizzare le impostazioni dei criteri del pacchetto in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. È possibile gestire i pacchetti dei criteri tramite l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

I pacchetti di criteri predefiniscono i criteri per gli elementi seguenti, a seconda del pacchetto:

- Messaggistica
- Riunioni
- Chiamate
- Configurazione delle app
- Eventi live

Teams include i pacchetti di criteri di gestione per **Responsabile in prima linea** e **dipendente in prima linea**.

|Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams|Descrizione |
|---------|---------|
|**Responsabile in prima linea** |Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea dell'organizzazione. |
|**Personale in prima linea**  |Crea un set di criteri e applica tali impostazioni al personale in prima linea nell'organizzazione.|

:::image type="content" source="media/policy-packages-flw.png" alt-text="Screenshot dei pacchetti di criteri per il personale in prima linea." lightbox="media/policy-packages-flw.png":::

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri responsabili in prima linea ai responsabili del punto vendita dell'organizzazione, viene creato un criterio denominato Frontline_Manager per ogni criterio del pacchetto.

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="Screenshot dei criteri nel pacchetto di criteri per i responsabili in prima linea." lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>Gestire i pacchetti di criteri

### <a name="view"></a>Visualizzare

Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri**, selezionare il nome del pacchetto poi selezionare il nome del criterio.

Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.

### <a name="customize"></a>Personalizzare

Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto. Per modificare le impostazioni di un criterio in un pacchetto di criteri, nel riquadro di spostamento a sinistra nell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetto di criteri** e selezionare il nome del criterio che si desidera modificare poi selezionare **Modifica**.

È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione. Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Assegnare

Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

> [!NOTE]
> Ogni utente richiederà il componente aggiuntivo Comunicazioni avanzate per ricevere un'assegnazione del pacchetto di criteri personalizzata. Per ulteriori informazioni, vedere [Componente aggiuntivo per comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Assegnare un pacchetto di criteri a uno o più utenti

Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Screenshot che illustra come assegnare un pacchetto di criteri a un utente nell'interfaccia di amministrazione di Teams." lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

Per altre informazioni, vedere [Assegnare pacchetti di criteri agli utenti](assign-policy-packages.md#assign-a-policy-package-to-users).

#### <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.

Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)

Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta. Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation). Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol). Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)
- [Assegnare pacchetti di criteri a utenti e gruppi](assign-policy-packages.md)
