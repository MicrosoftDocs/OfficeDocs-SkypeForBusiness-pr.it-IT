---
title: Reimpostare il controllo di ammissione di chiamata
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
ms.openlocfilehash: 6956b1a871a4a0a5c7e758d2890a58989f5ac8a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Reimpostare il controllo di ammissione di chiamata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-11_

Se un pool di front-end di Lync Server 2010 ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire l'hosting di CAC in un pool di Lync Server 2013 prima di poter rimuovere il pool di front end di Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Per reimpostare CAC

1.  Aprire Generatore di topologie.

2.  Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.

3.  In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** .

4.  In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Lync Server 2013 che ospita CAC e quindi fare clic su **OK**.

5.  Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

