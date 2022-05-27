---
title: supporto per app Microsoft Teams/line-of-business su pannelli Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Descrive il supporto per le app Teams/le app line-of-business.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f9d2e3b17f852dcd020dc11c323bbc24c2dfc30
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675908"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>supporto per app Microsoft Teams/line-of-business su pannelli Teams

Teams pannelli aggiunge il supporto per [app Teams o app line-of-business](/microsoftteams/platform/overview). In questo modo le aziende potranno aggiungere altre esperienze nei pannelli in base alle esigenze dell'organizzazione. Questa versione supporta contenuto Web statico.

> [!IMPORTANT]
> Questa funzionalità è disponibile solo dopo l'aggiornamento dei dispositivi dei pannelli Teams. È necessario avere l'app Teams versione 1449/1.0.97.2021070601 o successiva per avere il supporto dell'app all'interno di Teams pannelli.

## <a name="teams-app-experience-on-teams-panels"></a>Teams'esperienza dell'app nei pannelli Teams

![Screenshot dell'interfaccia di amministrazione di Teams che mostra quale sezione consentirà agli utenti di passare alle app.](media/tac1update.png)

*La schermata iniziale dei pannelli Teams include le opzioni di spostamento dell'app, indicate nello screenshot in rosso. Si noti che queste sono icone di esempio e potrebbero non essere disponibili per l'uso.*

![Screenshot dell'area di disegno dell'app in cui è possibile aggiungere app.](media/appscreen.png)

*Quando un utente tocca una delle icone dell'app, vedrà la schermata dell'app Teams visualizzata nello screenshot precedente. Il rettangolo grigio nello screenshot è la posizione in cui le app vengono visualizzate nel Pannello di Teams. La barra dell'app è fissa e parte dell'app Teams pannelli.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurare e gestire le app Teams pannelli nell Teams interfaccia di amministrazione

Microsoft Teams app portano informazioni chiave, strumenti comuni e processi attendibili in cui le persone si riuniscono, imparano e lavorano. Teams le app [funzionano con funzionalità integrate](/microsoftteams/platform/concepts/capabilities-overview). Ora, gli amministratori IT possono scegliere quali app includere nel dispositivo dei pannelli di Teams dell'organizzazione e personalizzare le autorizzazioni tramite [l'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/).

È ora possibile usare le app Teams nei pannelli Teams e personalizzare l'esperienza utente in base alle esigenze dell'organizzazione. È possibile decidere quale app Web gli utenti possono accedere e usare e assegnare priorità alle visualizzazioni dell'app. Alcune opzioni, come bot e funzionalità di messaggistica, non sono attualmente supportate. Altre informazioni [sulle app Teams](/microsoftteams/platform/overview) e [su come gestire i dispositivi in Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gestire le app nei pannelli Teams nell'interfaccia di amministrazione di Teams

**Nota**: per accedere all'interfaccia di amministrazione di Teams, è necessario essere un amministratore globale o un amministratore del servizio [Teams](https://admin.teams.microsoft.com/).

