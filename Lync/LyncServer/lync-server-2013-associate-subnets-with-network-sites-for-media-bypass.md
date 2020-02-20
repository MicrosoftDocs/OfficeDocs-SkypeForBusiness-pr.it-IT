---
title: 'Lync Server 2013: associare subnet a siti di rete per il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

<div>


> [!NOTE]  
> In questo argomento si presuppone che siano state configurate impostazioni globali per la funzionalità Media Bypass e che siano stati configurati l'area di rete e i siti di rete per tale funzionalità.



</div>

Ogni subnet della rete deve essere associata a un sito di rete specifico. Le informazioni della subnet, infatti, vengono utilizzate per determinare il sito di rete in cui si trova un endpoint. Quando sono note le posizioni di entrambe le parti di una sessione, il bypass multimediale consente di determinare dove inviare gli elementi multimediali per l'elaborazione.

Per il bypass multimediale non esistono requisiti speciali per l'associazione di subnet a siti di rete. Per creare un'associazione tra le subnet e i siti di rete nella topologia, seguire le procedure illustrate in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Passaggi successivi: creare profili di criteri di larghezza di banda

Dopo aver associato le subnet ai siti di rete per il bypass multimediale, è necessario creare uno o più profili di criteri di larghezza di banda per suddividere le subnet tra quelle con connettività di buon livello e quelle senza, ai fini del bypass multimediale. Tutte le subnet in un'area di rete con siti di rete che non hanno limiti di larghezza di banda dispongono di connettività di buon livello e possono pertanto utilizzare il bypass multimediale.

Per le procedure per la configurazione dei profili dei criteri di larghezza di banda, vedere [create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

