---
title: Delega messaggi
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Informazioni su come un utente con stato Non al computer o Non disturbare può impostare esplicitamente un altro utente come delegato nel messaggio di stato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790468"
---
# <a name="message-delegation"></a>Delega messaggi

Un utente può già impostare esplicitamente il proprio stato su Non al computer o Non disturbare e fornire testo personalizzato. La caratteristica di delega dei messaggi funziona come segue:

1. Un utente @username menziona un altro utente in una parte di un MESSAGGIO di stato di testo, suggerendo che, anche se non è disponibile, le persone che vogliono contattarlo contattano l'utente menzionato @username contatto.
2. Alla persona a cui è stato assegnato il ruolo di delegato viene notificato che è stata nominata come delegato.
3. Qualcuno che tenta di contattare il primo utente può quindi passare il mouse sul delegato proposto e inviare facilmente un messaggio al delegato.  

Si tratta di un processo avviato dall'utente nel client e per abilitare la caratteristica non è richiesto alcun coinvolgimento dell'amministratore. 

## <a name="delegation-use-scenario-in-healthcare"></a>Scenario di utilizzo della delega nel settore sanitario

*Esempio di utilizzo senza impostare delegati:*  Il dott. Franco Piccio è al telefono presso il reparto di radiology. Riceve una chiamata personale urgente e deve allontanarsi per un paio d'ore. Chiede a uno dei suoi colleghi del reparto radiologico, la dott. Lena Ehrle, di coprirlo mentre è fuori ufficio. In modo informale, porta il suo pager al dott. Ehrle, che ascolta i messaggi urgenti e effettua un ping sul pager e risponde per conto del dott. Piccio, oltre alle sue attuali responsabilità. Altri membri del team potrebbero non rendersi conto dell'avvenuta delega informale e si verifica confusione con le cure di un paziente.

*Esempio di utilizzo con l'impostazione di delegati:* Il dott. Franco Piccio è al telefono presso il reparto di radiology. Riceve una chiamata personale urgente e deve allontanarsi per un paio d'ore. Chiede a uno dei suoi colleghi del reparto radiologico, la dott. Lena Ehrle di coprirlo mentre è fuori ufficio. Modifica il suo messaggio di stato personalizzato in modo che sia simile a "Non sono disponibile per le prossime ore. Contatta il @DrEhrle per eventuali emergenze".  Altri membri del team hanno realizzato che la delega è avvenuta mentre provano a contattare il dott. Piccio, quindi ora sanno di contattare il dott. Ehrle nel frattempo. L'assistenza di un paziente non crea confusione.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams

Gli amministratori devono tenere presente che le note di stato e i comportamenti di menzione della delega dipendono in parte dalla modalità di coesistenza di un utente. Questa matrice mostra le possibilità:

|Co-Existence automatica | Comportamento previsto|
|---|---|
|TeamsOnly |Gli utenti possono impostare una nota solo da Teams. <br> La nota di Teams dell'utente è visibile in Teams & SfB. |
|Isole | Nota dell'utente impostata in Teams visibile solo in Teams. <br> Set di note dell'utente in SfB visibile solo in SfB |
|Modalità SfB* | Gli utenti possono impostare una nota solo da SfB. <br> La nota SfB dell'utente è visibile in SfB & Teams.  |
|||

Un utente può impostare una nota in Teams solo se la modalità è TeamsOnly o Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Visualizzazione di note impostate in Skype for Business
  
Non c'è alcuna indicazione visiva che una nota sia stata impostata da Skype for Business.

Skype for Business non applica un limite di caratteri alle note sullo stato. Microsoft Teams visualizza solo i primi 280 caratteri di un set di note di Skype for Business. Un puntoni di sospensione (...) alla fine di una nota indica il troncamento.
  
Skype for Business non supporta le ore di scadenza per le note.

La migrazione delle note da Skype for Business a Teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.

## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](../../coexistence-chat-calls-presence.md)
