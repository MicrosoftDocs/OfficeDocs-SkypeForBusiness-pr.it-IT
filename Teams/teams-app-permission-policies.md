---
title: Gestire i criteri di autorizzazione app in Microsoft Teams
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
description: Ulteriori informazioni sui criteri di autorizzazione app in Microsoft Teams e su come usarli per controllare quali applicazioni sono disponibili per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802496"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gestire i criteri di autorizzazione app in Microsoft Teams

Gli amministratori possono usare i criteri di autorizzazione app per controllare quali app sono disponibili per gli utenti di Microsoft Teams dell'organizzazione. È possibile consentire o bloccare tutte le app o determinate app pubblicate da Microsoft, da terze parti e dall'organizzazione. Quando si blocca un'app, gli utenti a cui è assegnato il criterio non possono a installarla dallo store delle app di Teams. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

È possibile gestire i criteri di autorizzazione app nell'interfaccia di amministrazione di Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.

![Screenshot di un criterio di autorizzazione app](media/app-permission-policies.png)

> [!NOTE]
> Le impostazioni app a livello di organizzazione sostituiscono il criterio globale e qualsiasi criterio personalizzato creato e assegnato agli utenti.

Se l'organizzazione è già su Teams, le impostazioni app configurate nelle **impostazioni a livello di tenant** nell'interfaccia di amministrazione di Microsoft 365 vengono rispecchiate nelle impostazioni app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md). Se si usa Teams per la prima volta, per impostazione predefinita tutte le app sono consentite nel criterio globale. Sono incluse le app pubblicate da Microsoft, da terze parti e dall'organizzazione.

Se si volesse bloccare tutte le app di terze parti e consentire app specifiche da Microsoft per il team HR nell'organizzazione. Per prima cosa, è necessario passare alla pagina [Gestisci app](manage-apps.md) e assicurarsi che tutte le app che si desidera consentire per il team HR siano consentite a livello di organizzazione. Quindi, creare un criterio personalizzato denominato Criterio di autorizzazione app HR, impostarlo in modo tale da bloccare e consentire le app desiderate e assegnarlo agli utenti del team HR.

> [!NOTE]
> Se si distribuisce Teams in un ambiente Government Community Cloud (GCC) di Microsoft 365, vedere [Gestisci le impostazioni app a livello di organizzazione per Government di Microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) per ulteriori informazioni sulle impostazioni app di terze parti proprie di GCC.

## <a name="create-a-custom-app-permission-policy"></a>Creare un criterio di autorizzazione app personalizzato

