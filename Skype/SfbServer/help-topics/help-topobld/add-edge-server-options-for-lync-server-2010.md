---
title: Aggiungere opzioni per il server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Si definisce un nuovo Edge Server o un pool di Edge e si presenta la possibilità di definire le caratteristiche per il nuovo server o pool. Le opzioni che è possibile scegliere sono:'
ms.openlocfilehash: 953aa6c0bcb5d5bf65f0ba649545aef909d3b647
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698361"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Aggiungere opzioni per il server perimetrale per Lync Server 2010

Si definisce un nuovo Edge Server o un pool di Edge e si presenta la possibilità di definire le caratteristiche per il nuovo server o pool. Le opzioni che è possibile scegliere sono:

- **Usare un singolo FQDN e un indirizzo IP**: selezionare la casella di controllo per usare un singolo IPv4 o IPv6 (se si sceglie di usare sia IPv4 che IPv6, sarà necessario definire uno dei singoli indirizzi IP) e il nome di dominio completo (FQDN) per le interfacce di Edge esterne.

    > [!IMPORTANT]
    > Se si sceglie questa opzione, si utilizzerà un solo indirizzo IP o uno IPv4 e un IPv6, ma è necessario assegnare numeri di porta diversi a ogni interfaccia Edge.

- **Enable Federation (porta 5061)**: selezionare questa casella di controllo se si vuole eseguire la Federazione con altre federazioni SIP, provider o offerte ospitate che usano il protocollo SIP (Session Initiation Protocol).

- **L'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**: selezionare questa casella di controllo se si usano indirizzi IP privati per le interfacce esterne di Edge e viene fornito un dispositivo NAT (Network Address Translation) per posizionare il pool di Edge o Edge in modo logico dietro.

## <a name="see-also"></a>Vedere anche

[Pianificazione per l'accesso degli utenti esterni](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Distribuzione dell'accesso degli utenti esterni](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
