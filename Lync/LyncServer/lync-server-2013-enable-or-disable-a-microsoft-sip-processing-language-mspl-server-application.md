---
title: "Lync Server 2013: abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language)"
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
ms.openlocfilehash: 12fb1160742898b65b14ea17bc10a9c6ed56c780
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

È possibile usare il pannello di controllo di Lync Server per abilitare o disabilitare le applicazioni server MSPL (Microsoft SIP Processing Language) eseguite nell'ambiente Lync Server 2013. Queste applicazioni sono applicazioni solo script che usano un linguaggio di scripting anziché l'API di Microsoft Lync 2013 Preview.

Non tutti gli script possono essere abilitati o disabilitati. Ad esempio, lo script DefaultRouting è abilitato e questa opzione non può essere modificata per DefaultRouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Per abilitare o disabilitare un'applicazione server MSPL

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **applicazione server**.

4.  Nella pagina **applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, e quindi fare clic sull'applicazione server che si desidera modificare.

5.  Fare clic su **azione**.

6.  Fare clic su **Abilita applicazione** o **Disabilita applicazione** , ovvero se lo script supporta questa opzione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica in Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

