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
ms.openlocfilehash: 0ce7744aa18fe8ffe3fc83ca40649672f521bbba
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346357"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Risolvere i problemi relativi all'accesso guest in Microsoft Teams

- Per vedere se siamo a conoscere il tuo problema, consulta [Team di supporto nella tua organizzazione.](Known-issues.md)
- Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Gli utenti guest sono persone esterne all'organizzazione. Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest. Lo stesso vale per le consociate.
- Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).
- Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>I guest visualizzano errori di licenza.

L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza. L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Microsoft 365 o Office 365.

> [!NOTE]
> Teams deve essere abilitato nel tenant home di un guest perché i guest possano accedere e usare Teams come guest in un altro tenant (risorse).

Se vengono visualizzati errori di licenza, assicurarsi di leggere il modello di fatturazione per le identità esterne di [Azure AD](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) per determinare i requisiti di licenza che soddisfino le proprie esigenze per l'accesso guest nell'organizzazione.

- Le licenze guest vengono conteggiate rispetto all'organizzazione che invita: tenerlo presente quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate a fronte dell'organizzazione indipendentemente dal fatto che i guest invitati provengono da un'altra organizzazione di Microsoft 365 o utilizzino i loro indirizzi di posta elettronica personali.

## <a name="support-for-b2b-user-types"></a>Supporto per i tipi di utente B2B

Attualmente, Teams prevede il supporto solo per i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Argomenti correlati

[Accesso guest in Teams](guest-access.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)