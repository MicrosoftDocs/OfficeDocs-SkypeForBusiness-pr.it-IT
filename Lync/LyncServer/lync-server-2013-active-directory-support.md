---
title: Lync Server 2013 supporto di Active Directory
description: Lync Server 2013 supporto di Active Directory.
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
ms.openlocfilehash: 349862b2f541ef3033c9a725a6ff04c6a4e219f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567932"
---
# <a name="active-directory-support-in-lync-server-2013"></a>Supporto di Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-04_

Di seguito sono riportate le topologie locali dei servizi di dominio Active Directory supportate da Lync Server 2013:

  - Foresta singola con singolo dominio

  - Foresta singola con albero singolo e più domini

  - Foresta singola con più alberi e spazi dei nomi disgiunti

  - Più foreste in una topologia di foreste centralizzate

  - Più foreste in una topologia di foresta di risorse

<div>


> [!NOTE]  
> Lync Server 2013 non supporta i domini con etichetta singola. Ad esempio, un insieme di strutture con un dominio radice denominato <STRONG>contoso. local</STRONG> è supportato, ma non è supportato un dominio radice con etichetta singola denominato <STRONG>local</STRONG> . Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per domini con nomi DNS con etichetta singola" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A> .



</div>

<div>


> [!NOTE]  
> Lync Server 2013 non supporta la ridenominazione dei domini. Se è necessario rinominare un dominio in cui è distribuito Lync Server, è necessario innanzitutto disinstallare Lync Server, rinominare il dominio e quindi reinstallare Lync Server.



</div>

Per informazioni dettagliate sulle topologie e i requisiti supportati per le distribuzioni locali, vedere [servizi di dominio Active Directory requisiti, supporto e topologie in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

