---
title: Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire le app di Teams. Informazioni su come consentire o bloccare le app, controllare lo stato a livello di organizzazione e le proprietà dell'app, caricare app personalizzate e gestire le impostazioni delle app.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: beaa10343570624b6ce9b01dbaf9f4a0e962b191
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486881"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gestire le app di Teams nell'interfaccia di amministrazione di Microsoft Teams

È possibile gestire le app per l'organizzazione nella pagina **App di Teams** dell'interfaccia di amministrazione di Microsoft Teams. Usare la pagina Gestisci app per visualizzare e gestire tutte le app di Teams nel catalogo app dell'organizzazione, soddisfare casi d'uso importanti per la gestione delle app, definire l'accesso alle app usando i criteri e altro ancora.

:::image type="content" source="media/manage-apps.png" alt-text="Screenshot della pagina Gestisci app." lightbox="media/manage-apps.png":::

Per gestire le app, usare i criteri per controllare le autorizzazioni per gli utenti, l'installazione delle app e il caricamento di app personalizzate create all'interno dell'organizzazione. Per informazioni sui criteri, vedere [Panoramica dei criteri delle app](app-policies.md).

Per usare l'interfaccia di amministrazione di Teams, è necessario avere un ruolo di Amministrazione globale o Amministratore di Teams. Per informazioni dettagliate, vedere [Ruoli di amministratore di Teams](./using-admin-roles.md) e [Ruoli di amministratore di Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La pagina Gestisci app non è disponibile nelle distribuzioni Microsoft 365 Government Community Cloud High (GCCH) o DoD (Department of Defense) di Teams.

Durante la creazione di un'app, gli sviluppatori creano e aggiungono un ID app al file manifesto. È possibile visualizzare questo ID dell'app esterna nella pagina Gestisci app dopo aver abilitato la colonna `External app ID` dalle impostazioni della colonna. È anche possibile visualizzarlo nella pagina dei dettagli dell'app di un'app personalizzata. L'ID è applicabile solo per le app personalizzate.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casi d'uso per la gestione delle app e le interfacce disponibili

Le opzioni per eseguire la maggior parte dei casi di utilizzo di gestione delle app sono disponibili nell'interfaccia di amministrazione di Teams. Inoltre, alcune opzioni sono disponibili in altri portali o in pagine diverse dell'interfaccia di amministrazione di Teams.

Le attività di gestione delle app supportate nell'interfaccia di amministrazione sono riportate nella tabella seguente.

| Casi d'uso per la gestione delle app | Collegamento all'interfaccia | Documentazione |
|:----|:----|:----|
| Controllare quali app sono disponibili per gli utenti dell'organizzazione consentendo e bloccando le app. È anche possibile caricare e approvare app personalizzate. Dopo aver gestito le app in questa pagina, è possibile usare i criteri di autorizzazione e di configurazione delle app per configurare le app disponibili per utenti specifici nell'app store dell'organizzazione. | [Gestire le app nell'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Articolo corrente |
| I criteri di autorizzazione delle app controllano le app che si vogliono rendere disponibili agli utenti di Teams nell'organizzazione. È possibile usare il criterio globale predefinito a livello di organizzazione e personalizzarlo oppure creare uno o più criteri per soddisfare le esigenze dell’organizzazione. | [Criteri di autorizzazione](https://admin.teams.microsoft.com/policies/app-permission) | [Gestire i criteri di autorizzazione delle app](teams-app-permission-policies.md) |
| I criteri di configurazione delle app controllano il modo in cui le app vengono rese disponibili a un utente con l'app Teams. Usare i criteri globali (predefiniti a livello di organizzazione) e personalizzarli o creare criteri personalizzati e assegnarli a un set di utenti. | [Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup) | [Gestire i criteri di configurazione delle app](teams-app-setup-policies.md) |
| È possibile sviluppare e caricare app personalizzate come pacchetti di app e renderle disponibili nell'app store dell'organizzazione. | Impostazioni delle app a livello di organizzazione in [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) | [Gestire i criteri delle app personalizzate](teams-custom-app-policies-and-settings.md) |
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

Nella pagina Gestisci app è possibile consentire o bloccare singole app a livello di organizzazione. Nella pagina vengono visualizzate tutte le app disponibili e lo stato corrente dell'app a livello di organizzazione. L'elenco delle app include le app fornite da Microsoft, dagli sviluppatori di terze parti e dagli sviluppatori all'interno dell'organizzazione.

Per consentire o bloccare un'app:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **app** >  Teams **[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Selezionare un'app dall'elenco delle app. È possibile eseguire una ricerca in base al nome dell'app.
1. Selezionare l'opzione **Consenti** o **Blocca**.

Quando si consente (o si blocca) un'app nella pagina [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) nell'interfaccia di amministrazione di Teams, l'app specifica viene consentita (o bloccata) per tutti gli utenti dell'organizzazione. Questo metodo è diverso dai criteri di autorizzazione dell'app nel contesto in cui l'abilitazione (o il blocco) di un'app tramite criteri di autorizzazione influisce solo sugli utenti specifici a cui sono assegnati i criteri.

Un utente può installare e usare un'app solo quando l'app è consentita tramite l'impostazione a livello di tenant e consentita per l'utente tramite criteri di autorizzazione.

