---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

Dopo la distribuzione del pool pilota, è necessario verificare la coesistenza dei due pool usando gli strumenti di amministrazione per visualizzare le informazioni sul pool. Per i pool di Lync Server 2013 e i pool legacy, è necessario usare il pannello di controllo e gli strumenti del generatore di topologia di Lync Server 2013.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Verificare che i servizi di Lync Server 2013 siano stati avviati

1.  Dal server front-end di Lync Server 2013 passare all'applet strumenti\\di amministrazione di servizi.

2.  Verificare che i servizi seguenti siano in uso nel server front-end:

**Servizi di Lync Server 2013**

![Elenco di servizi di Lync Server avviati](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Elenco di servizi di Lync Server avviati")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Aprire il pannello di controllo di Lync Server 2013

Dal server front-end nella distribuzione di Lync Server 2013 aprire il pannello di controllo di Lync Server 2013 e selezionare il pool di Lync Server 2010. Ripetere la procedura per aprire il pool di Lync Server 2013.

**Aprire il pannello di controllo di Lync Server 2013**

![Finestra di dialogo Seleziona URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Finestra di dialogo Seleziona URL")

<div>


> [!IMPORTANT]  
> In Lync Server 2013 è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di usare il pannello di controllo di Lync Server.



</div>

Questa topologia ora include i ruoli del server Lync Server 2010 e Lync Server 2013.

**Pagina della topologia del pannello di controllo di Lync Server 2013**

![Pannello di controllo di Lync Server - Pagina della topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Pannello di controllo di Lync Server - Pagina della topologia")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Non provare ad aprire la topologia in Generatore di topologia di Lync Server 2010

Se si tenta di aprire la topologia con il generatore di topologia di Lync Server 2010, si verificherà l'errore seguente. La topologia può essere visualizzata solo con il generatore di topologia di Lync Server 2013. Il generatore di topologia di Lync Server 2013 deve essere usato per creare pool sia per Lync Server 2013 che per Lync Server 2010.

**Messaggio di errore del generatore di topologia di Lync Server 2010**

![Errore dello snap-in MMC nel Generatore di topologie di Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Errore dello snap-in MMC nel Generatore di topologie di Lync Server")

</div>

</div>

<span> </span>

</div>

</div>

</div>

