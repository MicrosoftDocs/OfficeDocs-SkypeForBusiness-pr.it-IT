---
title: 'Lync Server 2013: Supporto di dispositivi hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="5f9b7-102">Supporto di dispositivi hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f9b7-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f9b7-103">_**Argomento Ultima modifica:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="5f9b7-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="5f9b7-104">Le configurazioni hardware specifiche devono essere posizionate prima di distribuire telefoni IP e dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="5f9b7-105">I telefoni IP con Lync Phone Edition supportano il protocollo di rilevamento dei collegamenti layer-Media Endpoint Discovery (LLDP-MED) e Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="5f9b7-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="5f9b7-106">Per sfruttare LLDP-MED, lo switch deve supportare IEEE 802.1 AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="5f9b7-107">Per trarre vantaggio da PoE, lo switch deve supportare PoE 802.3 AF o 802.3 at.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="5f9b7-108">Per abilitare LLDP-MED, l'amministratore deve abilitare LLDP usando la finestra switch console e impostando il criterio di rete LLDP-MED con l'ID VLAN vocale corretto.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="5f9b7-109">Inoltre, se la distribuzione include dispositivi analogici, è necessario configurare il gateway analogico per l'uso di Lync Server e il gateway deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f9b7-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="5f9b7-110">Un adattatore telefonico analogico (ATA)</span><span class="sxs-lookup"><span data-stu-id="5f9b7-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="5f9b7-111">Gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="5f9b7-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="5f9b7-112">Un Survivable Branch Appliance che include un gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="5f9b7-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="5f9b7-113">Un Survivable Branch Appliance che include un gateway PSTN che comunica con un ATA</span><span class="sxs-lookup"><span data-stu-id="5f9b7-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="5f9b7-114">Per informazioni su come configurare un gateway analogico, vedere la pagina relativa alla pianificazione [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) della distribuzione di dispositivi analogici nella raccolta TechNet di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="5f9b7-115">I dispositivi analogici funzionano allo stesso modo in Lync Server 2013 come in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f9b7-116">Puoi configurare lo switch per 9-1-1 avanzato (E9-1-1), se lo switch supporta questo.</span><span class="sxs-lookup"><span data-stu-id="5f9b7-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

