---
title: Gestire i criteri di autorizzazione app in Microsoft Teams
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
description: Informazioni sui criteri di autorizzazione per le app in Microsoft Teams e su come controllare la disponibilità delle app per gli utenti finali.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 20993aea7665893d71be1fd1094df9f0d1acdc91
ms.sourcegitcommit: e8a78c24fda7e56c7b217a843a8a5f1c30aa95f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2022
ms.locfileid: "65785956"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gestire i criteri di autorizzazione app in Microsoft Teams

Gli amministratori possono usare i criteri di autorizzazione app per controllare quali app sono disponibili per gli utenti di Microsoft Teams dell'organizzazione. È possibile consentire o bloccare tutte le app o determinate app pubblicate da Microsoft, da terze parti e dall'organizzazione. Quando si blocca un'app, gli utenti a cui è assegnato il criterio non possono a installarla dallo store delle app di Teams. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

È possibile gestire i criteri di autorizzazione app nell'interfaccia di amministrazione di Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

![Screenshot dei criteri di autorizzazione per le app.](media/app-permission-policies.png)

> [!NOTE]
> Le impostazioni app a livello di organizzazione sostituiscono il criterio globale e qualsiasi criterio personalizzato creato e assegnato agli utenti.

Se l'organizzazione è già su Teams, le impostazioni app configurate nelle **impostazioni a livello di tenant** nell'interfaccia di amministrazione di Microsoft 365 vengono rispecchiate nelle impostazioni app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md). Se si usa Teams per la prima volta, per impostazione predefinita tutte le app sono consentite nel criterio globale. Include app pubblicate da Microsoft, da provider di software di terze parti e dall'organizzazione.

Supponiamo, ad esempio, di voler consentire solo alcune app specifiche per il team delle risorse umane dell'organizzazione. Prima di tutto, nella pagina [Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps) verifica che le app che vuoi consentire per il team delle risorse umane siano consentite a livello di organizzazione. Quindi, creare un criterio personalizzato, impostarlo in modo da bloccare e consentire le app desiderate e assegnare il criterio agli utenti del team hr.

