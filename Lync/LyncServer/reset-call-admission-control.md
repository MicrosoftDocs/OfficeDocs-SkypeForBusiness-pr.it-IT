---
title: Reimpostare il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="fafa0-102">Reimpostare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="fafa0-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fafa0-103">_**Argomento Ultima modifica:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="fafa0-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="fafa0-104">Se un pool di front-end di Lync Server 2010 ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire l'hosting di CAC in un pool di Lync Server 2013 prima di poter rimuovere il pool di front end di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fafa0-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="fafa0-105">Per reimpostare CAC</span><span class="sxs-lookup"><span data-stu-id="fafa0-105">To reset CAC</span></span>

1.  <span data-ttu-id="fafa0-106">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fafa0-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="fafa0-107">Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fafa0-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="fafa0-108">In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** .</span><span class="sxs-lookup"><span data-stu-id="fafa0-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="fafa0-109">In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Lync Server 2013 che ospita CAC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fafa0-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="fafa0-110">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="fafa0-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

