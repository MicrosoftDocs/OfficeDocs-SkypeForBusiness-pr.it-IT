---
title: Server proxy per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
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
- Optimization
description: Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.
ms.openlocfilehash: fcae4ec366845818d515a4d78c79ea77d038a4a5
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211023"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Server proxy per Skype for Business online

[] Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Skype for Business più sicuro perché il suo traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi porteranno a un'esperienza negativa in scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguire le altre raccomandazioni nelle nostre linee guida di rete:
    
  - [Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Ottimizzare la rete per Skype for Business online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>See also

[Ottimizzare la rete per Skype for Business online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 