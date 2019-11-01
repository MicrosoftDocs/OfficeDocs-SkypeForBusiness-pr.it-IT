---
title: Pianificare la governance in teams-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Informazioni su come pianificare l'implementazione delle funzionalità di governance in teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ab8f3571ac38273f40cc228c05b51c8f00159a1
ms.sourcegitcommit: 800a5c3881d0ebceb505a538fcf7e48f7b6df17e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37913045"
---
# <a name="plan-for-governance-in-teams"></a>Pianificare la governance in Teams

Teams offre un ricco set di strumenti per implementare le funzionalità di governance che l'organizzazione può richiedere. Questo articolo illustra i professionisti IT per porre le domande giuste per determinare i loro requisiti per la governance e come soddisfarli. 

> [!Tip] 
> Per ulteriori informazioni sulla governance in Microsoft teams, vedere la sessione seguente: [governance, gestione e ciclo di vita in Microsoft teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creazione di gruppi e team, denominazione, classificazione e accesso Guest

L'organizzazione potrebbe richiedere l'implementazione di controlli severi sul modo in cui i team sono denominati e classificati, indipendentemente dal fatto che gli utenti possano essere aggiunti come membri del team e chi può creare team. Puoi configurare ognuna di queste aree usando Azure Active Directory (Azure AD). 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Punti decisionali|<ul><li>L'organizzazione richiede una specifica convenzione di denominazione per i team?</li><li>I creatori di team hanno la possibilità di assegnare classificazioni specifiche dell'organizzazione a teams?</li><li>È necessario limitare la possibilità di aggiungere Guest ai team per ogni singolo team?</li><li>L'organizzazione ha bisogno di limitare chi può creare Teams?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la creazione del team, la denominazione, la classificazione e l'accesso guest.</li><li>Pianificare l'implementazione di questi requisiti come parte dell'implementazione di teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

|Capacità |Dettagli |Azure AD Premium <br> licenza richiesta |Decisione |
|---------|---------|---------|---------|
|Criteri di denominazione del team | Usa parole bloccate con suffisso prefisso, personalizzate. |P1 |DA definire |
|Classificazione del team |Assegnare classificazioni a teams. |P1 |DA definire |
|Accesso Guest del team |Consentire o impedire l'aggiunta di Guest ai team. |No |DA definire |
|Creazione di Team |Limitare la creazione del team agli amministratori. |No |DA definire|
|Creazione di Team |Limitare la creazione del team ai membri del gruppo di sicurezza. |P1 |DA definire|

> [!NOTE]
> Per informazioni su come pianificare in anticipo, vedere [altre informazioni sull'impostazione di questi criteri e sulle licenze necessarie](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Limitare la creazione di gruppi e team può rallentare la produttività degli utenti, poiché molti servizi di Office 365 richiedono la creazione di gruppi per il servizio. Per altre informazioni, passare a ed espandere il [motivo per cui controllare chi crea i gruppi di Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Altre informazioni

Dopo aver determinato i requisiti, puoi implementarli usando i controlli di Azure AD. Per informazioni tecniche su come implementare queste impostazioni, vedere:

- [Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

- [Applicare un criterio di denominazione per i gruppi di Office 365 in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

- [Criteri di denominazione dei gruppi di Office 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Scadenza del gruppo e del team, conservazione e archiviazione

L'organizzazione potrebbe avere altri requisiti per l'impostazione di criteri per la scadenza, la conservazione e l'archiviazione dei dati di team e teams (canali e file di canale). È possibile configurare i criteri di scadenza del gruppo per gestire automaticamente il ciclo di vita del gruppo e i criteri di conservazione per mantenere o eliminare le informazioni in base alle esigenze ed è possibile archiviare i team (impostare la modalità di sola lettura) per mantenere una visualizzazione temporizzata di un team non più attivo.

|           |            |
|-----------|------------|
| ![Icona che descrive i punti di decisione](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede di specificare una data di scadenza per i team?</li><li>L'organizzazione richiede criteri specifici per la conservazione dei dati da applicare ai team?</li><li>L'organizzazione prevede di richiedere la possibilità di archiviare team inattivi per preservare il contenuto in uno stato di sola lettura?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la scadenza del team, la conservazione dei dati e l'archiviazione.</li><li>Pianificare l'implementazione di questi requisiti come parte dell'implementazione di teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

|Capacità |Dettagli |Licenza Premium di Azure AD |Decisione |
|---------|---------|---------|---------|
|Criteri di scadenza |Gestire il ciclo di vita dei gruppi di Office 365 impostando un criterio di scadenza. |P1 |DA definire|
|Criteri di conservazione |Mantenere o eliminare i dati per un determinato periodo di tempo impostando i criteri di conservazione per i team nel centro conformità & sicurezza. **Nota**: l'uso di questa funzionalità richiede la concessione di licenze di Office 365 Enterprise E3 o versioni successive. |No |DA definire |
|Archiviare e ripristinare |Archiviare un team quando non è più attivo, ma si vuole tenerlo in riferimento o per riattivarlo in futuro. |No |DA definire |

> [!Note]
> La scadenza del gruppo è una caratteristica di Azure AD Premium. Affinché questa funzionalità sia disponibile, il tenant deve avere un abbonamento ad Azure AD Premium e licenze per l'amministratore che configura le impostazioni e i membri dei gruppi interessati.

#### <a name="additional-information"></a>Altre informazioni

Per informazioni tecniche su come implementare queste impostazioni, vedere:

- [Configurare la scadenza di gruppi di Office 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurare i criteri di conservazione dei team](retention-policies.md).

- [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Gestione delle funzionalità Teams

Un altro aspetto importante della gestione della governance e del ciclo di vita per i team è la possibilità di controllare le caratteristiche a cui gli utenti avranno accesso. È possibile gestire le funzionalità di messaggistica, riunione e chiamata, sia a livello di tenant di Office 365 che per utente. 


|         |         |
|---------|---------|
| ![Icona che descrive i punti di decisione](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede la limitazione delle caratteristiche dei team per l'intero tenant?</li><li>L'organizzazione richiede la limitazione delle caratteristiche dei team per utenti specifici?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per limitare le caratteristiche dei team a livello di tenant e utente.</li><li>Pianificare l'implementazione dei requisiti specifici come parte dell'implementazione del team.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Aree di interesse per la gestione delle funzionalità Teams

Teams offre funzionalità granulari per il controllo della messaggistica, delle riunioni, delle chiamate e delle caratteristiche degli eventi live e altro ancora, tramite criteri. I criteri diversi possono essere applicati a tutti gli utenti per impostazione predefinita o per utente, come richiesto dall'organizzazione. 

Per gli elenchi dettagliati di tutte le impostazioni, incluse le indicazioni tecniche su come implementarle per l'organizzazione, vedere gli articoli seguenti:

- [Gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md)
- [Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).
- [Gestire i criteri delle riunioni in teams](meeting-policies-in-teams.md)
- [Gestire i criteri di messaggistica in teams](messaging-policies-in-teams.md)

Inoltre, puoi configurare la moderazione per un canale e dare funzionalità di moderatore a determinati utenti, in modo che possano controllare chi può creare post di canale e rispondere. Per altre informazioni, vedere [configurare e gestire la moderazione dei canali in Microsoft teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Sicurezza e conformità

Teams è basato sulle funzionalità avanzate di sicurezza e conformità di Office 365 e supporta il controllo e la creazione di report, la ricerca di contenuto di conformità, l'individuazione e, il blocco legale e i criteri di conservazione. 

> [!Important]
> Se l'organizzazione ha requisiti di conformità e sicurezza, esaminare il contenuto approfondito fornito su questo argomento nell'articolo [Panoramica della sicurezza e della conformità in Microsoft teams](security-compliance-overview.md).

## <a name="related-topics"></a>Argomenti correlati

[Guida introduttiva di governance per Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
