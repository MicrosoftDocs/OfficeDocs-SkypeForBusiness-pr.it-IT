---
title: Gestire le app nell'interfaccia di amministrazione di Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire le app di Teams nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: a6e6adbfbed5e1b371655ca74aa6ca6c717490c9
ms.sourcegitcommit: 06d1c50c9b55b062d61844a856676d9837fd5abe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "65030942"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gestire Teams app nell'interfaccia di amministrazione di Microsoft Teams

Le app per l'organizzazione possono essere gestite in **Teams app** nell'interfaccia di amministrazione. Usare la pagina [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) per visualizzare e gestire tutte le app Teams nel catalogo app dell'organizzazione. La pagina Gestisci app offre una visualizzazione di tutte le app disponibili nel catalogo tenant, fornendo le informazioni necessarie per decidere quali app consentire o bloccare nell'intera organizzazione. Puoi visualizzare lo stato e le proprietà delle app a livello di organizzazione, bloccare o consentire app a livello di organizzazione, caricare nuove app personalizzate nel catalogo tenant e gestire le impostazioni delle app a livello di organizzazione.

![Screenshot della pagina Gestisci app.](media/manage-apps.png)

Per gestire le app, usare i criteri seguenti per controllare le autorizzazioni per gli utenti, l'installazione delle app e il caricamento di app personalizzate create all'interno dell'organizzazione. Per informazioni sui criteri, vedere [Panoramica dei criteri delle app](app-policies.md).

