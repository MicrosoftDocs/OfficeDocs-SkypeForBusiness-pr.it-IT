---
title: Risolvere i problemi relativi all'accesso guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Assistenza per la risoluzione dei problemi relativi all'accesso guest in Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948683"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Risolvere i problemi relativi all'accesso guest in Microsoft Teams

- Per sapere se il problema è stato risolto, vedere [Team di supporto nell'organizzazione.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/).
- Gli utenti guest sono persone esterne all'organizzazione. Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest. Lo stesso vale per le consociate.
- Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).
- Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>I guest visualizzano errori di licenza.

L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza. L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Microsoft 365 o Office 365.

> [!NOTE]
> Teams deve essere abilitato nel tenant home di un guest per poter accedere e usare Teams come guest in un altro tenant (risorsa).

Se vengono visualizzati errori di licenza, leggere il modello di fatturazione per le identità esterne di [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) per determinare i requisiti di licenza per soddisfare le esigenze di accesso guest nell'organizzazione.

- Le licenze guest vengono conteggiate rispetto all'organizzazione che invita: tenerlo presente quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate in base all'organizzazione, indipendentemente dal fatto che gli invitati provengono da un'altra organizzazione di Microsoft 365 o che utilizzino i loro indirizzi di posta elettronica personali.

## <a name="support-for-b2b-user-types"></a>Supporto per i tipi di utente B2B

Attualmente, Teams prevede il supporto solo per i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Argomenti correlati

[Accesso guest in Teams](guest-access.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)