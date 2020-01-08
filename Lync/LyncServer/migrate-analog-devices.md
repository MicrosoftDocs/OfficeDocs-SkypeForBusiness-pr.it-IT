---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="c1991-102">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c1991-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1991-103">_**Argomento Ultima modifica:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c1991-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c1991-104">Lync Server offre il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c1991-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="c1991-105">In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici.</span><span class="sxs-lookup"><span data-stu-id="c1991-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c1991-106">Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1991-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="c1991-107">Dopo la migrazione da Lync Server 2010 a Lync Server 2013, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c1991-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c1991-108">USA Lync Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostarli nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1991-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="c1991-109">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c1991-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="c1991-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1991-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1991-111">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c1991-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="c1991-112">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1991-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c1991-113">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c1991-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="c1991-114">Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1991-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

