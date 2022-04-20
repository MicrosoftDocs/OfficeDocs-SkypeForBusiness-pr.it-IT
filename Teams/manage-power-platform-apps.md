---
title: Gestire le app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire l'accesso alle app personalizzate create su Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: c093d432faa8d4977f4d931ac948a35dc6fe6509
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2022
ms.locfileid: "63442672"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>App Microsoft Power Platform in Teams

Questo articolo offre una panoramica su come gestire le app [di Microsoft Power Platform](https://powerplatform.microsoft.com/) nell'interfaccia di amministrazione di Microsoft Teams.

> [!NOTE]
> Questo articolo si applica alle app personalizzate create dai creatori dell'organizzazione che usano Power Apps o Power Virtual Agents. Queste app personalizzate vengono aggiunte automaticamente a Teams. Questo articolo non si applica all'app Power Apps o all'app Power Virtual Agents installata dalla pagina App o aggiunta a Teams tramite un criterio di configurazione dell'app. Queste app vengono gestite come per qualsiasi altra app nella pagina [Gestisci app](manage-apps.md) , usando criteri di [autorizzazione](teams-app-permission-policies.md) e [criteri di configurazione delle app](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) è un ambiente di sviluppo di applicazioni a basso codice/senza codice che i creatori dell'organizzazione possono usare per creare app personalizzate che si connettono ai dati aziendali. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) è un ambiente di creazione di bot senza codice che consente ai produttori di creare bot potenti. Con l'integrazione delle app Microsoft Power Platform in Teams, le organizzazioni possono semplificare i processi aziendali, rispondere alle mutevoli esigenze aziendali più rapidamente per favorire una maggiore collaborazione e creare e condividere soluzioni personalizzate per aumentare la produttività.  

Le app Microsoft Power Platform create dai creatori dell'organizzazione vengono aggiunte automaticamente a Teams. I creatori possono controllare chi può accedere all'app usando la [funzionalità di condivisione in Power Apps](/powerapps/maker/canvas-apps/share-app) e la [funzionalità di condivisione in Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Quando viene creata o condivisa un'app Microsoft Power Platform, gli utenti possono visualizzarla e installarla nella pagina App in **Built for *Your Organization NameCompilata*** >  **dai colleghi**. Potrebbero essere necessari alcuni minuti prima che un'app venga creata o condivisa per essere visualizzata qui.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshot della pagina App che mostra le app di Microsoft Power Platform elencate in Predefinite dai colleghi":::

Un utente vedrà un'app **incorporata dai colleghi** se soddisfa una delle condizioni seguenti.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>L'utente ha creato l'app.</li><li>L'app è stata condivisa direttamente con l'utente.</li><li>L'utente ha usato di recente l'app. </li></ul>| <ul><li>L'utente ha creato il bot.</li><li>Il bot è di proprietà di un team di cui l'utente è membro. </li></ul>        |

Gli utenti installano le app Microsoft Power Platform nello stesso modo in cui installano qualsiasi altra app Teams. Tenere presente che gli utenti possono installare le app solo nel contesto in cui hanno le autorizzazioni, ad esempio un team di cui sono proprietari, una chat di cui fanno parte o il proprio ambito personale.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire l'accesso alle app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

Gli amministratori possono controllare se le app di Microsoft Power Platform sono elencate in **Predefinite dai colleghi** nella pagina App di Teams. Puoi bloccare o consentire collettivamente tutte le app create in Power Apps o tutte le app create in Power Virtual Agents a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) o per utenti specifici che usano [criteri di autorizzazione](teams-app-permission-policies.md) per le app.

Le app **Shared Power Apps** e **Shared Power Virtual Agent Apps** nell'app store dell'organizzazione rappresentano tutte le app create su quella particolare piattaforma. Se blocchi una o entrambe queste app a livello di organizzazione o per utenti specifici, tali utenti non potranno vedere le app di queste piattaforme in **Built by your colleagues** e non potranno installarle in Teams.  

Tieni presente che puoi controllare l'accesso a tutte le app create in Power Apps e Power Virtual Agents ma non puoi consentire o bloccare singole app. I creatori decidono chi può accedere alle app create tramite la funzionalità di condivisione dall'interno di Power Apps e Power Virtual Agents. Se un produttore ha condiviso un'app creata in Power Virtual Agents con un utente e hai bloccato **App di Power Virtual Agents condivise** per tale utente, l'utente non sarà in grado di vedere o installare app da tale piattaforma in Teams.

Se un utente è autorizzato ad accedere alle app da Power Apps o Power Virtual Agents e quindi si blocca l'accesso alle app da una o entrambe le piattaforme, l'utente può comunque accedere e usare le app Microsoft Power Platforms installate prima che l'app o le app vengano bloccate. Tuttavia, l'utente non può più visualizzare o installare le app di tali piattaforme in **Built by your colleagues**.

> [!NOTE]
> **L'impostazione Consenti l'interazione con app personalizzate** a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) si applica a tutti gli utenti dell'organizzazione e regola se possono interagire con le app personalizzate. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. Per impostazione predefinita, questa impostazione è attivata. Se questa impostazione è disattivata, gli utenti dell'organizzazione non possono visualizzare o installare app personalizzate, incluse le app Microsoft Power Platform. Per altre informazioni, vedi [Gestire le impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Consentire o bloccare le app di Microsoft Power Platform per l'organizzazione

Per impostazione predefinita, le app Shared **Power Apps** e **Shared Power Virtual Agent** sono consentite per tutti gli utenti Teams dell'organizzazione. È possibile bloccarli o consentirli a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) dell'interfaccia di amministrazione di Microsoft Teams.  

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina è necessario essere un amministratore globale o Teams servizio.
2. Nell'elenco delle app esegui una delle operazioni seguenti.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot della pagina Gestisci app che mostra le app condivise di Microsoft Power Platform":::

    - Per bloccare le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o **Shared Power Virtual Agent Apps**, selezionarla e quindi fare clic su **Blocca**.
    - Per consentire le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o **Shared Power Virtual Agent Apps**, selezionarla e quindi fare clic su **Consenti**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Consentire o bloccare le app di Microsoft Power Platform per utenti specifici

Per consentire o impedire a utenti specifici dell'organizzazione di accedere alle app create in Power Apps o Power Virtual Agents, creare e assegnare uno o più criteri di autorizzazione personalizzati per [le app](teams-app-permission-policies.md).

Ad esempio, per impedire a utenti specifici di accedere alle app create in Power Apps, creare un criterio di autorizzazione per l'app personalizzato per bloccare **i Power Apps condivisi** e quindi assegnarlo a tali utenti.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot di esempio di criteri di autorizzazione per le app personalizzati con Power Apps condivisi bloccati.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usare i log di controllo per analizzare l'attività di installazione di Microsoft Power Platform

È possibile usare i log di controllo per Teams per esaminare gli eventi in cui gli utenti hanno installato le app Microsoft Power Platform dalla sezione **Built by your colleagues** della pagina App in Teams. A questo scopo, [cercare nel log di controllo](./audit-log-events.md) **l'evento Teams dell'app installata** (nell'operazione **AppInstalled**) per un utente o un set di utenti. Per trovare le app installate da **Built by your colleagues**, cerca il valore **TemplatedInstance** nella proprietà **AppDistributionMode** nei dettagli di un determinato record.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot del valore TemplatedInstance nella proprietà AppDistributionMode.":::

> [!NOTE]
> È possibile esportare i record di controllo in formato CSV per semplificare l'applicazione di filtri.

## <a name="related-topics"></a>Argomenti correlati

- [Condividere un'app canvas in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Condividere il bot con altri utenti](/power-virtual-agents/admin-share-bots)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams](submit-approve-custom-apps.md)
