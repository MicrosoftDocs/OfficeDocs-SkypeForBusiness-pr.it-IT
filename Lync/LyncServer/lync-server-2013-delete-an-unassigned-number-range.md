---
title: 'Lync Server 2013: eliminare un intervallo di numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a80a28cf4ee5b310790a057253ea52ca17a14aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>Eliminare un intervallo di numeri non assegnati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Usare una delle procedure seguenti per eliminare un intervallo di numeri non assegnati per gli annunci.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>Per usare il pannello di controllo di Lync Server per eliminare un intervallo di numeri non assegnati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **numero non assegnato**.

4.  Nel campo di ricerca della pagina **numero non assegnato** digitare tutto o parte del nome dell'intervallo di numeri non assegnati che si desidera eliminare.

5.  Nell'elenco risultante di intervalli di numeri fare clic sul nome, scegliere **modifica**e quindi fare clic su **Elimina**.

6.  Fare clic su **commit tutti**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>Per usare Windows PowerShell per eliminare un intervallo di numeri non assegnati

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando digitare:
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Ad esempio:
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate su altre opzioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[Remove-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

