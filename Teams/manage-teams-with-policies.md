---
title: Gestire Teams con i criteri
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni sui criteri di Teams.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 932fed6b2a735aabee0511b6f1c6b863e01e403c
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646485"
---
# <a name="manage-teams-with-policies"></a>Gestire Teams con i criteri

I criteri sono una parte importante della gestione delle Teams. Usare questo articolo per informazioni su come usare i criteri a vantaggio dell'organizzazione.

## <a name="what-you-use-policies-for"></a>Cosa si usano i criteri per

I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni. È anche possibile consentire agli utenti di pianificare riunioni in un canale di teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app Teams.

## <a name="how-to-assign-policies"></a>Come assegnare i criteri

I criteri possono essere assegnati in diversi modi, a seconda delle operazioni che l'organizzazione sta tentando di eseguire. È possibile creare e visualizzare le attività nell'interfaccia di amministrazione di Teams.

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

Altre informazioni sull'assegnazione dei criteri [sono disponibili qui](policy-assignment-overview.md).

## <a name="how-to-manage-policies"></a>Come gestire i criteri

I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams o [con PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Ad esempio, un criterio di configurazione delle app può consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app Teams. Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

Inoltre, è possibile usare criteri riunione per controllare le impostazioni audio e video in Teams riunioni come trascrizioni, registrazioni cloud e audio/video IP.

![Screenshot dei criteri riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams per l'istruzione

È anche possibile usare la [procedura guidata Teams per l'istruzione](easy-policy-setup-edu.md) criteri per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.

![Screenshot della procedura guidata Teams per l'istruzione criteri.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipi di criteri

I criteri seguenti possono essere gestiti con Microsoft Teams.

Tipo di criterio | Descrizione
------------|------------
[Pacchetti di criteri](manage-policy-packages.md) | Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.
[Criteri riunione](meeting-policies-overview.md) | I criteri per le riunioni vengono usati per controllare le funzionalità disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione. I criteri delle riunioni includono gli argomenti seguenti.<br> - Criteri audio e video<br> - Criteri di condivisione del contenuto e dello schermo<br> - Partecipanti, guest e criteri di accesso<br> - Politiche generali
[Criteri per chiamate e voce](voice-and-calling-policies.md)| I criteri vocali e di chiamata gestiscono queste impostazioni tramite team come le chiamate di emergenza, il routing delle chiamate e l'ID chiamante.
[Criteri per le app](app-policies.md)| I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams. Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app Teams di un utente e installare l'applicazione per conto degli utenti.
[Criteri di messaggistica](messaging-policies-in-teams.md)| I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canale.

## <a name="related-topics"></a>Argomenti correlati

* [Assegnare criteri in Teams - Guida introduttiva](policy-assignment-overview.md)
* [Gestire i criteri di feedback in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gestire i criteri dei team in Microsoft Teams](teams-policies.md)
* [Configurare gli eventi live in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [criteri di Teams per l'istruzione e pacchetti di criteri](policy-packages-edu.md)