> [!NOTE]
> Per informazioni sulle impostazioni delle app di terze parti univoche per Microsoft 365 Government Community Cloud ambiente High (GCCH) e Department of Defense (DoD), vedi [Gestire le impostazioni delle app a livello di organizzazione per Microsoft 365 government](#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-a-custom-app-permission-policy"></a>Creare un criterio di autorizzazione app personalizzato

Usare uno o più criteri di autorizzazione personalizzati per le app, se si vogliono controllare le app disponibili per gruppi di utenti diversi. È possibile creare e assegnare criteri personalizzati in base a chi pubblica le app: Microsoft, terze parti o l'organizzazione. Dopo aver creato un criterio personalizzato, non è possibile modificarlo se le app di terze parti sono disabilitate nelle impostazioni delle app a livello di organizzazione.

1. Accedere all Teams [interfaccia di amministrazione](https://admin.teams.microsoft.com/dashboard)
1. Nel riquadro sinistro passare a **Teams app** > **Criteri di autorizzazione**.
1. Selezionare **Aggiungi**.

   ![Screenshot dei nuovi criteri di autorizzazione per le app.](media/app-permission-policies-new-policy.png)

1. Specificare un nome e una descrizione per il criterio.
1. In **App Microsoft**, **App di terze parti** e **App personalizzate**, selezionare una delle seguenti opzioni:

    * Consenti tutte le app
    * Consenti app specifiche e blocca tutte le altre
    * Blocca app specifiche e consenti tutte le altre
    * Blocca tutte le app

1. Se hai selezionato **Consenti app specifiche e blocca tutte le altre**, aggiungi le app che vuoi consentire:

    1. Selezionare **Consenti app**.
    1. Cerca le app che vuoi consentire e quindi seleziona **Aggiungi**. I risultati della ricerca vengono filtrati in base al server di pubblicazione dell'app (**app Microsoft**, **app di terze parti** o **app personalizzate**).
    1. Dopo aver scelto l'elenco di app, seleziona **Consenti**.

1. Analogamente, se hai selezionato **Blocca app specifiche e consenti tutte le altre**, cerca e aggiungi le app che vuoi bloccare e quindi seleziona **Blocca**.
1. Selezionare **Salva**.

## <a name="edit-an-app-permission-policy"></a>Modificare un criterio di autorizzazione app

È possibile usare l'interfaccia di amministrazione di Teams per modificare un criterio, inclusi i criteri globali e personalizzati creati.

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams app** > **Criteri di autorizzazione**.
1. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
1. Da lì, apportare le modifiche desiderate. È possibile gestire le impostazioni in base al server di pubblicazione delle app e aggiungere o rimuovere le app in base all'impostazione consenti/blocca.
1. Selezionare **Salva**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Assegnare un criterio di autorizzazione app agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gestire impostazioni app a livello di organizzazione per Government di Microsoft 365  

In un Microsoft 365 government - distribuzione GCC, GCCH e DoD di Teams, tutte le app di terze parti vengono bloccate per impostazione predefinita. Nelle nuvole GCCH e DOD le app di terze parti non sono disponibili. Inoltre, in GCC viene visualizzata la nota seguente sulla gestione di app di terze parti nella pagina criteri di autorizzazione dell'app nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Screenshot dei criteri di autorizzazione per le app in GCCH e DoD.":::

Usare le impostazioni app a livello di organizzazione per controllare se gli utenti possono installare le app di terze parti. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. È possibile usarle per controllare eventuali app dannose o problematiche.

<!---
1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. --->

### <a name="for-gcc-clouds"></a>Per GCC cloud

1. Nella pagina **Gestisci app** seleziona **Impostazioni app a livello di organizzazione**. È possibile quindi configurare le impostazioni desiderate nel pannello.

   ![Screenshot delle impostazioni delle app a livello di organizzazione in GCC.](media/app-permission-policies-gcc-org-wide.png)

1. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    * **Consenti app di terze parti**: questa opzione controlla se gli utenti possono usare app di terze parti. Se si disattiva questa impostazione, gli utenti non potranno installare o usare qualsiasi app di terze parti. In una distribuzione Microsoft 365 Government - GCCH e DoD di Teams, questa impostazione è disattivata per impostazione predefinita.
    * **Consenti nuove app di terze parti pubblicate nello Store per impostazione predefinita**: questa opzione controlla se le nuove app di terze parti pubblicate nell'app store Teams diventano automaticamente disponibili in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

1. In **App bloccate**, aggiungere le app che si desidera bloccare nell'organizzazione. In una distribuzione Microsoft 365 Government - GCCH e DoD di Teams, tutte le app di terze parti vengono aggiunte a questo elenco per impostazione predefinita. Per qualsiasi app di terze parti che si desidera consentire nell'organizzazione, rimuovere l'app da questo elenco delle app bloccate. Quando si blocca un'app a livello di organizzazione, l'app viene bloccata automaticamente per tutti gli utenti, indipendentemente dal fatto che sia consentita nei criteri di autorizzazione dell'app.

1. Seleziona **Salva** per rendere effettive le impostazioni delle app a livello di organizzazione.

Per consentire le app di terze parti, modificare e usare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati.

### <a name="for-gcch-and-dod-clouds"></a>Per le nuvole GCCH e DoD

1. Nella pagina **Criteri di autorizzazione**, selezionare **Impostazioni app a livello di organizzazione**. È possibile quindi configurare le impostazioni desiderate nel pannello.

   ![Screenshot delle impostazioni delle app a livello di organizzazione in GCCH e DoD.](media/app-permission-policies-gcch-dod-org-wide.png)

1. In **App bloccate**, aggiungere le app che si desidera bloccare nell'organizzazione. In una distribuzione Microsoft 365 Government - GCCH e DoD di Teams, tutte le app di terze parti vengono aggiunte a questo elenco per impostazione predefinita. Quando si blocca un'app a livello di organizzazione, l'app viene bloccata automaticamente per tutti gli utenti, indipendentemente dal fatto che sia consentita nei criteri di autorizzazione dell'app.
1. Seleziona **Salva** per rendere effettive le impostazioni delle app a livello di organizzazione.

## <a name="faq"></a>Domande frequenti

### <a name="work-with-app-permission-policies"></a>Usare i criteri di autorizzazione per le app

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Su quali interazioni delle app influiscono i criteri di autorizzazione?

I criteri di autorizzazione disciplinano l'utilizzo dell'app controllando installazione, individuazione e interazione per gli utenti finali. Gli amministratori possono ancora gestire le app nell'interfaccia di amministrazione di Microsoft Teams a prescindere dai criteri di autorizzazione assegnati.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Posso controllare le app line of business (LOB)?

Sì, è possibile usare i criteri di autorizzazione app per controllare l'implementazione e la distribuzione di app LOB personalizzate. È possibile creare un criterio personalizzato o modificare il criterio globale per consentire o bloccare le app personalizzate in base alle esigenze aziendali.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>In che modo i criteri di autorizzazione app riguardano le app aggiunte e i criteri di configurazione?

È possibile usare i criteri di configurazione app insieme ai criteri di autorizzazione app. Le app aggiunte in precedenza vengono selezionate dal set di app consentite per un utente. Inoltre, se un utente dispone di un criterio di autorizzazione app che blocca un'app nel criterio di configurazione app, tale app non comparirà in Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Posso usare i criteri di autorizzazione app per restringere il caricamento delle app personalizzate?

È possibile usare le impostazioni a livello di organizzazione nella pagina **Gestisci app** o i criteri di configurazione per restringere il caricamento delle app personalizzate dell'organizzazione.  

Per limitare il caricamento di app personalizzate da parte di determinati utenti, usare i criteri app personalizzate. Per altre informazioni, vedere [Gestisci criteri e impostazioni app personalizzate in Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Il blocco di un'app si applica anche ai client per dispositivi mobili Teams?

Sì, quando viene bloccata un'app, tale app viene bloccata per tutti i client Teams.  

### <a name="user-experience"></a>Esperienza utente

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Come viene influenzata l'esperienza utente quando un'app viene bloccata?

Gli utenti non possono interagire con un'app bloccata o con le sue funzionalità, come bot, schede ed estensioni per la messaggistica. In un contesto condiviso, come chat di team o gruppi, i bot possono inviare comunque messaggi a tutti i partecipanti di tale contesto. Teams informa l'utente quando un'app è bloccata.

Ad esempio, quando un'app viene bloccata, gli utenti non possono eseguire le attività seguenti:

* Aggiungere l'app personalmente a una chat o a un team
* Inviare messaggi al bot dell'app
* Eseguire azioni pulsante che rimandano informazioni all'app, come messaggi interattivi  
* Visualizzare la scheda dell'app
* Configurare connettori per ricevere notifiche
* Usare l'estensione di messaggistica dell'app

Il portale legacy consentiva di bloccare le app a livello di organizzazione, che significa che quando un'app è bloccata, è bloccata per tutti gli utenti nell'organizzazione. Il blocco di un'app nella pagina [Gestisci app](manage-apps.md) funziona esattamente allo stesso modo.

Per i criteri di autorizzazione app assegnati a utenti specifici, se un'app con funzionalità bot o connettore è stata consentita e quindi bloccata e se l'app è stata consentita solo per alcuni utenti in un contesto condiviso, i membri di una chat di gruppo o di un canale che non dispongono dell'autorizzazione a quell'app possono vedere la cronologia messaggi e i messaggi pubblicati dal bot o connettore, ma non possono interagire con essi.

## <a name="see-also"></a>Vedere anche

* [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
* [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
* [confronto Teams disponibilità delle funzionalità](/office365/servicedescriptions/teams-service-description#feature-availability)
