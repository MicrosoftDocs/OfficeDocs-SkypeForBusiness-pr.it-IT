---
title: 'Lync Server 2013: disabilitare il bypass multimediale di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Disabilitare il bypass multimediale di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Microsoft Lync Server 2013. Il bypass multimediale consente alle chiamate di aggirare il Mediation Server. Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione pianificazione. È possibile disabilitare il bypass multimediale dal pannello di controllo di Lync Server. Per informazioni dettagliate sull'abilitazione e la configurazione del bypass mediale, vedere [Abilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Per disabilitare il bypass multimediale

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** . Esiste sempre una sola configurazione ed è sempre denominata globale.

5.  Nel menu **modifica** fare clic su **Visualizza dettagli**.

6.  Nella pagina **Modifica impostazioni globali** deselezionare la casella di controllo **Abilita esclusione multimediale** .

7.  Fare clic su **conferma** per salvare le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare il bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

