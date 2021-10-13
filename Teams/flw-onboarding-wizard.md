---
title: Usare l'onboarding guidato Frontline Worker per far entrare in funzione la forza lavoro in prima linea
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare l'onboarding guidato Frontline Worker per distribuire rapidamente un'esperienza Teams personalizzata per i dipendenti e i responsabili in prima linea nell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 056c82b1f2c7a1872693cc9f4298cee6eea1eefb
ms.sourcegitcommit: 11882e93618b8d69d21586c7b1f6a4460b96dd7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "60283030"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usare l'onboarding guidato Frontline Worker per far entrare in funzione la forza lavoro in prima linea

## <a name="overview"></a>Panoramica

L'onboarding guidato Frontline Worker nel interfaccia di amministrazione di Microsoft 365 semplifica l'onboarding dei lavoratori in prima linea nell'organizzazione. La procedura guidata consente di distribuire rapidamente un'esperienza in Microsoft Teams personalizzata per la forza lavoro in prima linea. La procedura guidata consente di avviare facilmente la distribuzione pilota di Teams per i lavoratori in prima linea dell'organizzazione.

La procedura guidata configura un team per i dipendenti in prima linea e assegna licenze [e](manage-policy-packages.md) pacchetti di criteri a ogni membro del team. È possibile creare il team da zero o da un modello [di team](get-started-with-teams-templates-in-the-admin-console.md)e quindi aggiungere utenti e assegnare ruoli. Il ruolo determina il pacchetto di criteri assegnato dalla procedura guidata a ogni utente.

Attualmente, la procedura guidata supporta l'aggiunta di 100 utenti ogni volta che viene eseguita. Stiamo lavorando per aumentare il numero di utenti per esecuzione a breve. Torna qui per gli aggiornamenti più recenti.

La procedura guidata è disponibile per tutte le organizzazioni che hanno almeno una Microsoft 365 F. È possibile eseguire la procedura guidata tutte le volte che è necessario implementare Teams alla forza lavoro in prima linea in posizioni o siti diversi all'interno dell'organizzazione.

> [!NOTE]
> Questa procedura guidata consente di accedere rapidamente ai dipendenti in prima linea per Teams attraverso il interfaccia di amministrazione di Microsoft 365. Per informazioni su come distribuire Teams ai dipendenti in prima linea usando gli script, vedere Come eseguire il provisioning Teams su larga scala per [Frontline Workers.](flw-scripted-deployment.md)

> [!NOTE]
> La procedura guidata non supporta ancora [le etichette di](sensitivity-labels.md) riservatezza. Se l'organizzazione richiede etichette di riservatezza per creare un team, la procedura guidata non verrà visualizzata nel interfaccia di amministrazione di Microsoft 365.

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

1. Nel riquadro di spostamento sinistro del [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)scegliere **Imposta.** Passare alla sezione **App e posta** elettronica e quindi, in Attiva e attiva la forza lavoro in prima linea, selezionare **Visualizza.**  Qui sono disponibili altre informazioni sulle funzionalità offerte Microsoft 365 per i dipendenti in prima linea.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Screenshot della pagina dei dettagli per l'esperienza di onboarding frontline Worker nel interfaccia di amministrazione di Microsoft 365":::

2. Al termine, selezionare Inizia **per** eseguire la procedura guidata.

3. Immettere un nome per il team, aggiungere uno o più proprietari del team e selezionare un'impostazione di privacy. Scegliere quindi se creare il team da zero o da un modello di team. I modelli di team sono disponibili con canali e schede predefiniti, che ottimizzano il team per specifiche esigenze aziendali o progetti.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Screenshot della pagina Configurare un team della procedura guidata":::

4. Aggiungere utenti al team. È anche possibile aggiungere gruppi. Se si aggiungono gruppi, tenere presente che le licenze e i pacchetti di criteri vengono assegnati direttamente a ogni utente del gruppo, non al gruppo stesso.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Screenshot della pagina Aggiungi utenti della procedura guidata in cui si aggiungono utenti e gruppi al team":::

5. Assegnare uno dei ruoli seguenti a ogni membro del team: Frontline Worker, Frontline Manager, None. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Screenshot della pagina Assegna ruoli di lavoro della procedura guidata in cui si assegnano ruoli, posizioni e licenze ai membri del team":::

    Assegnando un ruolo di Frontline Worker o Frontline Manager, l'utente riceverà un pacchetto di criteri. Il pacchetto di criteri creerà un'esperienza Teams un'esperienza personalizzata in base al loro ruolo. Questa esperienza include app e criteri pre-aggiunti per la comunicazione e la collaborazione di worker e manager in prima linea.

    Selezionare quindi una posizione e assegnare una licenza Microsoft 365 F a ogni membro del team. Se non si hanno licenze sufficienti, è possibile selezionare Acquista **altre licenze** per acquistare altre licenze.  

6. Scegliere chi riceve il messaggio di posta elettronica di stato al termine della procedura guidata. Il messaggio di posta elettronica contiene informazioni sulle operazioni eseguite dalla procedura guidata per la creazione del team, l'aggiunta di membri del team e l'assegnazione di una licenza e un pacchetto di criteri &mdash; a ogni membro del team. Usare queste informazioni per risolvere gli eventuali errori che possono verificarsi.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Screenshot della pagina Aggiungi destinatari di posta elettronica di stato della procedura guidata":::

7. Rivedere le selezioni e quindi selezionare **Conferma.**

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Screenshot della pagina Rivedi team della procedura guidata in cui si esaminano le impostazioni del team":::

    La procedura guidata crea il team e assegna licenze e pacchetti di criteri ai membri del team. Il completamento dell'operazione potrebbe richiedere alcuni minuti, dopo di che i destinatari scelti ricevono un messaggio di posta elettronica di stato.

8. Stai arrivando, ma non hai ancora finito! Vedere quindi la sezione [Cosa fare dopo l'esecuzione della procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

## <a name="what-to-do-after-running-the-wizard"></a>Procedura dopo l'esecuzione della procedura guidata

Dopo aver eseguito la procedura guidata, è importante:

- In modo che i dipendenti e i responsabili in prima linea sappiano che sono assegnati Teams licenze.
- Se si usano dispositivi condivisi, assicurarsi che Teams sia installato in tali dispositivi. Se l'organizzazione usa un modello di "porta il tuo dispositivo", in modo che i dipendenti e i responsabili in prima linea sappiano che devono scaricare e installare Teams nei propri dispositivi.

Quando il dipendente in prima linea apre Teams per la prima volta, riceverà un'esperienza di prima esecuzione personalizzata, che include chat e canali, chiamate e gestione delle attività all'interno di Teams.

## <a name="related-articles"></a>Articoli correlati

- [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)
- [Usare i modelli di team nell'Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
