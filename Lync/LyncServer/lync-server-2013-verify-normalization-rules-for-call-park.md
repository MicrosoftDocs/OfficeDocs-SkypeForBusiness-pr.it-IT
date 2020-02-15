---
title: 'Lync Server 2013: verificare le regole di normalizzazione per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ab8e6038fd17daed7f10f11023793b702dd7d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

Le orbite del parcheggio di chiamata non devono essere normalizzate. Controllare i dial plan per assicurarsi che i numeri dell'orbita non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura illustrata in [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) per definire una nuova regola di normalizzazione, in modo che il **motivo corrispondente** identifichi l'intervallo di orbita e il **motivo di conversione** sia **$1**. Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000 – 7999, il **motivo corrispondente** è **^\\({3}7 d) $** e il **motivo della conversione** è **$1**.

<div>


> [!IMPORTANT]  
> Verificare che la regola di normalizzazione predefinita nei dial plan non contenga <STRONG>^ (\d *)</STRONG>. In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

