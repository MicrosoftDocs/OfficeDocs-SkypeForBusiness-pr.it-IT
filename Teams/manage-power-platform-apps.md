---
title: Gestire le app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire l'accesso alle app personalizzate basate su Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft teams.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831296"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>App Microsoft Power Platform in teams

Questo articolo offre una panoramica su come gestire le app [Microsoft Power Platform](https://powerplatform.microsoft.com/) nell'interfaccia di amministrazione di Microsoft teams.

> [!NOTE]
> Questo articolo si applica alle app personalizzate create dai creatori dell'organizzazione usando Power Apps o Power Virtual Agents. Queste app personalizzate vengono aggiunte automaticamente ai team. Questo articolo non si applica all'app Power Apps o Power Virtual Agents che vengono installate dalla pagina app o aggiunte ai team tramite criteri di configurazione dell'app. Puoi gestire le app come vuoi per qualsiasi altra app nella pagina [Gestisci](manage-apps.md) app, usando i criteri di [autorizzazione delle app](teams-app-permission-policies.md)e i criteri di [configurazione dell'app](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) è un ambiente di sviluppo di applicazioni a basso codice o senza codice che i creatori dell'organizzazione possono usare per creare app personalizzate che si connettono ai dati aziendali. [Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) è un ambiente di creazione di bot senza codice per i creatori per creare potenti bot. Con l'integrazione delle app Microsoft Power Platform in teams, le organizzazioni possono semplificare i processi aziendali, rispondere alle mutevoli esigenze aziendali in modo più rapido per una maggiore collaborazione e creare e condividere soluzioni personalizzate per essere più produttivi.  

Le app Microsoft Power Platform create dai creatori dell'organizzazione vengono aggiunte automaticamente ai team. I responsabili possono controllare chi può accedere alla propria app usando la [funzionalità di condivisione in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) e la [funzionalità di condivisione in agenti virtuali di Power](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).

Quando viene creata o condivisa un'app di Microsoft Power Platform, gli utenti possono visualizzarla e installarla nella pagina app passando a **built per *il nome dell'organizzazione*** creato  >  **dai colleghi**. Potrebbe essere necessario qualche minuto dopo che un'app viene creata o condivisa perché l'app venga visualizzata qui.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshot della pagina app, che mostra le app Microsoft Power Platform elencate in create dai colleghi":::

Se l'app soddisfa una delle condizioni seguenti, un utente visualizzerà un'app **incorporata dai colleghi** .

|Power Apps |Agenti virtuali di Power  |
|---------|---------|
|<ul><li>L'utente ha creato l'app.</li><li>L'app è stata condivisa direttamente con l'utente.</li><li>L'utente ha usato di recente l'app. </li></ul>| <ul><li>L'utente ha creato il bot.</li><li>Il bot è di proprietà di un team a cui appartiene l'utente. </li></ul>        |

Gli utenti installano le app Microsoft Power Platform nello stesso modo in cui installano qualsiasi altra app teams. Tieni presente che gli utenti possono installare le app solo nel contesto in cui hanno le autorizzazioni, ad esempio un team che possiedono, una chat di cui fanno parte o il loro ambito personale.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire l'accesso alle app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

Come amministratore, puoi controllare se le app Microsoft Power Platform sono elencate in **compilato dai colleghi** nella pagina app in teams. È possibile bloccare collettivamente o consentire a tutte le app create in Power Apps o tutte le app create in Power Virtual Agents a livello di organizzazione nella pagina [Manage Apps](manage-apps.md) o per utenti specifici che usano [criteri di autorizzazione](teams-app-permission-policies.md)per le app.

Le app di **Power Apps condivise** e le applicazioni di **Power Virtual Agent virtuali** nell'App Store dell'organizzazione rappresentano tutte le app create in quella particolare piattaforma. Se si blocca una o entrambe le app a livello di organizzazione o per utenti specifici, gli utenti non possono visualizzare le app da tali piattaforme in **base alle proprie colleghe** e non possono essere installate in teams.  

