---
title: Usare l'onboarding guidato di Frontline Worker per rendere operativa la forza lavoro in prima linea
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare la procedura guidata di onboarding dei frontline worker per distribuire rapidamente un'esperienza in Teams personalizzata per i frontline worker e i responsabili dell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac4db418927c34920614c65d6f94a400ff116a91
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703682"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usare l'onboarding guidato di Frontline Worker per rendere operativa la forza lavoro in prima linea

## <a name="overview"></a>Panoramica

La procedura guidata di onboarding dei frontline worker nel interfaccia di amministrazione di Microsoft 365 semplifica l'onboarding dei frontline worker all'organizzazione. La procedura guidata consente di distribuire rapidamente un'esperienza in Microsoft Teams su misura per la forza lavoro in prima linea. Con la procedura guidata è possibile avviare facilmente la distribuzione pilota di Teams per gli operatori in prima linea nell'organizzazione.

La procedura guidata configura un team per gli operatori in prima linea e assegna licenze e [pacchetti](manage-policy-packages.md) di criteri a ogni membro del team. È possibile creare il team da zero o da un [modello di team](get-started-with-teams-templates-in-the-admin-console.md), quindi aggiungere utenti e assegnare ruoli. Il ruolo determina il pacchetto di criteri assegnato dalla procedura guidata a ogni utente.

Attualmente, la procedura guidata supporta l'aggiunta di 100 utenti ogni volta che viene eseguita. Stiamo lavorando per aumentare il numero di utenti per ogni esecuzione a breve. Ricontrollare qui per gli aggiornamenti più recenti.

La procedura guidata è disponibile per tutte le organizzazioni che hanno almeno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline). È possibile eseguire la procedura guidata il numero di volte necessario per distribuire Teams al personale in prima linea in posizioni o siti diversi all'interno dell'organizzazione.

Guardare questo breve video per una panoramica su come eseguire la procedura guidata per eseguire l'onboarding della forza lavoro in prima linea.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Questa procedura guidata consente di eseguire rapidamente l'onboarding della forza lavoro in prima linea per Teams tramite il interfaccia di amministrazione di Microsoft 365. Per informazioni su come distribuire Teams alla forza lavoro in prima linea con gli script, vedere [Come eseguire il provisioning di Teams su scala per gli operatori in prima linea](flw-scripted-deployment.md).

> [!NOTE]
> La procedura guidata non supporta ancora [le etichette di riservatezza](sensitivity-labels.md) . Se l'organizzazione richiede etichette di riservatezza per creare un team, la procedura guidata non verrà visualizzata nel interfaccia di amministrazione di Microsoft 365.

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

1. Nel riquadro di spostamento sinistro della [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) scegliere **Configura**. Vai alla sezione **App e posta elettronica** e quindi in Funzionalità di gestione della **forza lavoro in prima linea** seleziona **Visualizza**. Qui puoi trovare altre informazioni sulle funzionalità offerte da Microsoft 365 for frontline workers.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Screenshot della pagina dei dettagli per l'esperienza di onboarding di Frontline Worker nella interfaccia di amministrazione di Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Quando sei pronto, seleziona **Attività iniziali** per eseguire la procedura guidata.

3. Immettere un nome per il team, aggiungere uno o più proprietari del team e selezionare un'impostazione di privacy. Scegliere quindi se creare il team da zero o da un modello di team. I modelli di team includono canali e schede predefiniti, che ottimizzano il team per specifiche esigenze aziendali o progetti.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Screenshot della pagina Configura un team della procedura guidata" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Aggiungere utenti al team. È anche possibile aggiungere gruppi. Se si aggiungono gruppi, tenere presente che le licenze e i pacchetti di criteri vengono assegnati direttamente a ogni utente del gruppo, non al gruppo stesso.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Screenshot della pagina Aggiungi utenti della procedura guidata in cui si aggiungono utenti e gruppi al team" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Assegnare uno dei ruoli seguenti a ogni membro del team: Frontline Worker, Frontline Manager, Nessuno. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Screenshot della pagina Assegna ruoli di lavoro della procedura guidata in cui si assegnano ruoli, posizioni e licenze ai membri del team" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    Assegnando un ruolo Frontline Worker o Frontline Manager, quell'utente riceverà un pacchetto di criteri. Il pacchetto di criteri creerà un'esperienza in Teams su misura per il loro ruolo. Questa esperienza include app e criteri pre-aggiunti per la collaborazione e la comunicazione in linea con i frontline worker e i manager.

    Seleziona quindi una posizione e assegna una licenza Microsoft 365 F a ogni membro del team. Se non si hanno licenze sufficienti, è possibile selezionare **Acquista altre licenze** per acquistare altre licenze.  

6. Scegliere chi riceve il messaggio di posta elettronica di stato al termine della procedura guidata. Il messaggio di posta elettronica contiene informazioni sull'esito positivo e negativo delle azioni eseguite dalla procedura guidata&mdash; creando il team, aggiungendo membri del team e assegnando una licenza e un pacchetto di criteri a ogni membro del team. Usare queste informazioni per risolvere eventuali errori.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Screenshot della pagina Aggiungi destinatari di posta elettronica di stato della procedura guidata" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Rivedere le selezioni e quindi selezionare **Conferma**.

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Screenshot della pagina Rivedi il team della procedura guidata in cui si rivedi le impostazioni del team" lightbox="media/flw-onboarding-wizard-review-team.png":::

    La procedura guidata crea il team e assegna licenze e pacchetti di criteri ai membri del team. Il completamento potrebbe richiedere alcuni minuti, dopodiché i destinatari scelti ricevono un messaggio di posta elettronica di stato.

8. Sei sulla strada, ma non hai ancora finito! Vedere quindi la sezione [Operazioni da eseguire dopo l'esecuzione della procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

## <a name="what-to-do-after-running-the-wizard"></a>Operazioni da eseguire dopo l'esecuzione della procedura guidata

Dopo aver eseguito la procedura guidata, è importante:

- Comunicare ai dipendenti e ai responsabili in prima linea che sono stati assegnati Teams licenze.
- Se l'organizzazione usa dispositivi condivisi, assicurarsi che Teams sia installato in tali dispositivi. Gli utenti aggiunti al team riceveranno un messaggio di posta elettronica di benvenuto in cui viene richiesto di aprire Teams.
- Se l'organizzazione usa un modello BYOD (Bring Your Own Device), comunicare a ogni utente aggiunto al team che deve scaricare e installare Teams nei propri dispositivi. Riceveranno anche un messaggio di posta elettronica di benvenuto in cui viene richiesto di scaricare Teams.

    > [!NOTE]
    > Tenere presente che gli utenti che hanno licenze F1 non riceveranno un messaggio di posta elettronica di benvenuto perché la licenza F1 non include l'accesso alla posta elettronica.  

Quando il dipendente in prima linea apre Teams per la prima volta, riceverà un'esperienza personalizzata per la prima esecuzione, che include chat e canali, chiamate e gestione delle attività, tutto all'interno di Teams.

## <a name="related-articles"></a>Articoli correlati

- [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)
- [Usare i modelli di team nell'interfaccia di amministrazione di Teams](get-started-with-teams-templates-in-the-admin-console.md)
