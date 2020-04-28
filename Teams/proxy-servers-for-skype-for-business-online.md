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
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Microsoft teams o Skype for business.
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905678"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Server proxy per Teams o Skype for Business Online

Questo articolo fornisce indicazioni sull'uso di un server proxy con team o Skype for business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda i team o il traffico di Skype for business sui proxy, Microsoft consiglia di ignorare i proxy. I proxy non rendono più sicure le squadre o Skype for business perché il traffico è già crittografato.
  
E avere un proxy può causare problemi. I problemi relativi alle prestazioni possono essere introdotti nell'ambiente attraverso la latenza e la perdita di pacchetti. I problemi come questi generano un'esperienza negativa in tali team o scenari di Skype for business come audio e video, dove i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno alcuna possibilità di ignorare un proxy per il traffico di teams o Skype for business. In questo caso, i problemi menzionati sopra devono essere tenuti in considerazione.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguire le altre raccomandazioni nelle nostre linee guida per la rete: [preparare la rete dell'organizzazione per i team](prepare-network.md)
  
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Office 365](https://aka.ms/pnc)

[Preparare la rete dell'organizzazione per Teams](prepare-network.md)
