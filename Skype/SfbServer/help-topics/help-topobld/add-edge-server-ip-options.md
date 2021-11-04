---
title: Aggiungere opzioni IP del server perimetrale
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali. Ecco come fare:'
ms.openlocfilehash: b26fdd7dccca93f04c5fa5d9ee40e644143f8f9c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776376"
---
# <a name="add-edge-server-ip-options"></a>Aggiungere opzioni Edge Server IP
 
Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali. Ecco come fare:
  
- **Abilita IPv4 sull'interfaccia** interna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv6 sull'interfaccia** interna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv4 sull'interfaccia** esterna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool di server perimetrali
    
- **Abilita IPv6 sull'interfaccia** esterna : selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool di server perimetrali
    
È inoltre possibile configurare il server perimetrale o il pool di server perimetrali per l'utilizzo di un indirizzo di conversione degli indirizzi di rete per gli indirizzi IP esterni. A tale scopo, selezionare la casella di controllo **L'indirizzo IP esterno di questo pool di server** perimetrali viene convertito da NAT.
  
Supporto NAT. Dato che la conversione NAT (Network Address Translation) non è supportata quando si usa il bilanciamento del carico hardware, non selezionare l'opzione NAT quando si distribuisce un pool di server perimetrali con bilanciamento del carico hardware.
  

