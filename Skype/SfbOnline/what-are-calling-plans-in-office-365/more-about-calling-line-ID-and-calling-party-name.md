---
title: Ulteriori informazioni sulla riga ID chiamante e la chiamata a nome entità
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: deb4320617d1840f2a237776ed0c4dc584fc2964
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Ulteriori informazioni sulla riga ID chiamante e la chiamata a nome entità

CallerID, come in genere denominato, effettivamente costituito da due parti personali per l'utente delle informazioni:
    - Un numero di telefono (in genere definito come CLID o chiamate linea ID) 
    - Nome di terze parti (denominato in genere CNAM) che può corrispondere al massimo 15 caratteri la chiamata. 

Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al gestore di destinazione (anche noto come vettore terminazione). Info CNAM per la chiamata può o non può essere inoltrata con la chiamata dipende dalle paese è implementato come CNAM (se affatto). L'affidabilità del recapito CNAM con la chiamata varia a seconda del paese e gestori telefonici che gestiscono le chiamate come un intermediario e/o un operatore di telefonia terminazione. 

Trasmissione CLID & CNAM è responsabilità del gestore telefonico di terminazione nella misura in cui il gestore telefonico terminazione deve supportare le funzionalità CLID & CNAM e su come fornire record aggiornati di entrambi i valori. Microsoft fornisce in modo affidabile i valori CLID quando le chiamate di origine, ma tali valori potrebbero non essere conservati dopo il passaggio attraverso un intermediario gestore o gestore terminazione. Purtroppo, nel caso in cui il valore CLID viene modificato, omesso o per portante intermedia o terminazione troncato, Microsoft non ha poche attività su il ricorso di risolvere questi problemi della rete telefonica pubblica.

Incongruenze nella CNAM possono essere causate da ritardi nel gestori telefonici intermediate o terminazione aggiornamento info CNAM nei database rilevanti, ad esempio Stati Uniti. Nei paesi in cui è presente alcun database rilevanti per CNAM, consigliate singolo vettore anche possono causare problemi con le informazioni CNAM in arrivo quando viene spostato con la chiamata. Microsoft attualmente non supporta origine CNAM informazioni nei paesi eccezione degli Stati Uniti."

## <a name="related-topics"></a>See also


