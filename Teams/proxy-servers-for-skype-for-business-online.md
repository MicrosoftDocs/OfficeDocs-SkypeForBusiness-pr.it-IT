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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436682"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Server proxy per Teams e Skype for Business Online

Questo articolo fornisce indicazioni sull'uso di un server proxy con Teams o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda Teams o il traffico Skype for Business tramite proxy, Microsoft consiglia di bypassare i proxy. I proxy non rendono Teams o Skype for Business più sicuri perché il traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. I problemi relativi alle prestazioni possono essere introdotti nell'ambiente tramite latenza e perdita di pacchetti tentando di instradare il traffico di Teams attraverso un server proxy. Problemi come questi produranno un'esperienza negativa in teams o scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.

È consigliabile che il traffico di Teams bypassi l'infrastruttura del server proxy. È possibile ottenere questo risultato inserendo i telefoni di Teams e i dispositivi delle sale riunioni sulla propria VLAN e fornendo loro l'accesso a Internet.

## <a name="windows-based-teams-devices"></a>Windows-Based dispositivi di Teams

Le sale riunioni di Teams basate su Windows e Surface Hub supportano alcuni server proxy, ma non supportano i server proxy che richiedono l'autenticazione.

È consigliabile che questi dispositivi bypassno l'infrastruttura proxy e accingono ai servizi di Microsoft 365 tramite il firewall.

## <a name="android-based-teams-devices"></a>Android-Based dispositivi di Teams

I dispositivi Teams basati su Android, inclusi i telefoni, i pannelli, gli schermi e le schede di Teams, non supportano i server proxy.

A causa del modo in cui determinati componenti in esecuzione su questi dispositivi accedono a Internet, non è possibile instradare tutto il traffico attraverso un proxy. È necessario assicurarsi che il traffico tra questi dispositivi e i servizi di Microsoft 365 sia consentito attraverso il firewall.

## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare un proxy per Teams o Skype for Business traffico. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.

> [!Note]
> Se si usa un certificato firmato privatamente nell'infrastruttura proxy, è necessario installare il certificato firmato privatamente e la catena di certificati nel dispositivo della sala riunioni di Teams per consentire al dispositivo di considerare attendibile il certificato. L'installazione di certificati firmati privatamente su telefoni Teams e altri dispositivi Teams basati su Android non è supportata.
  
Microsoft inoltre consiglia:
  
- Usando la risoluzione DNS locale esterna (alcune soluzioni proxy basate sul cloud possono causare la risoluzione DNS in un'altra posizione).

- Garantire il percorso tra il dispositivo Teams e il servizio è il più breve e diretto possibile
    
- Uso del routing diretto basato su UDP invece di affidarsi al routing basato su TCP per i supporti
    
- Consentire il traffico UDP per Teams Media (3478-3481) attraverso il firewall

- Consentire tutti gli URL e gli INDIRIZZI IP necessari, inclusi quelli per Azure, Office 365, Intune e Teams Room Pro (se usati) tramite il firewall
    
- Seguendo le altre raccomandazioni nelle linee guida per la rete: [Preparare la rete dell'organizzazione per Teams](prepare-network.md)
  
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Microsoft 365 e Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparare la rete dell'organizzazione per Teams](prepare-network.md)
