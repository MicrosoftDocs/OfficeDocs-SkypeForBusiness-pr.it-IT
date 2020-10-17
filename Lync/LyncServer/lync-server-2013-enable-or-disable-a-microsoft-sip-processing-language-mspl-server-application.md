---
title: "Lync Server 2013: abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language)"
description: "Lync Server 2013: abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language)."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f919599d6c6a39fea73424f4e287f00636c0982
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544782"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

È possibile utilizzare il pannello di controllo di Lync Server per abilitare o disabilitare le applicazioni server MSPL (Microsoft SIP Processing Language) eseguite nell'ambiente Lync Server 2013. Si tratta di applicazioni script che utilizzano un linguaggio di script anziché l'API Microsoft Lync 2013 Preview.

Non tutti gli script possono essere abilitati o disabilitati. Ad esempio, lo script DefaultRouting è abilitato e tale opzione non può essere modificata.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Per abilitare o disabilitare un'applicazione server MSPL

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Applicazione server**.

4.  Nella pagina **Applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, quindi fare clic sul'applicazione server che si desidera modificare.

5.  Fare clic su **Azione**.

6.  Fare clic su **Abilita applicazione** o **Disabilita applicazione**, se lo script supporta tale opzione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Contrassegnare un'applicazione Microsoft SIP Processing Language (MSPL) come critica o non critica in Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

