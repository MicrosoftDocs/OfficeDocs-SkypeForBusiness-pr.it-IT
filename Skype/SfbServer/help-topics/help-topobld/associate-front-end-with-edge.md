---
title: Associare Front End Server al server perimetrale
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: A ogni pool Front End può essere associato un solo server perimetrale o pool di server perimetrali. Quando si abilita l'accesso degli utenti esterni per un sito, è possibile fornire supporto per gli utenti remoti. È inoltre possibile abilitare il supporto per gli utenti federati, che possono includere il supporto per gli utenti di specifici provider di connettività di messaggistica istantanea pubblica (ad esempio Windows Live) e il supporto per gli utenti anonimi.
ms.openlocfilehash: 6a9288da87e259f770ae2404196a89770133df94
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752075"
---
# <a name="associate-front-end-with-edge"></a>Associare Front End Server al server perimetrale

A ogni pool Front End può essere associato un solo server perimetrale o pool di server perimetrali. Quando si abilita l'accesso degli utenti esterni per un sito, è possibile fornire supporto per gli utenti remoti. È inoltre possibile abilitare il supporto per gli utenti federati, che possono includere il supporto per gli utenti di specifici provider di connettività di messaggistica istantanea pubblica (ad esempio Windows Live) e il supporto per gli utenti anonimi.

Tutti i pool in un sito e i pool di più siti centrali possono usare lo stesso server perimetrale, se l'uso non supera la capacità di questo server. Per informazioni dettagliate sul monitoraggio, compresa la scalabilità, vedere [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulla progettazione di una topologia per supportare l'accesso degli utenti esterni, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) nella documentazione relativa alla distribuzione.