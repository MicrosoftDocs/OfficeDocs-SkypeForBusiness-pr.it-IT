---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Perché è necessario aggiungere una persona autorizzata che possa apportare modifiche all'account quando si usa la procedura guidata Nuovo ordine di portabilità numero locale.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255399"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Ulteriori informazioni su ID linea chiamante e nome del chiamante

CallerID, come si fa in genere, è costituito da due informazioni identificabili per l'utente:
    - Un numero di telefono (in genere denominato CLID o ID linea chiamante) 
    - Nome del chiamante (in genere denominato CNAM), che può avere una lunghezza massima di 15 caratteri. 

Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al corriere di destinazione (noto anche come gestore finale). Le informazioni CNAM per la chiamata possono essere instradati o meno con la chiamata, in quanto ciò dipende da come il Paese ha implementato il CNAM (se del tutto). L'affidabilità della consegna di CNAM con la chiamata varia a seconda del paese e dei gestori che gestiscono la chiamata come intermediario e/o gestore terminante. 

La trasmissione CLID & CNAM è responsabilità del corriere che termina nel momento in cui il vettore che termina deve supportare la funzionalità CLID & CNAM e fornire record aggiornati per entrambi i valori. Microsoft fornisce in modo affidabile i valori CLID al momento delle chiamate di origine, ma tali valori potrebbero non essere mantenuti intatti dopo il passaggio da un operatore intermedio o dal gestore di terminazione. Purtroppo, nel caso in cui il valore CLID sia cambiato, omesso o troncato dall'intermediario o dal gestore di terminazione, Microsoft non ha nulla in più per correggere tali problemi nella rete telefonica pubblica.

Le incoerenze nel CNAM possono essere causate da ritardi nei gestori intermedi o che terminano aggiornando le informazioni CNAM nei database autorevoli come nel caso degli Stati Uniti. Nei paesi in cui non esiste un database autorevole per il CNAM, le procedure dei singoli gestori possono anche causare problemi con le informazioni CNAM che rimangono intatte con la chiamata. Microsoft attualmente non supporta le informazioni CNAM provenienti da paesi diversi dagli Stati Uniti."

## <a name="related-topics"></a>Argomenti correlati


