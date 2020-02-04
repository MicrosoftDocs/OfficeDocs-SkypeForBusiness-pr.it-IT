---
title: 'Lync Server 2013: Supporto di Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd35b9444f0ede4abc9b66ab6b5513d049df57ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Supporto di Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-04_

Di seguito sono riportate le topologie locali dei servizi di dominio Active Directory supportate da Lync Server 2013:

  - Singola foresta con un singolo dominio

  - Singola foresta con un solo albero e più domini

  - Foresta singola con più alberi e spazi dei nomi disgiunti

  - Più foreste in una topologia di foresta centrale

  - Più foreste in una topologia di foresta di risorse

<div>


> [!NOTE]  
> Lync Server 2013 non supporta i domini con etichetta singola. Ad esempio, è supportata una foresta con un dominio radice denominato <STRONG>contoso. local</STRONG> , ma un dominio radice con etichetta singola denominata <STRONG>local</STRONG> non è supportato. Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>singola".



</div>

<div>


> [!NOTE]  
> Lync Server 2013 non supporta la ridenominazione dei domini. Se è necessario rinominare un dominio in cui è distribuito Lync Server, è necessario prima disinstallare Lync Server, quindi rinominare il dominio e quindi reinstallare Lync Server.



</div>

Per informazioni dettagliate sulle topologie e i requisiti supportati per le distribuzioni locali, vedere [requisiti di servizi di dominio Active Directory, supporto e topologie in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