Gli utenti finali possono visualizzare ma non installare le app nei pannelli Teams. Gli amministratori possono visualizzare e gestire tutte le app Teams per l'organizzazione tramite l'interfaccia di amministrazione di Teams. Altre informazioni su come [gestire le app nell'interfaccia di amministrazione di Microsoft Teams](/microsoftteams/manage-apps) tramite la pagina **Gestisci app**. La pagina **Gestisci app** all'interno dell'interfaccia di amministrazione di Teams consente anche di caricare [app personalizzate](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

Dopo aver configurato le app, è possibile usare i [criteri di autorizzazione delle app](/microsoftteams/teams-app-permission-policies) e i criteri di configurazione delle [app](/microsoftteams/teams-app-setup-policies) per configurare l'esperienza dell'app per specifici account della sala nell'organizzazione.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Aggiungere app nei pannelli Teams con i criteri di configurazione delle app

Poiché Teams offre la possibilità di visualizzare un'ampia gamma di app, gli amministratori possono decidere quali app sono più essenziali per l'organizzazione e aggiungerle solo per la schermata **iniziale** dei pannelli Teams per un accesso rapido. Se sono presenti più di cinque app aggiunte o quelle rimosse, verranno visualizzate sotto la schermata **Altro** . Microsoft consiglia di creare criteri di configurazione delle app personalizzati specifici per i pannelli Teams.

![Screenshot dell'interfaccia utente della pagina dei criteri di configurazione dell'app.](media/appsetup1.png)

Per gestire le app aggiunte visualizzate nei pannelli Teams, accedere all'interfaccia di amministrazione di Teams dell'organizzazione e passare alle **app** \> Teams **Criteri di configurazione** \> **Selezionare o creare un nuovo criterio** \> **App aggiunte**.

![Screenshot della sezione app aggiunte all'interno dell'interfaccia utente.](media/appsetup2.png)

*Le app incluse in questa immagine sono solo esempi e potrebbero non essere disponibili per l'uso.*

Microsoft consiglia di disattivare **Upload app personalizzate** e **l'aggiunta da parte dell'utente** per un'esperienza ottimale Teams app nei pannelli Teams.

Per altre informazioni sull'aggiunta di app, vedere [Gestire i criteri di configurazione delle app](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gestire l'ordine di visualizzazione delle app nei pannelli Teams

![Screenshot della sezione delle app all'interno dell'interfaccia utente.](media/appsetup3.png)

*Le app incluse in questa immagine sono solo esempi e potrebbero non essere disponibili per l'uso.*

Per gestire l'ordine in cui le app vengono visualizzate nei pannelli Teams, accedere all'interfaccia di amministrazione Teams dell'organizzazione e passare ai criteri di **configurazione** \> **delle app** \> Teams **Selezionare le** \> **app aggiunte** ai criteri: **Spostarti verso l'alto o verso il basso**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Assegnazione di criteri di configurazione a un account delle risorse della chat room

Dopo aver creato i criteri di configurazione, l'amministratore dovrà assegnare questo criterio all'account delle risorse della chat room che verrà connesso ai pannelli Teams. Per altre informazioni, vedere [Assegnare criteri a utenti e gruppi](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>Domande frequenti

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Quanto tempo è necessario per Teams pannelli per ottenere i criteri di configurazione delle app nuovi o aggiornati?

Dopo aver modificato o assegnato nuovi criteri nell'interfaccia di amministrazione di Teams, l'applicazione delle modifiche può richiedere fino a 24 ore. Gli amministratori possono provare a disconnettersi/accedere dal riquadro, toccare l'icona **Impostazioni** e tornare alla schermata **iniziale** per provare ad aggiornare i criteri.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Qual è l'ordine delle app nella schermata "Altro"?

Nella pagina **Altre** app le app aggiunte verranno visualizzate per prime. Quindi, tutte le altre app installate verranno visualizzate in ordine alfabetico.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Perché le app bot non vengono visualizzate nei pannelli Teams?

Al momento è supportato solo il contenuto Web delle schede statiche.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Perché le app Teams native, ad esempio Calendario e Attività, non vengono visualizzate sui pannelli Teams?

Le app Teams native, ad esempio Calendario e Attività, non vengono visualizzate nei pannelli Teams.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Nella sezione Criteri di configurazione dell'interfaccia di amministrazione di Teams qual è la differenza tra le app installate e le app aggiunte?

Per Teams pannelli, Microsoft consiglia di usare le app aggiunte, in modo che l'amministratore possa selezionare l'app desiderata e riorganizzarne l'ordinamento.

**Nota:** Alcune app non supportano l'aggiunta di app. Contatta lo sviluppatore dell'app per abilitare la funzionalità di aggiunta dell'app.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Perché altre app vengono visualizzate nella schermata "Altro" anche se non fanno parte delle app installate o aggiunte nella sezione dei criteri di configurazione delle app Teams?

Se le app sono state installate in precedenza tramite altri criteri dell'app o manualmente nei client desktop/Web Teams per l'account delle risorse della chat room usato nei pannelli Teams, l'amministratore potrebbe dover accedere all'account delle risorse della chat room in Teams e disinstallare manualmente le app facendo clic con il pulsante destro del mouse sull'app e scegliendo **Disinstalla**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non riesco a trovare un'app nel riquadro "Aggiungi app aggiunte"?

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cerca l'app nel riquadro **Aggiungi app aggiunte** . Per altre informazioni, fai riferimento alle [domande frequenti in Uso dei criteri di configurazione delle app](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Perché viene visualizzato un popup "Blocco utente" nel riquadro criteri di configurazione dopo la disattivazione di "Aggiunta utente"

![Screenshot della sezione dei criteri di configurazione all'interno dell'interfaccia utente con una finestra popup che conferma che l'aggiunta dell'utente è attiva.](media/appsetup4.png)

*Le app incluse in questa immagine sono solo esempi e potrebbero non essere disponibili per l'uso.*

Questo comportamento è previsto per un dispositivo in uno spazio condiviso e contribuisce a prevenire l'aggiunta accidentale di app.
