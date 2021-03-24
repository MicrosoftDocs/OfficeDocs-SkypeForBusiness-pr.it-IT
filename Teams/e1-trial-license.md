---
title: Gestire la versione di valutazione gratuita di Office 365 E1
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Se non si ha Microsoft Teams ma serve in fretta, distribuire la versione di valutazione di Office 365 E1 agli utenti che hanno l'esigenza di lavorare in remoto o da casa (WFH) a seguito dell'epidemia di COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6146b6d4a7ca3d988c5dc1042a7f75848cf4fc7b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092664"
---
<a name="manage-the-office-365-e1-trial"></a>Gestire la versione di valutazione di Office 365 E1
==============================

A partire dal 1° luglio 2020, la licenza della versione di valutazione di Office 365 E1 non è più disponibile. Se occorre fornire una licenza per Microsoft Teams agli utenti, leggere la [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description) per un elenco degli abbonamenti a pagamento che includono Teams. In alternativa, le organizzazioni idonee possono usare la **[versione gratuita di Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** oppure i dipendenti possono attivare l'esperienza **[Teams Exploratory](teams-exploratory.md)**.


I clienti di Teams for Education possono prendere in considerazione la [licenza di Office 365 A1](teams-edu-licensing.md) gratuita.

Usare le indicazioni fornite in questo articolo per gestire le licenze della versione di valutazione di Office 365 E1 esistenti, nonché il [passaggio a un abbonamento a pagamento](#upgrade-users-from-the-office-365-e1-trial-license).

Consultare le indicazioni imperdibili per il [supporto dei lavoratori remoti con Teams](support-remote-work-with-teams.md).

## <a name="manage-the-e1-trial"></a>Gestire la versione di valutazione E1

Dopo aver attivato la versione di valutazione di Office 365 E1, attivare la licenza per gli utenti che ne abbia bisogno. Per informazioni sulla procedura consultare [Gestire l'accesso degli utenti a Teams](user-access.md).


Dopo aver attivato la versione di valutazione E1, gli utenti verranno gestiti come quelli che hanno una licenza a pagamento. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md).



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Aggiornare gli utenti dalla licenza di valutazione di Office 365 E1

Per aggiornare gli utenti dalla versione di valutazione E1 a un abbonamento a pagamento:

1. Acquistare un abbonamento che include Teams.

2. Rimuovere l'abbonamento di valutazione di Office 365 E1 dall'utente.

3. Assegnare la licenza acquistata.

Per altre informazioni, vedere [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Se allo scadere della versione di valutazione E1 non viene immediatamente eseguito l'aggiornamento a un abbonamento che include Teams, i dati dell'utente non vengono rimossi. L'utente esiste ancora in Azure Active Directory e tutti i dati all'interno di Teams vengono conservati. Una volta assegnata una nuova licenza all'utente per abilitare nuovamente le funzionalità di Teams, tutto il contenuto sarà ancora disponibile. 

### <a name="remove-an-office-365-e1-trial-license"></a>Rimuovere la licenza di valutazione di Office 365 E1

- Se si vuole rimuovere questa licenza con PowerShell, vedere [Rimuovere le licenze dagli account utente con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Se si vuole rimuovere questa licenza tramite il portale di amministrazione, vedere [Eliminare un utente dall'organizzazione](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso degli utenti a Teams](user-access.md)

[Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md)

[Gestire l'esperienza Teams Exploratory](teams-exploratory.md)

[Microsoft 365 o Office 365 Nonprofit](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Ottenere assistenza con la distribuzione di Teams](https://go.microsoft.com/fwlink/?linkid=780698)