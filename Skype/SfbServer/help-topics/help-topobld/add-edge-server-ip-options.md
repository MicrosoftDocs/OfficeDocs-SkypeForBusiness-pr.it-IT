---
title: Aggiungere opzioni IP del server perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di Edge. Ecco come fare:'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219791"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere opzioni IP del server perimetrale
 
Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di Edge. Ecco come fare:
  
- **Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale
    
- **Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale
    
- **Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
- **Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni. A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.
  
Supporto NAT. Dato che la conversione NAT (Network Address Translation) non è supportata quando si usa il bilanciamento del carico hardware, non selezionare l'opzione NAT quando si distribuisce un pool di server perimetrali con bilanciamento del carico hardware.
  

