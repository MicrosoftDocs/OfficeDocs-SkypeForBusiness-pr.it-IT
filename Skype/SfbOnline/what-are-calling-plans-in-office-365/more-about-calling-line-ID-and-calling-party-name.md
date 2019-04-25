---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Informazioni sui motivi per cui si desidera aggiungere un utente autorizzato può apportare modifiche all'account quando si utilizza la procedura guidata nuovo ordine di porta numero locale.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229868"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Ulteriori informazioni su ID linea chiamante e nome del chiamante

CallerID, come in genere è definito, effettivamente costituito da due parti personali per l'utente di informazioni:
    - Un numero di telefono (in genere definito come CLID o chiamate linea ID) 
    - Nome di terze parti (denominato in genere CNAM) che può corrispondere al massimo 15 caratteri la chiamata. 

Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al gestore di destinazione (anche noto come vettore terminazione). Info CNAM per la chiamata può o non può essere inoltrata con la chiamata dipende dalle paese è implementato come CNAM (se affatto). L'affidabilità del recapito CNAM con la chiamata varia a seconda del paese e gestori telefonici che gestiscono le chiamate come un intermediario e/o un operatore di telefonia terminazione. 

Trasmissione di CNAM & CLID è responsabilità del gestore telefonico di terminazione nella misura in cui il gestore telefonico terminazione deve supportare le funzionalità CNAM & CLID e su come fornire record aggiornati per entrambi i valori. Microsoft fornisce in modo affidabile i valori CLID quando le chiamate di origine, ma tali valori potrebbero non essere conservati dopo il passaggio attraverso un intermediario gestore o gestore terminazione. Purtroppo, nel caso in cui il valore CLID viene modificato, omesso o per portante intermedia o terminazione troncato, Microsoft non ha poche attività su il ricorso di risolvere questi problemi della rete telefonica pubblica.

Incongruenze nella CNAM possono essere causate da ritardi nel gestori telefonici intermediate o terminazione aggiornamento info CNAM nei database rilevanti come nel caso degli Stati Uniti. Nei paesi in cui è presente alcun database rilevanti per CNAM, consigliate singolo vettore anche possono causare problemi con le informazioni CNAM in arrivo quando viene spostato con la chiamata. Microsoft attualmente non supporta origine CNAM informazioni nei paesi eccezione degli Stati Uniti."

## <a name="related-topics"></a>Argomenti correlati


