---
title: Server proxy per Teams o Skype for Business Online
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Microsoft Teams o Skype for Business.
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176673"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Server proxy per Teams o Skype for Business Online

Questo articolo fornisce indicazioni sull'uso di un server proxy con Teams o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda Teams o il traffico Skype for Business tramite proxy, Microsoft consiglia di bypassare i proxy. I proxy non rendono Teams o Skype for Business più sicuri perché il traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. I problemi relativi alle prestazioni possono essere introdotti nell'ambiente tramite latenza e perdita di pacchetti tentando di instradare il traffico di Teams attraverso un server proxy. Problemi come questi produranno un'esperienza negativa in teams o scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.

È consigliabile che il traffico di Teams bypassi l'infrastruttura del server proxy.

## <a name="teams-phones"></a>Telefoni di Teams

I telefoni Di Teams non supportano i server proxy.

Il nostro consiglio è quello di garantire che il traffico sia di segnalazione (TCP 443) che multimediale (UDP 3478-3481) bypassi l'infrastruttura del server proxy.

## <a name="teams-meeting-rooms-and-panels"></a>Sale riunioni e pannelli di Teams

È consigliabile assicurarsi che le sale riunioni di Teams bypassno l'infrastruttura proxy.

Le sale riunioni di Teams basate su Windows supportano i server proxy, ma non i server proxy che richiedono l'autenticazione. Le sale riunioni di Teams basate su Android non supportano i server proxy.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare un proxy per Teams o Skype for Business traffico. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.
  
Microsoft inoltre consiglia:
  
- Usando la risoluzione DNS locale esterna (alcune soluzioni proxy basate sul cloud possono causare la risoluzione DNS in un'altra posizione).
    
- Uso del routing diretto basato su UDP invece di affidarsi al routing basato su TCP per i supporti
    
- Consentire il traffico UDP (3478-3481)

- Consentire tutti gli URL e gli INDIRIZZI IP necessari, inclusi quelli per Azure, Office 365, Intune e Teams Room Pro (se usato)
    
- Seguendo le altre raccomandazioni nelle linee guida per la rete: [Preparare la rete dell'organizzazione per Teams](prepare-network.md)
  
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Microsoft 365 e Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparare la rete dell'organizzazione per Teams](prepare-network.md)
