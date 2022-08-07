---
title: Gestire le notifiche di chiamata per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notifica di chiamata instradamento diretto
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268431"
---
# <a name="manage-call-notifications"></a>Gestire le notifiche di chiamata

Questo articolo descrive come gestire le notifiche di chiamata per gli utenti di Direct Routing. È possibile configurare gli endpoint di chiamata sia per Teams che per un PRIVATE Branch Exchange (PBX) di terze parti o un session border controller (SBC). Questa configurazione è utile, ad esempio, se si vuole inviare una chiamata contemporaneamente ai telefoni cellulari e da tavolo di un utente.   

Nel diagramma seguente, l'utente Irena ha due endpoint:

- Endpoint di Teams
- Un telefono SIP connesso a una scheda SBC di terze parti

All'arrivo di una chiamata, SBC fork la chiamata tra Direct Routing e SBC di terze parti.


![Diagramma che mostra gli endpoint di Teams biforrati.](media/direct-routing-call-notification-1.png)

Se la chiamata viene accettata su Fork 2 (da parte di SBC di terze parti), Teams genererà una notifica "Chiamata senza risposta".  

È possibile impedire la notifica "Chiamata persa" configurando la SBC per inviare un Cancel on Fork 1 come segue:

MOTIVO: SIP; cause=200;text"Chiamata completata altrove" 

La chiamata non verrà registrata nei record dei dettagli della chiamata di Sistema telefonico teams come chiamata riuscita. La chiamata verrà registrata come "Tentativo" con codice SIP finale "487", sottocodice finale Microsoft "540200" e frase con codice SIP finale "Chiamata completata altrove".  (Per visualizzare i record dei dettagli delle chiamate, vai al centro Amministrazione teams -> **Report di analisi e report** -> **sull'utilizzo** e seleziona **Utilizzo PSTN**.


Il diagramma seguente illustra la scala SIP per Fork 1, illustra il flusso delle chiamate e il MOTIVO previsto nel messaggio Annulla. 

![Il diagramma mostra gli endpoint di Teams biforrati.](media/direct-routing-call-notification-2.png)
