---
title: Gestire i criteri di configurazione delle app in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come creare, modificare e gestire i criteri di configurazione delle app per aggiungere app, installare le app e consentire agli utenti di caricare app personalizzate.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b9dfe2ad2598e47175a0af433c0febac17255c09
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912465"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>Usare i criteri di configurazione delle app per aggiungere e installare automaticamente le app in Teams

Gli amministratori usano i criteri di configurazione delle app per installare e aggiungere app e controllare quali utenti specifici possono caricare app personalizzate. L'aggiunta consente di promuovere l'adozione e fornire un accesso rapido alle app pertinenti nell'organizzazione.

* **[Aggiungere app](#pin-apps):** I criteri di configurazione delle app consentono di scegliere le app da aggiungere, impostare l'ordine di visualizzazione delle app per gli utenti nella barra dell'app Teams o nell'area di composizione dei messaggi. Gli amministratori possono anche controllare se gli utenti finali possono aggiungere o meno le proprie app.

* **[Installa app](#install-apps):** I criteri di configurazione delle app consentono di installare le app consentite per conto degli utenti quando avviano Teams e durante le riunioni.

* **Caricare app personalizzate:** I criteri di configurazione delle app consentono di controllare quali utenti possono caricare app personalizzate in Teams. Vedere [l'articolo Caricare app personalizzate](teams-custom-app-policies-and-settings.md) .

Per impostazione predefinita, nell’interfaccia di amministrazione di Microsoft Teams sono disponibili i seguenti criteri di configurazione delle app integrati:

* **Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare i criteri globali per aggiungere le app più importanti per gli utenti.

* **FirstlineWorker**: questo criterio è per il ruolo di lavoro in prima linea. Impossibile personalizzare i criteri. È possibile assegnarlo ai ruoli di lavoro in prima linea nell'organizzazione.

## <a name="pin-apps"></a>Aggiungere app

Aggiungendo un'app, l'app viene visualizzata nella barra dell'app nel client di Teams. Gli amministratori possono aggiungere l'app e consentire agli utenti di aggiungerla. L'aggiunta viene usata per evidenziare le app più necessarie agli utenti e promuovere la facilità di accesso. L'aggiunta funziona per tutti i [tipi di app in Teams](deploy-apps-microsoft-teams-landing-page.md) : app di base, app fornite da Microsoft, app di terze parti e app personalizzate sviluppate all'interno dell'organizzazione.

Gli amministratori possono aggiungere un'app tramite un criterio di configurazione dell'app. Le app aggiunte dagli amministratori vengono installate automaticamente per gli utenti per cui è consentita l'app. Tale app non può essere disinstallata dagli utenti finali. Usando un criterio di configurazione dell'app, è possibile eseguire le attività seguenti:

* Personalizza Teams per gli utenti finali per evidenziare le app più importanti per loro. È possibile scegliere le app da appuntare e l'ordine di visualizzazione delle app.
* Controllare se gli utenti possono appuntare le app o meno.

Le app vengono appuntate nella barra delle app sul lato sinistro del client desktop di Teams e nella parte inferiore dei client mobili di Teams. Le estensioni di messaggistica sono disponibili nella parte inferiore dell'area di composizione dei messaggi.

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Screenshot che mostra la barra dell'app nel client desktop di Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Screenshot che mostra la barra dell'app nel client mobile di Teams.](media/mobile-app-ui.png)      |

Per aggiungere app usando un criterio di configurazione delle app, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selezionare **Aggiungi**.

1. Immettere un nome e una descrizione per il criterio.

1. Facoltativamente, attiva **Blocco utente** per consentire agli utenti di aggiungere app e modificare l'ordine delle app aggiunte.

1. In **App aggiunte** selezionare **Aggiungi app**.

1. Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi**.

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="Screenshot che mostra come aggiungere app aggiunte nei criteri di configurazione delle app." lightbox="media/add-pinned-apps-large.png":::

1. Selezionare **Aggiungi**.

1. Sotto la **barra dell'app** o le **estensioni messaggi**, disponi le app nell'ordine in cui vuoi che vengano visualizzate nel client di Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Screenshot delle app aggiunte e delle estensioni messaggi aggiunte nei criteri di configurazione.":::

1. Selezionare **Salva**.

> [!NOTE]
> In Teams per l'istruzione, l'app Assegnazioni viene aggiunta per impostazione predefinita nei criteri globali anche se non viene visualizzata nell'elenco dei criteri globali.

> [!NOTE]
> Per i lavoratori in prima linea della tua organizzazione, ti consigliamo di utilizzare l'esperienza dell'app Frontline su misura. Questa funzionalità aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline). Per altre informazioni, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Installare le app

Utilizzando un criterio di impostazione delle applicazioni, un amministratore può eseguire le seguenti operazioni:

* Installare le applicazioni per gli utenti finali nel loro ambiente personale di Teams.
* Installare le app per gli utenti finali come [estensioni di messaggistica](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Gli utenti finali possono installare le app autonomamente se i [criteri di autorizzazione](teams-app-permission-policies.md) consentono di installarle e l'app è consentita dall'amministratore di Teams. Se un'app è bloccata, gli utenti finali possono [richiedere l'approvazione dell'amministratore](user-requests-approve-apps.md).

Per installare le app usando un criterio di configurazione dell'app, procedere come segue:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selezionare **Aggiungi**.

1. Specificare un nome e una descrizione per il criterio.

1. In **App installate** selezionare **Aggiungi app**.

1. Nel riquadro **Aggiungi app installate** cercare gli utenti nelle app che si desidera installare. È anche possibile filtrare le app in base ai criteri di autorizzazione delle app.

1. Selezionare **Aggiungi**.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="Screenshot dell'installazione delle app tramite i criteri dell'app.":::

## <a name="manage-app-setup-policies"></a>Gestire i criteri di configurazione delle app

I criteri di configurazione delle app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Usare i criteri globali (predefiniti a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti finali ottengono i criteri globali. Se si crea un criterio personalizzato, questo sostituisce il criterio globale. L'amministratore globale o l'amministratore del servizio Teams possono gestire questi criteri.

È possibile modificare le impostazioni nei criteri globali per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti nell'organizzazione, creare e assegnare uno o più criteri personalizzati.

:::image type="content" source="media/app-setup-policies-update.png" alt-text="Screenshot che mostra la pagina dei criteri di configurazione delle app con le opzioni per gestire i criteri o aggiungere nuovi criteri.":::

### <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione di un'app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (predefiniti a livello di organizzazione) e i criteri personalizzati creati. La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Scegliere il criterio da modificare e quindi selezionare **Modifica**.

1. Apportare le modifiche desiderate.

1. Selezionare **Salva**.

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>Assegnare criteri personalizzati nei criteri di configurazione delle app a utenti e gruppi

Per sapere come assegnare criteri agli utenti finali e ai gruppi, vedere [come assegnare criteri a utenti e gruppi](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Considerazioni e limitazioni

* Non è possibile installare app personalizzate con schede configurabili usando i criteri di installazione delle app.

* Gli utenti finali non possono disinstallare un'app installata da un amministratore.

* Gli utenti finali possono rimuovere un'app aggiunta tramite i criteri di configurazione dell'app se l'aggiunta dell'utente è consentita nel criterio.

* Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e mobili di Teams se l'opzione di aggiunta dell'utente è attivata. Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di Teams.

* I pin di amministratore hanno sempre la precedenza. Se l'opzione Blocco utente è attivata, le app aggiunte dagli utenti vengono visualizzate sotto le app aggiunte dagli amministratori. Se l'opzione di aggiunta dell'utente è disattivata, gli utenti perdono i pin esistenti e nella barra dell'app sono disponibili solo le app aggiunte dagli amministratori.

* L'impostazione di aggiunta dell'utente è disponibile nell'interfaccia di amministrazione di Teams negli ambienti Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High e DoD), ma non ha alcun effetto.

* In Teams per l'istruzione, l'app Assegnazioni viene aggiunta per impostazione predefinita nei criteri globali anche se non viene visualizzata nell'elenco dei criteri globali.

* Non è previsto alcun limite al numero massimo di app aggiunte che è possibile aggiungere a un criterio. Tuttavia, almeno due app devono essere aggiunte ai client mobili di Teams (iOS e Android). Se un criterio ha meno di due app, i client per dispositivi mobili non rifletteranno le impostazioni dei criteri e continueranno a usare la configurazione esistente.

* La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

* Non tutte le app possono essere appuntate su Teams tramite un criterio di impostazione delle app. Alcune applicazioni potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cercare l'app nel riquadro **Aggiungi app aggiunte**. Le schede con ambito personale (schede statiche) e bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte**. Mentre nell'App Store di Teams sono elencate tutte le app di Teams. Il riquadro **Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.

* In Teams per l'istruzione, l'app Chiamate non è disponibile. Quando crei un nuovo criterio personalizzato nei criteri di configurazione delle app, l'app Chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non è inserita nei client di Teams e gli utenti di Teams for Education non vedranno l'app Calls in Teams.

## <a name="related-articles"></a>Articoli correlati

* [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
* [Assegnare criteri agli utenti finali in Teams](assign-policies-users-and-groups.md)
