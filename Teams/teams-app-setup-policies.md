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
ms.openlocfilehash: c741bb8a1b6ab7e27ec064dc0f22226f69bc6e10
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655892"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

Gli amministratori usano i criteri di configurazione delle app per installare e aggiungere app e consentire agli utenti di caricare app personalizzate. L'aggiunta consente di promuovere l'adozione di app pertinenti nell'organizzazione.

* **Aggiungi app:** i criteri di impostazione delle app consentono di scegliere le app da appuntare e di impostare l'ordine di visualizzazione delle app per gli utenti nella barra delle app di Teams o nell'area di composizione dei messaggi. Gli amministratori possono anche controllare se gli utenti finali possono aggiungere o meno le proprie app. Vedi [Aggiungi app](#pin-apps).
* **Installare le app:** i criteri di impostazione delle app consentono di installare le app consentite per conto degli utenti all'avvio di Teams e durante le riunioni. Per altre informazioni, vedere [Installare le app](#install-apps).
* **Caricare app personalizzate:** i criteri di configurazione delle app consentono agli utenti di caricare app personalizzate in Teams. Per altre informazioni, vedere [Caricare app personalizzate](teams-custom-app-policies-and-settings.md).

Per impostazione predefinita, nell’interfaccia di amministrazione di Microsoft Teams sono disponibili i seguenti criteri di configurazione delle app integrati:

* **Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare i criteri globali per aggiungere le app più importanti per gli utenti.

* **FirstlineWorker**: questo criterio è per il ruolo di lavoro in prima linea. Impossibile personalizzare i criteri. È possibile assegnarlo ai ruoli di lavoro in prima linea nell'organizzazione.

## <a name="pin-apps"></a>Aggiungere app

L'aggiunta di app consente di evidenziare le app di cui gli utenti dell'organizzazione hanno più bisogno. L'aggiunta funziona per tutti i tipi di app in Teams: app di base, app fornite da Microsoft, app di terze parti e personalizzate sviluppate all'interno dell'organizzazione. L’aggiunta di un'applicazione tramite un criterio di impostazione delle applicazioni la installa anche, se l'applicazione è consentita all'utente. Usando un criterio di configurazione dell'app, è possibile eseguire le attività seguenti:

* Personalizzare Microsoft Teams per gli utenti finali per evidenziare le app più importanti per loro. È possibile scegliere le app da appuntare e l'ordine di visualizzazione delle app.
* Controllare se gli utenti possono appuntare le app o meno.

Le app vengono appuntate nella barra delle app sul lato sinistro del client desktop di Teams e nella parte inferiore dei client mobili di Teams.

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Screenshot che mostra la barra dell'app nel client desktop di Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Screenshot che mostra la barra dell'app nel client mobile di Teams.](media/mobile-app-ui.png)      |

Le estensioni di messaggistica sono disponibili nella parte inferiore dell'area di composizione dei messaggi.

Per aggiungere app usando un criterio di configurazione delle app, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selezionare **Aggiungi**.

1. Immettere un nome e una descrizione per il criterio.

1. Attiva l’**Aggiunta dell'utente**.

   > [!NOTE]
   > **L'impostazione di aggiunta utente** è disponibile nell'interfaccia di amministrazione di Teams negli ambienti Microsoft 365 Government Community Cloud (GCC, GCC High e DoD), ma non ha alcun effetto.

1. In **App aggiunte** selezionare **Aggiungi app**.

1. Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi**. È anche possibile filtrare le app in base ai criteri di autorizzazione delle app.

1. Selezionare **Aggiungi**.

1. Nella **Barra dell'app** o nelle **Estensioni di messaggistica**, disporre le app nell'ordine in cui devono essere visualizzate in Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Uno screenshot delle app appuntate e delle estensioni di messaggistica appuntate nei criteri di configurazione.":::

1. Selezionare **Salva**.

> [!NOTE]
> In Teams per l'istruzione, l'app Assegnazioni viene aggiunta per impostazione predefinita nei criteri globali anche se non viene visualizzata nell'elenco dei criteri globali.

> [!NOTE]
> Per i lavoratori in prima linea della tua organizzazione, ti consigliamo di utilizzare l'esperienza dell'app Frontline su misura. Questa funzionalità aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Per altre informazioni, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Installare le app

Utilizzando un criterio di impostazione delle applicazioni, un amministratore può eseguire le seguenti operazioni:

