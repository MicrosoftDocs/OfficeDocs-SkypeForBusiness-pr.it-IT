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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Microsoft Teams o Skype for Business.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665958"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Server proxy per Teams o Skype for Business Online

Questo articolo fornisce indicazioni sull'uso di un server proxy con Teams o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda il traffico di Teams o Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Teams o Skype for Business più sicuro perché il traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. I problemi di prestazioni possono essere introdotti nell'ambiente attraverso latenza e perdita di pacchetti. Problemi come questi genere genereranno un'esperienza negativa in scenari di Teams o Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare un proxy per il traffico di Teams o Skype for Business. In questo caso, è necessario tenere presenti i problemi descritti in precedenza.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguendo le altre raccomandazioni nelle linee guida di rete: Preparare la rete [dell'organizzazione per Teams](prepare-network.md)
  
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Principi della connettività di rete di Microsoft 365 e Office 365](https://aka.ms/pnc)

[Preparare la rete dell'organizzazione per Teams](prepare-network.md)
