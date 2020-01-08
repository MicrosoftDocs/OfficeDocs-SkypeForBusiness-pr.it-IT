---
title: Eseguire la migrazione dei telefoni di aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Eseguire la migrazione dei telefoni di aree comuni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC di Lync Server. Dopo la migrazione di una distribuzione di Lync Server 2010 a Lync Server 2013, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Lync Server Management Shell si recupereranno prima tutti gli oggetti contatto associati ai telefoni delle aree comuni di Lync Server 2010 e quindi li sposteremo nel pool di Lync Server 2013.

**Eseguire la migrazione dei telefoni di aree comuni**

1.  Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013, in Lync Server Management Shell digitare quanto segue:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

