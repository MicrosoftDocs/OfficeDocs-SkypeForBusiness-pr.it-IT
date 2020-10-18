---
title: Eseguire la migrazione dei dispositivi analogici
description: Eseguire la migrazione di dispositivi analogici.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579402"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c2e36-103">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c2e36-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2e36-104">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c2e36-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c2e36-105">Lync Server fornisce il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c2e36-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="c2e36-106">Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici.</span><span class="sxs-lookup"><span data-stu-id="c2e36-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c2e36-107">È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2e36-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="c2e36-108">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c2e36-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c2e36-109">Utilizzare Lync Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2e36-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="c2e36-110">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c2e36-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="c2e36-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2e36-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c2e36-112">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c2e36-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="c2e36-113">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2e36-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c2e36-114">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c2e36-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="c2e36-115">Verificare che tutti gli oggetti contatto siano ora associati al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2e36-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

