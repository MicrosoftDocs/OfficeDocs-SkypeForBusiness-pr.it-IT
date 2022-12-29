---
title: Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.reviewer: kojika
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire le app di Teams. Informazioni su come consentire o bloccare le app, controllare lo stato a livello di organizzazione e le proprietà dell'app, caricare app personalizzate e gestire le impostazioni delle app.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: c88f8c4424cb82ea1482c5f6e1b90fd792279450
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677406"
---
# <a name="overview-of-app-management-and-governance-in-teams-admin-center"></a>Panoramica della gestione e della governance delle app nell'interfaccia di amministrazione di Teams

È possibile gestire le app per l'organizzazione nella pagina **App di Teams** dell'interfaccia di amministrazione di Microsoft Teams. Usare la pagina Gestisci app per visualizzare e gestire tutte le app di Teams nel catalogo app dell'organizzazione, soddisfare casi d'uso importanti per la gestione delle app, definire l'accesso alle app usando i criteri e altro ancora.

:::image type="content" source="media/manage-apps.png" alt-text="Screenshot della pagina Gestisci app." lightbox="media/manage-apps.png":::

Per gestire le app, usare i criteri per controllare le autorizzazioni per gli utenti, l'installazione delle app e il caricamento di app personalizzate create all'interno dell'organizzazione. Per informazioni sui criteri, vedere [Panoramica dei criteri delle app](app-policies.md).

Per usare l'interfaccia di amministrazione di Teams, è necessario avere un ruolo di Amministrazione globale o Amministratore di Teams. Per informazioni dettagliate, vedere [Ruoli di amministratore di Teams](./using-admin-roles.md) e [Ruoli di amministratore di Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La pagina Gestisci app non è disponibile nelle distribuzioni Microsoft 365 Government Community Cloud High (GCCH) o DoD (Department of Defense) di Teams.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casi d'uso per la gestione delle app e le interfacce disponibili

Le opzioni per eseguire la maggior parte dei casi di utilizzo di gestione delle app sono disponibili nell'interfaccia di amministrazione di Teams. Inoltre, alcune opzioni sono disponibili in altri portali o in pagine diverse dell'interfaccia di amministrazione di Teams.

Le attività di gestione delle app supportate nell'interfaccia di amministrazione sono riportate nella tabella seguente.