* Installare le applicazioni per gli utenti finali nel loro ambiente personale di Teams.
* Installare le app per gli utenti finali come [estensioni di messaggistica](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Gli utenti finali possono installare le app autonomamente se il [criterio di autorizzazione dell'app](teams-app-permission-policies.md) lo consente e l'app è consentita dall'amministratore di Teams. Se invece un'app viene bloccata per un utente o per un'organizzazione, gli utenti finali possono [richiedere l'approvazione dell'amministratore](user-requests-approve-apps.md).

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
* Le app aggiunte tramite i criteri di configurazione delle app possono essere sbloccate dall'utente (se l'aggiunta dell'utente è consentita nei criteri di configurazione).
* In Teams per l'istruzione, l'app Assegnazioni viene aggiunta per impostazione predefinita nei criteri globali anche se non viene visualizzata nell'elenco dei criteri globali.
* Non è previsto alcun limite al numero massimo di app aggiunte che è possibile aggiungere a un criterio. Tuttavia, almeno due app devono essere aggiunte ai client mobili di Teams (iOS e Android). Se un criterio ha meno di due app, i client per dispositivi mobili non rifletteranno le impostazioni dei criteri e continueranno a usare la configurazione esistente.
* La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

## <a name="faqs"></a>Domande frequenti

### <a name="working-with-app-setup-policies"></a>Uso dei criteri di configurazione delle app

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non riesco a trovare un'applicazione nel riquadro Aggiungi applicazioni appuntate

Non tutte le app possono essere appuntate su Teams tramite un criterio di impostazione delle app. Alcune applicazioni potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cercare l'app nel riquadro **Aggiungi app aggiunte**. Le schede con ambito personale (schede statiche) e bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte**.

Tenere presente che l'App Store di Teams elenca tutte le app di Teams. Il riquadro **Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un amministratore di Teams for Education. Cosa devo sapere sui criteri di configurazione delle app in Teams for Education?

L'app Chiamata non è disponibile in Teams for Education. Quando crei un nuovo criterio personalizzato nei criteri di configurazione delle app, l'app Chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non è inserita nei client di Teams e gli utenti di Teams for Education non vedranno l'app Calls in Teams.

### <a name="user-experience"></a>Esperienza utente

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Come possono gli utenti vedere tutte le loro app aggiunte in Teams?

Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le seguenti operazioni, a seconda del numero di app installate e delle dimensioni della finestra del client Teams.

|Client desktop di Teams |Client per dispositivi mobili di Teams |
|---------|---------|
|Nella barra dell'app sul lato di Teams seleziona **... Altre app**.| Nella barra delle app vicino alla parte inferiore di Teams, scorrere verso l'alto.|
|![Screenshot che mostra altre app aggiunte nel client desktop di Teams.](media/app-setup-policies-desktop-more-apps.png)   |![Screenshot che mostra altre app aggiunte nel client mobile di Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Cosa devo sapere sull'esperienza per dispositivi mobili di Teams

I client per dispositivi mobili di Teams (iOS e Android) supportano le app personali con schede statiche. Le app aggiunte al client desktop di Teams verranno visualizzate nei client per dispositivi mobili di Teams. I bot personali verranno visualizzati nella chat nei client per dispositivi mobili.

Le app di terze parti (che possono essere scaricate da Teams Store) devono essere approvate prima di essere visualizzate nei dispositivi mobili. Se un amministratore aggiunge un'app, che non è approvata da Microsoft per dispositivi mobili, verrà visualizzata sul desktop di Teams, ma non su dispositivi mobili. Per altre informazioni, vedere [Clienti dispositivi mobili](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Con i client mobili di Teams, gli utenti vedranno le app principali di Teams, come Attività, Chat e Teams, e puoi aggiungere alcune app fornite da Microsoft.

#### <a name="order-of-apps-pinned-through-a-policy"></a>Ordine delle app aggiunte tramite un criterio

Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e per dispositivi mobili di Teams se l'opzione di **aggiunta utente** è attivata. Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di Teams.

#### <a name="does-user-pinning-take-precedence"></a>L'aggiunta dell'utente ha la precedenza

I pin di amministratore hanno sempre la precedenza. Se l'opzione **Blocco utente** è attivata, le app aggiunte dagli utenti vengono visualizzate sotto le app aggiunte dagli amministratori. Se **l'opzione di aggiunta** dell'utente è disattivata, gli utenti perdono i pin esistenti e nella barra dell'app sono disponibili solo le app aggiunte dagli amministratori.

### <a name="custom-teams-apps"></a>App di Teams personalizzate

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>La mia organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata su AppSource o sul catalogo delle app del tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene appuntata sulla barra delle app in Teams. Come si risolve il problema?

Assicurarsi di seguire le linee guida sul logo prima di inviare l'applicazione. Per altre informazioni, vedi [Elenco di controllo per l'invio del Dashboard venditori](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Articoli correlati

* [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
* [Assegnare criteri agli utenti finali in Teams](assign-policies-users-and-groups.md)
