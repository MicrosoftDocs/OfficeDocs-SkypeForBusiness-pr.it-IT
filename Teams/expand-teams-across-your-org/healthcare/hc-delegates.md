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
description: Informazioni su come un utente con stato di assenza o non disturbare lo stato può impostare in modo esplicito un altro utente come delegato nel messaggio di stato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790468"
---
# <a name="message-delegation"></a>Delega messaggi

Un utente può già impostare esplicitamente lo stato su away o non disturbare e specificare il testo personalizzato. La caratteristica delega messaggio funziona nel modo seguente:

1. Un utente @username menziona un altro utente in parte di un messaggio di stato del testo, suggerendo che, mentre non sono disponibili persone che desiderano contattarle, contattare il @username utente menzionato.
2. La persona che è stata assegnata come delegato viene avvisata che è stata nominata come delegato.
3. Chi prova a contattare il primo utente può quindi passare il puntatore del mouse sul delegato nominato e facilmente Message il delegato.  

Si tratta di un processo avviato dall'utente nel client e non è necessario alcun coinvolgimento dell'amministratore per abilitare la caratteristica. 

## <a name="delegation-use-scenario-in-healthcare"></a>Scenario use Delegation in Healthcare

*Esempio di utilizzo senza impostare delegati:*  Il dottor Franco Piccio è in servizio presso il dipartimento di radiologia. Riceve una chiamata personale urgente e deve andarsene per le prossime due ore. Chiede a uno dei suoi coetanei del dipartimento di radiologia, la dottoressa Lena Ehrle, di occuparsi di lui mentre è fuori sede. Informalmente consegna il suo cercapersone al Dr. Ehrle, che sta ascoltando i messaggi urgenti e i ping sul pager e li risponde per conto del dottor Piccio, oltre alle sue attuali responsabilità. Gli altri membri del team potrebbero non realizzare la delegazione informale e la confusione che ne consegue con le cure di un paziente.

*Esempio di utilizzo con l'impostazione dei delegati:* Il dottor Franco Piccio è in servizio presso il dipartimento di radiologia. Riceve una chiamata personale urgente e deve andarsene per le prossime due ore. Chiede a uno dei suoi coetanei nel dipartimento di radiologia, la dottoressa Lena Ehrle di occuparsi di lui mentre è fuori sede. Modifica il messaggio di stato personalizzato per dire qualcosa di simile a "non sono disponibile per le prossime ore. Contattare @DrEhrle per eventuali emergenze. "  Altri membri del team realizzano che la delegazione è avvenuta mentre tentano di contattare il Dr. Piccio, in modo che ora sappiano di contattare il Dr. Ehrle nel frattempo. Non ne consegue confusione con il paziente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams

Gli amministratori devono tenere presente che le note di stato e i comportamenti di menzione della delega dipendono in parte dalla modalità di coesistenza di un utente. Questa matrice Mostra le possibilità:

|Modalità Co-Existence | Comportamento previsto|
|---|---|
|TeamsOnly |Gli utenti possono impostare una nota solo da teams. <br> La nota Teams dell'utente è visibile in teams & SfB. |
|Isole | Nota dell'utente impostata in teams visibile solo in teams. <br> Nota dell'utente impostata in SfB visibile solo in SfB |
|Modalità * SfB | Gli utenti possono impostare una nota solo da SfB. <br> La nota SfB dell'utente è visibile in SfB & teams.  |
|||

Un utente può impostare una nota solo in teams se la modalità è TeamsOnly o Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Visualizzazione delle note impostate in Skype for business
  
Non ci sono indicazioni visive che una nota sia stata impostata da Skype for business.

Skype for business non applica un limite di caratteri alle note di stato. Microsoft teams visualizzerà solo i primi 280 caratteri di una nota impostata da Skype for business. Un oggetto Ellipse (...) alla fine di una nota indica il troncamento.
  
Skype for business non supporta gli orari di scadenza delle note.

La migrazione delle note da Skype for business a teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.

## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](../../coexistence-chat-calls-presence.md)
