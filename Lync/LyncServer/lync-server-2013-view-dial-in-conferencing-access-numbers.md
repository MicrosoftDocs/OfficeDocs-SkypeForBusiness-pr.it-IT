---
title: 'Lync Server 2013: visualizzare i numeri di accesso per le conferenze telefoniche in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f897e773390cc894b3d9718b5eb354d1d4547a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Visualizzare i numeri di accesso per le conferenze telefoniche in ingresso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013, è possibile specificare i numeri di accesso esterno per gli utenti in modo che possano partecipare a una riunione esternamente.

<div>

## <a name="to-view-dial-in-access-numbers"></a>Per visualizzare i numeri di accesso esterno

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizi di conferenza** e quindi fare clic su **Numero di accesso esterno**.

4.  Nella pagina **Numero di accesso esterno** fare clic sul numero di accesso che si desidera visualizzare.

5.  In **Modifica** selezionare la casella di controllo **Mostra dettagli**.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Visualizzazione dei numeri di accesso per le conferenze telefoniche in ingresso tramite i cmdlet di Windows PowerShell

È possibile visualizzare i numeri di accesso per i servizi di conferenza telefonica tramite Windows PowerShell e il cmdlet Get-CsDialInConferencingAccessNumber. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>Per visualizzare i numeri di accesso per le conferenze telefoniche.

  - Per visualizzare informazioni su tutti i numeri di accesso per le conferenze telefoniche in ingresso, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsDialInConferencingAccessNumber
    
    Verranno restituite informazioni simili alle seguenti:
    
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

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

