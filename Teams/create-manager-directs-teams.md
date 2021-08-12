---
title: Creare team di people manager in Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni responsabile con i propri diretti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce7fb0a34f202481df0062367ec7a905b84848d21e7a2e5e4bce73bea4073eac
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282809"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Creare team di people manager in Microsoft Teams


Quando si esegue l'Microsoft Teams, invece di avviarlo con una "lista vuota" (senza team o canali), è consigliabile configurare un framework di base di team e canali. In questo modo si evita la "espansione del team", in cui gli utenti creano numerosi team quando devono creare canali nei team esistenti. Per iniziare a usare una struttura di team e canali ben progettata, è stato creato uno script di PowerShell che crea un team per ogni responsabile della prima e della seconda riga, con i report diretti di ogni manager come membri del team. Si tratta di uno script "point-in-time" (non aggiorna automaticamente i team o i canali quando le persone vengono aggiunte o rimosse da un'organizzazione). Ma è uno strumento prezioso che è possibile usare per imporre un ordine alla struttura Teams struttura fin dall'inizio. Questo script legge Azure AD e ottiene un elenco di responsabili e dei relativi report diretti. Usa questo elenco per creare un team per ogni responsabile delle persone. 

## <a name="how-to-use-the-powershell-script"></a>Come usare lo script di PowerShell 

Per iniziare, eseguire i responsabili dell'esportazione e il relativo [script](scripts/powershell-script-create-teams-from-managers-export-managers.md) dirette, presupponendo che siano già stati eseguiti i moduli [di PowerShell Connessione-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connessione-MicrosoftTeams).](/powershell/module/teams/connect-microsoftteams?view=teams-ps) Lo *script Export managers e directs* crea un file delimitato da tabulazioni (ExportedManagerDirects.txt) che elenca tutti i responsabili con i loro report diretti. 

Eseguire quindi lo [script Create new people manager teams](scripts/powershell-script-create-teams-from-managers-new-teams.md). Questo script legge il file ExportedManagerDirects.txt e crea un team per ogni responsabile, con i report diretti del responsabile come membri. Se un manager o un diretto non è abilitato per Teams, lo script li ignora e non crea un team. Esaminare il report, quindi eseguire di nuovo lo script dopo aver attivato Teams per chiunque ne abbia bisogno. Lo script non crea un secondo team per qualsiasi responsabile per cui è già stato creato un team.

Per ogni team, lo script crea un canale Generale e un canale "Solo per divertimento". 

## <a name="best-practices"></a>Procedure consigliate

- Chiedere a ogni responsabile delle persone di aggiungere il sito Web per le comunicazioni di emergenza dell'organizzazione come scheda al canale Generale per ogni team. 

- Controllare la nuova app Crisis Communications leggendo questo post di blog dell'8 marzo 2020: Coordinare le comunicazioni di emergenza [usando Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Argomenti correlati

[Procedure consigliate per l'organizzazione dei team](best-practices-organizing.md)

[Creare un team a livello di organizzazione in Teams](create-an-org-wide-team.md)