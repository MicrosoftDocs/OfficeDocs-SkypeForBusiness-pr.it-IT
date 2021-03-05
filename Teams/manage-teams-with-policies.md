---
title: Gestire Teams con i criteri
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni sui criteri di Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460496"
---
# <a name="manage-teams-with-policies"></a>Gestire Teams con i criteri

I criteri sono una parte importante della gestione di Teams. Usare questo articolo per informazioni su come usare i criteri a vantaggio dell'organizzazione.

## <a name="what-you-use-policies-for"></a>Per cosa si usano i criteri

I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni. Alcune delle operazioni che è possibile eseguire includono il consentire agli utenti di pianificare riunioni in un canale di Teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app di Teams.

## <a name="how-to-assign-policies"></a>Come assegnare criteri

I criteri possono essere assegnati in diversi modi a seconda del risultato che l'organizzazione sta cercando di eseguire. È possibile fare e visualizzare le attività nell'interfaccia di amministrazione di Teams.

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

Per altre informazioni sull'assegnazione dei criteri, [vedere](assign-policies.md)qui.

## <a name="how-to-manage-policies"></a>Come gestire i criteri

I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams [o con PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)

Ad esempio, un criterio di configurazione delle app può consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app di Teams. Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

Inoltre, un criterio di riunione può essere usato per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.

![Screenshot del criterio di riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams per l'istruzione

È anche possibile usare la procedura [guidata dei criteri di Teams for Education](easy-policy-setup-edu.md) per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.

![Screenshot della procedura guidata per i criteri di Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipi di criteri

I seguenti criteri possono essere gestiti con Microsoft Teams.

Tipo di criterio | Descrizione
------------|------------
[Pacchetti di criteri](manage-policy-packages.md) | Un pacchetto di criteri in Microsoft Teams è una raccolta di impostazioni e criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.
[Criteri riunione](meeting-policies-in-teams.md) | I criteri di riunione vengono utilizzati per controllare le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione. I criteri delle riunioni includono gli argomenti seguenti.<br> - Criteri audio e video<br> - Criteri di condivisione del contenuto e dello schermo<br> - Partecipanti, guest e criteri di accesso<br> - Criteri generali
[Criteri per chiamate e voce](voice-and-calling-policies.md)| I criteri vocali e di chiamata gestiscono queste impostazioni tramite team come chiamate di emergenza, instradamento chiamate e ID chiamante.
[Criteri delle app](app-policies.md)| I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams. Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app teams di un utente e installare l'applicazione per conto degli utenti.
[Criteri di messaggistica](messaging-policies-in-teams.md)| I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.

## <a name="related-topics"></a>Argomenti correlati

* [Gestire i criteri di feedback in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gestire i criteri dei team in Microsoft Teams](teams-policies.md)
* [Visualizzare le assegnazioni dei criteri nel log attività](activity-log.md)
* [Configurare gli eventi live in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Criteri e pacchetti di criteri di Teams for Education](policy-packages-edu.md)
