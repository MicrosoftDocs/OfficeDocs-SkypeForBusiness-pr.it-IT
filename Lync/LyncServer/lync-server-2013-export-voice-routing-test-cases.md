---
title: 'Lync Server 2013: Esportare test case di routing vocale'
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
ms.openlocfilehash: 781c9e312044193cb6195ee849a880bea6e08485
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Esportare test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

I casi di test consentono di testare le route vocali nell'organizzazione: si definiscono elementi come il numero da chiamare e il dial plan e il criterio vocale da utilizzare e Lync Server può quindi verificare che, in base a tali condizioni, il numero fornito possa essere indirizzato correttamente alla rete PSTN.

I casi di test, che possono essere creati tramite il pannello di controllo di Lync Server, vengono in genere salvati solo nel server in cui è stato originariamente creato ed eseguito il caso. Tuttavia, questi test case possono essere esportati come file XML (con estensione vtest) e quindi importati in altri server. In questo modo è possibile eseguire gli stessi test in computer diversi situati in punti diversi della topologia.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Per esportare un test case di routing vocale

1.  Nel pannello di controllo di Lync Server fare clic su **routing vocale** e quindi su **Test routing vocale**.

2.  Nella scheda **Test routing vocale** selezionare il test case (o i test case) da esportare. Per selezionare più test case, fare clic sul primo caso da esportare, quindi tenere premuto CTRL e selezionare i casi aggiuntivi da esportare.

3.  Fare clic su **azione**, quindi su **Esporta test case**.

4.  Nella finestra di dialogo **Salva con** nome selezionare una cartella in cui archiviare i test case esportati e digitare un nome per il file XML risultante nella casella **file name** . Tieni presente che se stai esportando più casi di test, tutti questi test case verranno salvati in un singolo file XML.

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

