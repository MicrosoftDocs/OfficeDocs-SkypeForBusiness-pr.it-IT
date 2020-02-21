---
title: Reimposta il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2140327f4c95f1f83f9720b7f14ef9650b8a7746
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Reimposta il controllo di ammissione di chiamata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-11_

Se un pool di front end di Lync Server 2010 ospita il controllo di ammissione di chiamata (CAC), è necessario spostare il servizio di hosting CAC in un pool di Lync Server 2013 prima di rimuovere il pool Front End di Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Per reimpostare il servizio Controllo di ammissione di chiamata

1.  Apre lo strumento di generazione topologia

2.  Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **Modifica proprietà**.

3.  In **Impostazione controllo di ammissione di chiamata** assicurarsi che l'opzione **Abilita il controllo di ammissione di chiamata** sia selezionata.

4.  In **pool Front end per eseguire il controllo di ammissione di chiamata (CAC)**, selezionare il pool Lync Server 2013 che ospita il servizio CAC e quindi fare clic su **OK**.

5.  Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

