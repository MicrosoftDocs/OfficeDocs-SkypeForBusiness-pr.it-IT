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
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8d54e236583211c2a8169987bf03ceba756facf
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641216"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Risolvere i problemi relativi all'accesso guest in Microsoft Teams

- Per sapere se il problema è stato risolto, vedere Supporto [Teams nell'organizzazione.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/).
- Gli utenti guest sono persone esterne all'organizzazione. Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest. Lo stesso vale per le consociate.
- Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).
- Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>I guest visualizzano errori di licenza.

L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza. L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Microsoft 365 o Office 365.

> [!NOTE]
> Teams deve essere abilitato nel tenant home di un guest per poter accedere e usare Teams come guest in un altro tenant (risorsa).

Se vengono visualizzati errori di licenza, leggere il modello di fatturazione per le identità esterne di [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) per determinare i requisiti di licenza per soddisfare le proprie esigenze di accesso guest nell'organizzazione.

- Le licenze guest vengono conteggiate rispetto all'organizzazione che invita: tenerlo presente quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate in base all'organizzazione, indipendentemente dal fatto che gli invitati provengono da un'altra Microsoft 365 o utilizzino i loro indirizzi di posta elettronica personali.

## <a name="related-topics"></a>Argomenti correlati

[Accesso guest in Teams](guest-access.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
