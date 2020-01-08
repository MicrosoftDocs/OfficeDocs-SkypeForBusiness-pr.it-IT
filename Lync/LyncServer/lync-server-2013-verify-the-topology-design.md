---
title: 'Lync Server 2013: Verificare la progettazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Verificare la progettazione della topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-01-02_

Generatore di topologia verifica automaticamente la topologia. Qualsiasi errore di topologia viene identificato come errore di convalida, indicato dall'icona di errore di convalida accanto al ruolo del server. È importante verificare anche che la topologia rappresenti correttamente la topologia della distribuzione.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Per verificare la topologia prima della pubblicazione

1.  Verificare che tutti gli URL semplici siano configurati correttamente.

2.  Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologia, incluse le regole del firewall necessarie.

3.  Verificare che la condivisione file sia disponibile e che siano definite le autorizzazioni appropriate.

4.  Verificare che i ruoli del server corretti che soddisfano i requisiti di distribuzione siano definiti nella topologia.

5.  Verificare che i server siano presenti in servizi di dominio Active Directory. Ciò avverrà automaticamente se i server sono stati aggiunti al dominio.

Dopo aver verificato la topologia e non sono presenti errori di convalida, è necessario essere pronti per pubblicare la topologia. Se sono presenti errori di convalida, è necessario correggerli prima di poter pubblicare la topologia. Per informazioni dettagliate sulla pubblicazione della topologia, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

