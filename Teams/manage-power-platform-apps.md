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
description: Informazioni su come gestire l'accesso ad app personalizzate create sulla piattaforma Microsoft Power nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831296"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app Microsoft Power Platform nell'interfaccia di amministrazione di Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>App Microsoft Power Platform in Teams

Questo articolo offre una panoramica su come gestire le app della piattaforma [Microsoft Power Nell'interfaccia](https://powerplatform.microsoft.com/) di amministrazione di Microsoft Teams.

> [!NOTE]
> Questo articolo si applica alle app personalizzate create dai produttori dell'organizzazione che usano Power Apps o agenti virtuali di Power. Queste app personalizzate vengono aggiunte automaticamente a Teams. Questo articolo non è applicabile all'app Power Apps o all'app Agenti virtuali Power che vengono installati dalla pagina App o aggiunti a Teams tramite un criterio di configurazione delle app. Queste app vengono gestite come per qualsiasi [](manage-apps.md) altra app nella pagina Gestisci app, usando i criteri di autorizzazione per le [app](teams-app-permission-policies.md)e i criteri [di configurazione delle app.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) è un ambiente di sviluppo di applicazioni a basso codice/senza codice che i produttori dell'organizzazione possono usare per creare app personalizzate che si connettono ai dati aziendali. [Power Virtual Agents è](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) un ambiente di creazione di bot senza codice in cui i produttori possono creare bot potenti. Grazie all'integrazione delle app Microsoft Power Platform in Teams, le organizzazioni possono semplificare i processi aziendali, rispondere alle mutevoli esigenze aziendali più rapidamente per aumentare la collaborazione e creare e condividere soluzioni personalizzate per aumentare la produttività.  

Le app Microsoft Power Platform create dai produttori nella tua organizzazione vengono aggiunte automaticamente a Teams. I produttori possono controllare chi può accedere alla propria app usando la funzionalità di [condivisione in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) e la funzionalità di condivisione in Agenti virtuali di [Power.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Quando viene creata o condivisa un'app Microsoft Power Platform, gli utenti **** possono visualizzarla e installarla nella pagina App facendo clic su Creato per il nome dell'organizzazione creato  >  **dai colleghi.** La visualizzazione dell'app in questa posizione può richiedere alcuni minuti dopo la creazione o la condivisione di un'app.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshot della pagina App che mostra le app della piattaforma Microsoft Power elencate in Predefinite dai colleghi":::

Un utente visualizza un'app in **Creata dai colleghi** se soddisfa una delle condizioni seguenti.

|Power Apps |Agenti virtuali di Power  |
|---------|---------|
|<ul><li>L'utente ha creato l'app.</li><li>L'app è stata condivisa direttamente con l'utente.</li><li>L'utente ha usato l'app di recente. </li></ul>| <ul><li>L'utente ha creato il bot.</li><li>Il bot è di proprietà di un team di cui fa parte l'utente. </li></ul>        |

Gli utenti installano le app Microsoft Power Platform nello stesso modo in cui installano qualsiasi altra app di Teams. Tenere presente che gli utenti possono installare app solo nel contesto in cui hanno le autorizzazioni, ad esempio un team di cui sono proprietari, una chat di cui fanno parte o il loro ambito personale.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestire l'accesso alle app microsoft power platform nell'interfaccia di amministrazione di Microsoft Teams

Come amministratore, puoi controllare se le app della piattaforma Microsoft Power sono elencate in **Built by your colleagues** on the Apps page in Teams. È possibile bloccare o consentire collettivamente tutte le app create in Power Apps [](manage-apps.md) o tutte le app create in agenti virtuali di Power a livello dell'organizzazione nella pagina Gestisci app o per utenti specifici che usano criteri di autorizzazione per le [app.](teams-app-permission-policies.md)

Le **app power apps** condivise e le app di Power Virtual Agent **condivise** nell'app store dell'organizzazione rappresentano tutte le app create in quella specifica piattaforma. Se si blocca una o entrambe queste app a livello dell'organizzazione o per utenti specifici, tali utenti non possono vedere alcuna app da queste piattaforme in Built **by your colleagues** e non possono installarle in Teams.  

Tenere presente che è possibile controllare l'accesso a tutte le app create in Power Apps e in agenti virtuali di power, ma non è possibile consentire o bloccare singole app. I produttori decidono chi può accedere alle app create tramite la funzionalità di condivisione da Power Apps e dagli agenti virtuali di Power. Se un produttore ha condiviso un'app che ha creato in Agenti virtuali di Power con un utente e sono state bloccate le app di agenti virtuali di **Power per** tale utente, l'utente non sarà in grado di vedere o installare le app da questa piattaforma in Teams.

Se un utente è autorizzato ad accedere alle app da Power Apps o da agenti virtuali di Power e quindi si blocca l'accesso alle app da una o entrambe le piattaforme, l'utente può comunque accedere e usare le app per piattaforme Microsoft Power installate prima che l'app o le app siano bloccate. Tuttavia, l'utente non può più visualizzare o installare app da queste piattaforme in modalità creata **dai colleghi.**

> [!NOTE]
> **L'impostazione Consenti interazione con** le app [](manage-apps.md) personalizzate a livello di organizzazione nella pagina Gestisci app si applica a tutti gli utenti dell'organizzazione e determina se possono interagire con le app personalizzate. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. Per impostazione predefinita, questa impostazione è attivata. Se questa impostazione è disattivata, gli utenti dell'organizzazione non possono vedere o installare app personalizzate, incluse le app della piattaforma Microsoft Power Platform. Per altre informazioni, vedere [Gestire le impostazioni delle app a livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Consentire o bloccare le app della piattaforma Microsoft Power Platform per l'organizzazione

Per impostazione predefinita, **le app di Power Apps** condivise e le app dell'agente virtuale di Power Virtual **Agent** condivise sono consentite a tutti gli utenti di Teams nell'organizzazione. È possibile bloccarli o consentirli a livello di organizzazione nella pagina Gestisci [app](manage-apps.md) dell'interfaccia di amministrazione di Microsoft Teams.  

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams. È necessario essere un amministratore globale o un amministratore dei servizi di Teams per accedere alla pagina.
2. Nell'elenco delle app eseguire una delle operazioni seguenti.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot della pagina Gestisci app con le app condivise della piattaforma Microsoft Power":::

    - Per bloccare le app create in Power Apps o in agenti virtuali di Power per tutti gli utenti dell'organizzazione, cercare app Power **Apps** condivise o app per l'agente virtuale di Power **Server** condivise, selezionarle e quindi fare clic su **Blocca.**
    - Per consentire le app create in Power Apps o in agenti virtuali di Power per tutti gli utenti dell'organizzazione, cercare le app Power **Apps** condivise o le app per l'agente virtuale di Power **Virtuale** condivise, selezionarle e quindi fare clic su **Consenti.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Consentire o bloccare le app della piattaforma Microsoft Power Platform per utenti specifici

Per consentire o impedire a utenti specifici dell'organizzazione di accedere alle app create in Power Apps o in agenti virtuali di Power, creare e assegnare uno o più criteri di autorizzazione [per le app personalizzati.](teams-app-permission-policies.md) 

Ad esempio, per impedire a utenti specifici di accedere ad app create in Power Apps, creare criteri di autorizzazione app personalizzati per bloccare le app power condivise **e** quindi assegnare i criteri a tali utenti.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot di esempio di criteri di autorizzazione per le app personalizzati con App power condivise bloccate":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usare i log di controllo per analizzare l'attività di installazione di Microsoft Power Platform

È possibile usare i log di controllo per Teams per  esaminare gli eventi in cui gli utenti hanno installato le app di Microsoft Power Platform dalla sezione Creata dai colleghi della pagina App in Teams. A questo scopo, [cercare un](https://docs.microsoft.com/microsoftteams/audit-log-events) utente o un set di utenti nel log di controllo per l'evento di Teams **dell'app** installata (nell'operazione **AppInstalled).** Per trovare le app installate **da Built by your colleagues,** cercare il valore **TemplatedInstance** nella proprietà **AppDistributionMode** nei dettagli di un determinato record. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot del valore TemplatedInstance nella proprietà AppDistributionMode":::

> [!NOTE]
> È possibile esportare i record di controllo in formato CSV per filtrare più facilmente.

## <a name="related-topics"></a>Argomenti correlati

- [Condividere un'app canvas in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Condividere il bot con altri utenti](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Pubblicare un'app personalizzata inviata tramite l'API di invio delle app di Teams](submit-approve-custom-apps.md)
