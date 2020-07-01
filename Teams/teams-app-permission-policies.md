---
title: Gestire i criteri di autorizzazione delle app in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni sui criteri di autorizzazione delle app in Microsoft teams e su come usarli per controllare quali app sono disponibili per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 83a06357402b44c5c15932211e562e488c2a2d5a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938475"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gestire i criteri di autorizzazione delle app in Microsoft Teams

Gli amministratori possono usare i criteri di autorizzazione app per controllare quali app sono disponibili per gli utenti di Microsoft Teams dell'organizzazione. È possibile consentire o bloccare tutte le app o le app specifiche pubblicate da Microsoft, da terze parti e dall'organizzazione. Quando si blocca un'app, gli utenti a cui è assegnato il criterio non possono a installarla dallo store delle app di Teams. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

Puoi gestire i criteri di autorizzazione delle app nell'interfaccia di amministrazione di Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Dopo aver modificato o assegnato un criterio, le modifiche apportate potrebbero richiedere qualche ora.

![Screenshot dei criteri di autorizzazione delle app](media/app-permission-policies.png)

> [!NOTE]
> Le impostazioni dell'app a livello di organizzazione eseguono l'override dei criteri globali e di tutti i criteri personalizzati creati e assegnati agli utenti.

Se l'organizzazione è già in teams, le impostazioni dell'app configurate in **impostazioni a livello di tenant** nell'interfaccia di amministrazione di Microsoft 365 si riflettono nelle impostazioni dell'app a livello di organigramma nella pagina [Manage Apps](manage-apps.md) . Se non si ha familiarità con i team e si è appena iniziato, per impostazione predefinita tutte le app sono consentite nel criterio globale. Sono incluse le app pubblicate da Microsoft, terze parti e dall'organizzazione.

Supponi ad esempio di voler bloccare tutte le app di terze parti e consentire ad app specifiche di Microsoft per il team HR dell'organizzazione. Prima di tutto, devi accedere alla pagina [Gestisci app](manage-apps.md) e verificare che le app che vuoi consentire al team HR siano consentite a livello di organizzazione. Crea quindi un criterio personalizzato denominato criteri di autorizzazione per le app HR, impostalo per bloccare e consentire le app desiderate e assegnalo agli utenti nel team HR.

