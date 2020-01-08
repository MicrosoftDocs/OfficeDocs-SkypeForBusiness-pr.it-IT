---
title: 'Lync Server 2013: Modifica del pool di server perimetrali associato a un pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Modifica del pool di server perimetrali associato a un pool Front End in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Se un pool di bordi scende ma il pool Front-end nello stesso sito è ancora in corso, è necessario impostare il pool Front-end in modo da usare un pool di Edge in un sito diverso fino a quando non viene ripristinato il pool di Edge non riuscito.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Modifica del pool di bordi associato a un pool Front-End

1.  In Generatore di topologie passare al nome del pool Front-end che è necessario modificare.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

3.  Nella sezione **associazioni** , in **associa Edge pool (per i componenti multimediali)**, usare la casella di controllo a discesa per selezionare il pool di bordi a cui si vuole associare questo pool Front-end.

4.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Ripristino di emergenza dei server perimetrali in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

