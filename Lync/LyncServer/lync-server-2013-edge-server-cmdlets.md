---
title: 'Lync Server 2013: cmdlet Edge Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5c743cb229adb6f1ed8298d51713da181750cea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a>Cmdlet Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

I server perimetrali consentono di estendere le funzionalità di Microsoft Lync Server 2013 a utenti che non hanno eseguito l'accesso alla rete interna. Se ad esempio sono presenti utenti remoti, gli utenti autenticati che accedono a Lync Server 2013 tramite Internet invece che tramite la rete interna, è necessario configurare un server perimetrale che esegua il servizio Access Edge di Lync Server. Inoltre, gli Edge Server sono obbligatori per stabilire la Federazione con un'altra organizzazione o per consentire agli utenti il diritto di comunicare con persone che hanno account con un servizio di messaggistica istantanea pubblico, ad esempio Yahoo\!, AOL o MSN.

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a>Cmdlet Edge Server

Di seguito è riportato un elenco di cmdlet correlati direttamente alla gestione di Edge Server:

**Edge Server**

  - <span></span>  
    [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))

  - <span></span>  
    [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Blog di PowerShell per Lync Server](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

