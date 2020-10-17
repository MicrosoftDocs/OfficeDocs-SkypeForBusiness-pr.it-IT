---
title: 'Lync Server 2013: nuova funzionalità trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0feda45fd6c035209783d173da3a85dec3876e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505283"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a>Nuova funzionalità trunk in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

In Microsoft Lync Server 2013, è possibile definire più trunk tra un Mediation Server e un gateway. Microsoft Lync Server 2010 è consentito solo per un singolo trunk tra un Mediation Server e un gateway PSTN. Questa funzionalità offre la flessibilità necessaria per definire ulteriori trunk. Un trunk è un'associazione logica tra un FQDN del Mediation Server e una porta di attesa e un FQDN del gateway PSTN e una porta di attesa. Questa nuova funzionalità consente di semplificare la definizione trunk per la resilienza (in cui è possibile utilizzare più Mediation Server per instradare le chiamate allo stesso gateway PSTN) per l'interoperabilità PBX, in cui è possibile utilizzare più trunk con criteri associati diversi e IP-PBX e Mediation Server e per le configurazioni trunk SIP in cui Mediation Server in siti diversi dispongono di trunk SIP per il vettore a cui fa riferimento lo stesso FQDN del vettore.

<div>

## <a name="see-also"></a>Vedere anche


[Nuove funzionalità di VoIP aziendale in Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

