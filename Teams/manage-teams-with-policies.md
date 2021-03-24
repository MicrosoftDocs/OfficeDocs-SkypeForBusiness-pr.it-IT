---
title: Gestire Teams con i criteri
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni dettagliate sui criteri di Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b54c64c637d44132ac0f978561267ef34f720e67
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101102"
---
# <a name="manage-teams-with-policies"></a>Gestire Teams con i criteri

I criteri sono una parte importante della gestione di Teams. Usare questo articolo per esplorare come usare i criteri a vantaggio dell'organizzazione.

## <a name="what-you-use-policies-for"></a>Per cosa si usano i criteri

I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni. Alcune delle operazioni che è possibile eseguire includono consentire agli utenti di pianificare riunioni in un canale di Teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app Teams.

## <a name="how-to-assign-policies"></a>Come assegnare criteri

I criteri possono essere assegnati in diversi modi, a seconda delle operazioni che l'organizzazione sta cercando di eseguire. È possibile effettuare e visualizzare le attività nell'interfaccia di amministrazione di Teams.

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

Per altre informazioni sull'assegnazione di [criteri, vedere](assign-policies.md).

## <a name="how-to-manage-policies"></a>Come gestire i criteri

I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams [o con PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)

Ad esempio, i criteri di configurazione delle app possono consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app Teams. Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

Inoltre, i criteri di riunione possono essere usati per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.

![Screenshot dei criteri della riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams per l'istruzione

È anche possibile usare la procedura [guidata dei criteri di Teams for Education](easy-policy-setup-edu.md) per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.

![Screenshot della procedura guidata dei criteri di Teams per l'istruzione.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipi di criteri

I criteri seguenti possono essere gestiti con Microsoft Teams.

Tipo di criterio | Descrizione
------------|------------
[Pacchetti di criteri](manage-policy-packages.md) | Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.
[Criteri riunione](meeting-policies-in-teams.md) | I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione. I criteri delle riunioni includono gli argomenti seguenti.<br> - Criteri audio e video<br> - Criteri di condivisione del contenuto e dello schermo<br> - Partecipanti, guest e criteri di accesso<br> - Criteri generali
[Criteri vocali e chiamate](voice-and-calling-policies.md)| I criteri vocali e chiamate gestiscono queste impostazioni tramite team come chiamate di emergenza, routing delle chiamate e ID chiamante.
[Criteri delle app](app-policies.md)| I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams. Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app Teams di un utente e installare l'applicazione per conto degli utenti.
[Criteri di messaggistica](messaging-policies-in-teams.md)| I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.

## <a name="related-topics"></a>Argomenti correlati

* [Gestire i criteri di feedback in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gestire i criteri dei team in Microsoft Teams](teams-policies.md)
* [Visualizzare le assegnazioni dei criteri nel log attività](activity-log.md)
* [Configurare gli eventi live in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Criteri e pacchetti di criteri di Teams per l'istruzione](policy-packages-edu.md)