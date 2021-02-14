---
title: Creare team di gestione delle persone in Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni responsabile, con i relativi diretti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583675"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Creare team di gestione delle persone in Microsoft Teams


Quando si implementazione di Microsoft Teams, invece di avviarlo con una "tela vuota" (senza team o canali), si consiglia di configurare una struttura di base di team e canali. In questo modo si evita che gli utenti creino numerosi team quando devono creare canali nei team esistenti. Per aiutarti a iniziare con una struttura ben progettata per team e canali, abbiamo creato uno script di PowerShell che crea un team per ognuno dei responsabili della prima e della seconda riga, con i relativi report diretti come membri del team. Si tratta di uno script "tempormente" (non aggiorna automaticamente i team o i canali quando le persone vengono aggiunte o rimosse da un'organizzazione). Si tratta di uno strumento prezioso che puoi usare per imporre un certo ordine alla struttura di Teams fin dall'inizio. Questo script legge Azure AD e ottiene un elenco di responsabili e i relativi report diretti. Usa questo elenco per creare un team per ogni responsabile delle persone. 

## <a name="how-to-use-the-powershell-script"></a>Come usare lo script di PowerShell 

Per iniziare, eseguire lo script di responsabili dell'esportazione e il relativo [script](scripts/powershell-script-create-teams-from-managers-export-managers.md) diretto, presupponendo che siano già stati eseguiti i moduli [di PowerShell Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams.](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) I *responsabili dell'esportazione* e il relativo script diretto creano un file con valori delimitati da tabulazioni (ExportedManagerDirects.txt) che elenca tutti i responsabili con i relativi report diretti. 

Eseguire quindi lo script Crea nuovi team di gestione [utenti.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Questo script legge il file di ExportedManagerDirects.txt e crea un team per ogni responsabile, con i relativi diretti rapporti come membri. Se un responsabile o un diretto non è abilitato per Teams, lo script lo ignora e non crea un team. Rivedere il report, quindi eseguire di nuovo lo script dopo aver attivato Teams per chiunque ne abbia bisogno. Lo script non crea un secondo team per qualsiasi responsabile per cui è già stato creato un team.

Per ogni team, lo script crea un canale Generale e un canale "Solo per divertimento". 

## <a name="best-practices"></a>Procedure consigliate

- Chiedere a ogni responsabile delle persone di aggiungere il sito Web per le comunicazioni relative alle emergenza dell'organizzazione come scheda al canale Generale di ogni team. 

- Consultare la nuova app Crisis Communications leggendo questo post del blog dell'8 marzo 2020: Coordinare le comunicazioni di emergenza [con Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Argomenti correlati

[Procedure consigliate per l'organizzazione dei team](best-practices-organizing.md)

[Creare un team a livello di organizzazione in Teams](create-an-org-wide-team.md)
