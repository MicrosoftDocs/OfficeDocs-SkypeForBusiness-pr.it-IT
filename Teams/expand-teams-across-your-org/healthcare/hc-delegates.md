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
description: Scopri come un utente con stato Assente o Non disturbare può impostare esplicitamente un altro utente come delegato nel proprio messaggio di stato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790468"
---
# <a name="message-delegation"></a>Delega messaggi

Un utente può già impostare esplicitamente il proprio stato su Assente o Non disturbare e fornire testo personalizzato. La funzionalità di delega dei messaggi funziona come segue:

1. Un utente @username menziona un altro utente in parte di un messaggio di stato di testo, indicando che mentre non sono disponibili, le persone che vogliono contattarlo invece possono contattare l'utente @username menzionato.
2. La persona assegnata come delegato viene informata di essere stata nominata come delegato.
3. Qualcuno che tenta di contattare il primo utente può quindi passare il mouse sul delegato nominato e inviare facilmente un messaggio al delegato.  

Si tratta di un processo avviato dall'utente nel client e non è richiesto il coinvolgimento dell'amministratore per abilitare la funzione. 

## <a name="delegation-use-scenario-in-healthcare"></a>Scenario di utilizzo della delega in Healthcare

*Esempio di utilizzo senza impostazione dei delegati:*  il dott. Franco Piccio è di guardia al reparto di radiologia. Riceve una chiamata personale urgente e deve allontanarsi per le prossime due ore. Chiede a uno dei suoi colleghi del reparto di radiologia, la dott.ssa Lena Ehrle, di coprirlo mentre è via. Consegna ufficiosamente il suo cercapersone alla dott.ssa Ehrle, che sta ascoltando messaggi urgenti e ping sul cercapersone e risponde a loro per conto del dott. Piccio oltre alle sue attuali responsabilità. Altri membri del team potrebbero non rendersi conto che la delega informale è avvenuta e ne deriva confusione con le cure di un paziente.

*Esempio di utilizzo con impostazione dei delegati:* il dott. Franco Piccio è di guardia al reparto di radiologia. Riceve una chiamata personale urgente e deve allontanarsi per le prossime due ore. Chiede a uno dei suoi colleghi del reparto di radiologia, la dott.ssa Lena Ehrle di coprirlo mentre è via. Cambia il suo messaggio di stato personalizzato per dire qualcosa di simile a "Non sono disponibile per le prossime ore. Si prega di contattare @DrEhrle per eventuali emergenze. "  Altri nel team si rendono conto della delega mentre tentano di contattare il dott. Piccio, quindi ora sanno di dover contattare la dott.ssa Ehrle. Ne consegue poca o nessuna confusione con le cure di un paziente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams

Gli amministratori devono essere consapevoli che le note sullo stato e i comportamenti di menzione della delega dipenderanno in parte dalla modalità di coesistenza dell'utente. Questa matrice mostra le seguenti possibilità:

|Modalità di Coesistenza | Comportamento Previsto|
|---|---|
|TeamsOnly |Gli utenti possono impostare una nota solo da Teams. <br> La nota Team dell'utente è visibile in Teams e SfB. |
|Isole | Nota dell'utente impostata in Teams visibile solo in Teams. <br> Nota utente impostata in SfB visibile solo in SfB |
|Modalità SfB | Gli utenti possono impostare una nota solo da SfB. <br> La nota SfB dell'utente è visibile in SfB e Teams.  |
|||

Un utente può impostare una nota in Teams solo se la modalità è TeamsOnly o Isole.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Visualizzazione delle note impostate in Skype for Business
  
Non vi è alcuna indicazione visiva che sia stata impostata una nota da Skype for Business.

Skype for Business non applica un limite di caratteri alle note di stato. Microsoft Teams visualizzerà solo i primi 280 caratteri di un set di note da Skype for Business. Un'ellisse (…) alla fine di una nota indica il troncamento.
  
Skype for Business non supporta i tempi di scadenza per le note.

La migrazione delle note da Skype for Business a Teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.

## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](../../coexistence-chat-calls-presence.md)
