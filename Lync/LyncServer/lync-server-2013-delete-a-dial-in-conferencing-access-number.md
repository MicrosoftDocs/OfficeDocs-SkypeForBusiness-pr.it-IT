---
title: 'Lync Server 2013: eliminare un numero di accesso per le conferenze telefoniche in ingresso'
description: 'Lync Server 2013: eliminare un numero di accesso per le conferenze telefoniche in ingresso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5bed6099f7464884c3bcde8e4ee86ad4207222
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566592"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Eliminare un numero di accesso per le conferenze telefoniche in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Eseguire questa procedura per eliminare un numero di accesso alle conferenze telefoniche con accesso esterno.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Per eliminare un numero di accesso alle conferenze telefoniche con accesso esterno

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.

4.  Nella pagina fare clic sul numero di accesso esterno che si desidera eliminare nell'elenco, fare clic su **Modifica** e quindi su **Elimina**.

5.  Fare clic su **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Rimozione dei numeri di accesso per le conferenze telefoniche in ingresso tramite i cmdlet di Windows PowerShell

È possibile eliminare i numeri di accesso per i servizi di conferenza telefonica tramite Windows PowerShell e il cmdlet **Remove-CsDialInConferencingAccessNumber** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Per rimuovere un determinato numero di accesso per le conferenze telefoniche con chiamata in ingresso

  - Questo comando consente di eliminare il numero di accesso alla conferenza telefonica con accesso esterno con Identity sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Per rimuovere tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso assegnati a un'area specifica

  - Questo comando consente di eliminare tutti i numeri di accesso alla conferenza telefonica con accesso esterno associati all'area Northwest:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Per rimuovere i numeri di accesso per le conferenze telefoniche con chiamata in base alla lingua principale

  - Questo comando consente di eliminare tutti i numeri di accesso per le conferenze telefoniche in ingresso in cui l'italiano è la lingua principale:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