Tieni presente che puoi controllare l'accesso a tutte le app create in Power Apps e Power Virtual Agents, ma non puoi consentire o bloccare singole app. I responsabili decidono chi può accedere alle app che creano tramite la funzionalità di condivisione all'interno di Power Apps e Power Virtual Agents. Se un produttore ha condiviso un'app creata in Power Virtual Agents con un utente e bloccato le **app di Power Virtual Agent condivise** per l'utente, l'utente non sarà in grado di vedere o installare le app da tale piattaforma in teams.

Se un utente può accedere alle app da Power Apps o Power Virtual Agents e quindi bloccare l'accesso delle app da una o entrambe queste piattaforme, l'utente potrà comunque accedere e usare le app di Microsoft Power Platforms installate prima di bloccare l'app o le applicazioni. Tuttavia, l'utente non può più vedere o installare le app da tali piattaforme in **base alle proprie colleghe**.

> [!NOTE]
> L'impostazione **Consenti l'interazione con** le app personalizzate nella pagina [Gestisci applicazioni](manage-apps.md) si applica a tutti gli utenti dell'organizzazione e determina se possono interagire con le app personalizzate. Le impostazioni dell'app a livello di organizzazione regolano il comportamento per tutti gli utenti ed eseguono l'override di qualsiasi altro criterio di autorizzazione dell'app assegnato agli utenti. Per impostazione predefinita, questa impostazione è attivata. Se questa impostazione è disattivata, gli utenti dell'organizzazione non possono vedere o installare app personalizzate, incluse le app Microsoft Power Platform. Per altre informazioni, Vedi [gestire le impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Consentire o bloccare le app Microsoft Power Platform per l'organizzazione

Per impostazione predefinita, le app di **Power condivise** e le app di Power **Virtual Agent condivise** sono consentite per tutti gli utenti di Teams dell'organizzazione. Puoi bloccarle o consentirle a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) dell'interfaccia di amministrazione di Microsoft teams.  

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**. Per accedere alla pagina è necessario essere un amministratore globale o un servizio di teams.
2. Nell'elenco delle app eseguire una delle operazioni seguenti.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot della pagina Manage Apps, che mostra le app Microsoft Power Platform condivise":::

    - Per bloccare le app create in Power Apps o Power Virtual Agent per tutti gli utenti dell'organizzazione, cercare le app di **Power condivise** o le app di Power **Virtual Agent condivise**, selezionarle e quindi fare clic su **blocca**.
    - Per consentire alle app create in Power Apps o Power Virtual Agent per tutti gli utenti dell'organizzazione, cercare **app Power condivise** o **app di Power Virtual Agent condivise**, selezionarla e quindi fare clic su **Consenti**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Consentire o bloccare le app Microsoft Power Platform per utenti specifici

Per consentire o bloccare gli utenti specifici dell'organizzazione dall'accesso alle app create in Power Apps o Power Virtual Agents, crea e assegna uno o più [criteri di autorizzazione](teams-app-permission-policies.md)per le app personalizzate. 

Ad esempio, per bloccare gli utenti specifici dall'accesso alle app create in Power Apps, crea un criterio di autorizzazione per le app personalizzate per bloccare le **app di Power condivise** e quindi assegnare i criteri a tali utenti.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot di esempio di criteri di autorizzazione app personalizzati con le app Power condivise bloccate":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usare i log di controllo per analizzare le attività di installazione di Microsoft Power Platform

È possibile usare i registri di controllo per i team per esaminare gli eventi in cui gli utenti hanno installato le app Microsoft Power Platform dalla sezione dei **colleghi** della pagina delle app in teams. Per eseguire questa operazione, eseguire una [ricerca nel log di controllo](https://docs.microsoft.com/microsoftteams/audit-log-events) per l'evento Teams dell' **app installato** (in **AppInstalled** ) per un utente o un set di utenti. Per trovare le app installate dalla **compilazione dei colleghi**, cercare il valore **TemplatedInstance** nella proprietà **AppDistributionMode** nei dettagli di un record specifico. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot del valore TemplatedInstance nella proprietà AppDistributionMode":::

> [!NOTE]
> È possibile esportare i record di controllo in formato CSV per semplificare i filtri.

## <a name="related-topics"></a>Argomenti correlati

- [Condividere un'app Canvas in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Condividere il bot con altri utenti](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams](submit-approve-custom-apps.md)
