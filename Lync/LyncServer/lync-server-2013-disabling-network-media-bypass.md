---
title: 'Lync Server 2013: disattivazione del bypass multimediale di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf551f94bc6b3ba919437730841f54dd01e291
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Disabilitazione del bypass multimediale di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

Le impostazioni di bypass multimediale vengono applicate a livello globale in una distribuzione di Microsoft Lync Server 2013. Il bypass multimediale consente alle chiamate di bypassare il Mediation Server. Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione Planning. È possibile disabilitare il bypass multimediale dal pannello di controllo di Lync Server. Per informazioni dettagliate sull'abilitazione e sulla configurazione del bypass mediale, vedere [Abilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su  **Configurazione di rete ** e quindi su  **Globale **.

4.  Nella pagina  **Globale ** fare clic sulla scheda della configurazione  **Globale **. Esiste sempre una sola configurazione ed è sempre denominata Globale.

5.  Scegliere  **Mostra dettagli ** dal menu  **Modifica **.

6.  Nella pagina  **Modifica impostazioni globali ** deselezionare la casella di controllo  **Abilita bypass multimediale **.

7.  Fare clic su  **Commit ** per salvare le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

