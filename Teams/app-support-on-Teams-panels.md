---
title: Microsoft Teams app line-of-business (LINEB) in Teams pannelli
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Descrive il supporto per Teams app o app LOB.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591220"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams app line-of-business (LINEB) in Teams pannelli

Teams pannello di controllo sta aggiungendo il supporto per Teams app/app Line of Business (LOB). In questo modo le aziende potranno aggiungere esperienze aggiuntive nei pannelli per soddisfare le esigenze dell'organizzazione. Questa versione supporta contenuto Web statico.

> [!IMPORTANT]
> Questa funzionalità è disponibile solo dopo l'aggiornamento dei Teams dei pannelli. Devi avere la versione dell'app Teams 1449/1.0.97.2021070601 o successiva per avere il supporto dell'app all'interno di Teams pannelli.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurare e gestire app Teams pannelli nell'Teams di amministrazione 

Microsoft Teams app portano informazioni chiave, strumenti comuni e processi attendibili in cui le persone raccolgono, imparano e lavorano. Teams app funzionano [tramite funzionalità integrate.](/platform/concepts/capabilities-overview) Ora, in quanto amministratore IT, puoi scegliere quali app includere nel dispositivo dei pannelli di Teams dell'organizzazione e personalizzare le autorizzazioni tramite l'interfaccia di amministrazione di Teams.

Ora puoi usare le app Teams su Teams e personalizzare l'esperienza utente in base alle esigenze dell'organizzazione. Puoi decidere a quale app Web gli utenti possono accedere e usare e definire le priorità per le visualizzazioni dell'app. Alcune opzioni, come il bot e le funzionalità di messaggistica, non sono attualmente supportate. Altre informazioni sulle app Teams e su come gestire i dispositivi in Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gestire le app nei Teams dell'Teams di amministrazione

**Nota:** devi essere un amministratore globale o un amministratore Teams servizio per accedere all'Teams di amministrazione.

Gli utenti finali possono visualizzare ma non installare app Teams pannelli. Gli amministratori possono visualizzare e gestire tutte le app Teams per l'organizzazione tramite l'Teams di amministrazione. Altre informazioni su come gestire le app nell'Microsoft Teams di amministrazione tramite **la pagina Gestisci** app. La **pagina Gestisci app** nell'Teams di amministrazione è anche la posizione in cui puoi caricare app [personalizzate.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Dopo aver configurato le app, puoi usare i criteri di autorizzazione delle [app](/teams-app-permission-policies) e i criteri di configurazione delle app per configurare l'esperienza [dell'app](/teams-app-setup-policies) per account sala specifici nell'organizzazione.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Aggiungere app nei Teams con i criteri di configurazione delle app

Poiché Teams offre la possibilità di visualizzare un'ampia gamma di app, gli amministratori possono decidere quali app sono più essenziali  per l'organizzazione e aggiungere solo queste per la schermata home dei pannelli di Teams per un accesso rapido. Se sono presenti più di cinque app aggiunte o app non aggiunte, verranno visualizzate nella **schermata Altro.** Microsoft consiglia di creare criteri di configurazione dell'app personalizzati specifici per Teams pannelli.

![Screenshot dell'interfaccia utente della pagina dei criteri di configurazione dell'app.](media/appsetup1.png) 

Per gestire le app aggiunte visualizzate nei pannelli di Teams, accedere all'interfaccia di amministrazione di Teams per l'organizzazione e passare **Teams Criteri** di installazione delle app Selezionare o Creare un nuovo criterio App \>  \>  \> aggiunte.

![Screenshot della sezione app aggiunte nell'interfaccia utente.](media/appsetup2.png) 

Microsoft consiglia di disattivare Upload **app** personalizzate e Consenti l'aggiunta degli utenti per la migliore esperienza Teams'app nei Teams personalizzati. 

Per altre informazioni sull'aggiunta di app, vedi [Gestire i criteri di configurazione delle app.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Gestire l'ordine di visualizzazione delle app Teams pannelli 

![Screenshot della sezione app nell'interfaccia utente.](media/appsetup3.png) 

Per gestire l'ordine di visualizzazione delle app nei pannelli di Teams, accedere all'interfaccia di amministrazione di Teams per l'organizzazione e passare **Teams criteri** di installazione delle app Selezionare i criteri App aggiunte: Sposta \>  \>  \>  **su/giù**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Assegnazione di criteri di installazione a un account di risorsa sala

Dopo aver creato il criterio di configurazione, l'amministratore dovrà assegnare questo criterio all'account della risorsa sala che verrà eseguito l'accesso ai pannelli Teams chat. Per ulteriori informazioni, vedere [Assegnare criteri a utenti e gruppi.](/assign-policies-users-and-groups)

## <a name="faq"></a>Domande frequenti

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Quanto tempo è necessario per Teams per ottenere i criteri di configurazione delle app nuovi o aggiornati?

Dopo aver modificato o assegnato nuovi criteri nell'Teams di amministrazione, possono essere necessarie fino a 24 ore per l'applicazione delle modifiche. Gli amministratori possono provare a disconnettersi/accedere dal pannello, toccare l'icona Impostazioni e tornare alla **schermata Home** per provare **ad** aggiornare i criteri.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Qual è l'ordinamento delle app nella schermata "Altro"?

Nella pagina **Altre** app verranno visualizzate per prime le app aggiunte. Quindi, tutte le altre app installate verranno visualizzate in ordine alfabetico.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Perché le app bot non vengono visualizzate Teams pannelli?

Al momento è supportato solo il contenuto Web delle schede statiche.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Perché le app Teams native, ad esempio Calendario e Attività, non vengono visualizzate Teams pannelli?

Le Teams native, ad esempio Calendario e Attività, non vengono visualizzate Teams pannelli.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Nell'Teams di amministrazione, nella sezione Criteri di installazione, qual è la differenza tra le app installate e le app aggiunte?

Per Teams, Microsoft consiglia di usare le app aggiunte, in modo che l'amministratore sia in grado di selezionare l'app desiderata e riorganizzare l'ordinamento.

**Nota:** Alcune app non supportano l'aggiunta di app. Contatta lo sviluppatore dell'app per abilitare la funzionalità di aggiunta delle app.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Perché altre app vengono visualizzate nella schermata "Altro" anche se non fanno parte delle app installate o aggiunte nella sezione dei criteri di configurazione delle app Teams app?

Se le app sono state installate in precedenza tramite altri criteri app o manualmente nei client desktop/Web di Teams per l'account della risorsa sala usato nei pannelli di Teams, l'amministratore potrebbe dover accedere all'account della risorsa sala in Teams e disinstallare manualmente le app facendo clic con il pulsante destro del mouse sull'app, quindi selezionando **Disinstalla**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non è possibile trovare un'app nel riquadro "Aggiungi app aggiunte"?

Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione dell'app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere aggiunte, cerca l'app nel **riquadro Aggiungi app aggiunte.** Per altre informazioni, fai riferimento alle domande frequenti [in Utilizzo dei criteri di configurazione delle app.](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>Perché viene visualizzato un popup "Consenti aggiunta utente" nel pannello dei criteri di configurazione dopo aver disattivato "Consenti l'aggiunta di utenti?"

![Screenshot of the setup policy section within the user interface with a pop-up confirming user pinning is active.](media/appsetup4.png) 

Questo comportamento è previsto per un dispositivo in uno spazio condiviso e consente di evitare l'aggiunta involontaria di app.
