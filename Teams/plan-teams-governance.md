---
title: Pianificare la governance in Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In questo articolo imparerai a pianificare l'implementazione delle funzionalità di governance in Teams.
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

Teams offre un set di strumenti avanzati per implementare tutte le funzionalità di governance che potrebbero essere richieste dall'organizzazione. Questo articolo guida i professionisti IT a porre le domande giuste per determinare i requisiti per la governance e come soddisfarli. 

> [!Tip] 
> Guardare la sessione seguente per saperne di più sulla governance in Microsoft Teams: [Governance, gestione e ciclo di vita in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creazione di gruppi e team, denominazione, classificazione e accesso guest

L'organizzazione potrebbe richiedere l'implementazione di controlli rigorosi sul modo in cui i team vengono denominati e classificati, se i guest possono essere aggiunti come membri del team e chi può creare team. È possibile configurare queste aree usando Azure Active Directory (Azure AD) e le etichette di riservatezza. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Punti decisionali|<ul><li>L'organizzazione richiede una convenzione di denominazione specifica per i team?</li><li>I creatori di team hanno bisogno della possibilità di assegnare classificazioni specifiche dell'organizzazione ai team?</li><li>È necessario limitare la possibilità di aggiungere guest ai team per ogni singolo team?</li><li>L'organizzazione richiede di limitare chi può creare team?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la creazione del team, la denominazione, la classificazione e l'accesso guest.</li><li>Pianificare l'implementazione di questi requisiti nell'ambito dell'implementazione di Teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti di Teams del comportamento che possono aspettarsi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per soddisfare i requisiti dell'organizzazione.

|Funzionalità |Dettagli |Azure AD Premium <br> licenza necessaria |Decisione |
|---------|---------|---------|---------|
|Criteri di denominazione dei team | Usare parole bloccate personalizzate basate su prefissi e suffissi. |P1 |TBD |
|Classificazione del team |Assegnare classificazioni ai team. |P1 |TBD |
|Accesso guest del team |Consentire o impedire l'aggiunta di guest ai team. |No |TBD |
|Creazione di team |Limitare la creazione di team agli amministratori. |No |TBD|
|Creazione di team |Limitare la creazione di team ai membri del gruppo di sicurezza. |P1 |TBD|
|Etichette di riservatezza|Configurare la privacy e la condivisione guest|No|TBD|

> [!NOTE]
> Per pianificare in anticipo, [leggere altre informazioni sull'impostazione di questi criteri e sulle licenze necessarie.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Limitare la creazione di gruppi e team può rallentare la produttività degli utenti, perché per il funzionamento di molti servizi di Microsoft 365 e Office 365 è necessario creare gruppi. Per altre informazioni, esplorare ed espandere Perché controllare chi può creare gruppi di [Microsoft 365.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>Informazioni aggiuntive

Dopo aver determinato i requisiti, è possibile implementarli usando i controlli di Azure AD. Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- [Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Applicare criteri di denominazione per i gruppi di Microsoft 365 in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Criteri di denominazione dei gruppi di Microsoft 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opzioni per la fine del ciclo di vita per gruppi, team e Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Scadenza, conservazione e archiviazione di gruppi e team

L'organizzazione potrebbe avere requisiti aggiuntivi per l'impostazione di criteri di scadenza, conservazione e archiviazione dei team e dei dati dei team (messaggi del canale e file del canale). È possibile configurare criteri di scadenza dei gruppi per gestire automaticamente il ciclo di vita del gruppo e dei criteri di conservazione per conservare o eliminare le informazioni in base alle esigenze, nonché archiviare i team (impostarli in modalità di sola lettura) per mantenere una visualizzazione temporizzazione di un team non più attivo. Tenere presente che i team archiviati continuano ad avere i criteri di scadenza applicati e possono essere eliminati a meno che non vengano esclusi o rinnovati.

|           |            |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede di specificare una data di scadenza per i team?</li><li>L'organizzazione richiede l'applicazione di criteri di conservazione dei dati specifici ai team?</li><li>L'organizzazione prevede che sia necessario poter archiviare i team inattivi per conservare il contenuto in stato di sola lettura?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per la scadenza, la conservazione dei dati e l'archiviazione del team.</li><li>Pianificare l'implementazione di questi requisiti nell'ambito dell'implementazione di Teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti di Teams del comportamento che possono aspettarsi.</li></ul>|

> [!TIP]
> Usare la tabella seguente per soddisfare i requisiti dell'organizzazione.

|Funzionalità |Dettagli |Licenza di Azure AD Premium richiesta |Decisione |
|---------|---------|---------|---------|
|Criteri di scadenza |Gestire il ciclo di vita dei gruppi di Microsoft 365 impostando criteri di scadenza. |P1 |TBD|
|Criteri di conservazione |Conservare o eliminare dati per un periodo di tempo specifico impostando criteri di conservazione per Teams nel Centro sicurezza & conformità. **Nota:** l'uso di questa funzionalità richiede la licenza di Microsoft 365 o Office 365 Enterprise E3 o versioni successive. |No |TBD |
|Archiviare e ripristinare |Archiviare un team quando non è più attivo, ma si vuole mantenerlo per riferimento o riattivarlo in futuro. |No |TBD |

> [!Note]
> La scadenza del gruppo è una funzionalità di Azure AD Premium. Per poter essere disponibile, il tenant deve avere una sottoscrizione di Azure AD Premium e licenze per l'amministratore che configura le impostazioni e i membri dei gruppi interessati.

#### <a name="additional-information"></a>Informazioni aggiuntive

Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- Impostare la scadenza dei gruppi di [Microsoft 365.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Configurare i criteri di conservazione di Teams.](retention-policies.md)

- [Archiviare o ripristinare un team.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Gestione dell'appartenenza a gruppi e team

Una gestione coerente dei membri di gruppi basati su progetto o con restrizioni è necessaria per i team che richiedono un rapido onboarding e offboarding oppure utenti e guest. L'organizzazione potrebbe anche avere l'esigenza di verificare che tutti i membri correnti abbia la motivazione aziendale necessaria per far parte di un team. Gestire i membri può essere difficile perché i proprietari dei team possono lasciarlo e in genere gli utenti non lasciano i gruppi per proprio conto al termine di un progetto o quando cambiano ruolo. Il modo migliore per gestire l'appartenenza ai gruppi che consente agli utenti di accedere quando necessario, ma che il gruppo non rischi di accedere inappropriato è attraverso due processi distrettuale: la gestione dei diritti e le revisioni di accesso.

[La gestione](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) dei diritti consente di delegare a qualcuno, ad esempio un project manager, di raccogliere tutte le risorse necessarie, incluse le appartenenze ai team, in un unico pacchetto. Possono anche definire chi può effettuare richieste, ad esempio gli utenti del tenant o di altre organizzazioni connesse. Il project manager riceverà le richieste di accesso nella posta elettronica e approverà o rifiuta le richieste nel portale MyAccess. Gli amministratori possono configurare le condizioni di accesso in modo da includere una data di scadenza o un periodo entro il momento in cui l'utente o il guest verrà rimosso dal team a meno che l'accesso non venga rinnovato. Gli amministratori possono anche configurare i gruppi associati ai team per partecipare alle revisioni di accesso. Per [le revisioni](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)di accesso, i proprietari del gruppo riceveranno promemoria regolari per rivedere i membri di un team. Le revisioni di Access includono suggerimenti, che semplificano l'esecuzione del normale processo di attestazione da parte dei proprietari del gruppo.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Punti decisionali | L'organizzazione richiede un processo coerente per la gestione dell'appartenenza a uno o più team? <br> L'organizzazione richiede ai proprietari o ai membri stessi di giustificare regolarmente la continua appartenenza a uno o più team? <br> L'organizzazione richiede l'approvazione di utenti e guest per richiedere l'accesso a risorse come team, gruppi, siti di SharePoint e app? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Passaggi successivi? | Documentare i requisiti dell'organizzazione per ogni team o team specifici per la scadenza dell'appartenenza.<br>Pianificare in che modo l'organizzazione può raggruppare team, gruppi, siti di SharePoint e app in pacchetti di accesso.<br>Pianificare quali persone, ad esempio il responsabile del richiedente, un project manager, uno sponsor per un'organizzazione connessa o un responsabile della sicurezza dell'organizzazione dovranno approvare o negare le richieste di accesso. |

> [!TIP]
> Usare la tabella seguente per soddisfare i requisiti dell'organizzazione.

| Funzionalità | Dettagli | Licenza di Azure AD Premium richiesta | Decisione |
|:-|:-|:-|:-|
| Recensioni di Access | Configurare le revisioni di accesso per certificati l'appartenenza a team specifici a intervalli regolari | P2 | TBD |
| Gestione dei diritti | Configurare il pacchetto di accesso per consentire a utenti e guest di richiedere l'accesso ai team | P2 | TBD |

> [!NOTE]
> Per una pianificazione in anticipo, [leggere altre informazioni sulle licenze necessarie.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Informazioni aggiuntive

Per indicazioni tecniche su come implementare queste impostazioni, vedere:

- [Gestione dei diritti](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Recensioni di Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Gestione delle funzionalità dei team

Un altro aspetto importante della gestione della governance e del ciclo di vita per Teams è la possibilità di controllare a quali caratteristiche gli utenti avranno accesso. È possibile gestire le funzionalità di messaggistica, riunioni e chiamate a livello di organizzazione di Microsoft 365 o Office 365 oppure a livello di utente.


|         |         |
|---------|---------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>L'organizzazione richiede di limitare le funzionalità di Teams per l'intero tenant?</li><li>La tua organizzazione richiede di limitare le funzionalità di Teams per utenti specifici?</li></ul>|
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare i requisiti dell'organizzazione per limitare le funzionalità di Teams a livello di tenant e utente.</li><li>Pianificare l'implementazione dei requisiti specifici nell'ambito dell'implementazione di Teams.</li><li>Comunicare e pubblicare i criteri per informare gli utenti di Teams del comportamento che possono aspettarsi.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Aree di interesse per la gestione delle funzionalità di Teams

Teams offre funzionalità granulari per il controllo delle funzionalità di messaggistica, riunioni, chiamate ed eventi live e altro ancora, tramite criteri. È possibile applicare criteri diversi a tutti gli utenti per impostazione predefinita o per ogni utente, come richiesto dall'organizzazione. 

Per elenchi dettagliati di tutte le impostazioni, incluse le indicazioni tecniche su come implementarle per l'organizzazione, vedere gli articoli seguenti:

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).
- [Canali privati in Microsoft Teams](private-channels.md)
- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)

Inoltre, è possibile impostare la moderazione per un canale e assegnare capacità di moderatore a determinati utenti in modo che possano controllare chi può creare post del canale e rispondere. Per altre informazioni, vedere Configurare e gestire [la moderazione dei canali in Microsoft Teams.](manage-channel-moderation-in-teams.md)

## <a name="security-and-compliance"></a>Sicurezza e conformità

Teams si basa sulle funzionalità avanzate di sicurezza e conformità di Microsoft 365 e Office 365 e supporta il controllo e la creazione di report, la ricerca di contenuti per la conformità, l'e-discovery, il blocco a tutti gli elementi legali e i criteri di conservazione.

> [!Important]
> Se l'organizzazione ha requisiti di conformità e sicurezza, esaminare i contenuti approfonditi forniti su questo argomento nell'articolo Panoramica della sicurezza e [conformità in Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Argomenti correlati

[Guida introduttiva sulla governance per Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
