---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 029fe44d33d41b410d23068551203b1532893354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499693"
---
# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Lync Server supporta tre URL semplici:

  - L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.

  - L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN.

  - L' **amministratore** consente di accedere rapidamente al pannello di controllo di Lync Server. L'URL semplice di amministrazione è interno all'organizzazione.

Dopo aver eseguito la migrazione a Lync Server 2013, è necessario essere a conoscenza del modo in cui la modifica incide sui record DNS e sui certificati per gli URL semplici. Se l'amministratore di Lync Server 2010 Legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici. Se Lync Server 2010 Director è stato rimosso dalla topologia dopo la migrazione, è necessario aggiornare i record DNS degli URL semplificati in modo che puntino a uno dei pool di Lync Server 2013. Ogni volta che si modifica il nome di un URL semplice, è necessario però eseguire Enable-CsComputer in ogni Director e Front End Server per registrare la modifica.

<div>

## <a name="changing-simple-urls-after-migration"></a>Modifica degli URL semplici dopo la migrazione

**Per aggiornare l'URL semplice riunione**

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **Lync Server**e quindi scegliere **modifica proprietà**.

2.  Nel riquadro sinistro selezionare URL **semplici** , quindi fare clic su URL di **riunione** e quindi su **modifica URL**.

3.  Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.

**Per aggiornare l'URL semplice di amministrazione**

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **Lync Server**e quindi scegliere **modifica proprietà**.

2.  Nel riquadro sinistro selezionare URL **semplici** , quindi nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.
    
    <div>
    

    > [!TIP]  
    > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è <STRONG> https://admin .</STRONG> &lt; dominio &gt; .

    
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

