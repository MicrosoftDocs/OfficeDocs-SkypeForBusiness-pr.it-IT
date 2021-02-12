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
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145923"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

Gli amministratori possono usare i criteri di configurazione delle app per eseguire le attività seguenti:

- Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate. L'aggiunta di app consente di presentare le app necessarie agli utenti dell'organizzazione, incluse quelle create da terze parti o da sviluppatori dell'organizzazione.
- Controllare se gli utenti possono aggiungere app a Teams.
- Installare le app per conto degli **utenti (in anteprima).** È possibile scegliere quali app vengono installate per impostazione predefinita per gli utenti quando avviano Teams. Tenere presente che gli utenti possono comunque installare le app se i criteri di autorizzazione per le [app](teams-app-permission-policies.md) loro assegnati lo consentono.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams (iOS e Android).

|Client desktop di Teams  |Client per dispositivi mobili di Teams |
|---------|---------|
|![Client desktop di Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client teams per dispositivi mobili](media/mobile-app-ui.png)      |

Per visualizzare le app preinstallte, nella barra dell'app gli utenti **selezionano... Altre app** nei client desktop e web di Teams e scorrere rapidamente verso l'alto nei client mobili.

È possibile gestire i criteri di configurazione delle app nell'interfaccia di amministrazione di Microsoft Teams. Usare i criteri globali (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati.  Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

È possibile modificare le impostazioni nel criterio globale per includere le app desiderate. Per personalizzare Teams per diversi gruppi di utenti nell'organizzazione, creare e assegnare uno o più criteri personalizzati.

![Pagina Criteri di configurazione delle app](media/app-setup-policies.png)

> [!NOTE]
> Se si dispone di Teams per l'istruzione, è importante sapere che l'app Attività è aggiunta per impostazione predefinita ai criteri globali anche se attualmente non è elencata nei criteri globali. Sarà la quarta app nell'elenco delle app aggiunte nei client di Teams.

## <a name="create-a-custom-app-setup-policy"></a>Creare criteri di configurazione delle app personalizzati

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per creare criteri personalizzati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **delle app di**  >  **Teams.**

2. Selezionare **Aggiungi**.

   ![Pagina Aggiungi criteri di configurazione delle app](media/app-setup-policies-add.png)
    
3. Immettere un nome e una descrizione per il criterio.

4. Attivare o disattivare **Carica app** personalizzate, a seconda che si voglia o meno consentire agli utenti di caricare app personalizzate in Teams. Non puoi modificare questa  impostazione se Consenti app di terze parti è disattivato nelle impostazioni dell'app [a livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)

5. Attivare o disattivare **Consenti** l'aggiunta di app agli utenti, a seconda che si voglia consentire o meno agli utenti di personalizzare la barra dell'app aggiungendo app alla barra.

   > [!NOTE]
   > L'impostazione Consenti l'aggiunta di utenti è disponibile nell'interfaccia di amministrazione di Teams negli ambienti Microsoft 365 Government Community Cloud (GCC), ma attualmente non ha alcun effetto. 

