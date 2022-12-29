---
title: Gestire le app di Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire l'accesso alle app personalizzate create con Microsoft Power Platform nell'interfaccia di amministrazione di Teams.
ms.openlocfilehash: cf47cb5a2441676aba706b2353837d51997d9b4f
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677396"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gestire le app di Microsoft Power Platform nell'interfaccia di amministrazione di Teams

Questo articolo offre una panoramica su come gestire le app personalizzate create con le app [Microsoft Power Platform](https://powerplatform.microsoft.com/) nell'interfaccia di amministrazione di Microsoft Teams. Le app personalizzate vengono create dagli sviluppatori all'interno dell'organizzazione per gli utenti interni.

> [!NOTE]
> Questo articolo non si applica all'app `Power Apps` o `Power Virtual Agents` all'app installata dall'App Store o aggiunta a Teams tramite un criterio di configurazione dell'app. È possibile gestire le app dello Store tramite i [criteri di autorizzazione](teams-app-permission-policies.md) e i [criteri di configurazione](teams-app-setup-policies.md) delle app.

[Power Apps](https://powerapps.microsoft.com) è un ambiente di sviluppo di applicazioni a basso o senza codice che i creatori di app nell'organizzazione possono usare per creare app personalizzate che si connettono ai dati aziendali. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) è un ambiente di creazione di bot senza codice che consente agli sviluppatori di app di creare bot efficaci. Con l'integrazione delle app di Microsoft Power Platform in Teams, le organizzazioni possono semplificare i processi aziendali, rispondere alle mutevoli esigenze aziendali più rapidamente per aumentare la collaborazione e creare e condividere soluzioni personalizzate per una maggiore produttività.  

Le app di Microsoft Power Platform create dagli sviluppatori nell'organizzazione vengono aggiunte automaticamente a Teams. Gli sviluppatori possono controllare chi può accedere alla propria app usando la [funzionalità di condivisione in Power Apps](/powerapps/maker/canvas-apps/share-app) e la [funzionalità di condivisione in Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Quando viene creata o condivisa un'app Microsoft Power Platform, gli utenti possono visualizzarla e installarla nella pagina App in **Creato con Power Platform**. Potrebbero essere necessari alcuni minuti prima che un'app creata o condivisa venga visualizzata qui.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshot della pagina App, che mostra le app Microsoft Power Platform riportate in Creato con Power Platform.":::

Gli utenti finali possono visualizzare un'app in **Creato con Power Platform** se l'app soddisfa una delle condizioni seguenti.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>L'utente ha creato l'app.</li><li>L'app è stata condivisa direttamente con l'utente.</li><li>L'utente ha usato di recente l'app. </li></ul>| <ul><li>L'utente ha creato il bot.</li><li>Il bot è di proprietà di un team di cui l'utente è membro. </li></ul>        |

Gli utenti possono installare le app di Microsoft Power Platform nello stesso modo in cui installano qualsiasi altra app di Teams. Si tenga presente che gli utenti possono installare le app solo nel contesto di cui dispongono delle autorizzazioni. Ad esempio, un team di cui un utente è proprietario, una chat di cui fa parte l'utente o il suo ambito personale.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gestire l'accesso alle app di Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

Gli amministratori possono controllare se le app di Microsoft Power Platform sono riportate in **Creato con Power Platform** nella pagina App in Teams. È possibile bloccare o consentire collettivamente tutte le app create in Power Apps o in Power Virtual Agents a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) o per utenti specifici che usano [criteri di autorizzazione per le app](teams-app-permission-policies.md).

Le app **Shared Power Apps** e **Shared Power Virtual Agent Apps** nell'app store dell'organizzazione rappresentano tutte le app create su tale piattaforma specifica. Se blocchi una o entrambe queste app per l'intera organizzazione o per utenti specifici, gli utenti non possono installarle in Teams. Gli utenti non possono richiedere l'approvazione dell'amministratore per consentire le app.

Si tenga presente che è possibile controllare l'accesso a tutte le app create in Power Apps e Power Virtual Agents, ma non è possibile consentire o bloccare singole app. L'autore dell'app decide chi può accedere all'app creata tramite la funzionalità di condivisione da Power Apps e Power Virtual Agents. Se un autore ha condiviso un'app creata in Power Virtual Agents con un utente e **Shared Power Virtual Agents Apps** è stato bloccato per questo utente, tale utente non sarà in grado di vedere o installare app dalla piattaforma in Teams.

Se un utente è autorizzato ad accedere alle app da Power Apps o Power Virtual Agents e quindi si impedisce all'utente di accedere alle app da una o entrambe queste piattaforme, l'utente può comunque accedere e usare le app Microsoft Power Platforms installate prima che l'app o le app sono state bloccate. Tuttavia, l'utente non può più installare alcun app da tali piattaforme in **Creato con Power Platform**.

> [!NOTE]
> Le impostazioni delle app a livello di organizzazione **Consenti interazione con app** nella pagina [Gestisci app](manage-apps.md), riguardano a tutti gli utenti dell'organizzazione e regolano la possibilità interagire con app personalizzate. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. Se questa impostazione è disattivata, gli utenti dell'organizzazione non possono installare app personalizzate, incluse le app di Microsoft Power Platform. Per altre informazioni, vedere [Gestire le impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Consentire o bloccare le app di Microsoft Power Platform per l'organizzazione

Per impostazione predefinita, **Shared Power Apps** e **Shared Power Virtual Agent Apps** sono consentiti per tutti gli utenti di Teams nell'organizzazione. È possibile disattivare o attivare le app a livello di organizzazione dalla pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.  

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)** È necessario essere un amministratore globale o un amministratore del servizio Teams per accedere alla pagina.
1. Nell'elenco delle app, eseguire una delle operazioni seguenti.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot della pagina Gestisci app che mostra le app condivise di Microsoft Power Platform.":::

    * Per bloccare le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o **Shared Power Virtual Agent Apps**, selezionarlo, quindi selezionare **Blocca**.
    * Per consentire le app create in Power Apps o Power Virtual Agents per tutti gli utenti dell'organizzazione, cercare **Shared Power Apps** o **Shared Power Virtual Agent Apps**, selezionarlo, quindi selezionare **Consenti**.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>Consentire le app Microsoft Power Platform per utenti specifici

Per consentire o impedire a utenti specifici dell'organizzazione di accedere alle app create in Power Apps o Power Virtual Agents, creare e assegnare uno o più [criteri di autorizzazione app](teams-app-permission-policies.md) personalizzati.

Ad esempio, per impedire a utenti specifici di accedere alle app create in Power Apps, creare un criterio personalizzato per le autorizzazioni delle app per bloccare le **app con alimentazione condivisa** e quindi assegnare il criterio a tali utenti.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot dei criteri personalizzati di esempio per le autorizzazioni delle app con Le app di alimentazione condivise sono bloccate.":::

### <a name="use-audit-logs-to-check-microsoft-power-platform-installation-activity"></a>Usare i log di controllo per controllare l'attività di installazione di Microsoft Power Platform

È possibile usare i log di controllo di Teams per analizzare gli eventi in cui gli utenti hanno installato le app di Microsoft Power Platform dalla sezione **Creato con Power Platform** della pagina App in Teams. A tale scopo, [cercare il log di controllo](./audit-log-events.md) per l'evento di Teams **App installata** (nell'operazione **AppInstalled**) per un utente o un set di utenti. Per trovare le app installate da **Creato con Power Platform**, cercare il valore **TemplatedInstance** nella proprietà **AppDistributionMode** nei dettagli di un determinato record.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot del valore TemplatedInstance nella proprietà AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> È possibile esportare i record di controllo in formato CSV per semplificare l'applicazione di filtri.

## <a name="related-articles"></a>Articoli correlati

* [Condividere un'app canvas in Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Condividere il bot con altri utenti](/power-virtual-agents/admin-share-bots)
* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
* [Pubblicare un'app personalizzata inviata tramite l'API di l’invio app di Teams](submit-approve-custom-apps.md)
