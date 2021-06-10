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
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117724"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Server proxy per Teams o Skype for Business Online

Questo articolo fornisce indicazioni sull'uso di un server proxy con Teams o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda il traffico Teams o Skype for Business proxy, Microsoft consiglia di ignorare i proxy. I proxy non rendono più Teams o Skype for Business perché il traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi comportano un'esperienza negativa in scenari Teams o Skype for Business audio e video, in cui i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno alcuna opzione per ignorare un proxy per Teams o Skype for Business traffico. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguire gli altri suggerimenti nelle linee guida di rete: Preparare la rete [dell'organizzazione per Teams](prepare-network.md)
  
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Microsoft 365 e Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparare la rete dell'organizzazione per Teams](prepare-network.md)