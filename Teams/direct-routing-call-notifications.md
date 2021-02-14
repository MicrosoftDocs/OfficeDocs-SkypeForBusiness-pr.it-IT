---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notifica di chiamata instradamento diretto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341802"
---
# <a name="manage-call-notifications"></a>Gestire le notifiche di chiamata

Questo articolo descrive come gestire le notifiche di chiamata per gli utenti. È possibile configurare gli endpoint di chiamata sia per Teams che per un pbx (Private Branch Exchange) o un controller dei confini della sessione (SBC) di terze parti.  Questa opzione è utile, ad esempio, se si vuole inviare una chiamata contemporaneamente al cellulare e ai telefoni da tavolo di un utente.   

Nel diagramma seguente l'utente Irena ha due endpoint:

- Endpoint di Teams
- Un telefono SIP connesso a un SBC di terze parti

Quando arriva una chiamata, SBC la forierà tra l'instradamento diretto del sistema telefonico e la SBC di terze parti.


![Diagramma che mostra gli endpoint di Teams forked](media/direct-routing-call-notification-1.png)

Se la chiamata viene accettata su Fork 2 (dalla SBC di terze parti), Teams genererà una notifica "Chiamata senza chiamata".  

È possibile impedire la notifica "Chiamata senza chiamata" configurando SBC in modo da inviare l'opzione Annulla il Fork 1 come indicato di seguito:

MOTIVO: SIP; cause=200;testo"Chiamata completata altrove" 

Nota che la chiamata non verrà registrata nelle registrazioni dei dettagli delle chiamate del Sistema telefonico Microsoft come chiamata riuscita. La chiamata verrà registrata come "Tentativo" con codice SIP finale "487", sottocodice finale Microsoft "540200" e frase del codice SIP finale "Chiamata completata altrove".  Per visualizzare i record di dettaglio delle chiamate, passa al portale di amministrazione di Teams, a Analytics e report, ai report di utilizzo e seleziona Utilizzo PSTN.


Il diagramma seguente illustra la causa sip per Fork 1, spiega il flusso delle chiamate e il motivo previsto nel messaggio Annulla. 

![Diagramma che mostra gli endpoint di Teams forked](media/direct-routing-call-notification-2.png)
