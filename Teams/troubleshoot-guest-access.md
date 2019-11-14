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
description: Informazioni sulla risoluzione dei problemi relativi all'accesso guest in Microsoft teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 2931a3f5440492aa1ab99a53cd196ab2973eb122
ms.sourcegitcommit: b1bf37a96a8faa169d8a32b7478f1e2d1022ebbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311261"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Risolvere i problemi relativi all'accesso guest in Microsoft Teams
======================================================

> [!IMPORTANT]
> Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto. 


- Per verificare se sono presenti problemi di supporto corrente con l'accesso guest in teams, vedere [risoluzione dei problemi relativi ai team](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Per scoprire se si conosce il problema, vedere [problemi noti di Microsoft teams](Known-issues.md).
- Gli ospiti sono utenti esterni all'organizzazione. Se un utente si trova all'interno dell'organizzazione (inclusi i dipendenti, gli appaltatori onsite o gli agenti onsite), non può essere aggiunto come Guest. Lo stesso vale per gli affiliati.
- Informazioni sulle prossime funzionalità di accesso Guest nuove o aggiornate nella roadmap per i [Team](https://aka.ms/teamsroadmap).
- Dirci cosa si vuole in [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Se i clienti vedono gli errori di licenza

L'accesso guest in teams USA Azure Active Directory (Azure AD) business to business (B2B) e il relativo modello di licenza. L'accesso guest è incluso in tutti gli abbonamenti di Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Office 365.

Se si verificano errori di gestione delle licenze, leggere le [istruzioni per la licenza B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per determinare i requisiti di licenza per soddisfare le proprie esigenze per l'accesso guest nell'organizzazione.


- Le licenze Guest vengono conteggiate con l'organizzazione invitante. Considerate questa operazione quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate in base all'organizzazione se gli ospiti invitati provengono da un altro tenant di Office 365 o usano gli indirizzi di posta elettronica personali.

## <a name="support-for-b2b-user-types"></a>Supporto per i tipi di utenti B2B
Attualmente Teams ha solo il supporto per lo stato 1 e i due tipi di utenti Guest [definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Argomenti correlati

[Accesso guest in Teams](guest-access.md)


