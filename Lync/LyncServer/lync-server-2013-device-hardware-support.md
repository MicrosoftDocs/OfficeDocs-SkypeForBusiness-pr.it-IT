---
title: Supporto hardware per dispositivi di Lync Server 2013
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
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="e4afe-102">Supporto hardware per dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4afe-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4afe-103">_**Ultimo argomento modificato:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="e4afe-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="e4afe-104">Prima di distribuire telefoni IP e dispositivi analogici, è necessario implementare configurazioni hardware specifiche.</span><span class="sxs-lookup"><span data-stu-id="e4afe-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="e4afe-105">Telefoni IP che eseguono Lync Phone Edition Support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) e Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="e4afe-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="e4afe-106">Per poter utilizzare LLDP-MED, il commutatore deve supportare IEEE802.1AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="e4afe-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="e4afe-107">Per poter utilizzare PoE, il commutatore deve supportare PoE802.3AF o 802.3at.</span><span class="sxs-lookup"><span data-stu-id="e4afe-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="e4afe-108">Per abilitare LLDP-MED, l'amministratore deve abilitare LLDP tramite la finestra della console del commutatore e impostare i criteri di rete LLDP-MED con l'ID VLAN voce corretto.</span><span class="sxs-lookup"><span data-stu-id="e4afe-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="e4afe-109">Inoltre, se la distribuzione include dispositivi analogici, è necessario configurare il gateway analogico per l'utilizzo di Lync Server e il gateway deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4afe-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="e4afe-110">Un adattatore telefonico analogico (ATA, Analog Telephone Adapter)</span><span class="sxs-lookup"><span data-stu-id="e4afe-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="e4afe-111">Un gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="e4afe-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="e4afe-112">Un Survivable Branch Appliance che include un gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="e4afe-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="e4afe-113">Un Survivable Branch Appliance che include un gateway PSTN che comunica con un adattatore telefonico analogico</span><span class="sxs-lookup"><span data-stu-id="e4afe-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="e4afe-114">Per informazioni su come configurare un gateway analogico, vedere la sezione relativa alla pianificazione [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) della distribuzione di dispositivi analogici nella libreria TechNet di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e4afe-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="e4afe-115">I dispositivi analogici funzionano nello stesso modo in Lync Server 2013 come in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e4afe-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4afe-116">È possibile configurare il commutatore per Enhanced 9-1-1 (E9-1-1), se supportato dal commutatore.</span><span class="sxs-lookup"><span data-stu-id="e4afe-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

