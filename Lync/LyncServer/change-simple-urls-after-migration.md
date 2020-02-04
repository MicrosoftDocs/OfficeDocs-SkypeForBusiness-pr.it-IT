---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Lync Server supporta tre semplici URL:

  - L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire.

  - L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con **chiamata in ingresso** . L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie.

  - L' **amministratore** consente l'accesso rapido al pannello di controllo di Lync Server. L'URL semplice amministratore è interno dell'organizzazione.

Dopo aver eseguito la migrazione a Lync Server 2013, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici. Se l'eredità di Lync Server 2010 Director rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici. Se il Director di Lync Server 2010 viene rimosso dalla topologia dopo la migrazione, è necessario che i record DNS URL semplici vengano aggiornati in modo che puntino a uno dei pool di Lync Server 2013. Ogni volta che si modifica un nome di URL semplice, è necessario eseguire Enable-CsComputer su ogni Director e front end server per registrare la modifica.

<div>

## <a name="changing-simple-urls-after-migration"></a>Modifica di URL semplici dopo la migrazione

**Per aggiornare l'URL semplice riunione**

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul **Server Lync**superiore e quindi scegliere **modifica proprietà**.

2.  Selezionare **URL semplici** nel riquadro sinistro, quindi sotto gli **URL delle riunioni:** Selezionare l'URL di riunione e quindi fare clic su **modifica URL**.

3.  Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.

**Per aggiornare l'URL semplice dell'amministratore**

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul **Server Lync**superiore e quindi scegliere **modifica proprietà**.

2.  Selezionare **URL semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.
    
    <div>
    

    > [!TIP]  
    > È consigliabile usare l'URL più semplice possibile per l'URL di amministratore. L'opzione più semplice è <STRONG> https://admin.</STRONG> &lt;domain&gt;.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione degli URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

