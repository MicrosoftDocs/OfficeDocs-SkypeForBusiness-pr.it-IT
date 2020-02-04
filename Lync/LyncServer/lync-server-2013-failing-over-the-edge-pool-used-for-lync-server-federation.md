---
title: 'Lync Server 2013: Failover del pool di server perimetrali utilizzato per la federazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f144def3d3a8df9cc63221342a85666eb3c28913
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Se il pool di Edge in cui è configurata la Federazione di Lync Server è configurato, è necessario cambiare la Federazione per usare un pool di bordi diverso per la Federazione.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Non superato il pool di Edge usato per la Federazione di Lync Server

1.  In un server front-end aprire Generatore di topologia. Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione. Selezionare **modifica proprietà**.

2.  In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.

3.  Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server che si desidera utilizzare per la Federazione. Selezionare **modifica proprietà**.

4.  In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.

5.  Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**. Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**. Al termine della pubblicazione, fare clic su **fine**.

6.  Nell'Edge Server aprire la distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna Lync Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Lync Server**. Fare di nuovo clic su **Esegui**.

7.  In configurazione componenti di Lync Server fare clic su **Avanti**. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **fine** per completare la distribuzione.
    
    Se il sito che contiene il pool di Edge non riuscito contiene server front-end ancora in corso, è necessario aggiornare il servizio servizi di conferenza Web e il servizio di conferenza telefonica a/V in questi pool di front-end per usare un pool di Edge in un sito remoto ancora in corso. Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Ripristino di emergenza dei server perimetrali in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

