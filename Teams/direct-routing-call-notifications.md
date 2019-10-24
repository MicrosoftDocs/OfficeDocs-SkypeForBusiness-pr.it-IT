---
title: Routing diretto del sistema telefonico
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
description: Notifica delle chiamate di routing diretto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37639380"
---
# <a name="manage-call-notifications"></a>Gestire le notifiche delle chiamate

Questo articolo descrive come gestire le notifiche delle chiamate per gli utenti. È possibile configurare gli endpoint delle chiamate sia in team che in un PBX (Private Branch Exchange) di terze parti o in SBC (Session Border Controller).  Questa operazione è utile, ad esempio, se si vuole inviare una chiamata ai telefoni mobili e da tavolo di un utente contemporaneamente.   

Nel diagramma seguente l'utente Irena ha due endpoint:

- Un endpoint Teams
- Un telefono SIP connesso a un SBC di terze parti

Quando arriva una chiamata, l'SBC biforca la chiamata tra il routing diretto del sistema telefonico e lo SBC di terze parti.


![Diagramma che Mostra gli endpoint di Team biforcati](media/direct-routing-call-notification-1.png)

Se la chiamata viene accettata in fork 2 (da parte di SBC di terze parti), i team generano una notifica "chiamata persa".  

È possibile impedire la notifica "chiamata persa" configurando il SBC per l'invio di un annullamento su fork 1 come indicato di seguito:

MOTIVO: SIP; causa = 200; testo "chiamata completata altrove" 

Tieni presente che la chiamata non verrà registrata nei record dettagli chiamata di Microsoft Phone System come chiamata corretta. La chiamata verrà registrata come "tentativo" con il codice SIP finale "487", il sottocodice finale Microsoft "540200" e la frase finale del codice SIP "chiamata completata altrove".   Per visualizzare i record dettagli chiamata, visitare il portale di amministrazione di teams, le analisi e i report, i report sull'utilizzo e selezionare l'uso di PSNT.


Il diagramma seguente illustra la scala SIP per il fork 1, spiega il flusso delle chiamate e il motivo previsto nel messaggio di annullamento. 

![Diagramma che Mostra gli endpoint di Team biforcati](media/direct-routing-call-notification-2.png)
