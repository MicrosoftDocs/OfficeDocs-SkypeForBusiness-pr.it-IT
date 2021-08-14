---
title: Gestire la versione di valutazione gratuita di Office 365 G1 per il governo degli Stati Uniti
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Per il governo degli Stati Uniti, se non si ha Microsoft Teams ma serve in fretta, distribuire la versione di valutazione di Office 365 G1 agli utenti che hanno l'esigenza di lavorare in remoto o da casa a seguito dell'epidemia di COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad58e4388c6a20dc64f67dff5097158ac5c26bbf
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234521"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>Gestire la versione di valutazione di Office 365 G1 per il governo degli Stati Uniti 

A partire dal 1° luglio 2020, la licenza della versione di valutazione di Office 365 E1 non è più disponibile. Se occorre fornire una licenza per Microsoft Teams agli utenti, leggere la [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description) per un elenco degli abbonamenti a pagamento che includono Teams. 

Usare le indicazioni fornite in questo articolo per gestire le licenze della versione di valutazione di Office 365 G1 esistenti, nonché il [passaggio a un abbonamento a pagamento](#upgrade-users-from-the-office-365-g1-trial-license). Per maggiori informazioni, vedere [Piani Microsoft 365 Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) e le [funzionalità di Microsoft Teams disponibili nel cloud GCC](plan-for-government-gcc.md).

Consultare le indicazioni imperdibili per il [supporto dei lavoratori remoti con Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Gestire la versione di valutazione G1

Dopo aver attivato la versione di valutazione di Office 365 G1, attivare la licenza per gli utenti che ne hanno bisogno. Per informazioni sulla procedura consultare [Gestire l'accesso degli utenti a Teams](user-access.md).

Dopo aver attivato la versione di valutazione G1, gli utenti verranno gestiti come quelli che hanno una licenza a pagamento. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Aggiornare gli utenti dalla licenza di valutazione di Office 365 G1

Per aggiornare gli utenti dalla versione di valutazione G1 a un abbonamento a pagamento:

1.  Acquistare un abbonamento che include Teams.

2.  Rimuovere l'abbonamento di valutazione di Office 365 G1 dall'utente.

3.  Assegnare la licenza acquistata.

Per altre informazioni, vedere [Teams per enti pubblici](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> Se allo scadere della versione di valutazione G1 non viene immediatamente eseguito l'aggiornamento a un abbonamento che include Teams, i dati dell'utente non vengono rimossi. L'utente esiste ancora in Azure Active Directory e tutti i dati all'interno di Teams vengono conservati. Una volta assegnata una nuova licenza all'utente per abilitare nuovamente le funzionalità di Teams, tutto il contenuto sarà ancora disponibile.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Rimuovere la licenza di valutazione di Office 365 G1

  - Se si vuole rimuovere questa licenza con PowerShell, vedere [Rimuovere le licenze dagli account utente con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - Se si vuole rimuovere questa licenza tramite il portale di amministrazione, vedere [Eliminare un utente dall'organizzazione](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso degli utenti a Teams](user-access.md)

[Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md)
