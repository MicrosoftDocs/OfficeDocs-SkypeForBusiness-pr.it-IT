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
ms.openlocfilehash: b56e617321cea25fe677b7d9a7a00afba0940b07
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156534"
---
# <a name="manage-teams-with-policies"></a>Gestire Teams con i criteri

I criteri sono una parte importante della gestione di Teams. Usare questo articolo per informazioni su come usare i criteri a vantaggio dell'organizzazione.

## <a name="what-you-use-policies-for"></a>Cosa si usano i criteri per

I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni. Alcune delle cose che puoi fare includono consentire agli utenti di pianificare riunioni in un canale di teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app Teams.

## <a name="how-to-assign-policies"></a>Come assegnare i criteri

I criteri possono essere assegnati in diversi modi, a seconda delle operazioni che l'organizzazione sta tentando di eseguire. È possibile effettuare e visualizzare le attività nell'interfaccia di amministrazione di Teams.

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

Altre informazioni sull'assegnazione dei criteri [sono disponibili qui](policy-assignment-overview.md).

> [!NOTE]
> Per annullare l'assegnazione dei criteri, è possibile rimuovere le assegnazioni in blocco per tutti gli utenti direttamente assegnati a un criterio. Per altre informazioni, vedere [Annullare l'assegnazione di criteri in blocco](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="how-to-manage-policies"></a>Come gestire i criteri

I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams o [tramite PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Ad esempio, un criterio di configurazione delle app può consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra delle app di Teams. Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

Inoltre, i criteri per le riunioni possono essere usati per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.

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