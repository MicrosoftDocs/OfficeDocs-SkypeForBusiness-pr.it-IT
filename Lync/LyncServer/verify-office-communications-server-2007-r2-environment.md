---
title: Verificare l'ambiente Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Verificare l'ambiente Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Office Communications Server 2007 R2, è necessario verificare che i servizi Office Communications Server 2007 R2 siano configurati e avviati.

**Verificare che il pool venga avviato con lo strumento di amministrazione di Office Communications Server 2007 R2**

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Espandere il nodo **Forest** , espandere il nodo **Standard Edition Servers** o **pool Enterprise** e quindi espandere il nome del pool o del server.

3.  Verificare che i servizi siano in uso nel server standard o nel pool Enterprise.
    
    Console di amministrazione di ![Office Communications server 2007 R2], console di amministrazione di(images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "office Communications Server 2007 R2")

**Rivedere gli utenti configurati per Office Communications Server 2007 R2**

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Espandere il nodo **Forest** , espandere il nodo **Standard Edition Servers** o **pool Enterprise** e quindi espandere il nome del pool o del server.

3.  Fare clic su **utenti**.

4.  Verificare l'elenco degli utenti di Office Communications Server 2007 R2.
    
    ![Elenco fo utenti nell'elenco degli strumenti di amministrazione OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "per gli utenti nello strumento di amministrazione OCS")

**Verificare la configurazione legacy del partner federato XMPP**

1.  Dal server XMPP legacy, passare all'applet strumenti\\di amministrazione di servizi.

2.  Verificare che il servizio gateway XMPP di Office Communications Server sia stato avviato.
    
    Servizio gateway ![XMPP di Office Communications Server Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP")

</div>

<span> </span>

</div>

</div>

</div>