> [!NOTE]
> Se i team sono stati distribuiti in un ambiente governativo-GCC di Microsoft 365, vedere [criteri di autorizzazione delle app per GCC](#app-permission-policies-for-gcc) per altre informazioni sulle impostazioni dell'app di terze parti che sono univoche per GCC.

## <a name="create-a-custom-app-permission-policy"></a>Creare un criterio di autorizzazione per le app personalizzate

Per controllare le app disponibili per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri di autorizzazione per le app personalizzate. È possibile creare e assegnare criteri personalizzati distinti a seconda che le app vengano pubblicate da Microsoft, da terze parti o dall'organizzazione. È importante sapere che dopo aver creato un criterio personalizzato, non è possibile modificarlo se le app di terze parti sono disabilitate nelle impostazioni dell'app a livello di organizzazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di autorizzazione delle **app teams**  >  **Permission policies**.
2. Fare clic su **Aggiungi**. <br>
    ![Schermata dei criteri di autorizzazione per i nuovi app](media/app-permission-policies-new-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. In app **Microsoft**, **app di terze parti**e **app personalizzate**seleziona una delle opzioni seguenti:

    - **Consenti tutte le app**
    - **Consenti app specifiche e blocca tutte le altre**
    - **Bloccare app specifiche e consentire a tutti gli altri utenti**
    - **Bloccare tutte le app**

5. Se è stata selezionata l'opzione **Consenti app specifiche e blocca altre**, aggiungere le app che si vuole consentire:

    1. Selezionare **Consenti app**.
    1. Cercare le app che si desidera consentire e quindi fare clic su **Aggiungi**. I risultati della ricerca vengono filtrati in Publisher di app (app**Microsoft**, app di **terze parti**o **app personalizzate**).
    1. Dopo aver scelto l'elenco di app, fare clic su **Consenti**. 

6. Allo stesso modo, se si è selezionato **Blocca app specifiche e si consente a tutti gli altri utenti**, cercare e aggiungere le app da bloccare e quindi fare clic su **blocca**.
7. Fare clic su **Salva**.

## <a name="edit-an-app-permission-policy"></a>Modificare i criteri di autorizzazione delle app

È possibile usare l'interfaccia di amministrazione di Microsoft teams per modificare un criterio, inclusi i criteri globali e i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di autorizzazione delle **app teams**  >  **Permission policies**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Da qui apportare le modifiche desiderate. Puoi gestire le impostazioni in base all'App Publisher e aggiungere e rimuovere app in base all'impostazione Consenti/blocca.
4. Fare clic su **Salva**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Assegnare un criterio di autorizzazione app personalizzata agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="app-permission-policies-for-gcc"></a>Criteri di autorizzazione dell'app per GCC

In Microsoft 365 Government-GCC Deployment of teams è importante conoscere le informazioni seguenti sulle impostazioni dell'app di terze parti, che sono univoche per GCC.

In GCC tutte le app di terze parti sono bloccate per impostazione predefinita. Verranno inoltre visualizzate le note seguenti sulla gestione delle app di terze parti nella pagina Criteri di autorizzazione dell'app nell'interfaccia di amministrazione di Microsoft teams.

![Screenshot dei criteri di autorizzazione delle app in GCC](media/app-permission-policies-gcc.png)

Per abilitare un'app di terze parti per un utente o un gruppo di utenti dell'organizzazione, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle app **Teams**  >  **Manage Apps**e quindi, nell'elenco delle app, verifica che l'app di terze parti che vuoi consentire a un set di utenti sia impostata su **bloccato** a livello di organizzazione.

2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di autorizzazione delle **app teams**  >  **Permission policies**e quindi modificare il criterio globale per bloccare l'app di terze parti. Procedi come segue.
    1. Nella pagina Criteri di autorizzazione dell'app fare clic su **globale (impostazione predefinita a livello di organizzazione)**, quindi fare clic su **modifica**.
    2. In **app di terze parti**selezionare **Blocca app specifiche e Consenti a tutti gli altri utenti**di aggiungere l'app e quindi fare clic su **Salva**.

    > [!NOTE]
    > È importante eseguire questa operazione prima di procedere con il passaggio successivo per consentire l'app a livello di organizzazione. Questo perché se l'app di terze parti non è bloccata nei criteri di autorizzazione dell'app globale, tutti gli utenti a cui si applica il criterio globale potranno accedere all'app di terze parti quando la consentirai a livello di organizzazione.

3. Consenti all'app di terze parti a livello di organizzazione. A questo scopo, nella barra di spostamento sinistra, vai a **app teams**  >  **Gestisci app**. Nell'elenco delle app fare clic a sinistra del nome dell'app per selezionare l'app e quindi selezionare **Consenti**.
4. [Crea un criterio di autorizzazione per l'app personalizzata](#create-a-custom-app-permission-policy) per consentire l'app e quindi [assegna i criteri](#assign-a-custom-app-permission-policy-to-users) agli utenti desiderati.

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-permission-policies"></a>Uso dei criteri di autorizzazione delle app

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quali interazioni delle app influenzano i criteri di autorizzazione?
I criteri di autorizzazione regolano l'utilizzo dell'app controllando installazione, individuazione e interazione per gli utenti finali. Gli amministratori possono comunque gestire le app nell'interfaccia di amministrazione di Microsoft teams indipendentemente dai criteri di autorizzazione assegnati.

#### <a name="can-i-control-line-of-business-lob-apps"></a>È possibile controllare le app line of business (LOB)?
Sì, è possibile usare i criteri di autorizzazione delle app per controllare l'implementazione e la distribuzione delle app personalizzate (line-of-business). È possibile creare criteri personalizzati o modificare i criteri globali per consentire o bloccare le app personalizzate in base alle esigenze dell'organizzazione.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>In che modo i criteri di autorizzazione delle app sono correlati alle app e ai criteri di configurazione delle app bloccati?

Puoi usare i criteri di configurazione delle app insieme ai criteri di autorizzazione per le app. Le app predefinite vengono selezionate dal set di app abilitate per un utente. Inoltre, se un utente ha un criterio di autorizzazione per le app che blocca un'app nei criteri di configurazione dell'app, l'app non verrà visualizzata in teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>È possibile usare I criteri di autorizzazione delle app per limitare il caricamento di app personalizzate?

Puoi usare le impostazioni a livello di organizzazione nella pagina **Gestisci app** o i criteri di configurazione dell'app per limitare il caricamento di app personalizzate per l'azienda.  

Per limitare utenti specifici al caricamento di app personalizzate, USA criteri per le app personalizzate. Per altre informazioni, vedere [gestire i criteri e le impostazioni dell'app personalizzata in teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Il blocco di un'app si applica ai client per dispositivi mobili Teams?

Sì, quando blocchi un'app, l'app viene bloccata in tutti i client di teams.  

### <a name="user-experience"></a>Esperienza utente

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Che cosa fa un'esperienza utente quando un'app viene bloccata?

Gli utenti non possono interagire con un'app bloccata o le relative funzionalità, ad esempio bot, schede e estensioni di messaggistica. In un contesto condiviso, ad esempio un team o una chat di gruppo, i bot possono comunque inviare messaggi a tutti i partecipanti al contesto. Teams indica all'utente quando un'app è bloccata.

Ad esempio, quando un'app viene bloccata, gli utenti non possono eseguire una delle operazioni seguenti:

- Aggiungere l'app personalmente o in una chat o in un team
- Inviare messaggi al bot dell'app
- Eseguire le azioni dei pulsanti che restituiscono informazioni all'app, ad esempio i messaggi di azione  
- Visualizzare la scheda dell'app
- Configurare i connettori per la ricezione delle notifiche
- Usare l'estensione di messaggistica dell'app

Il portale Legacy ha consentito il controllo delle app a livello di organizzazione, il che significa che quando un'app viene bloccata, è bloccata per tutti gli utenti dell'organizzazione. Il blocco di un'app nella pagina [Gestisci app](manage-apps.md) funziona esattamente nello stesso modo.

Per i criteri di autorizzazione delle app assegnati a utenti specifici, se è stata consentita un'app con un bot o una funzionalità di connessione e quindi è stata bloccata e se l'app è consentita solo per alcuni utenti in un contesto condiviso, i membri di una chat di gruppo o di un canale che non hanno l'autorizzazione per l'app possono vedere la cronologia dei messaggi inviati dal bot , ma non può interagire con essa.

## <a name="related-topics"></a>Argomenti correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare criteri agli utenti in teams](assign-policies.md)
