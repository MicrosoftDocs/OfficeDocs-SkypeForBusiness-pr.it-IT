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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="59996-102">Supporto hardware per dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59996-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59996-103">_**Ultimo argomento modificato:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="59996-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="59996-104">Prima di distribuire telefoni IP e dispositivi analogici, è necessario implementare configurazioni hardware specifiche.</span><span class="sxs-lookup"><span data-stu-id="59996-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="59996-105">Telefoni IP che eseguono Lync Phone Edition Support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) e Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="59996-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="59996-106">Per poter utilizzare LLDP-MED, il commutatore deve supportare IEEE802.1AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="59996-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="59996-107">Per poter utilizzare PoE, il commutatore deve supportare PoE802.3AF o 802.3at.</span><span class="sxs-lookup"><span data-stu-id="59996-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="59996-108">Per abilitare LLDP-MED, l'amministratore deve abilitare LLDP tramite la finestra della console del commutatore e impostare i criteri di rete LLDP-MED con l'ID VLAN voce corretto.</span><span class="sxs-lookup"><span data-stu-id="59996-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="59996-109">Inoltre, se la distribuzione include dispositivi analogici, è necessario configurare il gateway analogico per l'utilizzo di Lync Server e il gateway deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="59996-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="59996-110">Un adattatore telefonico analogico (ATA, Analog Telephone Adapter)</span><span class="sxs-lookup"><span data-stu-id="59996-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="59996-111">Un gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="59996-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="59996-112">Un Survivable Branch Appliance che include un gateway analogico PSTN</span><span class="sxs-lookup"><span data-stu-id="59996-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="59996-113">Un Survivable Branch Appliance che include un gateway PSTN che comunica con un adattatore telefonico analogico</span><span class="sxs-lookup"><span data-stu-id="59996-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="59996-114">Per informazioni su come configurare un gateway analogico, vedere la sezione relativa alla pianificazione [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) della distribuzione di dispositivi analogici nella libreria TechNet di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59996-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="59996-115">I dispositivi analogici funzionano nello stesso modo in Lync Server 2013 come in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59996-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59996-116">È possibile configurare il commutatore per Enhanced 9-1-1 (E9-1-1), se supportato dal commutatore.</span><span class="sxs-lookup"><span data-stu-id="59996-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

