---
title: Aggiungere opzioni IP per il server perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool. A questo scopo, eseguire le operazioni seguenti:'
ms.openlocfilehash: f6721f170bbe9a05a247d5ab79fb2cbd1cb7ccaf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698411"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere opzioni IP per il server perimetrale
 
Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool. A questo scopo, eseguire le operazioni seguenti:
  
- **Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge
    
- **Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge
    
- **Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge
    
- **Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge
    
È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni. A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.
  
Supporto NAT. NAT (Network Address Translation) non è supportato quando si usa il bilanciamento del carico hardware, quindi non selezionare l'opzione NAT se si distribuisce un pool di Edge Server con il bilanciamento del carico hardware.
  

