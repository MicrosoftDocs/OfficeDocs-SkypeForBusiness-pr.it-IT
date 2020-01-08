---
title: Verificare le informazioni sulla topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Verificare le informazioni sulla topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

Il primo passaggio per verificare l'Unione completata correttamente consiste nel visualizzare le informazioni sulla topologia di Office Communications Server 2007 R2 Unite a Lync Server 2013. In Generatore di topologia il nodo **BackCompatSite** Visualizza il nome di dominio completo (FQDN) di ogni pool e server di Office Communications Server 2007 R2 che è stato Unito.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Per visualizzare BackCompatSite in Generatore di topologie

1.  Nell'ambiente Office Communications Server 2007 R2 aprire lo strumento di amministrazione di Office Communications Server 2007 R2 e prendere nota dei nomi di dominio completi dei pool e server legacy.

2.  Nell'ambiente Lync Server 2013 aprire Generatore di topologie e quindi espandere il nodo **BackCompatSite** .

3.  Verificare che i nomi di dominio completi per i pool e i server che si fondono vengano visualizzati.
    
    <div>
    

    > [!NOTE]  
    > Non vengono visualizzate informazioni in <STRONG>BackCompatSite</STRONG> per i ruoli server collocati in un server front-end o in un server Standard Edition. Vengono mostrati solo i ruoli del server necessari per l'interoperabilità tra Office Communications Server 2007 R2 e Lync Server 2013.

    
    </div>

Finestra di dialogo Generatore di topologia della finestra di ![BackCompatSite]generatore di topologia(images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "BackCompatSite")

È anche possibile usare il pannello di controllo di Lync Server 2013 per visualizzare la topologia unita. Nel pannello di controllo di Lync Server 2013 è possibile visualizzare ogni nome di dominio completo del server, FQDN del pool e sito per la topologia unita. I server Uniti hanno un nome di **sito** di **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Per visualizzare la topologia unita nel pannello di controllo di Lync Server 2013

1.  Aprire il pannello di controllo di Lync Server 2013.

2.  Fare clic su **topologia**.

3.  Nella scheda **stato** verificare che i server e i pool conglobati vengano visualizzati cercando **BackCompatSite** nella colonna **sito** .

![Pannello di controllo di Lync Server che mostra la topologia unita](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Pannello di controllo di Lync Server con topologia unita")

Per visualizzare altri dettagli su un pool Unito, usare il cmdlet **Get-CsPool** . Oltre alle informazioni disponibili in Generatore di topologia e nel pannello di controllo di Lync Server 2013, questo cmdlet Visualizza i servizi eseguiti nel pool di Lync Server 2013.

<div>


> [!NOTE]  
> Quando si pubblica la topologia dopo l'esecuzione della creazione guidata unione in Generatore di topologie, le directory conferenza vengono unite a Lync Server 2013. Le directory conferenza possono essere verificate eseguendo il cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Per visualizzare i servizi in un pool Unito

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Ad esempio:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Per verificare l'Unione delle directory conferenza

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsConferenceDirectory

3.  Verificare che tutte le directory conferenza per il pool o il server da unire siano ora in Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

