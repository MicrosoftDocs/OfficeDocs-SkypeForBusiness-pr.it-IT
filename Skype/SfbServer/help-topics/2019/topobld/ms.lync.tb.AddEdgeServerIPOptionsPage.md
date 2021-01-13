---
title: Aggiungere opzioni IP del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di Edge. Ecco come fare:'
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801076"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere opzioni Edge Server IP
 
Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di Edge. Ecco come fare:
  
- **Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale
    
- **Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale
    
- **Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
- **Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni. A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.
  
Supporto NAT. Dato che la conversione NAT (Network Address Translation) non è supportata quando si usa il bilanciamento del carico hardware, non selezionare l'opzione NAT quando si distribuisce un pool di server perimetrali con bilanciamento del carico hardware.
  

