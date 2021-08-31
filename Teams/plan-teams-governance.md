---
title: Pianificare la governance in Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Questo articolo illustra come pianificare l'implementazione delle funzionalità di governance in Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca020de2f2ce96daa3fe213b7b5c0d80b720165b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728625"
---
# <a name="plan-for-governance-in-teams"></a>Pianificare la governance in Teams

Teams offre un set di strumenti avanzati per implementare tutte le funzionalità di governance che l'organizzazione potrebbe richiedere. Questo articolo guida i professionisti IT a porre le domande giuste per determinare i requisiti di governance e come soddisfarli. 

> [!Tip] 
> Guardare la sessione seguente per altre informazioni sulla governance in Microsoft Teams: [Governance, gestione e ciclo](https://aka.ms/teams-governance) di vita in Microsoft Teams

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creazione di gruppi e team, denominazione, classificazione e accesso guest

L'organizzazione potrebbe richiedere l'implementazione di controlli rigorosi sul modo in cui i team vengono denominati e classificati, se i guest possono essere aggiunti come membri del team e chi può creare i team. È possibile configurare queste aree usando Azure Active Directory (Azure AD) e le etichette di riservatezza. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Punti decisionali|<ul><li>L'organizzazione richiede una convenzione di denominazione specifica per i team?</li><li>I creatori di team hanno bisogno della possibilità di assegnare classificazioni specifiche dell'organizzazione ai team?</li><li>È necessario limitare la possibilità di aggiungere guest ai team in base al team?</li><li>L'organizzazione richiede di limitare gli utenti che possono creare team?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la creazione, la denominazione, la classificazione e l'accesso guest del team.</li><li>Pianificare l'implementazione di questi requisiti come parte dell'Teams distribuzione.</li><li>Comunicare e pubblicare i criteri per informare Teams utenti del comportamento che possono aspettarsi.</li></ul>|

> [!NOTE]
> Per pianificare in anticipo, [altre informazioni sull'impostazione di questi criteri e sulle licenze necessarie.](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Limitare la creazione di gruppi e team può rallentare la produttività degli utenti, perché molti servizi di Microsoft 365 e Office 365 richiedono la creazione di gruppi per il funzionamento del servizio. Per altre informazioni, vedere [Pianificare la governance in Teams](/microsoft-365/solutions/manage-creation-of-groups).


#### <a name="additional-information"></a>Informazioni aggiuntive

Dopo aver determinato i requisiti, è possibile implementarli usando i controlli di Azure AD. Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- [Azure Active Directory cmdlet per la configurazione delle impostazioni di gruppo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Applicare criteri di denominazione per Microsoft 365 gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 Criteri di denominazione dei gruppi](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, Microsoft 365 gruppi e SharePoint siti](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opzioni di fine ciclo di vita per gruppi, team e Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Scadenza, conservazione e archiviazione di gruppi e team

L'organizzazione potrebbe avere requisiti aggiuntivi per l'impostazione di criteri per la scadenza, la conservazione e l'archiviazione dei dati dei team e dei team (messaggi di canale e file di canale). È possibile configurare i criteri di scadenza del gruppo per gestire automaticamente il ciclo di vita del gruppo e i criteri di conservazione per conservare o eliminare le informazioni in base alle esigenze, nonché archiviare i team (impostarli in modalità di sola lettura) per mantenere una visualizzazione temporizzazione di un team che non è più attivo. Tenere presente che i team archiviati continuano a applicare i criteri di scadenza e possono essere eliminati a meno che non vengano esclusi o rinnovati.

|-          |-           |
|-----------|------------|
| ![Icona che rappresenta i punti decisionali.](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede di specificare una data di scadenza per i team?</li><li>L'organizzazione richiede l'applicazione di criteri di conservazione dei dati specifici ai team?</li><li>L'organizzazione prevede di richiedere la possibilità di archiviare i team inattivi per mantenere il contenuto in uno stato di sola lettura?</li></ul>|
| ![Icona che illustra i passaggi successivi.](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la scadenza del team, la conservazione dei dati e l'archiviazione.</li><li>Pianificare l'implementazione di questi requisiti nell'ambito dell Teams di distribuzione.</li><li>Comunicare e pubblicare i criteri per informare Teams utenti del comportamento che possono aspettarsi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

|Funzionalità |Dettagli |Azure AD Premium richiesta una licenza |Decisione |
|---------|---------|---------|---------|
|Criteri di scadenza |Gestire il ciclo di vita Microsoft 365 gruppi impostando criteri di scadenza. |P1 |TBD|
|Criteri di conservazione |Conservare o eliminare i dati per un periodo di tempo specifico impostando criteri di conservazione per Teams nel Centro sicurezza & conformità. **Nota:** l'uso di questa funzionalità richiede la licenza di Microsoft 365 o Office 365 Enterprise E3 o versioni successive. |No |TBD |
|Archiviare e ripristinare |Archiviare un team quando non è più attivo, ma si vuole tenerlo in giro per riferimento o per riattivarlo in futuro. |No |TBD |

> [!Note]
> La scadenza del gruppo è una Azure AD Premium caratteristica. Per la disponibilità di questa caratteristica, il tenant deve avere un abbonamento a Azure AD Premium e licenze per l'amministratore che configura le impostazioni e i membri dei gruppi interessati.

#### <a name="additional-information"></a>Informazioni aggiuntive

Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- [Configurare la scadenza Microsoft 365 gruppi.](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Configurare i Teams di conservazione.](retention-policies.md)

- [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Gestione dell'appartenenza a gruppi e team

La gestione coerente dei membri di gruppi basati su progetti o con restrizioni è necessaria per i team che richiedono l'onboarding rapido e l'offboarding o gli utenti e gli utenti guest. L'organizzazione potrebbe anche dover verificare che tutti i membri correnti hanno la motivazione aziendale per far parte di un team. La gestione dei membri può essere difficile perché i proprietari dei team possono andarsene e gli utenti in genere non lasciano i gruppi di propria iniziativa al termine di un progetto o quando cambiano ruolo. Il modo migliore per gestire l'appartenenza ai gruppi che consente agli utenti di accedere quando necessario, assicurando però che il gruppo non abbia il rischio di un accesso inappropriato, è attraverso due processi distrettuale: gestione dei diritti e revisione dell'accesso.

[La gestione](/azure/active-directory/governance/entitlement-management-overview) dei diritti consente di delegare a qualcuno, ad esempio un project manager, di raccogliere tutte le risorse necessarie, incluse le appartenenze ai team, in un unico pacchetto. Possono anche definire chi può effettuare richieste: utenti nel tenant o da altre organizzazioni connesse. Il project manager riceverà le richieste di accesso tramite posta elettronica e approverà o rifiuta le richieste nel portale MyAccess. Gli amministratori possono configurare le condizioni di accesso in modo da includere una data o un periodo di scadenza entro il momento in cui l'utente o il guest verrà rimosso dal team a meno che l'accesso non venga rinnovato. Gli amministratori possono anche configurare i gruppi associati ai team per partecipare alle revisioni di accesso. Per [le revisioni di](/azure/active-directory/governance/access-reviews-overview)accesso, i proprietari del gruppo riceveranno regolarmente promemoria per rivedere i membri di un team. Le revisioni di Access includono suggerimenti, che semplificano l'esecuzione del normale processo di attestazione da parte dei proprietari dei gruppi.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Punti decisionali | L'organizzazione richiede un processo coerente per gestire l'appartenenza a uno o più team? <br> L'organizzazione richiede ai proprietari o ai membri stessi di giustificare regolarmente l'appartenenza a uno o più team? <br> L'organizzazione richiede l'approvazione di utenti e guest per richiedere l'accesso alle risorse, inclusi team, gruppi, SharePoint siti e app? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Passaggi successivi? | Documentare i requisiti dell'organizzazione per ogni team o team specifico per la scadenza dell'appartenenza.<br>Pianificare in che modo l'organizzazione può raggruppare team, gruppi, SharePoint siti e app in pacchetti di accesso.<br>Pianificare quali persone, ad esempio il responsabile del richiedente, un project manager, uno sponsor di un'organizzazione connessa o un responsabile della sicurezza dell'organizzazione dovranno approvare o rifiutare le richieste di accesso. |

> [!TIP]
> Usare la tabella seguente per acquisire i requisiti dell'organizzazione.

| Funzionalità | Dettagli | Azure AD Premium richiesta una licenza | Decisione |
|:-|:-|:-|:-|
| Recensioni di Access | Configurare le revisioni di accesso per ricertificare l'appartenenza di team specifici a intervalli regolari | P2 | TBD |
| Gestione dei diritti | Configurare il pacchetto di accesso per consentire a utenti e guest di richiedere l'accesso ai team | P2 | TBD |

> [!NOTE]
> Per pianificare in anticipo, [altre informazioni sulle licenze necessarie.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Informazioni aggiuntive

Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- [Gestione dei diritti](/azure/active-directory/governance/entitlement-management-overview)
- [Recensioni di Access](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams delle funzionalità

Un altro aspetto importante della governance e della gestione del ciclo di Teams è la possibilità di controllare le caratteristiche a cui gli utenti avranno accesso. È possibile gestire le funzionalità di messaggistica, riunione e chiamata, a livello Microsoft 365 o Office 365 dell'organizzazione o per utente.


|-        |-        |
|---------|---------|
| ![Icona che rappresenta i punti decisionali.](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede la limitazione Teams caratteristiche per l'intero tenant?</li><li>L'organizzazione richiede la limitazione delle Teams per utenti specifici?</li></ul>|
| ![Icona che illustra i passaggi successivi.](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per limitare Teams caratteristiche a livello di tenant e utente.</li><li>Pianificare l'implementazione di requisiti specifici nell'ambito dell'Teams distribuzione.</li><li>Comunicare e pubblicare i criteri per informare Teams utenti del comportamento previsto.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams focus sulla gestione delle funzionalità

Teams funzionalità granulari per il controllo delle funzionalità di messaggistica, riunione, chiamate ed eventi live e altro ancora, tramite i criteri. È possibile applicare criteri diversi a tutti gli utenti per impostazione predefinita o per utente, come richiesto dall'organizzazione. 

Per elenchi dettagliati di tutte le impostazioni, incluse indicazioni tecniche su come implementarle per l'organizzazione, vedere gli articoli seguenti:

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).
- [Canali privati in Microsoft Teams](private-channels.md)
- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md)
- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)

Inoltre, è possibile configurare la moderazione per un canale e fornire funzionalità di moderatore a determinati utenti in modo che possano controllare chi può creare post del canale e rispondere. Per [altre informazioni, vedere](manage-channel-moderation-in-teams.md) Configurare e gestire la moderazione Microsoft Teams canale.

## <a name="security-and-compliance"></a>Sicurezza e conformità

Teams è basato sulle funzionalità avanzate di sicurezza e conformità di Microsoft 365 e Office 365 e supporta il controllo e la creazione di report, la ricerca di contenuto di conformità, l'individuazione elettronica, il blocco legale e i criteri di conservazione.

> [!Important]
> Se l'organizzazione ha requisiti di conformità e sicurezza, esaminare il contenuto approfondito fornito su questo argomento nell'articolo Panoramica della sicurezza e della conformità [in Microsoft Teams](security-compliance-overview.md).

## <a name="related-topics"></a>Argomenti correlati

[Guida introduttiva sulla governance per Teams](teams-adoption-governance-quick-start.md)

[Microsoft 365 sulle licenze per la conformità & sicurezza](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->