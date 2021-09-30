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
ms.openlocfilehash: da44a5eb25e56a974214472782e424cda735b6dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636804"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usare l'onboarding guidato Frontline Worker per far entrare in funzione la forza lavoro in prima linea

> [!NOTE]
> Questo articolo descrive una funzionalità che non è ancora stata rilasciata. Sarà presto disponibile. Gli amministratori possono scoprire quando questa funzionalità verrà rilasciata nel Centro messaggi (nel interfaccia di amministrazione di Microsoft 365 [).](https://portal.office.com/adminportal/home) Per essere sempre al top delle funzionalità Teams, vedere la roadmap [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>Panoramica

L'onboarding guidato Frontline Worker nel interfaccia di amministrazione di Microsoft 365 semplifica l'onboarding dei lavoratori in prima linea nell'organizzazione. La procedura guidata consente di distribuire rapidamente un'esperienza Microsoft Teams personalizzata per la forza lavoro in prima linea. La procedura guidata consente di avviare facilmente la distribuzione pilota di Teams per i lavoratori in prima linea dell'organizzazione.

La procedura guidata configura un team per i dipendenti in prima linea e assegna licenze [e](manage-policy-packages.md) pacchetti di criteri a ogni membro del team. È possibile creare il team da zero o da un modello [di team](get-started-with-teams-templates-in-the-admin-console.md)e quindi aggiungere utenti e assegnare ruoli. Il ruolo determina il pacchetto di criteri assegnato dalla procedura guidata a ogni utente.

La procedura guidata è disponibile per tutte le organizzazioni con almeno una Microsoft 365 F. È possibile eseguire la procedura guidata tutte le volte che è necessario implementare Teams alla forza lavoro in prima linea in posizioni o siti diversi all'interno dell'organizzazione.

> [!NOTE]
> Questa procedura guidata consente di eseguire rapidamente l'onboardboard dei dipendenti in prima linea per Teams l'interfaccia di amministrazione di Microsoft 365. Per altre informazioni su come distribuire i Teams ai dipendenti in prima linea usando gli script, vedere Come eseguire il provisioning Teams su larga scala per [Frontline Workers.](flw-scripted-deployment.md)

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

1. Nel riquadro di spostamento sinistro del [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)selezionare **Imposta.** Passare alla sezione **App e posta** elettronica e quindi, in Attiva e attiva la forza lavoro in prima linea, selezionare **Visualizza.**  Qui sono disponibili altre informazioni sulle funzionalità offerte Microsoft 365 per i dipendenti in prima linea.

2. Al termine, selezionare Inizia **per** eseguire la procedura guidata.

3. Immettere un nome per il team, selezionare un'impostazione di privacy e aggiungere uno o più proprietari del team. Scegliere quindi se creare il team da zero o da un modello di team. I modelli di team sono disponibili con canali e schede predefiniti, che ottimizzano il team per specifiche esigenze aziendali o progetti.

4. Aggiungere utenti al team. È anche possibile aggiungere gruppi. Se si aggiungono gruppi, tenere presente che le licenze e i pacchetti di criteri vengono assegnati direttamente a ogni utente del gruppo, non al gruppo stesso.

5. Assegnare uno dei ruoli seguenti a ogni membro del team.

    - Operaio in prima linea
    - Frontline Manager
    - Nessuno

    Assegnando un ruolo di frontline worker o frontline manager, l'utente riceverà un'esperienza Teams personalizzata in base al proprio ruolo. Sono incluse le app e i criteri pre-aggiunti per la comunicazione e la collaborazione di worker e manager in prima linea.

    Assegnare quindi una Microsoft 365 F a ogni membro del team. Se non si hanno licenze sufficienti, è possibile selezionare Acquista **altre licenze** per acquistare altre licenze.  

6. Scegliere chi riceve il messaggio di posta elettronica di stato al termine della procedura guidata. Il messaggio di posta elettronica contiene informazioni sulle operazioni eseguite dalla procedura guidata per la creazione del team, l'aggiunta di membri del team e l'assegnazione di una licenza e un pacchetto di criteri &mdash; a ogni membro del team. Usare queste informazioni per risolvere gli eventuali errori che possono verificarsi.

7. Rivedere le selezioni e quindi selezionare **Conferma.**

    La procedura guidata crea il team e assegna licenze e pacchetti di criteri ai membri del team. Il completamento dell'operazione potrebbe richiedere alcuni minuti, dopo di che i destinatari scelti ricevono un messaggio di posta elettronica di stato.

8. Stai arrivando, ma non hai ancora finito! Vedere quindi la sezione [Cosa fare dopo l'esecuzione della procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

## <a name="what-to-do-after-running-the-wizard"></a>Procedura dopo l'esecuzione della procedura guidata

Dopo aver eseguito la procedura guidata, è importante:

- In modo che i dipendenti e i responsabili in prima linea sappiano che sono assegnati Teams licenze.
- Se si usano dispositivi condivisi, verificare che Teams sia installato in tali dispositivi. Se l'organizzazione usa un modello di "porta il tuo dispositivo", in modo che i dipendenti e i responsabili in prima linea sappiano che devono scaricare e installare Teams nei propri dispositivi.

Quando il dipendente in prima linea apre Teams per la prima volta, riceverà un'esperienza di prima esecuzione personalizzata, che include chat e canali, chiamate e gestione delle attività all'interno di Teams.

## <a name="related-articles"></a>Articoli correlati

- [Gestire i pacchetti di criteri in Teams](manage-policy-packages.md)
- [Usare i modelli di team nell'Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)