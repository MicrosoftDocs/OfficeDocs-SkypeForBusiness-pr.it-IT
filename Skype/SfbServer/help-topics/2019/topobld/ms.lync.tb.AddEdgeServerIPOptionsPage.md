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
description: 'Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali. Ecco come fare:'
ms.openlocfilehash: 60b9931a8fd3fad950f3277a27deb420ddb749dbee9269ca628023ea0806e14c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294253"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere opzioni Edge Server IP
 
Skype for Business Server consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali. Ecco come fare:
  
- **Abilita IPv4 sull'interfaccia** interna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv6 sull'interfaccia** interna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv4 sull'interfaccia** esterna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv6 sull'interfaccia** esterna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool di server perimetrali
    
È inoltre possibile configurare il server perimetrale o il pool di server perimetrali per l'utilizzo di un indirizzo di conversione degli indirizzi di rete per gli indirizzi IP esterni. A tale scopo, selezionare la casella di controllo **L'indirizzo IP esterno del pool di server** perimetrali viene convertito da NAT.
  
Supporto NAT. Dato che la conversione NAT (Network Address Translation) non è supportata quando si usa il bilanciamento del carico hardware, non selezionare l'opzione NAT quando si distribuisce un pool di server perimetrali con bilanciamento del carico hardware.
  

