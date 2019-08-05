---
title: Aggiungere le opzioni IP di Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool. A questo scopo, eseguire le operazioni seguenti:'
ms.openlocfilehash: 12b1cdb36809ac703bd3383795ea92bdf48cdd31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195524"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere le opzioni IP di Edge Server
 
Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool. A questo scopo, eseguire le operazioni seguenti:
  
- **Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge
    
- **Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge
    
- **Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge
    
- **Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge
    
È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni. A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.
  
Supporto NAT. NAT (Network Address Translation) non è supportato quando si usa il bilanciamento del carico hardware, quindi non selezionare l'opzione NAT se si distribuisce un pool di Edge Server con il bilanciamento del carico hardware.
  

