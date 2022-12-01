---
title: Creare team di responsabili delle persone in Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni responsabile con i propri diretti come membri del team.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198928"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Creare team di responsabili delle persone in Microsoft Teams


Quando si distribui Microsoft Teams, invece di avviarsi con una "lista vuota" (nessun team o canale), si consiglia vivamente di configurare un framework di base di team e canali. Questo aiuta a prevenire "team tentacolare", in cui gli utenti creano numerosi team quando dovrebbero creare canali in team esistenti. Per aiutarti a iniziare con una struttura ben progettata di team e canali, abbiamo creato uno script di PowerShell che crea un team per ogni responsabile della prima e seconda riga, con i dipendenti diretti di ogni manager come membri del team. Questo è uno script "point-in-time" (non aggiorna automaticamente i team o i canali quando le persone vengono aggiunte o rimosse da un'organizzazione). Ma è uno strumento prezioso che puoi usare per imporre un certo ordine sulla struttura di Teams fin dall'inizio. Questo script legge Azure AD, ottiene un elenco di responsabili e i relativi dipendenti diretti. Usa questo elenco per creare un team per ogni responsabile delle persone. 

## <a name="how-to-use-the-powershell-script"></a>Come usare lo script di PowerShell 

Per iniziare, eseguire lo [script Export manager e il relativo script directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) ( che presuppone che siano già stati eseguiti i moduli [Connect-AzureAd](/powershell/module/azuread/connect-azuread) e [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell). Lo script *Export manager e i relativi directs* crea un file con valori delimitati da tabulazioni (ExportedManagerDirects.txt) che elenca tutti i responsabili con i propri dipendenti diretti. 

Quindi, eseguire lo [script Crea nuovi team di gestione persone](scripts/powershell-script-create-teams-from-managers-new-teams.md). Questo script legge nel file ExportedManagerDirects.txt e crea un team per ogni responsabile, con i dipendenti diretti di quel responsabile come membri. Se un manager o un diretto non è abilitato per Teams, lo script li ignora e non crea un team. (Rivedere il report, quindi eseguire di nuovo lo script dopo aver attivato Teams per chiunque ne abbia bisogno. Lo script non crea un secondo team per nessun responsabile per cui è già stato creato un team.

Per ogni team, lo script crea un canale Generale e "Solo per divertimento". 

## <a name="best-practices"></a>Procedure consigliate

- Chiedi a ciascun responsabile di aggiungere il sito Web di comunicazione delle crisi della tua organizzazione come scheda al canale Generale per ogni team. 

- Scopri la nuova app Crisis Communications leggendo questo post di blog dell'8 marzo 2020: [Coordinare le comunicazioni di crisi usando Microsoft Teams e Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Argomenti correlati

[Procedure consigliate per l'organizzazione dei team](best-practices-organizing.md)

[Creare un team a livello di organizzazione in Teams](create-an-org-wide-team.md)