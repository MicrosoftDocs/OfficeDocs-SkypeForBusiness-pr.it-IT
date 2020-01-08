---
title: 'Lync Server 2013: eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Seguire questa procedura per eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Per eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.

4.  Nella pagina fare clic sul numero di accesso esterno che si vuole eliminare nell'elenco, fare clic su **modifica**e quindi su **Elimina**.

5.  Fare clic su **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Rimozione dei numeri di conferenza telefonica con accesso esterno con i cmdlet di Windows PowerShell

I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso possono essere eliminati usando Windows PowerShell e il cmdlet **Remove-CsDialInConferencingAccessNumber** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Per rimuovere un determinato numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso

  - Questo comando consente di eliminare il numero di accesso per i servizi di conferenza telefonica con l'identità sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Per rimuovere tutti i numeri di accesso ai servizi di conferenza telefonica con chiamata in ingresso assegnati a una specifica area geografica

  - Questo comando Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso associati all'area nord-ovest:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Per rimuovere i numeri di accesso per i servizi di conferenza telefonica con chiamata in base alla lingua principale

  - Questo comando Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso in cui l'italiano è la lingua principale:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

