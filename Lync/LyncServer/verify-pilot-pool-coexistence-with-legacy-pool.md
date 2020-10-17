---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8958fbf22e096a1d9fef03afd3aac3b4656ed0e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515933"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool. Per i pool Lync Server 2013 e i pool legacy, è necessario utilizzare il pannello di controllo di Lync Server 2013 e gli strumenti del generatore di topologie.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Verificare che i servizi di Lync Server 2013 siano stati avviati

1.  Dal front end server di Lync Server 2013 passare all'applet servizi di amministrazione degli strumenti \\ .

2.  Verificare che i servizi seguenti siano in esecuzione nel Front End Server:

**Servizi di Lync Server 2013**

![Elenco dei servizi di Lync Server avviati](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Elenco dei servizi di Lync Server avviati")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Aprire il pannello di controllo di Lync Server 2013

Dal front end server nella distribuzione di Lync Server 2013, aprire il pannello di controllo di Lync Server 2013 e selezionare il pool Lync Server 2010. Ripetere la procedura per aprire il pool di Lync Server 2013.

**Aprire il Pannello di controllo di Lync Server 2013**

![Finestra di dialogo Seleziona URL.](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Finestra di dialogo Seleziona URL.")

<div>


> [!IMPORTANT]  
> In Lync Server 2013, è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di utilizzare il pannello di controllo di Lync Server.



</div>

Questa topologia ora include i ruoli del server Lync Server 2010 e Lync Server 2013.

**Pagina della topologia del Pannello di controllo di Lync Server 2013**

![Pannello di controllo di Lync Server-pagina della topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Pannello di controllo di Lync Server-pagina della topologia")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Non tentare di aprire la topologia in Generatore di topologie di Lync Server 2010

Se si tenta di aprire la topologia mediante il generatore di topologie di Lync Server 2010, verrà visualizzato l'errore seguente. La topologia può essere visualizzata solo utilizzando il generatore di topologie di Lync Server 2013. Il generatore di topologie di Lync Server 2013 deve essere utilizzato per creare pool sia per Lync Server 2013 che per Lync Server 2010.

**Messaggio di errore di Generatore di topologie di Lync Server 2010**

![Errore di snap MMC generatore di topologie di Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Errore di snap MMC generatore di topologie di Lync Server")

</div>

</div>

<span> </span>

</div>

</div>

</div>