Se si vuole controllare le app disponibili per diversi gruppi di utenti dell'organizzazione, è possibile creare e assegnare uno o più criteri di autorizzazione app personalizzati. È possibile creare e assegnare criteri personalizzati in base a chi pubblica le app: Microsoft, terze parti o l'organizzazione. È importante sapere che, dopo aver creato un criterio personalizzato, non sarà possibile cambiarlo se le app di terze parti sono disabilitate nelle impostazioni app a livello di organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Criteri di autorizzazione**.
2. Fare clic su **Aggiungi**. <br>
    ![Screenshot di un nuovo criterio di autorizzazione app](media/app-permission-policies-new-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. In **App Microsoft**, **App di terze parti** e **App personalizzate**, selezionare una delle seguenti opzioni:

    - **Consenti tutte le app**
    - **Consenti app specifiche e blocca tutte le altre**
    - **Blocca app specifiche e consenti tutte le altre**
    - **Blocca tutte le app**

5. Se si seleziona **Consenti app specifiche e blocca le altre**, aggiungere le app che si desidera consentire:

    1. Selezionare **Consenti app**.
    1. Cercare le app che si desidera consentire e fare clic su **Aggiungi**. I risultati della ricerca vengono filtrati in base al server di pubblicazione dell'app (**app Microsoft**, **app di terze parti** o **app personalizzate**).
    1. Una volta scelto l'elenco delle app, fare clic su **Consenti**. 

6. Analogamente, se si seleziona **Blocca app specifiche e consenti tutte le altre**, cercare e aggiungere le app che si desidera bloccare, quindi fare clic su **Blocca**.
7. Fare clic su **Salva**.

## <a name="edit-an-app-permission-policy"></a>Modificare un criterio di autorizzazione app

È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi il criterio globale e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Criteri di autorizzazione**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Da lì, apportare le modifiche desiderate. È possibile gestire le impostazioni in base al server di pubblicazione delle app e aggiungere o rimuovere le app in base all'impostazione consenti/blocca.
4. Fare clic su **Salva**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Assegnare un criterio di autorizzazione app agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gestire impostazioni app a livello di organizzazione per Government di Microsoft 365  

Nell'ambito della distribuzione GCC di Microsoft 365 di Teams, è importante sapere quanto segue in merito alle impostazioni app di terze parti, proprie di GCC.

In GCC, tutte le app di terze parti vengono bloccate per impostazione predefinita. Inoltre, verrà visualizzata la seguente nota in merito alla gestione delle app di terze parti nella pagina dei criteri di autorizzazione app nell'interfaccia di amministrazione di Microsoft Teams.

![Screenshot di un criterio di autorizzazione app in GCC](media/app-permission-policies-gcc.png)

Usare le impostazioni app a livello di organizzazione per controllare se gli utenti possono installare le app di terze parti. Le impostazioni app a livello di organizzazione disciplinano il comportamento di tutti gli utenti e sostituiscono qualsiasi criterio di autorizzazione app assegnato agli utenti. È possibile usarle per controllare eventuali app dannose o problematiche.

1. Nella pagina **Criteri di autorizzazione**, selezionare **Impostazioni app a livello di organizzazione**. È possibile quindi configurare le impostazioni desiderate nel pannello.

    ![Screenshot di impostazioni app a livello di organizzazione](media/app-permission-policies-gcc-org-wide.png)
    
2. In **App di terze parti**, disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consenti app di terze parti**: questa impostazione controlla se gli utenti possono usare app di terze parti. Se si disattiva questa impostazione, gli utenti non potranno installare o usare qualsiasi app di terze parti. Nell'ambito della distribuzione GCC di Microsoft 365 di Teams, questa impostazione è disattivata per impostazione predefinita.
    - **Consenti qualsiasi nuova app di terze parti pubblicata nello Store per impostazione predefinita**: questa impostazione consente di controllare se eventuali nuove app di terze parti pubblicate nello Store di Teams diventano disponibili automaticamente in Teams. È possibile impostare questa opzione solo se si consentono le app di terze parti.

3. In **App bloccate**, aggiungere le app che si desidera bloccare nell'organizzazione. Nell'ambito della distribuzione GCC di Microsoft 365 di Teams, tutte le app di terze parti vengono aggiunte all'elenco per impostazione predefinita. Per qualsiasi app di terze parti che si desidera consentire nell'organizzazione, rimuovere l'app da questo elenco delle app bloccate. Quando si blocca un'app a livello di organizzazione, l'app viene bloccata automaticamente per tutti gli utenti, che sia consentita o meno dai criteri di autorizzazione app.
4. Fare clic su **Salva** per fare in modo che le impostazioni app a livello di organizzazione abbiano effetto.

Come indicato in precedenza, per consentire app di terze parti è possibile modificare e usare il criterio globale (a livello di organizzazione, per impostazione predefinita) o creare e assegnare criteri personalizzati.

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-permission-policies"></a>Lavorare con i criteri di autorizzazione app

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

Ad esempio, quando un'app è bloccata gli utenti non possono eseguire le seguenti operazioni:

- Aggiungere l'app personalmente a una chat o a un team
- Inviare messaggi al bot dell'app
- Eseguire azioni pulsante che rimandano informazioni all'app, come messaggi interattivi  
- Visualizzare la scheda dell'app
- Configurare connettori per ricevere notifiche
- Usare l'estensione per la messaggistica dell'app

Il portale legacy consentiva di bloccare le app a livello di organizzazione, che significa che quando un'app è bloccata, è bloccata per tutti gli utenti nell'organizzazione. Il blocco di un'app nella pagina [Gestisci app](manage-apps.md) funziona esattamente allo stesso modo.

Per i criteri di autorizzazione app assegnati a utenti specifici, se un'app con funzionalità bot o connettore è stata consentita e quindi bloccata e se l'app è stata consentita solo per alcuni utenti in un contesto condiviso, i membri di una chat di gruppo o di un canale che non dispongono dell'autorizzazione a quell'app possono vedere la cronologia messaggi e i messaggi pubblicati dal bot o connettore, ma non possono interagire con essi.

## <a name="related-topics"></a>Argomenti correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
