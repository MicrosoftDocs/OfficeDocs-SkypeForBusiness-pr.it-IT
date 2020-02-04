---
title: Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP
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
ms.openlocfilehash: 98fec3082c172cc9e31d931d1c64ef3eaeccd04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Dopo che un pool di Edge non riuscito usato per ospitare la Federazione è stato riportato online, usare questa procedura per non tornare più alla route federativo di Lync Server e/o alla route della Federazione XMPP per usare di nuovo questo pool di Edge ripristinato.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Riattivazione della Federazione in un pool Edge ripristinato

1.  Nel pool di Edge ora disponibile di nuovo, avviare i servizi Edge.

2.  Se si vuole ripristinare la route federativo di Lync Server per l'uso del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - In un server front-end aprire Generatore di topologia. Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione. Selezionare **modifica proprietà**.
    
      - In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.
    
      - Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server originale che si vuole usare per la Federazione. Selezionare **modifica proprietà**.
    
      - In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.
    
      - Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**. Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**. Al termine della pubblicazione, fare clic su **fine**.
    
      - Nell'Edge Server aprire la distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna Lync Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Lync Server**. Fare di nuovo clic su **Esegui**.
    
      - In configurazione componenti di Lync Server fare clic su **Avanti**. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **fine** per completare la distribuzione.

3.  Se si vuole eseguire il failover della route federativa XMPP per usare il server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP al pool Edge che ora ospiterà la Federazione XMPP (in questo esempio, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In questo esempio, Microsoft1 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer1.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.
    
      - Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente. Questo record SRV deve avere un valore di porta 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.
    
      - Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.

4.  Se i pool Front-End sono rimasti in uso nel sito che contiene il pool di bordi non riuscito ed è stato ripristinato, è necessario aggiornare il servizio di Web Conferencing e il servizio di conferenza telefonica a/V in questi pool di front-end per usare di nuovo i pool di bordi nel sito locale. Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Se il pool Front-end nello stesso sito del pool di Edge non è riuscito anche, è ora possibile usare Invoke-CsPoolFailback per non eseguire il backup del pool Front-end.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Ripristino di emergenza dei server perimetrali in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