Per informazioni su come ottenere i ruoli di amministratore e le autorizzazioni, vedere [Teams ruoli di amministratore](./using-admin-roles.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> La pagina Gestisci app non è disponibile nelle distribuzioni Microsoft 365 Government Community Cloud High (GCCH) o DoD (Department of Defense) di Teams.

<!--- TBD: This info belongs in the app policy overview article. Title it as mentioned in the spreadsheet.

* **App permission policy**: With it, you can control what apps are available to specific users in your organization. You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization. See [Manage app permission policies in Teams](teams-app-permission-policies.md).
* **App setup policies**: It lets you customize the app experience for your users. You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients. See [Manage app setup policies in Teams](teams-app-setup-policies.md).
* **Custom app policies and settings**: Teams allows developers in your organization to build, test, and deploy custom apps to other users. Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context. You can use app setup policies to control who in your organization can upload custom apps. You can also set org-wide settings to control whether users can interact with specific custom apps. See [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings).

The following are the important use cases you can accomplish via the the Manage apps page:

* [Allow or block apps at the org level](#allow-and-block-apps)
* [Apps blocked by publishers](#apps-blocked-by-publishers)
* [Add apps to teams](#add-an-app-to-a-team)
* [Approve or upload new custom apps to your organization's app store](#publish-a-custom-app-to-your-organizations-app-store)
* [View permissions requested by apps](#view-resource-specific-consent-permissions)
* [Grant consent to apps](#grant-admin-consent-to-apps)
* [Purchase service for third-party apps](#purchase-services-for-third-party-apps)
* [See org-level status and properties of apps](#view-apps)
* [Manage org-wide app settings](#manage-org-wide-app-settings)
* [View security and compliance information for Microsoft 365 Certified apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

<!--- TBD: Commenting for now in favor of the definition list above: 

The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization. You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.

In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**. You must be a global admin or Teams service admin to access the page.

--->

<!--- TBD: Move this view apps section to a new article about navigating and understanding TAC. It is yet to be created.

## View apps

You can view every app including the following information about each app.

![Screenshot of the apps details page for an app.](media/app-detail-page.jpg)

- **Name**: The app name. Select the app name to go to the app details page to see more information about the app. This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.
- **Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**. Select the link to view certification details for the app. If you see `--`, we don't have certification information for the app. To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/microsoft-365-app-certification/overview).
- **Publisher**: Name of the publisher.
- **Publishing status**: Publishing status of custom apps.
- **Status**: Status of the app at the org level, which can be one of the following:
  - **Allowed**: The app is available for all users in your organization.
  - **Blocked**: The app is blocked and not available for any users in your organization.
  - **Blocked by publisher**: The app is blocked by the publisher and is hidden from end-users by default. After you set up the app using the publisher's guidance, you can allow or block the app to make it available to end-users.
  - **Blocked org-wide**: The app is blocked in org-wide app settings.
      It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane. You now view, block, and allow apps at the org-wide on the **Manage apps** page.
- **Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase. This column applies only to third-party apps. Each third-party app will have one of the following values:
  - **Purchase**: The app offers a SaaS subscription and is available to purchase.  
  - **Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.
  - **- -**: The app doesn't offer a SaaS subscription.
- **Custom app**: Whether the app is a custom app.
- **Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent. You'll see one of the following values:
  - **View details**: The app has permissions that require consent before the app can access data.
  - **- -**: The app doesn't have permissions that need consent.
- **Categories**: Categories that apply to the app.
- **Version**: App version.
- **Admin can install in meetings**: Indicates whether an app can be installed by admins in Team meetings. [Learn more](teams-app-setup-policies.md#install-apps)

To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Pubblicare un'app personalizzata nell'app store dell'organizzazione

Usare la pagina Gestisci app per pubblicare app create appositamente per l'organizzazione. Dopo la pubblicazione, un'app personalizzata è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata nell'app store dell'organizzazione. La modalità di utilizzo dipende da come si ottiene l'app.

* [Approvare un'app personalizzata](#approve-a-custom-app): usare questo metodo se lo sviluppatore invia l'app direttamente alla pagina Gestisci app usando l'API di invio di app Teams. È quindi possibile rivedere e pubblicare (o rifiutare) l'app direttamente dalla pagina dei dettagli dell'app.
* [Upload un pacchetto dell'app](#upload-an-app-package): usare questo metodo se lo sviluppatore invia il pacchetto dell'app in formato .zip. L'app viene pubblicata caricando il pacchetto dell'app.

### <a name="approve-a-custom-app"></a>Approvare un'app personalizzata

Il widget **Approvazioni in sospeso** nella pagina Gestisci app ti invia una notifica quando uno sviluppatore invia un'app usando l'API di invio di app Teams. Viene elencata un'app appena inviata con **lo stato Pubblicazione** **inviato** e **lo stato** **Bloccato**. Passare alla pagina dei dettagli dell'app per visualizzare altre informazioni sull'app e quindi, per pubblicarla, impostare **Lo stato pubblicazione** su **Pubblica**.

Riceverai anche una notifica quando uno sviluppatore invia un aggiornamento a un'app personalizzata. È quindi possibile rivedere e pubblicare (o rifiutare) l'aggiornamento nella pagina dei dettagli dell'app. Tutti i criteri di autorizzazione e i criteri di configurazione delle app rimangono applicati per l'app aggiornata.

Per altre informazioni, vedi [Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Upload un pacchetto dell'app

Lo sviluppatore crea un pacchetto di app Teams usando [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) e quindi lo invia all'utente in .zip formato. Quando si dispone del pacchetto dell'app, è possibile caricarlo nell'app store dell'organizzazione.

Per caricare una nuova app personalizzata, selezionare **Upload** per caricare il pacchetto dell'app. L'app non viene evidenziata dopo il caricamento, quindi è necessario cercare nell'elenco delle app nella pagina Gestisci app per trovarla.

Per aggiornare un'app dopo il caricamento, seleziona il nome dell'app nell'elenco delle app nella pagina Gestisci app e quindi seleziona **Aggiorna**. In questo modo vengono sostituiti l'app esistente e tutti i criteri di autorizzazione e i criteri di configurazione dell'app rimangono applicati per l'app aggiornata.

Per altre informazioni, vedere [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Consentire e bloccare le app

Nella pagina Gestisci app puoi consentire o bloccare singole app a livello di organizzazione. Mostra ogni app disponibile e lo stato corrente dell'app a livello di organizzazione. Il blocco e l'abilitazione di app a livello di organizzazione sono passati dal riquadro **impostazioni app a livello di organizzazione** a qui.

Per consentire o bloccare un'app, selezionala e quindi seleziona **Consenti** o **Blocca**. Quando si blocca un'app, tutte le interazioni con l'app vengono disabilitate e l'app non viene visualizzata in Teams per gli utenti dell'organizzazione.

Quando si blocca o si consente un'app nella pagina Gestisci app, l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione.  Quando si blocca o si consente un'app in un criterio di autorizzazione di un'app Teams, questa viene bloccata o consentita per gli utenti a cui sono assegnati criteri. Per consentire a un utente di installare e interagire con qualsiasi app, è necessario consentire l'app a livello di organizzazione nella pagina Gestisci app e nei criteri di autorizzazione dell'app assegnati all'utente.

 > [!NOTE]
 > Per disinstallare un'app, fare clic con il pulsante destro del mouse sull'app e quindi scegliere **Disinstalla** o usare il menu **Altre app** a sinistra.

## <a name="apps-blocked-by-publishers"></a>App bloccate dagli autori

Quando un ISV pubblica un'app nell'app store globale, potrebbe essere necessario che gli amministratori configurino o personalizzino l'esperienza dell'app. L'amministratore può renderla disponibile agli utenti finali quando l'app è completamente configurata.

Ad esempio, Contoso Electronics è un ISV che ha creato un'app help desk per Microsoft Teams. Contoso Electronics vuole che i clienti configurino alcune proprietà dell'app in modo che, quando gli utenti interagiscono con l'app, funzioni come previsto. Prima che un amministratore possa consentire o bloccare l'applicazione, verrà **visualizzata come Bloccata dall'autore** nell'interfaccia di amministrazione di Teams e verrà nascosta agli utenti finali per impostazione predefinita. Dopo aver seguito le indicazioni dell'autore per configurare l'app, è possibile renderla disponibile per gli utenti passando allo stato **Consentito** o impedire agli utenti di usare l'app impostando lo stato **su Bloccata**.

![Screenshot di bloccato dallo stato dell'autore nell'interfaccia di amministrazione di Teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Aggiungere un'app a un team

Si usa il pulsante **Aggiungi al team** per installare un'app in un team. Tenere presente che questo vale solo per le app che possono essere installate in un ambito del team. Il pulsante **Aggiungi al team** non è disponibile per le app che possono essere installate solo nell'ambito personale.

![Screenshot del pulsante Aggiungi al team.](media/manage-apps-add-app-team.png)

1. Cerca l'app desiderata e quindi seleziona l'app facendo clic a sinistra del nome dell'app.
1. Selezionare **Aggiungi al team**.
1. Nel riquadro **Aggiungi al team** cercare il team a cui si vuole aggiungere l'app, selezionare il team e quindi selezionare **Applica**.

## <a name="customize-an-app"></a>Personalizzare un'app

È ora possibile personalizzare un'app per includere un aspetto specifico in base alle esigenze dell'organizzazione. Vedere [Personalizzare le app in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Acquisto di servizi per app di terze parti

È possibile cercare e acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione direttamente dalla pagina Gestisci app. La colonna **Licenze** nella tabella indica se un'app offre un abbonamento SaaS a pagamento. Selezionare **Acquista ora** per visualizzare i piani e le informazioni sui prezzi e acquistare licenze per gli utenti. Per altre informazioni, vedere [Acquistare servizi per Teams app di terze parti nell'interfaccia di amministrazione di Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Concedere il consenso dell'amministratore alle app

È possibile esaminare e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. In questo modo gli utenti non dovranno rivedere e accettare le autorizzazioni richieste dall'app all'avvio dell'app. La colonna **Autorizzazioni** indica se un'app ha autorizzazioni che richiedono il consenso. Vedrai un collegamento **Visualizza dettagli** per ogni app registrata in Azure AD con autorizzazioni che richiedono il consenso. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Visualizzare le autorizzazioni di consenso specifiche per le risorse

Le autorizzazioni per il consenso specifico delle risorse consentono ai proprietari del team di concedere a un'app il consenso per l'accesso e la modifica dei dati di un team. Le autorizzazioni RSC sono granulari, Teams autorizzazioni specifiche che definiscono cosa può fare un'app in un team specifico. È possibile visualizzare le autorizzazioni RSC nella scheda **Autorizzazioni** della pagina dei dettagli dell'app per un'app. Per altre informazioni, vedere [Visualizzare le autorizzazioni per le app e concedere il consenso di amministratore nell'interfaccia di amministrazione di Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni delle app a livello di organizzazione

Usare le impostazioni delle app a livello di organizzazione per controllare se gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza personalizzata per le app in prima linea, se gli utenti possono installare app di terze parti e se gli utenti possono caricare o interagire con le app personalizzate nell'organizzazione. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. È possibile usarle per controllare eventuali app dannose o problematiche.

> [!NOTE]
> Per informazioni su come usare le impostazioni delle app a livello di organizzazione in Microsoft 365 Government - Government Community Cloud le distribuzioni High GCCH e Department of Defense (DoD) di Teams, vedere [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md).

1. Nella pagina Gestisci app seleziona **Impostazioni app a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel riquadro.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot del riquadro Impostazioni app a livello di organizzazione nella pagina Gestisci app":::

1. In **App personalizzate** disattiva o attiva **Mostra app personalizzate**. Quando questa impostazione è attivata, gli utenti con [una licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) ottengono l'esperienza app frontline personalizzata. Questa esperienza aggiunge le app più rilevanti in Teams per gli operatori in prima linea. Per altre informazioni, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

    Questa funzionalità è disponibile per le licenze F. Altri tipi di licenza saranno supportati in futuro.
1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se disattivi questa impostazione, gli utenti non potranno installare o usare app di terze parti e lo stato dell'app di queste app viene visualizzato come Bloccato a **livello di organizzazione** nella tabella.

        > [!NOTE]
        > Quando **l'opzione Consenti app di terze parti** è disattivata, [i webhook in uscita sono ancora abilitati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) per tutti gli utenti, ma è possibile controllarli a livello di utente consentendo o bloccando l'app Webhook in uscita tramite [criteri di autorizzazione dell'app](teams-app-permission-policies.md). Se sono presenti [criteri di autorizzazione](teams-app-permission-policies.md) per le **app Microsoft** che usano l'impostazione **Consenti app specifiche e bloccano tutte le altre** e si vogliono abilitare i webhook in uscita per gli utenti, aggiungere l'app Webhook in uscita all'elenco.

        > [!NOTE]
        > Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione.

    - **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa impostazione consente di controllare se eventuali nuove app di terze parti pubblicate nello Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App personalizzate** disattiva o attiva **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate. Per altre informazioni, vedere [Gestisci criteri e impostazioni app personalizzate in Teams](teams-custom-app-policies-and-settings.md).
1. Seleziona **Salva** per rendere effettive le impostazioni delle app a livello di organizzazione.

<!--- TBD: Commenting this info for now. Move it later to the new article about compliance program and how/where admins can find info about compliant apps.

## View security and compliance information for Microsoft 365 Certified apps

When evaluating an app for their organization, admins can use independent Cloud Access Security Brokers (CASB), such as Microsoft Cloud App Security (MCAS), to find information about security and behaviors of an app. The Teams admin center includes security and compliance information from MCAS for Microsoft 365 Certified apps so you'll have more information on whether or not the app meets your needs.

> [!NOTE]
> This feature is available to all admins, whether or not your organization has a license that supports MCAS.

To access MCAS information, follow these steps:

1. In the Teams admin center, select **Manage apps** under **Teams apps**.
1. Select **Certification** to sort apps and push all Microsoft 365 Certified apps to the top of the table.
1. Choose a Microsoft 365 Certified app.
1. Select the **Security and compliance** tab.

![Screenshot of Teams admin center security and compliance tab.](media/mcas.png)

On this tab, you'll find information on security, compliance, and data protection. You can also expand each dropdown list to get more details about which capabilities are supported for the selected application.
--->
