---
title: 'Lync Server 2013: modificare un trunk in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c82664129cf7eae8b0155fc07b921896203376d4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="2a42f-102">Modificare un trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a42f-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a42f-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2a42f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2a42f-104">Seguire questi passaggi per modificare l'indirizzo IP multimediale alternativo e il BypassID alternativo di un trunk.</span><span class="sxs-lookup"><span data-stu-id="2a42f-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="2a42f-105">Per modificare l'indirizzo IP multimediale alternativo di un trunk</span><span class="sxs-lookup"><span data-stu-id="2a42f-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="2a42f-106">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a42f-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a42f-107">Eseguire il cmdlet Set-CsPstnGateway e modificare il campo AlternateBypassId in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2a42f-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="2a42f-108">Per modificare il BypassID alternativo di un trunk</span><span class="sxs-lookup"><span data-stu-id="2a42f-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="2a42f-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a42f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a42f-110">Eseguire il cmdlet Set-CsPstnGateway e modificare il campo AlternateBypassId in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2a42f-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

