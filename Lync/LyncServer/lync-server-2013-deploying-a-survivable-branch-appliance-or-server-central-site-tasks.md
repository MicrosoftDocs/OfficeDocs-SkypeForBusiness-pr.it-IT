---
title: Distribuzione di Survivable Branch Appliance o Survivable Branch Server - Attività presso il sito centrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013 - Attività presso il sito centrale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Completare le attività in questa sezione nel sito centrale. Se si sta distribuendo un Survivable Branch Server, ignorare la prima attività.

<div>


> [!IMPORTANT]
> Prima di eseguire le attività in questa sezione, è necessario che siano presenti le condizioni seguenti: 
> <UL>
> <LI>
> <P>Lync Server deve essere configurato nel sito centrale.</P>
> <LI>
> <P>Il tecnico dell'installazione presso il sito della filiale deve essere aggiunto al gruppo RTCUniversalSBATechnicians.</P></LI></UL>Inoltre, è consigliabile eseguire le operazioni seguenti:
> <UL>
> <LI>
> <P>Distribuire un server DHCP in ogni sito di filiale per consentire ai client di ottenere indirizzi IP.</P>
> <LI>
> <P>In alternativa alla distribuzione di un server DHCP in ogni sito di succursale, abilitare il protocollo DHCP di Lync Server nel Survivable Branch Appliance o Survivable Branch Server usando il cmdlet <STRONG>Set-CsRegistrarConfiguration-EnableDHCPServer $True</STRONG>di Lync Server Management Shell. Per informazioni dettagliate, vedere la sezione "requisiti hardware e software" dei <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza del sito filiale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