## <a name="manage-user-requests-to-allow-apps"></a>Gestire le richieste degli utenti di consentire le app

Gli utenti finali possono visualizzare, ma non usare, le app bloccate nel Teams Store. Per le app bloccate, è disponibile un'opzione per richiedere l'approvazione dell'amministratore. Queste richieste vengono fascicolate nell'interfaccia di amministrazione di Teams e gli amministratori possono visualizzarle e gestirle quando desiderano. È consigliabile effettuare una valutazione regolare per verificare la presenza di richieste da parte dell'utente finale.

  :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Richiedere all'amministratore di approvare un'app bloccata selezionando l'opzione di approvazione della richiesta nel Teams Store.":::

### <a name="view-a-request"></a>Visualizzare una richiesta

 1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **app** > **[di Teams Per gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

    :::image type="content" source="media/requested-apps1.png" alt-text="Le richieste degli utenti finali per le app bloccate vengono visualizzate nell'interfaccia di amministrazione di Teams nella colonna intitolata Richieste degli utenti." lightbox="media/requested-apps.png":::

 1. Per visualizzare e controllare il numero di richieste per ogni app, ordinare le richieste nella colonna **Richieste dell’utente**. Non è possibile visualizzare il nome degli utenti che hanno richiesto un'app.
 1. Per consentire un'app, seleziona il nome dell'app e aprire la pagina dei dettagli dell'app.
 1. Selezionare **Gestisci richieste** e completare i passaggi visualizzati nella finestra di dialogo popup. In base al metodo usato per bloccare un'app, per sbloccarla sono necessari uno o più dei passaggi seguenti:

    * Se l'app è stata bloccata tramite criteri di autorizzazione, consentire l'app modificando i [criteri di autorizzazione](teams-app-permission-policies.md).
    * Se l'app è stata bloccata per tutti gli utenti, [consentire l'app](#allow-and-block-apps).
    * Se tutte le app sono state bloccate per tutti gli utenti, modificare le [impostazioni a livello di organizzazione](#manage-org-wide-app-settings).

 Se un amministratore consente un'app, Teams non informa l'utente finale che la sua richiesta è stata presa in carico. L'utente può visualizzare l'app nel Teams Store per verificare se può o meno aggiungere l'app al client di Teams. Se l'app viene approvata da un amministratore, gli utenti possono aggiungerla. In alternativa, se l'amministratore non approva la richiesta e la ignora, gli utenti finali possono richiederla di nuovo.

### <a name="dismiss-a-user-request"></a>Ignorare una richiesta utente

 1. Selezionare il nome dell'app per cui si desidera ignorare le richieste dell'utente.
 1. Selezionare **Gestisci richieste** e quindi **Ignora tutte le richieste** nella finestra di dialogo.
 1. Quando una richiesta viene ignorata, le richieste dell'utente vengono azzerate.

  :::image type="content" source="media/reject.png" alt-text="Gli amministratori possono approvare una richiesta dell'utente consentendo un'app o ignorando la richiesta e non intraprendendo alcuna azione.":::

Se un amministratore rifiuta una richiesta, non informa l'utente finale che la sua richiesta è stata presa in carico. Dopo che un amministratore ha ignorato una richiesta, l'utente finale può richiedere di nuovo l'app.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Consentire le app bloccate dagli sviluppatori

Quando uno sviluppatore pubblica un'app nel Teams Store, può essere necessario che gli amministratori configurino l'app. Gli amministratori rendono l'app disponibile agli utenti finali quando l'app è configurata.

Ad esempio, Contoso Electronics è uno sviluppatore di app che ha creato un'app help desk per Microsoft Teams. Contoso Electronics vuole che i clienti configurino alcune proprietà dell'app in modo che, quando interagiscono con l'app, funzioni come previsto. Prima che un amministratore consenta l'applicazione, questa verrà visualizzata come **Bloccata dall'editore** nell'interfaccia di amministrazione di Teams e verrà nascosta agli utenti finali per impostazione predefinita. Dopo aver seguito le indicazioni dell'autore per configurare l'app, è possibile renderla disponibile agli utenti impostando lo stato su **Consentito**.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Screenshot dello stato Bloccato dall'autore nell'interfaccia di amministrazione di Teams.":::

Per informazioni su come gli sviluppatori possono bloccare un'app per impostazione predefinita, vedere [Nascondere l'app finché l'amministratore non l'approva](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves).

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni dell'app a livello di organizzazione

Usare le impostazioni delle app a livello di organizzazione per controllare se gli utenti con una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza personalizzata per le app in prima linea, se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con le app personalizzate nell'organizzazione. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti.

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

1. In **App personalizzate**, disattivare o attivare **Consentire interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [Gestisci criteri e impostazioni app personalizzate in Teams](teams-custom-app-policies-and-settings.md).
1. Selezionare **Salvare** per le impostazioni dell'app a livello di organizzazione per avere effetto.

## <a name="related-article"></a>Articolo correlato

* [Gestire Teams durante la transizione dall’interfaccia di amministrazione di Skype for Business](manage-teams-skypeforbusiness-admin-center.md)
