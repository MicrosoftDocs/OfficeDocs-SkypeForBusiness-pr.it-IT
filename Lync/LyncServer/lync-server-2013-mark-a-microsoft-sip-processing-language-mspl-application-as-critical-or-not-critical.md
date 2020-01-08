---
title: "Lync Server 2013: contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le applicazioni server MSPL (Microsoft SIP Processing Language) sono applicazioni solo script che usano il linguaggio di scripting MSPL invece dell'API Microsoft Lync 2010. Alcune applicazioni server MSPL sono specificate come critiche. Se uno script è critico, lo script deve iniziare durante l'avvio del sistema per consentire l'avvio di Lync Server 2013. Se lo script non riesce mentre Lync Server è in esecuzione, il server non si arresta, ma smette di inviare il traffico allo script e scrive gli errori nel log eventi.

È possibile usare il pannello di controllo di Lync Server per contrassegnare le applicazioni server MSPL (Microsoft SIP Processing Language) come critiche o deselezionarle.

Non tutti gli script supportano questa opzione. Ad esempio, lo script DefaultRouting è contrassegnato come critico e questa opzione non può essere modificata per DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Per contrassegnare o decontrassegnare un'applicazione server MSPL come critica

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **applicazione server**.

4.  Nella pagina **applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, e quindi fare clic sull'applicazione server che si desidera modificare.

5.  Fare clic su **azione**.

6.  Fare clic su **Segna come critico** o **deselezionare come critica** , ovvero se lo script supporta questa opzione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

