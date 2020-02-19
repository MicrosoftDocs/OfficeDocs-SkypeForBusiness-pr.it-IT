---
title: Compatibilità di Lync Server 2013 con la resilienza del sito metropolitano di Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589120a382d07f611eeb6c8c78ee31a9f2e367ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Resilienza del sito metropolitano di Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-19_

La soluzione di resilienza del sito metropolitano supportata per Lync Server 2010 non è supportata per Lync Server 2013. Tale soluzione prevedeva l'estensione di un singolo pool Front End tra due data center situati nella stessa area metropolitana.

La soluzione di resilienza del sito metropolitano è stata progettata per il ripristino dalla perdita di un datacenter completo. Quando si estende il pool tra due datacenter, in genere si colloca la metà dei front-end in un centro dati e l'altra metà nel secondo centro dati. In caso di perdita di un intero centro dati, la metà dei server front end è stata persa. Ciò può causare problemi con il nuovo modello di sistema distribuito per i pool Front end in Lync Server 2013. Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

