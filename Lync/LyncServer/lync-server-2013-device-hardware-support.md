---
title: 'Lync Server 2013: Supporto di dispositivi hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Supporto di dispositivi hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-14_

Le configurazioni hardware specifiche devono essere posizionate prima di distribuire telefoni IP e dispositivi analogici.

I telefoni IP con Lync Phone Edition supportano il protocollo di rilevamento dei collegamenti layer-Media Endpoint Discovery (LLDP-MED) e Power over Ethernet (PoE).Per sfruttare LLDP-MED, lo switch deve supportare IEEE 802.1 AB e ANSI/TIA-1057. Per trarre vantaggio da PoE, lo switch deve supportare PoE 802.3 AF o 802.3 at.

Per abilitare LLDP-MED, l'amministratore deve abilitare LLDP usando la finestra switch console e impostando il criterio di rete LLDP-MED con l'ID VLAN vocale corretto.

Inoltre, se la distribuzione include dispositivi analogici, è necessario configurare il gateway analogico per l'uso di Lync Server e il gateway deve essere uno dei seguenti:

  - Un adattatore telefonico analogico (ATA)

  - Gateway analogico PSTN

  - Un Survivable Branch Appliance che include un gateway analogico PSTN

  - Un Survivable Branch Appliance che include un gateway PSTN che comunica con un ATA

Per informazioni su come configurare un gateway analogico, vedere la pagina relativa alla pianificazione [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) della distribuzione di dispositivi analogici nella raccolta TechNet di Lync Server 2010. I dispositivi analogici funzionano allo stesso modo in Lync Server 2013 come in Lync Server 2010.

<div>


> [!IMPORTANT]  
> Puoi configurare lo switch per 9-1-1 avanzato (E9-1-1), se lo switch supporta questo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

