---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Informazioni sull'ID della linea di chiamata e sul nome della parte chiamante.
ms.openlocfilehash: 7baae8ff6ed48919e4ee540890dd31a47ad81c943e5ce8e9db8d934331d0ce75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350638"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Ulteriori informazioni su ID linea chiamante e nome del chiamante

CallerID è costituito da due informazioni rivolte all'utente:

- Un numero di telefono (in genere definito CLID o ID della linea telefonica).

- Nome della parte chiamante (in genere denominata CNAM). 

Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al gestore di destinazione (noto anche come gestore di terminazione). Le informazioni CNAM per la chiamata possono essere instradati o meno con la chiamata, perché queste informazioni dipendono da come il paese ha implementato CNAM (se del tutto). L'affidabilità della consegna CNAM con la chiamata varia a seconda del paese e dei gestori che gestiscono la chiamata, sia come intermediario che come gestore di terminazione. 

La trasmissione CLID & CNAM è responsabilità del gestore di terminazione. Il gestore di terminazione deve supportare & CNAM clid e fornire record aggiornati per entrambi i valori. Microsoft fornisce in modo affidabile i valori CLID durante le chiamate di origine, ma questi valori potrebbero non essere mantenuti intatti quando passano attraverso un gestore intermedio o il gestore di terminazione. Se il valore CLID viene modificato, omesso o troncato dal gestore intermedio o di terminazione, Microsoft non ha alcun ricorso per correggere tali problemi nella rete telefonica pubblica.

Le incoerenze in CNAM possono essere causate quando i gestori intermedi o terminanti ritardano l'aggiornamento delle informazioni CNAM in database autorevoli, come nel caso degli Stati Uniti. Nei paesi in cui non sono presenti database autorevoli per CNAM, le procedure dei singoli gestori possono anche causare problemi con le informazioni CNAM che arrivano intatte con la chiamata. Microsoft attualmente non supporta le informazioni CNAM di origine in paesi diversi dagli Stati Uniti.

## <a name="related-topics"></a>Argomenti correlati


