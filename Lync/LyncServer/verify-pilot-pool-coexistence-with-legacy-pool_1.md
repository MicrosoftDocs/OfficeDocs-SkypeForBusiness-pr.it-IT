---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4952640d6f6e938b460855118163d98e001f6a77
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Verificare il pool nello strumento di amministrazione di Office Communications Server 2007 R2

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.

3.  Verificare che i servizi Office Communications Server 2007 R2 siano in esecuzione nel pool.
    
    ![Console di amministrazione di Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console di amministrazione di Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Verificare il pool pilota nel pannello di controllo di Lync Server 2013

1.  Da un account utente membro del ruolo CsAdministrator accedere al front end server Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Fare clic su **Topologia**.

4.  Verificare che i server distribuiti siano presenti nel pool pilota.
    
    ![Pagina della topologia del pannello di controllo di Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Pagina della topologia del pannello di controllo di Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Verificare che i servizi di Lync Server 2013 siano stati avviati

1.  Nel server front end di Lync Server 2013 aprire l'applet **Servizi** dal gruppo **strumenti di amministrazione** .

2.  Verificare che i servizi elencati corrispondano all'elenco mostrato nella figura che segue.
    
    ![Pagina Servizi in cui è stato avviato Lync Services](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Pagina Servizi in cui è stato avviato Lync Services")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

