---
title: Compatibilità di Lync Server 2013 con la resilienza di siti metropolitani di Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Resilienza di siti metropolitani di Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-19_

La soluzione di resilienza del sito metropolitano supportata per Lync Server 2010 non è supportata per Lync Server 2013. Questa soluzione implicava un unico pool Front-end tra due centri dati della stessa area metropolitana.

La soluzione di resilienza del sito metropolitano è stata progettata per il ripristino dalla perdita di un data center completo. Quando si estende il pool in due centri dati, in genere si colloca la metà delle estremità anteriori in un centro dati e l'altra metà nel secondo Data Center. Se si perde un intero centro dati, è stato perso metà dei server front-end. Ciò può causare problemi con il nuovo modello di sistema distribuito per i pool Front-end in Lync Server 2013. Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

