---
title: Aggiungere l'indirizzo IP di NAT del server perimetrale
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione Indirizzo IP del pool Edge Server convertito da NAT nella pagina Selezione funzionalità di questa procedura guidata.
ms.openlocfilehash: 178b8af0fbb97a0fc3d7737a7e12381b9fdba1eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840358"
---
# <a name="add-edge-server-nat-ip"></a>Aggiungere Edge Server NAT IP

L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione **Indirizzo IP del pool Edge Server convertito da NAT** nella pagina **Selezione funzionalità** di questa procedura guidata.

> [!NOTE]
> Nat (Network Address Translation) consente ai client o ai server di una rete privata (ad esempio, l'intervallo 192.168.0.0)di comunicare con i sistemi su reti remote tramite le reti Internet pubbliche. NAT funziona utilizzando un solo indirizzo IP pubblico su un'interfaccia esterna e associando gli indirizzi IP interni a quell'unico indirizzo IP pubblico. Il mapping NAT associa un indirizzo interno all'indirizzo IP pubblico esterno. Il sistema remoto vede solo l'indirizzo pubblico dell'origine. Risponde pertanto all'origine e questa, a sua volta, fa riferimento alla mappa NAT per determinare l'indirizzo IP interno a cui deve essere restituita la risposta.

È possibile aggiungere il supporto dell'accesso utente esterno quando si distribuisce la topologia iniziale o successivamente. Per informazioni dettagliate sull'aggiunta di Edge Server a una topologia esistente, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) nella documentazione relativa alla distribuzione di Edge Server.