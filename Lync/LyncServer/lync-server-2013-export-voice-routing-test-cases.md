---
title: 'Lync Server 2013: esportare i test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d014d9c2748a5e6479c0f86ebd32255f3361ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Esportare test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

I test case consentono di testare le route vocali nell'organizzazione: è possibile definire elementi quali il numero da comporre e il dial plan e i criteri vocali da utilizzare e Lync Server può quindi verificare che, date queste condizioni, il numero fornito possa essere instradato correttamente alla rete PSTN.

I test case, che possono essere creati utilizzando il pannello di controllo di Lync Server, vengono in genere salvati solo sul server in cui è stato creato ed eseguito originariamente il caso. È comunque possibile esportarli come file XML (con estensione vtest) per poi importarli in altri server. Ciò consente di eseguire gli stessi test in computer diversi situati in punti diversi della topologia.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Per esportare un test case di routing vocale

1.  Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **Test routing vocale**.

2.  Nella scheda **Test routing vocale** selezionare il test case (o i test case) da esportare. Per selezionare più test case, fare clic sul primo che si desidera esportare e quindi tenere premuto CTRL e selezionare eventuali altri case da esportare.

3.  Fare clic su **Azione** e quindi su **Esporta test case**.

4.  Nella finestra di dialogo **Salva con nome** selezionare una cartella in cui memorizzare i test case esportati e digitare un nome per il file XML risultante nella casella **Nome file**. Se si esportano più test case, verranno tutti salvati in un unico file XML.

5.  Per salvare i test case, fare clic su **Salva**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Importare test case di routing vocale in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

