---
title: Server proxy per Teams o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Skype for Business.
ms.openlocfilehash: c6c094bad366cf6a7febb092d471dd0723ce219b90664963a5e58a2ce64d70ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323518"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Server proxy per Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo articolo fornisce indicazioni sull'uso di un server proxy con Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono più sicuro Skype for Business perché il traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi comportano un'esperienza negativa in scenari Teams o Skype for Business audio e video, in cui i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguendo le altre raccomandazioni nelle linee guida di rete:
    
  - [Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md)
    
  - [Ottimizzare la rete per Skype for Business online](optimizing-your-network.md)
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare la rete per Skype for Business online](optimizing-your-network.md)
 
