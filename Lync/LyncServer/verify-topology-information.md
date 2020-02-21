---
title: Verificare le informazioni sulla topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 491078161d86d379ebb78baf819f5b1d888018ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Verificare le informazioni sulla topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

Il primo passaggio per la verifica dell'Unione completata ha esito positivo per visualizzare le informazioni sulla topologia di Office Communications Server 2007 R2 Unite a Lync Server 2013. In Generatore di topologie il nodo **BackCompatSite** Visualizza il nome di dominio completo (FQDN) di ogni pool e server di Office Communications Server 2007 R2 che è stato Unito.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Per visualizzare BackCompatSite in Generatore di topologie

1.  Nell'ambiente Office Communications Server 2007 R2, aprire lo strumento di amministrazione di Office Communications Server 2007 R2 e prendere nota dei nomi FQDN dei pool e server legacy.

2.  Nell'ambiente Lync Server 2013 aprire Generatore di topologie e quindi espandere il nodo **BackCompatSite** .

3.  Verificare che siano visualizzati gli FQDN dei pool e dei server da unire.
    
    <div>
    

    > [!NOTE]  
    > In <STRONG>BackCompatSite</STRONG> non viene visualizzata alcuna informazione per i ruoli del server collocati in un Front End Server o in un server Standard Edition. Vengono visualizzati solo i ruoli del server necessari per l'interoperabilità tra Office Communications Server 2007 R2 e Lync Server 2013.

    
    </div>

![Finestra di dialogo Generatore di topologie BackCompatSite](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Finestra di dialogo Generatore di topologie BackCompatSite")

È inoltre possibile utilizzare il pannello di controllo di Lync Server 2013 per visualizzare la topologia unita. Nel pannello di controllo di Lync Server 2013, è possibile visualizzare ogni server FQDN, FQDN del pool e nome del sito per la topologia unita. Il **Sito** dei server uniti si chiama **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Per visualizzare la topologia unita nel pannello di controllo di Lync Server 2013

1.  Aprire il pannello di controllo di Lync Server 2013.

2.  Fare clic su **Topologia**.

3.  Nella scheda **Stato** verificare che i server e i pool uniti siano visualizzati cercando **BackCompatSite** nella colonna **Sito**.

![Pannello di controllo di Lync Server che mostra la topologia unita](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Pannello di controllo di Lync Server che mostra la topologia unita")

Per visualizzare altri dettagli su un pool unito, utilizzare il cmdlet **Get-CsPool**. Oltre alle informazioni disponibili nel pannello di controllo di generatore di topologie e Lync Server 2013, questo cmdlet consente di visualizzare i servizi in esecuzione nel pool di Lync Server 2013.

<div>


> [!NOTE]  
> Quando si pubblica la topologia dopo aver eseguito la procedura di Unione guidata in Generatore di topologie, le directory conferenze vengono unite a Lync Server 2013. Le directory conferenze possono essere verificate eseguendo il cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Per visualizzare i servizi in un pool unito

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Ad esempio:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Per verificare le directory conferenze unite

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsConferenceDirectory

3.  Verificare che tutte le directory conferenze per il pool o il server in cui si esegue l'Unione siano presenti in Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

