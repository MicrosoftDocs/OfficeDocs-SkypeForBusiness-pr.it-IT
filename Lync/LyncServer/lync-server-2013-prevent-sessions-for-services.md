---
title: 'Lync Server 2013: Impedisci sessioni per i servizi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bfb2316de9ea09db49ac22e0cf0addd0a699739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513243"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>Impedisci sessioni per i servizi in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile utilizzare il pannello di controllo di Lync Server per impedire nuove sessioni per tutti i servizi di Lync Server 2013 in esecuzione in un computer specifico o per impedire nuove sessioni per un servizio Lync Server 2013 specifico.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Per impedire nuove sessioni di tutti i servizi di Lync Server in un computer

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.

5.  Fare clic su **Azione**.

6.  Fare clic su **Impedisci nuove sessioni per tutti i servizi**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per uno specifico servizio

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.

5.  Fare clic su **Proprietà**.

6.  Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.

7.  Fare clic su **Azione**.

8.  Fare clic su **Impedisci nuove sessioni per il servizio**.

9.  Fare clic su **Chiudi**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

