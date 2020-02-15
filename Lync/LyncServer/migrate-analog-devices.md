---
title: Eseguire la migrazione di dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e176b03adf3d64b06e7bd9e2a0e72282a1f0f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="c18ff-102">Eseguire la migrazione di dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c18ff-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c18ff-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c18ff-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c18ff-104">Lync Server fornisce il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c18ff-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="c18ff-105">Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici.</span><span class="sxs-lookup"><span data-stu-id="c18ff-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c18ff-106">È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c18ff-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="c18ff-107">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="c18ff-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c18ff-108">Utilizzare Lync Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c18ff-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="c18ff-109">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="c18ff-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="c18ff-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c18ff-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c18ff-111">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c18ff-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="c18ff-112">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c18ff-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c18ff-113">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c18ff-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="c18ff-114">Verificare che tutti gli oggetti contatto siano ora associati al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c18ff-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

