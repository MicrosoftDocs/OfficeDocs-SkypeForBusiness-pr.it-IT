---
title: Creare teams manager di persone in Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni Manager con i propri dirigenti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796226"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Creare teams manager di persone in Microsoft Teams


Quando si distribuisce Microsoft teams anziché il lancio con una "tabulazione vuota" (nessun team o canale), è consigliabile configurare un Framework di base di team e canali. Questo consente di evitare "espansione del team", in cui gli utenti creano numerosi team quando devono creare canali in team esistenti. Per iniziare a usare una struttura di team e canali ben progettata, abbiamo creato uno script di PowerShell che crea un team per ogni manager della prima e della seconda riga, con i report diretti di ogni Manager come membri del team. Si tratta di uno script "Point-in-Time" (non aggiorna automaticamente i team o i canali quando gli utenti vengono aggiunti o rimossi da un'organizzazione). Ma è uno strumento valido che puoi usare per imporre un ordine nella struttura teams fin dall'inizio. Questo script legge il tuo Azure AD, riceve un elenco di Manager e i relativi report diretti. Usa questo elenco per creare un team per Manager di persone. 

## <a name="how-to-use-the-powershell-script"></a>Come usare lo script di PowerShell 

Iniziare eseguendo i [responsabili dell'esportazione e il relativo script directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (che presuppone che siano già stati eseguiti i moduli di PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) ). L' *export managers and its directs* script crea un file delimitato da tabulazioni (ExportedManagerDirects. txt) che elenca tutti i responsabili con i relativi report diretti. 

Esegui quindi lo [script crea nuovi teams manager](scripts/powershell-script-create-teams-from-managers-new-teams.md). Questo script legge il file ExportedManagerDirects. txt e crea un team per ogni Manager, con i report diretti di tale Manager come membri. Se un Manager o Direct non è abilitato per i team, lo script li ignora e non crea un team. (Rivedere il report, quindi rieseguire lo script dopo aver attivato team per tutti gli utenti che ne hanno bisogno. Lo script non creerà un secondo team per qualsiasi Manager per cui è già stato creato un team.

Per ogni team, lo script crea un canale generale e "solo per divertimento". 

## <a name="best-practices"></a>Procedure consigliate

- Chiedere a ogni responsabile del personale di aggiungere il sito Web delle comunicazioni di crisi dell'organizzazione come Tab per il canale generale per ogni team. 

- Vedere la nuova app crisi Communications leggendo questo post di Blog di 2020 marzo: [coordinare le comunicazioni di crisi con Microsoft teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Argomenti correlati

[Procedure consigliate per organizzare i team](best-practices-organizing.md)

[Creare un team a livello di organizzazione in Teams](create-an-org-wide-team.md)
