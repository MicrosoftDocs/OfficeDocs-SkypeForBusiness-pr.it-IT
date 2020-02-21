---
title: Migrare i telefoni delle aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e33642fe4556397f4c3f71d5dfb582e1868a7ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migrare i telefoni delle aree comuni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità UC di Lync Server. Dopo aver eseguito la migrazione di una distribuzione di Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono delle aree comuni legacy. Utilizzando Lync Server Management Shell, è necessario recuperare tutti gli oggetti contatto associati ai telefoni delle aree comuni di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.

**Migrare i telefoni delle aree comuni**

1.  Dal front end server Lync Server 2013 aprire Lync Server Management Shell.

2.  Dalla riga di comando digitare quanto segue:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013, dal tipo Lync Server Management Shell, eseguire le operazioni seguenti:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

