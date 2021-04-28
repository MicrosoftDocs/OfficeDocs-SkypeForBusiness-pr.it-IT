---
title: Gestire i criteri di configurazione delle app in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di configurazione delle app in Microsoft Teams per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059200"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

Gli amministratori possono usare i criteri di configurazione delle app per eseguire le attività seguenti:

- Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate. L'aggiunta di app consente di mostrare le app necessarie agli utenti dell'organizzazione, incluse le app create da terze parti o dagli sviluppatori dell'organizzazione.
- Controllare se gli utenti possono aggiungere app a Teams.
- Installare le app per conto degli utenti. È possibile scegliere le app installate per impostazione predefinita per gli utenti all'avvio di Teams. Tenere presente che gli utenti possono comunque installare le app se i criteri di autorizzazione [dell'app](teams-app-permission-policies.md) assegnati lo consentono.

> [!Note]
> Per le app installate dagli amministratori, gli utenti non possono disinstallare tali app.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams (iOS e Android).

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Client desktop di Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client per dispositivi mobili di Teams](media/mobile-app-ui.png)      |

Per visualizzare le app installate dagli amministratori, nella barra dell'app gli utenti **selezionano ... Altre app** nei client desktop e Web di Teams e scorri verso l'alto nei client mobili.

I criteri di configurazione delle app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati.  Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

Modificare le impostazioni nei criteri globali per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati.

![pagina Criteri di configurazione delle app](media/app-setup-policies.png)

> [!NOTE]
> Se si dispone di Teams per l'istruzione, è importante sapere che l'app Attività è aggiunta per impostazione predefinita nei criteri globali anche se attualmente non è elencata nei criteri globali. Sarà la quarta app nell'elenco delle app aggiunte nei client di Teams.

## <a name="create-a-custom-app-setup-policy"></a>Creare criteri di configurazione dell'app personalizzati

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per creare criteri personalizzati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Criteri di **configurazione delle app** di  >  **Teams.**

2. Selezionare **Aggiungi**.

   ![Pagina Aggiungi criteri di configurazione delle app](media/app-setup-policies-add.png)

3. Immettere un nome e una descrizione per il criterio.

4. Attivare o disattivare **Carica app personalizzate,** a seconda che si voglia consentire agli utenti di caricare app personalizzate in Teams. Non è possibile modificare questa impostazione se Consenti **app** di terze parti è disattivato nelle impostazioni dell'app a [livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)

5. Attivare o disattivare **Consenti** l'aggiunta all'utente, a seconda che si voglia consentire agli utenti di personalizzare la barra dell'app aggiungendo app.

   > [!NOTE]
   > L'impostazione Consenti blocco utenti è disponibile nell'interfaccia di amministrazione di Teams negli ambienti GCC (Government Community Cloud) di Microsoft 365 (GCC, GCC High e DoD), ma attualmente non ha alcun effetto. 

