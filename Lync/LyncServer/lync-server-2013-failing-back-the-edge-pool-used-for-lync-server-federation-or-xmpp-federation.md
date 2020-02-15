---
title: Failover del pool di server perimetrali utilizzato per la Federazione o la Federazione XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1adafdb90b9ea42d3694410b2103ef0e46aa70b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Dopo la riconnessione di un pool di server perimetrali utilizzato per ospitare la federazione e in cui si era verificato un problema, eseguire questa procedura per il failback della route di federazione di Lync Server e/o della route di federazione XMPP in modo che venga riutilizzato questo pool di server perimetrali ripristinato.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Failback della federazione a un pool di server perimetrali ripristinato

1.  Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.

2.  Se si desidera eseguire il failback della route di federazione di Lync Server per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - In un server Front End aprire Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.
    
      - In **Generale** in **Modifica proprietà** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.
    
      - Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali originale che si desidera utilizzare di nuovo per la federazione. Scegliere **Modifica proprietà**.
    
      - In **Generale** in **Modifica proprietà** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.
    
      - Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.
    
      - Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna il sistema Lync Server** e quindi su **Installazione o rimozione componenti di Lync Server**. Fare clic su **Riesegui**.
    
      - In Installazione componenti di Lync Server fare clic su **Avanti**. Nella schermata di riepilogo verranno mostrate le azioni man mano che vengono eseguite. Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **Fine** per completare la distribuzione.

3.  Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.
    
      - Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.
    
      - Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.

4.  Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale. Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Ripristino di emergenza del server perimetrale in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

