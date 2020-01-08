---
title: 'Lync Server 2013: visualizzare i numeri di accesso per le conferenze telefoniche con chiamata in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9d9e6ca8d4f388edf6f04f4012726f6abee9e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Visualizzare i numeri di accesso per i servizi di conferenza telefonica con chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013 fornisci i numeri di accesso esterno agli utenti in modo che possano partecipare a una riunione esternamente.

<div>

## <a name="to-view-dial-in-access-numbers"></a>Per visualizzare i numeri di accesso per la chiamata in ingresso

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno** .

4.  Nella pagina **numero di accesso** esterno, fare clic sul numero di accesso che si vuole visualizzare.

5.  In **modifica**selezionare la **visualizzazione dettagli..** . casella di controllo.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Visualizzazione dei numeri di accesso ai servizi di conferenza telefonica con chiamata in ingresso con i cmdlet di Windows PowerShell

I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsDialInConferencingAccessNumber. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>Per visualizzare i numeri di accesso per i servizi di conferenza telefonica

  - Per visualizzare informazioni su tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsDialInConferencingAccessNumber
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

