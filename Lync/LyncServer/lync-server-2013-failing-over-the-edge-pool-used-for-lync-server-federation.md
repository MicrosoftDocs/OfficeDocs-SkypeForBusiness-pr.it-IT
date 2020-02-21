---
title: 'Lync Server 2013: failover del pool di server perimetrali utilizzato per la Federazione di Lync'
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
ms.openlocfilehash: 1589fe63c41cb2c4cbff9b72f42a3cc06b43e5d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Se il pool di server perimetrali in cui è stato configurata la federazione di Lync Server diventa non disponibile, è necessario modificare la federazione in modo da utilizzare un pool di server perimetrali diverso, affinché la federazione funzioni.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Failover del pool di server perimetrali utilizzato per la federazione di Lync Server

1.  In un Front End Server aprire Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.

2.  In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.

3.  Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali che si desidera utilizzare per la federazione. Scegliere **Modifica proprietà**

4.  In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.

5.  Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.

6.  Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna il sistema Lync Server** e quindi su **Installazione o rimozione componenti di Lync Server**. Fare clic su **Riesegui**.

7.  In Installazione componenti di Lync Server fare clic su **Avanti**. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **Fine** per completare la distribuzione.
    
    Se il sito che contiene il pool di server perimetrali in errore contiene Front End Server ancora in esecuzione, è necessario aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End per l'utilizzo di un pool di server perimetrali in un sito remoto ancora funzionante. Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Ripristino di emergenza del server perimetrale in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

