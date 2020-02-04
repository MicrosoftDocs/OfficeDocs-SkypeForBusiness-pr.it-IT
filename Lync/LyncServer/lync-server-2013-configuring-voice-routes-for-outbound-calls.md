---
title: 'Lync Server 2013: Configurazione di route vocali per le chiamate in uscita'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configurazione di route vocali per le chiamate in uscita in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Una route vocale di Lync Server 2013 associa i numeri di telefono di destinazione con uno o più gateway PSTN (Public Switched Telephone Network) o trunk SIP e uno o più record di utilizzo PSTN.

**Per visualizzare le route vocali tramite il pannello di controllo di Lync Server**

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Fare clic su **routing vocale**.

3.  Fare clic su **Route**.

4.  Fare doppio clic su una route vocale per visualizzare altre proprietà dall'elenco di route vocali oppure selezionare la route e fare clic su **modifica**. Quindi fare clic su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare informazioni dettagliate solo per una singola route alla volta.

    
    </div>

**Per visualizzare le route vocali tramite Windows PowerShell**

  - Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**. Le route vocali possono essere visualizzate usando Windows PowerShell e il cmdlet **Get-CsVoiceRoute** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.
    
    Per visualizzare informazioni su tutte le route vocali, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsVoiceRoute
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Per informazioni dettagliate, vedere <A href="lync-server-2013-voice-routes.md">route vocali in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione del routing vocale in Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

