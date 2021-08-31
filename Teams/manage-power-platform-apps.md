---
title: Gestire le app Microsoft Power Platform nell'Microsoft Teams di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
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
description: Informazioni su come gestire l'accesso alle app personalizzate integrate in Microsoft Power Platform nell'Microsoft Teams di amministrazione.
ms.openlocfilehash: d3bf125415f3459913d7b23f5a496cb44eb51856
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730665"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app Microsoft Power Platform nell'Microsoft Teams di amministrazione

## <a name="microsoft-power-platform-apps-in-teams"></a>App Microsoft Power Platform in Teams

Questo articolo offre una panoramica su come gestire le app [Microsoft Power Platform](https://powerplatform.microsoft.com/) nell'Microsoft Teams di amministrazione.

> [!NOTE]
> Questo articolo si applica alle app personalizzate create dai creatori dell'organizzazione che usano Power Apps o Power Virtual Agents. Queste app personalizzate vengono aggiunte automaticamente Teams. Questo articolo non si applica all'app Power Apps o all'app Power Virtual Agents installata dalla pagina App o aggiunta a Teams tramite un criterio di configurazione dell'app. Queste app vengono gestite come per qualsiasi [](manage-apps.md) altra app nella pagina Gestisci app, usando i criteri di autorizzazione delle [app](teams-app-permission-policies.md)e i criteri [di configurazione delle app.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) è un ambiente di sviluppo di applicazioni a basso codice/senza codice che i creatori dell'organizzazione possono usare per creare app personalizzate che si connettono ai dati aziendali. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) è un ambiente di creazione di bot senza codice che consente ai creatori di creare potenti bot. Con l'integrazione delle app Microsoft Power Platform in Teams, le organizzazioni possono semplificare i processi aziendali, rispondere alle mutevoli esigenze aziendali più rapidamente per aumentare la collaborazione e creare e condividere soluzioni personalizzate per aumentare la produttività.  

Le app Microsoft Power Platform create dai creatori dell'organizzazione vengono aggiunte automaticamente Teams. I creatori possono controllare chi può accedere alla propria app usando la funzionalità di condivisione [in Power Apps](/powerapps/maker/canvas-apps/share-app) e la funzionalità di condivisione [in Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Quando si crea o si condivide un'app Microsoft Power Platform, gli **** utenti possono visualizzarla e installarla nella pagina App facendo clic su Creato per il nome dell'organizzazione creato  >  **dai colleghi.** Dopo la creazione o la condivisione di un'app, potrebbero essere necessario alcuni minuti prima che l'app venga visualizzata qui.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshot della pagina App che mostra le app di Microsoft Power Platform elencate in Built by your colleagues":::

Un utente visualizza un'app in **Built by your colleagues** se l'app soddisfa una delle condizioni seguenti.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>L'utente ha creato l'app.</li><li>L'app è stata condivisa direttamente con l'utente.</li><li>L'utente ha usato di recente l'app. </li></ul>| <ul><li>L'utente ha creato il bot.</li><li>Il bot è di proprietà di un team di cui l'utente è membro. </li></ul>        |

Gli utenti installano le app Microsoft Power Platform nello stesso modo in cui installano qualsiasi altra app Teams app. Tenere presente che gli utenti possono installare le app solo nel contesto in cui hanno le autorizzazioni, ad esempio un team di cui sono proprietari, una chat di cui fanno parte o l'ambito personale.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire l'accesso alle app Microsoft Power Platform nell'Microsoft Teams di amministrazione

Gli amministratori possono controllare se le app Microsoft Power Platform sono elencate in Built **by your colleagues** nella pagina Apps in Teams. È possibile bloccare o consentire collettivamente tutte le app create in Power Apps o tutte [](manage-apps.md) le app create in Power Virtual Agents a livello di organizzazione nella pagina Gestisci app o per utenti specifici che usano i criteri di autorizzazione [delle app.](teams-app-permission-policies.md)

Le **app Power Apps** **e App** agente virtuale power condiviso nell'app store dell'organizzazione rappresentano tutte le app create in quella specifica piattaforma. Se si bloccano una o entrambe queste app a livello di organizzazione o per utenti specifici, tali utenti non possono vedere le app di queste piattaforme in Built **by your colleagues** e non possono installarle in Teams.  

Tenere presente che è possibile controllare l'accesso a tutte le app create in Power Apps e Power Virtual Agents ma non è possibile consentire o bloccare singole app. I creatori decidono chi può accedere alle app create tramite la funzionalità di condivisione dall'interno Power Apps e Power Virtual Agents. Se un creatore ha condiviso un'app creata in Power Virtual Agents con un utente e l'utente ha bloccato app **Power Virtual Agents** condivise per quell'utente, l'utente non sarà in grado di visualizzare o installare app da tale piattaforma in Teams.

Se un utente è autorizzato ad accedere alle app da Power Apps o Power Virtual Agents e quindi si blocca l'accesso alle app da una o entrambe queste piattaforme, l'utente può comunque accedere e usare le app di Microsoft Power Platforms installate prima di bloccare l'app o le app. Tuttavia, l'utente non può più vedere o installare app da queste piattaforme in **Built by your colleagues**.

> [!NOTE]
> **L'impostazione** Consenti interazione con le app [](manage-apps.md) personalizzate a livello di organizzazione nella pagina Gestisci app si applica a tutti gli utenti dell'organizzazione e determina se possono interagire con le app personalizzate. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. Per impostazione predefinita, questa impostazione è attivata. Se questa impostazione è disattivata, gli utenti dell'organizzazione non possono vedere o installare app personalizzate, incluse le app Microsoft Power Platform. Per altre informazioni, vedere [Gestire le impostazioni dell'app a livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Consentire o bloccare le app Microsoft Power Platform per l'organizzazione

Per impostazione predefinita, **le app Power Apps** di power virtual **agent** condivise sono consentite per tutti Teams utenti dell'organizzazione. È possibile bloccarli o consentirli a livello di organizzazione nella pagina Gestisci [app](manage-apps.md) dell'Microsoft Teams di amministrazione.  

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Per accedere alla pagina, è necessario essere un amministratore globale o un Teams servizio.
2. Nell'elenco delle app eseguire una delle operazioni seguenti.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot della pagina Gestisci app che mostra le app condivise di Microsoft Power Platform":::

    - Per bloccare le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o Shared Power Virtual **Agent Apps,** selezionarla e quindi fare clic su **Blocca**.
    - Per consentire le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o Shared Power Virtual **Agent Apps**, selezionarla e quindi fare clic su **Consenti**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Consentire o bloccare le app Microsoft Power Platform per utenti specifici

Per consentire o impedire a utenti specifici dell'organizzazione di accedere ad app create in Power Apps o Power Virtual Agents, creare e assegnare uno o più criteri di autorizzazione [delle app personalizzati.](teams-app-permission-policies.md) 

Ad esempio, per impedire a utenti specifici di accedere alle app create in Power Apps, creare un criterio di autorizzazione per l'app personalizzato per bloccare **l'Power Apps** condiviso e quindi assegnare il criterio a tali utenti.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot di un esempio di criteri di autorizzazione per le app personalizzate con Power Apps bloccati.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usare i log di controllo per esaminare l'attività di installazione di Microsoft Power Platform

È possibile usare i log di controllo Teams per esaminare gli eventi in cui gli utenti hanno installato le app microsoft power platform dalla sezione Built **by your colleagues** della pagina Apps in Teams. A questo scopo, [cercare un](./audit-log-events.md) utente o un set di utenti nel log di controllo per l'evento Teams app installata (nell'operazione  **AppInstalled).** Per trovare le app installate da **Built by your colleagues,** cercare il valore **TemplatedInstance** nella **proprietà AppDistributionMode** nei dettagli di un determinato record. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot del valore TemplatedInstance nella proprietà AppDistributionMode.":::

> [!NOTE]
> È possibile esportare i record di controllo in formato CSV per filtrare più facilmente.

## <a name="related-topics"></a>Argomenti correlati

- [Condividere un'app canvas in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Condividere il bot con altri utenti](/power-virtual-agents/admin-share-bots)
- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Pubblicare un'app personalizzata inviata tramite l'API Teams per l'invio di app](submit-approve-custom-apps.md)