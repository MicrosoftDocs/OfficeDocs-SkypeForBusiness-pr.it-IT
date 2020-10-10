---
title: Pianificare la governance in teams-Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In questo articolo verranno fornite informazioni su come pianificare l'implementazione delle funzionalità di governance in teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416913"
---
# <a name="plan-for-governance-in-teams"></a>Pianificare la governance in Teams

Teams offre un ricco set di strumenti per implementare le funzionalità di governance che l'organizzazione può richiedere. Questo articolo illustra i professionisti IT per porre le domande giuste per determinare i loro requisiti per la governance e come soddisfarli. 

> [!Tip] 
> Per ulteriori informazioni sulla governance in Microsoft teams, vedere la sessione seguente: [governance, gestione e ciclo di vita in Microsoft teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creazione di gruppi e team, denominazione, classificazione e accesso Guest

L'organizzazione potrebbe richiedere l'implementazione di controlli severi sul modo in cui i team sono denominati e classificati, indipendentemente dal fatto che gli utenti possano essere aggiunti come membri del team e chi può creare team. Puoi configurare queste aree usando Azure Active Directory (Azure AD) e le etichette di sensitività. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Punti decisionali|<ul><li>L'organizzazione richiede una specifica convenzione di denominazione per i team?</li><li>I creatori di team hanno la possibilità di assegnare classificazioni specifiche dell'organizzazione a teams?</li><li>È necessario limitare la possibilità di aggiungere Guest ai team per ogni singolo team?</li><li>L'organizzazione ha bisogno di limitare chi può creare Teams?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la creazione del team, la denominazione, la classificazione e l'accesso guest.</li><li>Pianificare l'implementazione di questi requisiti come parte dell'implementazione di teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

|Funzionalità |Dettagli |Azure AD Premium <br> licenza richiesta |Decisione |
|---------|---------|---------|---------|
|Criteri di denominazione del team | Usa parole bloccate con suffisso prefisso, personalizzate. |P1 |DA definire |
|Classificazione del team |Assegnare classificazioni a teams. |P1 |DA definire |
|Accesso Guest del team |Consentire o impedire l'aggiunta di Guest ai team. |No |DA definire |
|Creazione di Team |Limitare la creazione del team agli amministratori. |No |DA definire|
|Creazione di Team |Limitare la creazione del team ai membri del gruppo di sicurezza. |P1 |DA definire|
|Etichette di sensitività|Configurare la privacy e la condivisione Guest|No|DA definire|

> [!NOTE]
> Per informazioni su come pianificare in anticipo, vedere [altre informazioni sull'impostazione di questi criteri e sulle licenze necessarie](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Limitare la creazione di gruppi e team può rallentare la produttività degli utenti, poiché molti servizi Microsoft 365 e Office 365 richiedono che i gruppi vengano creati per il servizio. Per altre informazioni, passare a ed espandere il motivo per cui [controllare chi crea i gruppi di Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Altre informazioni

Dopo aver determinato i requisiti, puoi implementarli usando i controlli di Azure AD. Per informazioni tecniche su come implementare queste impostazioni, vedere:

- [Cmdlet di Azure Active Directory per la configurazione delle impostazioni del gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Applicare criteri di denominazione per i gruppi di Microsoft 365 in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Criteri di denominazione dei gruppi di Microsoft 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usare le etichette di sensitività per proteggere il contenuto in Microsoft teams, Microsoft 365 Groups e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opzioni di fine ciclo di vita per gruppi, team e Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Scadenza del gruppo e del team, conservazione e archiviazione

L'organizzazione potrebbe avere altri requisiti per l'impostazione di criteri per la scadenza, la conservazione e l'archiviazione dei dati di team e teams (canali e file di canale). È possibile configurare i criteri di scadenza del gruppo per gestire automaticamente il ciclo di vita del gruppo e i criteri di conservazione per mantenere o eliminare le informazioni in base alle esigenze ed è possibile archiviare i team (impostarli in modalità di sola lettura) per mantenere una visualizzazione temporizzata di un team non più attivo. Tieni presente che i team archiviati continuano ad applicare i criteri di scadenza e possono essere eliminati, a meno che non siano esclusi o rinnovati.

|           |            |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede di specificare una data di scadenza per i team?</li><li>L'organizzazione richiede criteri specifici per la conservazione dei dati da applicare ai team?</li><li>L'organizzazione prevede di richiedere la possibilità di archiviare team inattivi per preservare il contenuto in uno stato di sola lettura?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la scadenza del team, la conservazione dei dati e l'archiviazione.</li><li>Pianificare l'implementazione di questi requisiti come parte dell'implementazione di teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

|Funzionalità |Dettagli |Licenza Premium di Azure AD |Decisione |
|---------|---------|---------|---------|
|Criteri di scadenza |Gestire il ciclo di vita dei gruppi di Microsoft 365 impostando un criterio di scadenza. |P1 |DA definire|
|Criteri di conservazione |Mantenere o eliminare i dati per un determinato periodo di tempo impostando i criteri di conservazione per i team nel centro conformità & sicurezza. **Nota**: l'uso di questa funzionalità richiede la licenza di Microsoft 365 o Office 365 Enterprise E3 o versioni successive. |No |DA definire |
|Archiviare e ripristinare |Archiviare un team quando non è più attivo, ma si vuole tenerlo in riferimento o per riattivarlo in futuro. |No |DA definire |

> [!Note]
> La scadenza del gruppo è una caratteristica di Azure AD Premium. Affinché questa funzionalità sia disponibile, il tenant deve avere un abbonamento ad Azure AD Premium e licenze per l'amministratore che configura le impostazioni e i membri dei gruppi interessati.

#### <a name="additional-information"></a>Altre informazioni

Per informazioni tecniche su come implementare queste impostazioni, vedere:

- [Configurare la scadenza di Microsoft 365 groups](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurare i criteri di conservazione dei team](retention-policies.md).

- [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Gestione di gruppi e membri del team

Per i team che richiedono una rapida onboarding e offboarding o utenti e Guest, è necessario gestire in modo coerente i membri di gruppi basati su progetti o con restrizioni. L'organizzazione potrebbe anche dover verificare che tutti i membri correnti abbiano la giustificazione aziendale in un team. La gestione dei membri può essere difficile perché i proprietari del team possono andarsene e gli utenti di solito non lasciano i gruppi per conto proprio quando un progetto termina o quando cambiano ruolo. Il modo migliore per gestire l'appartenenza ai gruppi che consente agli utenti di accedere quando necessario, ma assicurarsi che il gruppo non abbia un rischio di accesso non appropriato sia attraverso due processi distrettuali: la gestione dei diritti e le recensioni di Access.

La [gestione dei diritti](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) consente di delegare a un utente, ad esempio un Project Manager, di raccogliere tutte le risorse necessarie, incluse le appartenenze ai team, in un unico pacchetto. Possono anche definire chi può effettuare richieste: gli utenti nel tenant o da altre organizzazioni connesse. Project Manager riceverà le richieste di accesso nel proprio messaggio di posta elettronica e approverà o negherà le richieste nel portale di accesso. Gli amministratori possono configurare le condizioni di accesso per includere una data o un periodo di scadenza quando l'utente o l'ospite verrà rimosso dal team, a meno che l'accesso non venga rinnovato. Gli amministratori possono anche configurare i gruppi associati ai team per partecipare alle recensioni di Access. Per le [recensioni di Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), i proprietari del gruppo riceveranno promemoria regolari per rivedere i membri di un team. Le recensioni di Access includono raccomandazioni, che semplificano l'esecuzione del processo di attestazione normale per i proprietari dei gruppi.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Punti decisionali | L'organizzazione richiede un processo coerente per la gestione dell'appartenenza a uno o più team? <br> La propria organizzazione richiede i proprietari o i membri stessi per giustificare l'appartenenza continua di uno o più team regolarmente? <br> L'organizzazione richiede l'approvazione per gli utenti e gli ospiti per richiedere l'accesso alle risorse, inclusi team, gruppi, siti di SharePoint e app? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Passaggi successivi | Documentare i requisiti delle organizzazioni per ogni team o team specifici per la scadenza dell'appartenenza.<br>Pianificare in che modo l'organizzazione può raggruppare Team, gruppi, siti di SharePoint e app in pacchetti di Access.<br>Pianificare quali persone, ad esempio il responsabile del richiedente, un Project Manager, uno sponsor per un'organizzazione connessa o un responsabile della sicurezza dell'organizzazione dovranno approvare o rifiutare le richieste di accesso. |

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

| Funzionalità | Dettagli | Licenza Premium di Azure AD | Decisione |
|:-|:-|:-|:-|
| Recensioni di Access | Configurare le recensioni di Access per ricertificare l'appartenenza di team specifici a intervalli regolari | P2 | DA definire |
| Gestione dei diritti | Configurare il pacchetto di Access per consentire agli utenti e agli ospiti di richiedere l'accesso ai team | P2 | DA definire |

> [!NOTE]
> Per informazioni su come pianificare in anticipo, vedere [altre informazioni sulle licenze necessarie](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="additional-information"></a>Altre informazioni

Per informazioni tecniche su come implementare queste impostazioni, vedere:

- [Gestione dei diritti](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Recensioni di Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Gestione delle funzionalità Teams

Un altro aspetto importante della gestione della governance e del ciclo di vita per i team è la possibilità di controllare le caratteristiche a cui gli utenti avranno accesso. È possibile gestire le funzionalità di messaggistica, riunione e chiamata in Microsoft 365 o Office 365 a livello di organizzazione o per utente.


|         |         |
|---------|---------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede la limitazione delle caratteristiche dei team per l'intero tenant?</li><li>L'organizzazione richiede la limitazione delle caratteristiche dei team per utenti specifici?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per limitare le caratteristiche dei team a livello di tenant e utente.</li><li>Pianificare l'implementazione dei requisiti specifici come parte dell'implementazione del team.</li><li>Comunicare e pubblicare i criteri per informare gli utenti dei team del comportamento che possono attendersi.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Aree di interesse per la gestione delle funzionalità Teams

Teams offre funzionalità granulari per il controllo della messaggistica, delle riunioni, delle chiamate e delle caratteristiche degli eventi live e altro ancora, tramite criteri. I criteri diversi possono essere applicati a tutti gli utenti per impostazione predefinita o per utente, come richiesto dall'organizzazione. 

Per gli elenchi dettagliati di tutte le impostazioni, incluse le indicazioni tecniche su come implementarle per l'organizzazione, vedere gli articoli seguenti:

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).
- [Canali privati in Microsoft Teams](private-channels.md)
- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Gestire i criteri di messaggistica in teams](messaging-policies-in-teams.md)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)

Inoltre, puoi configurare la moderazione per un canale e dare funzionalità di moderatore a determinati utenti, in modo che possano controllare chi può creare post di canale e rispondere. Per altre informazioni, vedere [configurare e gestire la moderazione dei canali in Microsoft teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Sicurezza e conformità

Teams è basato sulle funzionalità avanzate di sicurezza e conformità di Microsoft 365 e Office 365 e supporta il controllo e la creazione di report, la ricerca di contenuto di conformità, l'individuazione e, il blocco legale e i criteri di conservazione.

> [!Important]
> Se l'organizzazione ha requisiti di conformità e sicurezza, esaminare il contenuto approfondito fornito su questo argomento nell'articolo [Panoramica della sicurezza e della conformità in Microsoft teams](security-compliance-overview.md).

## <a name="related-topics"></a>Argomenti correlati

[Guida introduttiva sulla governance per Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
