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

# <a name="device-hardware-support-in-lync-server-2013"></a>Supporto hardware per dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-14_

Prima di distribuire telefoni IP e dispositivi analogici, è necessario implementare configurazioni hardware specifiche.

Telefoni IP che eseguono Lync Phone Edition Support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) e Power over Ethernet (PoE).Per poter utilizzare LLDP-MED, il commutatore deve supportare IEEE802.1AB e ANSI/TIA-1057. Per poter utilizzare PoE, il commutatore deve supportare PoE802.3AF o 802.3at.

Per abilitare LLDP-MED, l'amministratore deve abilitare LLDP tramite la finestra della console del commutatore e impostare i criteri di rete LLDP-MED con l'ID VLAN voce corretto.

Inoltre, se la distribuzione include dispositivi analogici, è necessario configurare il gateway analogico per l'utilizzo di Lync Server e il gateway deve essere uno dei seguenti:

  - Un adattatore telefonico analogico (ATA, Analog Telephone Adapter)

  - Un gateway analogico PSTN

  - Un Survivable Branch Appliance che include un gateway analogico PSTN

  - Un Survivable Branch Appliance che include un gateway PSTN che comunica con un adattatore telefonico analogico

Per informazioni su come configurare un gateway analogico, vedere la sezione relativa alla pianificazione [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) della distribuzione di dispositivi analogici nella libreria TechNet di Lync Server 2010. I dispositivi analogici funzionano nello stesso modo in Lync Server 2013 come in Lync Server 2010.

<div>


> [!IMPORTANT]  
> È possibile configurare il commutatore per Enhanced 9-1-1 (E9-1-1), se supportato dal commutatore.



</div>

</div>

<span> </span>

</div>

</div>

</div>

