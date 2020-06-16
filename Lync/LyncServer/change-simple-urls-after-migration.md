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
ms.openlocfilehash: 2c9f46944e80c5eb7a2d81de6f164d19aab64d29
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Lync Server supporta tre URL semplici:

  - **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.

  - **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.

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