| Casi d'uso per la gestione delle app | Collegamento all'interfaccia | Documentazione |
|:----|:----|:----|
| Controllare quali app sono disponibili per gli utenti dell'organizzazione consentendo e bloccando le app. È anche possibile caricare e approvare app personalizzate. Dopo aver gestito le app in questa pagina, è possibile usare i criteri di autorizzazione e di configurazione delle app per configurare le app disponibili per utenti specifici nell'app store dell'organizzazione. | [Gestire le app nell'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Articolo corrente |
| I criteri di autorizzazione delle app controllano le app che si vogliono rendere disponibili agli utenti di Teams nell'organizzazione. È possibile usare il criterio globale predefinito a livello di organizzazione e personalizzarlo oppure creare uno o più criteri per soddisfare le esigenze dell’organizzazione. | [Criteri di autorizzazione](https://admin.teams.microsoft.com/policies/app-permission) | [Gestire i criteri di autorizzazione delle app](teams-app-permission-policies.md) |
| I criteri di configurazione delle app controllano il modo in cui le app vengono rese disponibili a un utente con l'app Teams. Usare i criteri globali (predefiniti a livello di organizzazione) e personalizzarli o creare criteri personalizzati e assegnarli a un set di utenti. | [Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup) | [Gestire i criteri di configurazione delle app](teams-app-setup-policies.md) |
| È possibile sviluppare e caricare app personalizzate come pacchetti di app e renderle disponibili nell'app store dell'organizzazione. | Impostazioni delle app a livello di organizzazione in [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) | [Gestire l'impostazione dei criteri per le app personalizzate](teams-custom-app-policies-and-settings.md) |
| È possibile personalizzare l'app store di Teams con il logo, lo sfondo o il colore dell'organizzazione. | [Personalizzare lo Store](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personalizzare l'app store dell'organizzazione](customize-your-app-store.md) |
| Il report Utilizzo app Teams fornisce informazioni sulle app in uso, gli utenti attivi e altre informazioni sull'utilizzo delle app. | [Report sull'uso](https://admin.teams.microsoft.com/analytics/reports) | [Report sull’utilizzo dell’app Teams](teams-analytics-and-reports/app-usage-report.md) |
| Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione. | [Accesso esterno](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportamento dell'app a seconda dei tipi di utenti](non-standard-users.md) |
| Tramite l’accesso guest, è possibile consentire l'accesso alle applicazioni e ad altre funzionalità di Teams a persone esterne all’organizzazione, pur mantenendo il totale controllo dei dati aziendali. | [Accesso guest](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Accesso guest in Teams](guest-access.md) |
| I criteri di aggiornamento di Teams vengono usati per gestire gli utenti di Teams e di Office Preview che possono vedere le funzionalità di anteprima o non rilasciate nell'app Teams. | [Criteri di aggiornamento di Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Anteprima pubblica di Teams](public-preview-doc-updates.md) |

Le attività di gestione delle app supportate in altri portali sono riportate nella tabella seguente.

| Casi d'uso per la gestione delle app | Collegamento all'interfaccia | Documentazione |
|:----|:----|:----|
| Gestire licenze e abbonamenti di app di terze parti nell’interfaccia di amministrazione di Microsoft 365 | [Interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/#/licenses) | [Gestire gli abbonamenti alle app di terze parti](/microsoft-365/commerce/manage-saas-apps) |
| Controllare gli eventi dell'app Teams nel Portale di conformità di Microsoft Purview. | [Audit](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Attività di Teams](audit-app-management-activities.md) |
| Le applicazioni possono essere concesse all'organizzazione e ai relativi dati con tre metodi: un amministratore concede il consenso all'applicazione per tutti gli utenti, un utente concede il consenso all'applicazione o un amministratore integra un'applicazione e abilita l'accesso in modalità self-service o assegna gli utenti direttamente all'applicazione. Verificare le autorizzazioni di Graph per le app. Verificare le autorizzazioni fornite dagli utenti o delegate dagli amministratori. | [Portale di Azure AD](https://aad.portal.azure.com/) | [Rivedere le autorizzazioni concesse alle applicazioni](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Consentire e bloccare le app

Gli amministratori possono controllare l'accesso a tutti i tipi di app che vengono usati in tutto il contesto da tutti gli utenti. Teams fornisce controlli granulari per configurare l'accesso per ogni app e per ogni utente.

Per consentire un'app, è necessario completare tutte le impostazioni seguenti. Per bloccare un'app, bloccala tramite una delle impostazioni seguenti.

* [Impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings): usare questa impostazione per consentire l'uso delle app nell'organizzazione. Decidi quali app specifiche usare.
* [Consenti una singola app](manage-apps.md#allow-and-block-apps): usa questa impostazione per consentire un'app specifica nella tua organizzazione. Decidi quali utenti possono usare l'app.
* [Criteri di autorizzazione](teams-app-permission-policies.md) per le app: usare i criteri per consentire l'uso di un'app a tutti o a utenti specifici. L'accesso viene deciso in base all'utente e all'app.

Nella pagina Gestisci app è possibile consentire o bloccare singole app a livello di organizzazione. Nella pagina vengono visualizzate tutte le app disponibili e lo stato corrente dell'app a livello di organizzazione. Per consentire o bloccare un'app, procedere come segue:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **app** >  Teams **[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Individua un'app e selezionala.
1. Selezionare l'opzione **Consenti** o **Blocca**.

Per consentire un'app per utenti specifici, vedere [Criteri di autorizzazione per le app](teams-app-permission-policies.md).

Quando uno sviluppatore pubblica un'app in Teams Store, per configurare l'app potrebbe essere necessario un amministratore. Prima che un amministratore consenta tale app, viene visualizzata come `Blocked by publisher` nell'interfaccia di amministrazione. Dopo aver seguito le indicazioni dell'autore per configurare l'app, è possibile renderla disponibile agli utenti consentendola.

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni dell'app a livello di organizzazione

Usare le impostazioni delle app a livello di organizzazione per controllare se gli utenti con una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza personalizzata per le app in prima linea, se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con le app personalizzate nell'organizzazione.

> [!NOTE]
> Per informazioni su come usare le impostazioni delle app a livello di organizzazione in Microsoft 365 Government - Government Community Cloud High GCCH e le distribuzioni DoD (Department of Defense) di Teams, vedere [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md).

1. Nella pagina **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)** seleziona **Impostazioni app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel riquadro.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot del riquadro Impostazioni app a livello di organizzazione nella pagina Gestisci app":::

1. In **App personalizzate** disattivare o attivare **Mostra app personalizzate**. Quando questa impostazione è attivata, gli utenti con una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza personalizzata dell'app in prima linea. Questa esperienza consente di individuare le app più importanti in Teams per gli operatori di prima linea. Per altre informazioni, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

    Questa funzionalità è disponibile per le licenze F. Altri tipi di licenze saranno supportati in futuro.
1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    * **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se si disattiva questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app verrà visualizzato come **Bloccato a livello di organizzazione** nella tabella.

        > [!NOTE]
        > Quando l'opzione **Consenti app di terze parti** è disattivata, i [ webhook in uscita](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sono ancora abilitati per tutti gli utenti, ma è possibile controllarli a livello di utente consentendo o bloccando l'app Webhook in uscita tramite [criteri di autorizzazione dell'app](teams-app-permission-policies.md). Se sono presenti [criteri di autorizzazione delle app](teams-app-permission-policies.md) per le **app Microsoft** che usano l'impostazione **Consenti app specifiche e blocca tutte le altre** e si vogliono abilitare i webhook in uscita per gli utenti, aggiungere l'app Webhook in uscita all'elenco.

        > [!NOTE]
        > Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione.

    * **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa impostazione consente di controllare se eventuali nuove app di terze parti pubblicate nello Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App personalizzate**, disattivare o attivare **Consentire interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [Gestire criteri e impostazioni per le app personalizzate](teams-custom-app-policies-and-settings.md).

1. Selezionare **Salva**. Le impostazioni hanno effetto dopo alcune ore.

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gestire impostazioni app a livello di organizzazione per Government di Microsoft 365  

Nell'ambito della distribuzione di Microsoft 365 Government - GCC, GCCH e DoD di Teams, tutte le app di terze parti vengono bloccate per impostazione predefinita. Nei Cloud GCCH e DOD le app di terze parti non sono disponibili. In GCC viene inoltre visualizzata la nota seguente sulla gestione delle app di terze parti nella pagina dei criteri di autorizzazione delle app nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Screenshot dei criteri di autorizzazione app in GCCH e DoD." lightbox="media/app-permission-policies-gcc.png":::

Usare le impostazioni app a livello di organizzazione per controllare se gli utenti possono installare le app di terze parti. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti.

<!---1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. 
--->

### <a name="for-gcc-clouds"></a>Per i Cloud GCC

1. Nella pagina **Gestisci app** **di** >  Teams selezionare **Impostazioni app a livello di organizzazione**. È possibile quindi configurare le impostazioni desiderate nel pannello.

   :::image type="content" source="media/app-permission-policies-gcc-org-wide.png" alt-text="Screenshot che mostra le impostazioni dell'app a livello di organizzazione in GCC.":::

1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    * **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se si disattiva questa impostazione, gli utenti non potranno installare o usare qualsiasi app di terze parti. Nell'ambito della distribuzione di Microsoft 365 Government - GCC, GCCH e DoD di Teams, questa impostazione è disattivata per impostazione predefinita.
    * **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa opzione controlla se eventuali nuove app di terze parti pubblicate nell’App Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App bloccate**, aggiungere le app che si desidera bloccare nell'organizzazione. Nell'ambito della distribuzione di Microsoft 365 Government - GCC, GCCH e DoD di Teams, tutte le app di terze parti vengono aggiunte a questo elenco per impostazione predefinita. Per qualsiasi app di terze parti che si desidera consentire nell'organizzazione, rimuovere l'app da questo elenco delle app bloccate. Quando si blocca un'app a livello di organizzazione, l'app viene bloccata automaticamente per tutti gli utenti, indipendentemente dal fatto che sia consentita da altri criteri di autorizzazione app.

1. Selezionare **Salvare** per le impostazioni dell'app a livello di organizzazione per avere effetto.

Per consentire le app di terze parti, modificare e usare il criterio globale (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri creati dall'amministratore.

### <a name="for-gcch-and-dod-clouds"></a>Per i Cloud GCCH e DoD

1. Accedere all'interfaccia di amministrazione di Teams e accedere ai **criteri di autorizzazione** **per le app** >  di Teams.

1. Seleziona **Impostazioni app a livello di organizzazione**. In **App bloccate**, aggiungere le app che si desidera bloccare nell'organizzazione. Nell'ambito della distribuzione di Microsoft 365 Government - GCC, GCCH e DoD di Teams, tutte le app di terze parti vengono aggiunte a questo elenco per impostazione predefinita. Quando si blocca un'app a livello di organizzazione, l'app viene bloccata automaticamente per tutti gli utenti, indipendentemente dal fatto che sia consentita da altri criteri di autorizzazione app.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Screenshot delle impostazioni app a livello di organizzazione in GCCH e DoD.":::

1. Selezionare **Salvare** per le impostazioni dell'app a livello di organizzazione per avere effetto.

## <a name="related-article"></a>Articolo correlato

* [Gestire le richieste degli utenti per consentire le app](user-requests-approve-apps.md).
