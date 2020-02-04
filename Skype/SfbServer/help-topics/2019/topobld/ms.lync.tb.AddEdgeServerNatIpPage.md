---
title: Aggiungere Edge Server NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: L'indirizzo IP pubblico è l'indirizzo IP usato da NAT (Network Address Translation). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stato selezionato l'indirizzo IP esterno di questo pool di bordi viene tradotto dall'opzione NAT nella pagina Seleziona caratteristiche della procedura guidata.
ms.openlocfilehash: f06d9b61d5ffad29d24e143cf3afbbc4501a67d4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689415"
---
# <a name="add-edge-server-nat-ip"></a>Aggiungere Edge Server NAT IP

L'indirizzo IP pubblico è l'indirizzo IP usato da NAT (Network Address Translation). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stato selezionato **l'indirizzo IP esterno di questo pool di bordi viene tradotto dall'opzione NAT** nella pagina **Seleziona caratteristiche** della procedura guidata.

> [!NOTE]
> NAT (Network Address Translation) Abilita client o server in una rete privata, ad esempio l'intervallo 192.168.0.0, per comunicare con sistemi su reti remote tramite le reti Internet pubbliche. NAT funziona usando un singolo indirizzo IP pubblico su un'interfaccia esterna e associando indirizzi IP interni con l'unico indirizzo IP pubblico. Il mapping NAT associa un indirizzo interno all'indirizzo IP pubblico esterno. Il sistema remoto Visualizza solo l'indirizzo pubblico dell'origine. Il sistema remoto risponde all'origine e la fonte si riferisce alla mappa NAT per determinare l'indirizzo IP interno a cui deve essere restituita la risposta.

È possibile aggiungere il supporto per l'accesso degli utenti esterni durante o dopo la distribuzione della topologia iniziale. Per informazioni dettagliate sull'aggiunta di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.