6. Per installare le app per gli utenti, eseguire le attività seguenti:

    1. In **App installate** selezionare Aggiungi **app.**

    2. Nel riquadro **Aggiungi app installate** cercare le app da installare automaticamente per gli utenti all'avvio di Teams. È anche possibile filtrare le app in base ai criteri di autorizzazione delle app. Dopo aver scelto l'elenco di app, selezionare **Aggiungi**.

       ![Riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. Per aggiungere app, eseguire la procedura seguente:

    1. In **App aggiunte** selezionare Aggiungi **app.**

    2. Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi**. È anche possibile filtrare le app in base ai criteri di autorizzazione delle app. Dopo aver scelto l'elenco di app da aggiungere, selezionare **Aggiungi**.

       ![Riquadro Aggiungi app aggiunte](media/app-setup-policies-add-apps.png)

    3. Disporre le app nell'ordine in cui si vuole che vengano visualizzate in Teams e quindi selezionare **Salva**.

       ![sezione App aggiunte](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione dell'app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (impostazione predefinita a livello di organizzazione) e i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Criteri di **configurazione delle app** di  >  **Teams.**

2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.

3. Da lì, apportare le modifiche desiderate.

4. Selezionare **Salva**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Assegnare criteri di configurazione dell'app personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-setup-policies"></a>Uso dei criteri di configurazione delle app

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quali criteri di configurazione delle app predefiniti sono inclusi nell'interfaccia di amministrazione di Microsoft Teams

- **Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare i criteri globali per aggiungere app più importanti per gli utenti.

- **FrontlineWorker:** questo criterio è per i frontline worker. È possibile assegnarlo ai Frontline Worker dell'organizzazione. È importante sapere che, come i criteri personalizzati creati dall'utente, è necessario assegnare il criterio agli utenti perché le impostazioni siano attive. Per altre informazioni, vedere la sezione Assegnare un criterio di configurazione [dell'app](#assign-a-custom-app-setup-policy-to-users) personalizzato agli utenti di questo articolo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non si trova un'app nel riquadro Aggiungi app aggiunte

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cercare l'app nel **riquadro Aggiungi app aggiunte.** Le schede con ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte.**

Tenere presente che l'app Store di Teams elenca tutte le app di Teams. Il **riquadro Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un amministratore di Teams for Education. Informazioni sui criteri di configurazione delle app in Teams for Education

L'app Chiamate non è disponibile in Teams per l'istruzione. Quando si crea un nuovo criterio di configurazione dell'app personalizzato, l'app Chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non è aggiunta ai client di Teams e gli utenti di Teams per l'istruzione non vedono l'app Chiamate in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quante app aggiunte possono essere aggiunte a un criterio

È necessario aggiungere almeno due app ai client mobili di Teams (iOS e Android). Se un criterio ha meno di due app, i client mobili non rifletteranno le impostazioni dei criteri e continueranno invece a usare la configurazione esistente.

Non ci sono limiti al numero di app aggiunte che è possibile aggiungere a un criterio.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo è necessario per l'applicazione delle modifiche ai criteri

La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

### <a name="user-experience"></a>Esperienza utente

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Come possono gli utenti vedere tutte le app aggiunte in Teams

Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le operazioni seguenti a seconda del numero di app installate e delle dimensioni della finestra del client di Teams.

|Client desktop di Teams |Client per dispositivi mobili di Teams |
|---------|---------|
|Nella barra dell'app sul lato di Teams seleziona **... Altre app**.| Nella barra dell'app nella parte inferiore di Teams scorrere rapidamente verso l'alto.|
|![Altre app nel client desktop di Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Altre app nel client di Teams per dispositivi mobili](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Cosa c'è da sapere sull'esperienza di Teams per dispositivi mobili

I client mobili di Teams (iOS e Android) supportano le app personali con schede statiche. Le app aggiunte al client desktop di Teams verranno visualizzate nei client mobili di Teams. I bot personali verranno visualizzati in Chat sui client mobili.

Le app di terze parti (che possono essere scaricate da Teams Store) devono essere approvate prima di essere mostrate su dispositivi mobili. Se un amministratore aggiunge un'app, che non è approvata da Microsoft per dispositivi mobili, verrà visualizzata in Teams Desktop, ma non su un dispositivo mobile. Per [altre informazioni, vedere](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) Client per dispositivi mobili.

Con i client di Teams per dispositivi mobili, gli utenti potranno vedere le app principali di Teams, come Attività, Chat e Teams, ed è possibile aggiungere alcune app di prima parte da Microsoft, ad esempio Turni.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Gli utenti possono modificare l'ordine delle app aggiunte tramite un criterio

Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e mobili di Teams se l'opzione Consenti **blocco** utenti è attivata. Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di Teams.

#### <a name="does-user-pinning-take-precedence"></a>Il blocco degli utenti ha la precedenza

I pin di amministratore hanno sempre la precedenza. Se **l'opzione Consenti aggiunta utenti** è attivata, gli utenti manterranno le app aggiunte sotto le app aggiunte dall'amministratore. Se **l'opzione** Consenti blocco utenti è disattivata, gli utenti perderanno i pin preesistnti e nella barra dell'app saranno presenti solo le app aggiunte dall'amministratore.

### <a name="custom-teams-apps"></a>App di Teams personalizzate

L'organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams. Come si risolve il problema

Assicurarsi di seguire le linee guida del logo prima di inviare l'app. Per altre informazioni, vedere Elenco [di controllo per l'invio del dashboard del venditore.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Argomenti correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
