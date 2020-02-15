---
title: "Lync Server 2013: contrassegnare un'applicazione Microsoft SIP Processing Language (MSPL) come critica o non critica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Contrassegnare un'applicazione Microsoft SIP Processing Language (MSPL) come critica o non critica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Le applicazioni server MSPL (Microsoft SIP Processing Language) sono applicazioni solo script che utilizzano il linguaggio di scripting di MSPL anziché l'API Microsoft Lync 2010. Alcune applicazioni server MSPL sono specificate come di importanza critica. Se uno script è critico, è necessario che lo script venga avviato durante l'avvio del sistema in modo che Lync Server 2013 inizi. Se lo script ha esito negativo durante l'esecuzione di Lync Server, il server non viene arrestato, ma interrompe l'invio del traffico allo script e scrive gli errori nel registro eventi.

È possibile utilizzare il pannello di controllo di Lync Server per contrassegnare le applicazioni server MSPL (Microsoft SIP Processing Language) come critiche o non contrassegnate.

Non tutti gli script supportano questa opzione. Ad esempio, lo script DefaultRouting è contrassegnato come critico e non è possibile modificare questa opzione per DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Per contrassegnare un'applicazione server MSPL come critica o rimuovere il contrassegno

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Applicazione server**.

4.  Nella pagina **Applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, quindi fare clic sul'applicazione server che si desidera modificare.

5.  Fare clic su **Azione**.

6.  Fare clic su **Seleziona come critica** o su **Deseleziona come critica** (ossia, se lo script supporta questa opzione).

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

