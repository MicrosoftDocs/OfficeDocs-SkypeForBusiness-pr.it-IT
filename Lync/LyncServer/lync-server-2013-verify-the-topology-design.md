---
title: 'Lync Server 2013: verificare la progettazione della topologia'
description: 'Lync Server 2013: verificare la progettazione della topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560192"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a>Verificare la progettazione della topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-01-02_

Generatore di topologie verifica automaticamente la topologia. Gli eventuali errori di topologia vengono identificati come errori di convalida e indicati dall'apposita icona accanto al ruolo del server. È inoltre importante verificare che la topologia rappresenti correttamente la topologia della propria distribuzione.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Per verificare la topologia prima della pubblicazione

1.  Controllare che tutti gli URL semplici siano configurati in modo corretto.

2.  Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologie, incluse le eventuali regole del firewall necessarie.

3.  Verificare che la condivisione file sia disponibile e siano state definite le autorizzazioni appropriate.

4.  Verificare che nella topologia siano definiti i ruoli del server corretti conformi ai requisiti della distribuzione.

5.  Verificare che i server siano presenti in servizi di dominio Active Directory. Ciò avviene automaticamente se i server sono stati aggiunti al dominio.

Dopo aver verificato la topologia e stabilito che non sono presenti errori di convalida, è possibile procedere con la pubblicazione della topologia. Gli eventuali errori di convalida rilevati dovranno essere risolti prima di poter pubblicare la topologia. Per informazioni dettagliate sulla pubblicazione della topologia, vedere [publish the topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

