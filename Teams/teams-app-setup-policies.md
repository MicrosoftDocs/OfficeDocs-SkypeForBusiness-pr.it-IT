---
title: Gestire i criteri di configurazione delle app in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di configurazione delle app in Microsoft Teams per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 328f2676ccec6cd1450166d7032877e176d5f1cd
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910822"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

Gli amministratori possono usare i criteri di configurazione delle app per installare e aggiungere app per promuovere le app più usate nell'organizzazione e per decidere se caricare app personalizzate in Teams.

- **Aggiungere app:** I criteri di configurazione delle app consentono di scegliere le app da aggiungere, impostare l'ordine in cui vengono visualizzate per gli utenti nella barra dell'app Teams o nell'area di composizione dei messaggi e controllare se gli utenti possono o meno aggiungere le proprie app. Per altre informazioni, vedi [Aggiungere app](#pin-apps).
- **Installa app:** I criteri di configurazione delle app consentono di installare le app per conto degli utenti quando iniziano Teams e durante le riunioni. Per altre informazioni, vedi [Installare le app](#install-apps).
- **Upload app personalizzate: i** criteri di configurazione delle app consentono agli utenti di caricare app personalizzate in Teams. Per altre informazioni, vedere [Upload app personalizzate](#upload-custom-apps).

## <a name="pin-apps"></a>Aggiungere app

> [!NOTE]
> Per gli operatori in prima linea nell'organizzazione, è consigliabile usare l'esperienza app frontline personalizzata. Questa funzionalità aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Per altre informazioni, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

L'aggiunta di app consente di mostrare le app di cui hanno bisogno gli utenti dell'organizzazione, incluse le app create da terze parti o dagli sviluppatori dell'organizzazione.

Usando i criteri di configurazione delle app, è possibile eseguire le attività seguenti:

- Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegli le app da aggiungere e impostare l'ordine in cui vengono visualizzate.
- Controllare se gli utenti possono aggiungere app a Teams.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato sinistro del client desktop Teams e nella parte inferiore della Teams client mobili (iOS e Android).

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Client desktop Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Client per dispositivi mobili Teams](media/mobile-app-ui.png)      |

Le estensioni di messaggistica sono disponibili nella parte inferiore dell'area di composizione dei messaggi.

> [!NOTE]
> Se hai Teams per l'istruzione, è importante sapere che l'app Attività è stata aggiunta per impostazione predefinita ai criteri globali, anche se attualmente non è elencata nei criteri globali.

Per creare un criterio di configurazione delle app per aggiungere app, procedere come segue:

1. Accedere all [Microsoft Teams interfaccia di amministrazione](https://admin.teams.microsoft.com).

1. Nel riquadro sinistro passare a **Teams app** >  **Criteri di installazione**.

1. Selezionare **Aggiungi**.

1. Immettere un nome e una descrizione per il criterio.

1. Attiva **Blocco utente**.

   > [!NOTE]
   > **L'impostazione Blocco utente** è disponibile nell'interfaccia di amministrazione di Teams in ambienti Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High e DoD), ma attualmente non ha alcun effetto.

1. In **App aggiunte** seleziona **Aggiungi app**.

1. Nel riquadro **Aggiungi app aggiunte** cerca le app che vuoi aggiungere e quindi seleziona **Aggiungi**. Puoi anche filtrare le app in base ai criteri di autorizzazione delle app.

1. Selezionare **Aggiungi**.

1. Nella **barra dell'app** o nelle **estensioni messaggi** disponi le app nell'ordine in cui vuoi che vengano visualizzate in Teams.

   ![sezione App aggiunte.](media/pin-messaging-extensions.png)

1. Selezionare **Salva**.

## <a name="install-apps"></a>Installare app

È possibile scegliere quali app installare per impostazione predefinita per gli utenti nel proprio ambiente di Teams personale, installare le app come [estensioni di messaggistica](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions) e designare le app da installare nelle riunioni.

Usando i criteri di configurazione delle app, è possibile eseguire le attività seguenti:

- Installare le app per gli utenti nel proprio ambiente di Teams personale
- Installare le app per gli utenti come estensioni di messaggistica
- Installare app nelle riunioni per gli organizzatori delle riunioni

> [!NOTE]
> Gli utenti possono comunque installare le app autonomamente se il [criterio di autorizzazione dell'app](teams-app-permission-policies.md) assegnato lo consente.

Per creare un criterio di configurazione delle app per installare le app, procedere come segue:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams app** >  **Criteri di configurazione**.

2. Selezionare **Aggiungi**.

3. Immettere un nome e una descrizione per il criterio.

4. In **App installate** seleziona **Aggiungi app**.

5. Nel riquadro **Aggiungi app installate** cerca le app che vuoi installare automaticamente per gli utenti. Puoi anche filtrare le app in base ai criteri di autorizzazione delle app.

6. Selezionare **Aggiungi**.

![Installa i criteri per le app.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Gli utenti non possono disinstallare le app installate dagli amministratori.

## <a name="upload-custom-apps"></a>Upload app personalizzate

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per creare un criterio personalizzato che consente agli utenti di caricare app personalizzate in Teams.

Per creare criteri di configurazione delle app che consentano agli utenti di caricare app personalizzate in Teams, procedere come segue:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams app** >  **Criteri di configurazione**.

2. Selezionare **Aggiungi**.

3. Immettere un nome e una descrizione per il criterio.

4. Attivare o disattivare **Upload app personalizzate**, a seconda che si voglia consentire agli utenti di caricare app personalizzate in Teams.

> [!NOTE]
> Non puoi modificare questa impostazione se **le app di terze parti** sono disattivate nelle [impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

## <a name="manage-app-setup-policies"></a>Gestire i criteri di configurazione delle app

I criteri di configurazione delle app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati.  Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

È possibile modificare le impostazioni nel criterio globale per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati.

![pagina Criteri di configurazione delle app.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione delle app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (predefiniti a livello di organizzazione) e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams app** >  **Criteri di configurazione**.

2. Scegliere il criterio da modificare e quindi selezionare **Modifica**.

3. Apportare le modifiche desiderate.

4. Selezionare **Salva**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Assegnare criteri di configurazione delle app personalizzati a utenti e gruppi

Per altre informazioni sull'assegnazione di criteri a utenti e gruppi, vedere [Assegnare criteri a utenti e gruppi](assign-policies-users-and-groups.md).

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-setup-policies"></a>Utilizzo dei criteri di configurazione delle app

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quali criteri di configurazione delle app predefiniti sono inclusi nell'interfaccia di amministrazione di Microsoft Teams

- **Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare i criteri globali per aggiungere app più importanti per gli utenti.

- **FrontlineWorker**: questo criterio è per gli operatori in prima linea. È possibile assegnarla agli operatori in prima linea nell'organizzazione. È importante sapere che, come i criteri personalizzati creati dall'utente, è necessario assegnarli agli utenti affinché le impostazioni siano attive. Per altre informazioni, vedere la sezione [Assegnare criteri di configurazione delle app personalizzate agli utenti](#assign-a-custom-app-setup-policy-to-users-and-groups) di questo articolo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non riesco a trovare un'app nel riquadro Aggiungi app aggiunte

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cerca l'app nel riquadro **Aggiungi app aggiunte** . Le schede con un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte**.

Tieni presente che l'app store Teams elenca tutte le app Teams. Il riquadro **Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite criteri.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un amministratore Teams per l'istruzione. Informazioni utili sui criteri di configurazione delle app in Teams per l'istruzione

L'app Chiamate non è disponibile in Teams per l'istruzione. Quando crei un nuovo criterio di configurazione dell'app personalizzato, l'app Chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non viene aggiunta ai client Teams e Teams per l'istruzione utenti non vedranno l'app Chiamate in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quante app aggiunte possono essere aggiunte a un criterio

È necessario aggiungere almeno due app al Teams client per dispositivi mobili (iOS e Android). Se un criterio include meno di due app, i client mobili non rifletteranno le impostazioni dei criteri e continueranno a usare la configurazione esistente.

Non esistono limiti al numero di app aggiunte che è possibile aggiungere a un criterio.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo è necessario per applicare le modifiche ai criteri?

La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

### <a name="user-experience"></a>Esperienza utente

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>In che modo gli utenti possono visualizzare tutte le app aggiunte in Teams

Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le operazioni seguenti a seconda del numero di app installate e delle dimensioni della finestra del client Teams.

|Client desktop di Teams |Client per dispositivi mobili di Teams |
|---------|---------|
|Nella barra dell'app sul lato di Teams seleziona **... Altre app**.| Nella barra dell'app nella parte inferiore di Teams scorrere rapidamente verso l'alto.|
|![Altre app nel client desktop Teams.](media/app-setup-policies-desktop-more-apps.png)   |![altre app nel client per dispositivi mobili Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Cosa devo sapere sull'esperienza di Teams per dispositivi mobili

Il Teams client mobili (iOS e Android) supportano le app personali con schede statiche. Le app aggiunte al client desktop Teams verranno visualizzate nella Teams client per dispositivi mobili. I bot personali verranno visualizzati nella chat nei client mobili.

Le app di terze parti (scaricabili da Teams Store) devono essere approvate prima di essere visualizzate nei dispositivi mobili. Se un amministratore aggiunge un'app, non approvata da Microsoft per dispositivi mobili, verrà visualizzata nella Teams Desktop, ma non nei dispositivi mobili. Per altre informazioni, vedere [Client](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) mobili.

Con i client per dispositivi mobili Teams, gli utenti vedranno i principali Teams app come Attività, Chat e Teams e potrai aggiungere alcune app di terze parti da Microsoft, ad esempio Turni.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Gli utenti possono modificare l'ordine delle app aggiunte tramite un criterio

Gli utenti possono modificare l'ordine delle app aggiunte in Teams client desktop e per dispositivi mobili se l'opzione **Blocco utente** è attivata. Gli utenti non possono modificare l'ordine delle app aggiunte in Teams client Web.

#### <a name="does-user-pinning-take-precedence"></a>Il blocco dell'utente ha la precedenza?

I pin dell'amministratore hanno sempre la precedenza. Se l'opzione **Blocco utente** è attivata, gli utenti mantengono le app aggiunte sotto le app aggiunte dall'amministratore. Se l'opzione **Blocco utente** è disattivata, gli utenti perderanno i pin preesistenti e nella barra dell'app saranno presenti solo le app aggiunte dall'amministratore.

### <a name="custom-teams-apps"></a>App Teams personalizzate

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>L'organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams. Ricerca per categorie risolvere il problema?

Assicurati di seguire le linee guida per il logo prima di inviare l'app. Per altre informazioni, vedi [Elenco di controllo per l'invio di dashboard venditori](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Articoli correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies-users-and-groups.md)
