---
title: 'Teams: Gestire le notifiche di chiamata'
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
ms.openlocfilehash: 8326a9eb1f7a6ad9fb13c622c4f03d0f9af40af8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233041"
---
# <a name="manage-call-notifications"></a>Gestire le notifiche di chiamata

Questo articolo descrive come gestire le notifiche di chiamata per gli utenti. È possibile configurare gli endpoint di chiamata sia per Teams che per un PBX (Private Branch Exchange) o SBC (Session Border Controller) di terze parti.  Questa configurazione è utile, ad esempio, se si vuole inviare una chiamata ai telefoni cellulari e da tavolo di un utente contemporaneamente.   

Nel diagramma seguente l'utente Irena ha due endpoint:

- Un endpoint Teams
- Un telefono SIP connesso a un SBC di terze parti

Quando arriva una chiamata, la SBC forizza la chiamata tra Sistema telefonico Direct Routing e SBC di terze parti.


![Diagramma che mostra gli endpoint Teams forked](media/direct-routing-call-notification-1.png)

Se la chiamata viene accettata su Fork 2 (da parte di SBC di terze parti), Teams genererà una notifica "Chiamata persa".  

È possibile impedire la notifica "Chiamata persa" configurando SBC in modo che invii un messaggio Annulla al fork 1 nel modo seguente:

MOTIVO: SIP; causa=200;testo"Chiamata completata altrove" 

La chiamata non verrà registrata nei record dei dettagli della chiamata di Telefono Microsoft sistema come chiamata riuscita. La chiamata verrà registrata come "Tentativo" con codice SIP finale "487", sottocodice finale Microsoft "540200" e frase del codice SIP finale "Chiamata completata altrove".  Per visualizzare i record dei dettagli delle chiamate, passare al portale di amministrazione di Teams, analisi e report, report sull'utilizzo e selezionare Utilizzo PSTN.


Il diagramma seguente illustra la scala SIP per fork 1, spiega il flusso delle chiamate e il motivo previsto nel messaggio Annulla. 

![Diagramma che mostra gli endpoint Teams forked](media/direct-routing-call-notification-2.png)
