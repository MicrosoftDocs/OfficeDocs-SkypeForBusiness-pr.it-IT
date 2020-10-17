---
title: 'Lync Server 2013: modifica del pool di Edge associato a un pool Front End'
description: 'Lync Server 2013: modifica del pool di Edge associato a un pool Front end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab22ba35420341e291d51a1ff012459840e63a56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543572"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Modifica del pool di server perimetrali associato a un pool Front end in Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Modifica del pool di server perimetrali associato a un pool Front End

1.  Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.

2.  Fare clic con il pulsante destro del mouse sul pool e scegliere **Modifica proprietà**.

3.  Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.

4.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Ripristino di emergenza del server perimetrale in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

