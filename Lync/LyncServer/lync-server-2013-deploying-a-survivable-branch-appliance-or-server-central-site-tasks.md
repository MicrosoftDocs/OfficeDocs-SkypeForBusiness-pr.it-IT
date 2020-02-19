---
title: Distribuzione di un Survivable Branch Appliance o di un'attività del sito server centrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39b0d9e4d10f4e28afa2a01e02dc2fab4c842bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013-attività del sito centrale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Le attività indicate in questa sezione devono essere eseguite presso il sito centrale. Se si sta distribuendo un Survivable Branch Server, ignorare la prima attività.

<div>


> [!IMPORTANT]
> Prima di eseguire le attività descritte in questa sezione, è necessario soddisfare le condizioni seguenti: 
> <UL>
> <LI>
> <P>È necessario configurare Lync Server nel sito centrale.</P>
> <LI>
> <P>Al gruppo RTCUniversalSBATechnicians deve essere aggiunto un tecnico addetto all'installazione presso il sito di succursale.</P></LI></UL>È inoltre consigliabile eseguire le operazioni seguenti:
> <UL>
> <LI>
> <P>Distribuire un server DHCP in ogni sito di succursale per consentire ai client di ottenere gli indirizzi IP.</P>
> <LI>
> <P>In alternativa alla distribuzione di un server DHCP in ogni sito di succursale, abilitare Lync Server DHCP nel Survivable Branch Appliance o Survivable Branch Server utilizzando il cmdlet <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $True</STRONG>di Lync Server Management Shell. Per informazioni dettagliate, vedere la sezione "requisiti hardware e software" <A href="lync-server-2013-branch-site-resiliency-requirements.md">per i requisiti di resilienza dei siti di succursale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

