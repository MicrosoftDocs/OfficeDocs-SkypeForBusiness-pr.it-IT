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
description: Informazioni su come creare, modificare e gestire i criteri di configurazione delle app per aggiungere app, installare app e consentire agli utenti di caricare app personalizzate.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 58a2b8730c4f3d02746aeb0bb3887bcd63d44918
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190477"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

Gli amministratori usano i criteri di configurazione delle app per installare e aggiungere app e consentire agli utenti di caricare app personalizzate. L'aggiunta consente di promuovere l'adozione di app pertinenti nell'organizzazione.

* **Aggiungere app:** I criteri di configurazione delle app consentono di scegliere le app da aggiungere, impostare l'ordine di visualizzazione delle app per gli utenti nella barra dell'app Teams o nell'area di composizione dei messaggi. Gli amministratori possono anche controllare se gli utenti finali possono aggiungere o meno le proprie app. Vedi [Aggiungere app](#pin-apps).
* **Installa app:** I criteri di configurazione delle app consentono di installare le app per conto degli utenti quando iniziano Teams e durante le riunioni. Per altre informazioni, vedi [Installare le app](#install-apps).
* **Upload app personalizzate: i** criteri di configurazione delle app consentono agli utenti di caricare app personalizzate in Teams. Per altre informazioni, vedere [Upload app personalizzate](#upload-custom-apps).

## <a name="pin-apps"></a>Aggiungere app

L'aggiunta di app consente di evidenziare le app di cui gli utenti dell'organizzazione hanno più bisogno. L'aggiunta funziona per le app fornite da Microsoft, dalle aziende isv e dagli sviluppatori all'interno dell'organizzazione. L'aggiunta di un'app tramite un criterio di configurazione dell'app consente anche di installarla. Usando i criteri di configurazione delle app, è possibile eseguire le attività seguenti:

* Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegli le app da aggiungere e impostare l'ordine in cui vengono visualizzate.
* Controlla se gli utenti possono o meno aggiungere app.

Le app vengono aggiunte alla barra dell'app sul lato sinistro del client desktop Teams e nella parte inferiore del Teams client per dispositivi mobili.

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Barra dell'app nel client desktop Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Barra dell'app nel client per dispositivi mobili Teams.](media/mobile-app-ui.png)      |

Le estensioni di messaggistica sono disponibili nella parte inferiore dell'area di composizione dei messaggi.

Per creare un criterio di configurazione delle app per aggiungere app, procedere come segue:

1. Accedere all [Microsoft Teams interfaccia di amministrazione](https://admin.teams.microsoft.com).

1. Nel riquadro sinistro passare a Teams **criteri di configurazione** **delle app** > .

1. Selezionare **Aggiungi**.

1. Immettere un nome e una descrizione per il criterio.

1. Attiva **Blocco utente**.

   > [!NOTE]
   > **L'impostazione Blocco utente** è disponibile nell'interfaccia di amministrazione di Teams in ambienti Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High e DoD), ma attualmente non ha alcun effetto.

1. In **App aggiunte** seleziona **Aggiungi app**.

1. Nel riquadro **Aggiungi app aggiunte** cerca le app che vuoi aggiungere e quindi seleziona **Aggiungi**. Puoi anche filtrare le app in base ai criteri di autorizzazione delle app.

1. Selezionare **Aggiungi**.

1. Nella **barra dell'app** o nelle **estensioni messaggi** disponi le app nell'ordine in cui vuoi che vengano visualizzate in Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="sezione app aggiunte"border="true":::

1. Selezionare **Salva**.

> [!NOTE]
> In Teams per l'istruzione, l'app Attività viene aggiunta per impostazione predefinita ai criteri globali, anche se non è elencata nel criterio globale.

> [!NOTE]
> Per gli operatori in prima linea nell'organizzazione, è consigliabile usare l'esperienza app frontline personalizzata. Questa funzionalità aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Per altre informazioni, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

## <a name="install-apps"></a>Installare app

Usando i criteri di configurazione delle app, un amministratore può eseguire le attività seguenti:

* Installare le app per gli utenti finali nel proprio ambiente di Teams personale, per impostazione predefinita.
* Installare le app per gli utenti finali come [estensioni di messaggistica](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).
* Installa le app nelle riunioni per gli organizzatori delle riunioni.

Gli utenti finali possono installare le app autonomamente se il [criterio di autorizzazione dell'app](teams-app-permission-policies.md) lo consente.

Per creare un criterio di configurazione delle app per installare le app, procedere come segue:

1. Accedere all Teams interfaccia di amministrazione e accedere **ai criteri di configurazione di Teams app** > .

2. Selezionare **Aggiungi**.

3. Specificare un nome e una descrizione per il criterio.

4. In **App installate** seleziona **Aggiungi app**.

5. Nel riquadro **Aggiungi app installate** cercare gli utenti nelle app da installare. Puoi anche filtrare le app in base ai criteri di autorizzazione delle app.

6. Selezionare **Aggiungi**.

![Installa i criteri per le app.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Gli utenti non possono disinstallare le app installate dagli amministratori.

## <a name="upload-custom-apps"></a>Upload app personalizzate

Per creare criteri personalizzati che consentano agli utenti di caricare app personalizzate, seguire questa procedura:

1. Accedere all Teams interfaccia di amministrazione e accedere **ai criteri di configurazione di Teams app** > .

2. Selezionare **Aggiungi**.

3. Specificare un nome e una descrizione per il criterio.

4. Attivare o disattivare **Upload app personalizzate**.

> [!NOTE]
> Per modificare questa impostazione, [le impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings) del tenant devono consentire le **app di terze parti**.

## <a name="manage-app-setup-policies"></a>Gestire i criteri di configurazione delle app

I criteri di configurazione delle app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti finali ottengono i criteri globali. Se si crea un criterio personalizzato, viene eseguito l'override del criterio globale. Questi criteri possono essere gestiti da un amministratore globale o da un amministratore dei servizi di Teams.

È possibile modificare le impostazioni nel criterio globale per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati.

![Pagina Criteri di configurazione delle app per gestire i criteri o aggiungere nuovi criteri.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione delle app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (predefiniti a livello di organizzazione) e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **App di Teams** > **Criteri di configurazione**.

2. Scegliere il criterio da modificare e quindi selezionare **Modifica**.

3. Apportare le modifiche desiderate.

4. Selezionare **Salva**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Assegnare criteri di configurazione delle app personalizzati a utenti e gruppi

Per altre informazioni sull'assegnazione di criteri a utenti e gruppi, vedere [Assegnare criteri a utenti e gruppi](assign-policies-users-and-groups.md).

## <a name="faqs"></a>Faq

<!--- TBD: Incorporate these pointers in the content itself.
--->

### <a name="working-with-app-setup-policies"></a>Utilizzo dei criteri di configurazione delle app

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quali criteri di configurazione delle app predefiniti sono inclusi nell'interfaccia di amministrazione di Microsoft Teams

* **Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare i criteri globali per aggiungere app più importanti per gli utenti.

* **FrontlineWorker**: questo criterio è per gli operatori in prima linea. È possibile assegnarla agli operatori in prima linea nell'organizzazione. È importante sapere che, come i criteri personalizzati creati dall'utente, è necessario assegnarli agli utenti affinché le impostazioni siano attive. Per altre informazioni, vedere la sezione [Assegnare criteri di configurazione delle app personalizzate agli utenti](#assign-a-custom-app-setup-policy-to-users-and-groups) di questo articolo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non riesco a trovare un'app nel riquadro Aggiungi app aggiunte

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cerca l'app nel riquadro **Aggiungi app aggiunte** . Le schede con un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte**.

Tieni presente che l'app store Teams elenca tutte le app Teams. Il riquadro **Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite criteri.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un amministratore Teams per l'istruzione. Informazioni utili sui criteri di configurazione delle app in Teams per l'istruzione

L'app Chiamate non è disponibile in Teams per l'istruzione. Quando crei un nuovo criterio di configurazione dell'app personalizzato, l'app Chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non viene aggiunta ai client Teams e Teams per l'istruzione utenti non vedranno l'app Chiamate in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quante app aggiunte possono essere aggiunte a un criterio

È necessario aggiungere almeno due app ai client per dispositivi mobili Teams (iOS e Android). Se un criterio include meno di due app, i client mobili non rifletteranno le impostazioni dei criteri e continueranno a usare la configurazione esistente.

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

Amministrazione i pin hanno sempre la precedenza. Se l'opzione **Blocco utente** è attivata, gli utenti mantengono le app aggiunte sotto le app aggiunte dall'amministratore. Se l'opzione **Blocco utente** è disattivata, gli utenti perderanno i pin preesistenti e nella barra dell'app saranno presenti solo le app aggiunte dall'amministratore.

### <a name="custom-teams-apps"></a>App Teams personalizzate

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>L'organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams. Ricerca per categorie risolvere il problema?

Assicurati di seguire le linee guida per il logo prima di inviare l'app. Per altre informazioni, vedi [Elenco di controllo per l'invio di dashboard venditori](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="see-also"></a>Vedere anche

* [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
* [Assegnare criteri agli utenti finali in Teams](assign-policies-users-and-groups.md)
