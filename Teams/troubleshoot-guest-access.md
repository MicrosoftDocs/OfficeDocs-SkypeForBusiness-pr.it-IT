---
title: Risolvere i problemi relativi all'accesso guest in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837636"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Risolvere i problemi relativi all'accesso guest in Microsoft Teams
======================================================

> [!IMPORTANT]
> Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive. 


- Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Per sapere se questo problema è stato già riscontrato, vedere [Problemi noti di Microsoft Teams](Known-issues.md).
- I guest sono utenti esterni all'organizzazione. Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest. Lo stesso vale per le consociate.
- Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).
- Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>I guest visualizzano errori di licenza.

L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza. L'accesso guest è incluso in tutti gli abbonamenti di Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Office 365.

Se vengono visualizzati errori di licenza, leggere la [Guida alle licenze Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per determinare i requisiti di licenza necessari per soddisfare le esigenze di accesso guest nella propria organizzazione.


- Le licenze guest vengono conteggiate rispetto all'organizzazione che invita: tenerlo presente quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate rispetto all'organizzazione, indipendentemente dal fatto che i guest invitati provengano da un altro tenant di Office 365 o utilizzino i loro indirizzi di posta elettronica personali.

## <a name="support-for-b2b-user-types"></a>Supporto per i tipi di utente B2B
Attualmente, Teams prevede il supporto solo per i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Argomenti correlati

[Accesso guest in Teams](guest-access.md)


