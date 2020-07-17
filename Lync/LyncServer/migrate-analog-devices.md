---
title: Eseguire la migrazione dei dispositivi analogici
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
ms.openlocfilehash: 70e756fdaa49fc4c825a2c8548eb2c7f2e4acab2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="e4311-102">Eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="e4311-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4311-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="e4311-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="e4311-104">Lync Server fornisce il supporto per i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="e4311-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="e4311-105">Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici.</span><span class="sxs-lookup"><span data-stu-id="e4311-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="e4311-106">È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4311-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="e4311-107">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="e4311-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="e4311-108">Utilizzare Lync Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4311-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="e4311-109">Per eseguire la migrazione dei dispositivi analogici</span><span class="sxs-lookup"><span data-stu-id="e4311-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="e4311-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e4311-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e4311-111">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e4311-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="e4311-112">Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4311-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e4311-113">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e4311-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="e4311-114">Verificare che tutti gli oggetti contatto siano ora associati al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4311-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

