---
title: "Lync Server 2013: eliminazione di collegamenti all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>Eliminazione di collegamenti all'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network). È possibile usare il pannello di controllo di Lync Server per eliminare un collegamento esistente tra due aree di rete. Per informazioni dettagliate su come creare o modificare il collegamento all'area di rete, vedere [configurazione dei collegamenti all'area di rete in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Per eliminare un collegamento all'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.

4.  Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > Puoi eliminare più di un collegamento all'area geografica alla volta. Per eseguire questa operazione, premere CTRL e selezionare più collegamenti all'area geografica tenendo premuto CTRL. In alternativa, per selezionare tutti i collegamenti all'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di collegamenti all'area di rete in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