6. Per installare le app per gli **utenti (in anteprima),** eseguire le attività seguenti:

    1. In **App installate** selezionare Aggiungi **app.**
    
    2. Nel riquadro **Aggiungi app installate,** cerca le app che vuoi installare automaticamente per gli utenti quando avviano Teams. È anche possibile filtrare le app in base ai criteri di autorizzazione per le app. Dopo aver scelto l'elenco di app, seleziona **Aggiungi.**

       ![Riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. Per aggiungere app, eseguire le operazioni seguenti:

    1. In **App aggiunte** selezionare Aggiungi **app.**
    
    2. Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi.** È anche possibile filtrare le app in base ai criteri di autorizzazione per le app. Dopo aver scelto l'elenco di app da aggiungere, seleziona **Aggiungi.**

       ![Riquadro Aggiungi app aggiunte](media/app-setup-policies-add-apps.png)

    3. Disponi le app nell'ordine in cui vuoi che vengano visualizzate in Teams, quindi seleziona **Salva.**

       ![Sezione App aggiunte](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione di un'app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (impostazione predefinita a livello di organizzazione) e i criteri personalizzati creati dall'utente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **delle app di**  >  **Teams.**

2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.

3. Da lì, apportare le modifiche desiderate.

4. Selezionare **Salva**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Assegnare criteri di configurazione delle app personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-setup-policies"></a>Uso dei criteri di configurazione delle app

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quali criteri di configurazione delle app incorporati sono inclusi nell'interfaccia di amministrazione di Microsoft Teams

- **Globale (impostazione predefinita a livello** di organizzazione): questo criterio predefinito viene applicato a tutti gli utenti dell'organizzazione, a meno che non venga assegnato un altro criterio. Modificare i criteri globali per aggiungere le app più importanti per gli utenti.

- **FrontlineWorker:** questo criterio è per gli operatori sul campo. È possibile assegnarla agli operatori sul campo nell'organizzazione. È importante sapere che, ad esempio, i criteri personalizzati creati dall'utente devono essere assegnati agli utenti perché le impostazioni siano attive. Per altre informazioni, vedere la sezione [Assegnare criteri](#assign-a-custom-app-setup-policy-to-users) di configurazione di app personalizzati agli utenti di questo articolo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non riesco a trovare un'app nel riquadro Aggiungi app aggiunte

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cerca l'app nel **riquadro Aggiungi app aggiunte.** Le schede con un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte.**

Tenere presente che nell'app store di Teams sono elencate tutte le app di Teams. Il **riquadro Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un amministratore di Teams per l'istruzione. Cosa devo sapere sui criteri di configurazione delle app in Teams for Education

L'app Chiamate non è disponibile in Teams per l'istruzione. Quando crei un nuovo criterio di configurazione delle app personalizzato, l'app per le chiamate viene visualizzata nell'elenco delle app. Tuttavia, l'app non viene aggiunta ai client di Teams e gli utenti di Teams for Education non vedono l'app Chiamate in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quante app aggiunte possono essere aggiunte a un criterio

È necessario aggiungere almeno due app ai client mobili di Teams (iOS e Android). Se un criterio include meno di due app, i client per dispositivi mobili non rifletteranno le impostazioni dei criteri, ma continueranno a usare la configurazione esistente.

Non ci sono limiti al numero di app aggiunte che è possibile aggiungere a un criterio.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo è necessario per l'applicazione delle modifiche ai criteri

La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

### <a name="user-experience"></a>Esperienza utente

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>In che modo gli utenti possono vedere tutte le app aggiunte in Teams?

Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le operazioni seguenti a seconda del numero di app installate e delle dimensioni della finestra client di Teams.

|Client desktop di Teams |Client per dispositivi mobili di Teams |
|---------|---------|
|Nella barra dell'app sul lato di Teams, **seleziona... Altre app.**| Nella barra dell'app, nella parte inferiore di Teams, scorri rapidamente verso l'alto.|
|![Altre app nel client desktop di Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![altre app nel client teams per dispositivi mobili](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Cosa devo sapere sull'esperienza di Teams per dispositivi mobili

I client mobili di Teams (iOS e Android) attualmente non supportano le app personali con schede statiche. A seconda delle app impostate nel criterio, le app aggiunte al client desktop di Teams potrebbero non essere visualizzate nei client mobili di Teams. I bot personali verranno comunque visualizzati in Chat sui client mobili.

Con i client di Teams per dispositivi mobili, gli utenti vedono le app principali di Teams, come Attività, Chat e Teams, e puoi aggiungere alcune app di prima parte di Microsoft, come Turni.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Gli utenti possono modificare l'ordine delle app aggiunte tramite un criterio

Se l'opzione Consenti l'aggiunta di utenti è  attivata, gli utenti possono cambiare l'ordine delle app aggiunte nei client desktop e per dispositivi mobili di Teams. Gli utenti non possono cambiare l'ordine delle app aggiunte nei client Web di Teams.

#### <a name="does-user-pinning-take-precedence"></a>L'aggiunta utente ha la precedenza

Se il criterio di configurazione delle app assegnato all'utente viene modificato in modo da bloccare il blocco dell'app utente, Teams rimuove tutte le app aggiunte alla barra dell'app. Se il criterio viene modificato per consentire l'aggiunta di app utente, gli utenti devono aggiungere di nuovo le app aggiunte in precedenza.

### <a name="custom-teams-apps"></a>App di Teams personalizzate

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>La mia organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams. Come si corregge?

Assicurarsi di seguire le linee guida per il logo prima di inviare l'app. Per altre informazioni, vedi l'elenco [di controllo per l'invio al dashboard del venditore.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Argomenti correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
