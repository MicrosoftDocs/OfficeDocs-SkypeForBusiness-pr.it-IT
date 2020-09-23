---
title: Aggiungere l'indirizzo IP di NAT del server perimetrale
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
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione Indirizzo IP del pool Edge Server convertito da NAT nella pagina Selezione funzionalità di questa procedura guidata.
ms.openlocfilehash: 12749d3bcaec2478481fc1a4bc5597fb9693c5c4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216547"
---
# <a name="add-edge-server-nat-ip"></a>Aggiungere l'indirizzo IP di NAT del server perimetrale

L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione **Indirizzo IP del pool Edge Server convertito da NAT** nella pagina **Selezione funzionalità** di questa procedura guidata.

> [!NOTE]
> NAT (Network Address Translation) consente ai client o ai server di una rete privata (ad esempio, l'intervallo 192.168.0.0) di comunicare con sistemi nelle reti remote tramite le reti Internet pubbliche. NAT funziona utilizzando un solo indirizzo IP pubblico su un'interfaccia esterna e associando gli indirizzi IP interni a quell'unico indirizzo IP pubblico. Il mapping NAT associa un indirizzo interno all'indirizzo IP pubblico esterno. Il sistema remoto vede solo l'indirizzo pubblico dell'origine. Risponde pertanto all'origine e questa, a sua volta, fa riferimento alla mappa NAT per determinare l'indirizzo IP interno a cui deve essere restituita la risposta.

È possibile aggiungere il supporto dell'accesso utente esterno quando si distribuisce la topologia iniziale o successivamente. Per informazioni dettagliate sull'aggiunta di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.


