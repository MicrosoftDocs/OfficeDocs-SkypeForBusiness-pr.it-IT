---
title: Gestire Teams con i criteri
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: È possibile utilizzare Teams criteri.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 307eccf1d6e919593cdfadaf2b902a7a15c7b4cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588148"
---
# <a name="manage-teams-with-policies"></a>Gestire Teams con i criteri

I criteri sono una parte importante della gestione Teams. Usare questo articolo per esplorare come usare i criteri a vantaggio dell'organizzazione.

## <a name="what-you-use-policies-for"></a>Per cosa si usano i criteri

I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni. Alcune delle operazioni che è possibile eseguire includono consentire agli utenti di pianificare riunioni in un canale di teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra Teams app.

## <a name="how-to-assign-policies"></a>Come assegnare criteri

I criteri possono essere assegnati in diversi modi, a seconda delle operazioni che l'organizzazione sta cercando di eseguire. È possibile eseguire e visualizzare le attività nell'Teams di amministrazione.

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

Per altre informazioni sull'assegnazione di [criteri, vedere](policy-assignment-overview.md).

## <a name="how-to-manage-policies"></a>Come gestire i criteri

I criteri vengono gestiti con l'Microsoft Teams di amministrazione o [con PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)

Ad esempio, i criteri di configurazione delle app possono consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra Teams app. Questi criteri sono configurati nell'Teams di amministrazione.

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

Inoltre, i criteri di riunione possono essere usati per controllare le impostazioni audio e video nelle riunioni Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.

![Screenshot dei criteri della riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams per l'istruzione

È anche possibile usare la procedura [guidata Teams per l'istruzione criteri per](easy-policy-setup-edu.md) configurare e gestire facilmente i criteri per l'ambiente di apprendimento.

![Screenshot della procedura guidata Teams per l'istruzione criteri di gruppo.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipi di criteri

I criteri seguenti possono essere gestiti con Microsoft Teams.

Tipo di criterio | Descrizione
------------|------------
[Pacchetti di criteri](manage-policy-packages.md) | Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.
[Criteri riunione](meeting-policies-in-teams.md) | I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione. I criteri delle riunioni includono gli argomenti seguenti.<br> - Criteri audio e video<br> - Criteri di condivisione del contenuto e dello schermo<br> - Partecipanti, guest e criteri di accesso<br> - Criteri generali
[Criteri vocali e chiamate](voice-and-calling-policies.md)| I criteri vocali e chiamate gestiscono queste impostazioni tramite team come chiamate di emergenza, routing delle chiamate e ID chiamante.
[Criteri delle app](app-policies.md)| I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams. Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere le applicazioni alla barra delle app Teams di un utente e installare l'applicazione per conto degli utenti.
[Criteri di messaggistica](messaging-policies-in-teams.md)| I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.

## <a name="related-topics"></a>Argomenti correlati

* [Assegnare criteri in Teams - Guida introduttiva](policy-assignment-overview.md)
* [Gestire i criteri di feedback in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gestire i criteri dei team in Microsoft Teams](teams-policies.md)
* [Configurare gli eventi live in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams per l'istruzione criteri e pacchetti di criteri](policy-packages-edu.md)