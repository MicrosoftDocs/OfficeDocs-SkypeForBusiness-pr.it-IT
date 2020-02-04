---
title: 'Lync Server 2013: Requisiti tecnici per il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad3ea630a173d0925defcd476e6269b7e14e96e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Requisiti tecnici per il bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Per ogni chiamata alla rete PSTN, Mediation Server determina se l'elemento multimediale proveniente dall'endpoint di origine di Lync può essere inviato direttamente a un peer di Mediation Server senza attraversare il Mediation Server. Il peer può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) in un provider di servizi di telefonia Internet (ITSP) associato al trunk tra il Mediation Server in cui viene instradata la chiamata.

Il bypass multimediale può essere impiegato quando si soddisfano i requisiti seguenti:

  - Un peer di Mediation Server deve supportare le funzionalità necessarie per il bypass multimediale, la più importante è la possibilità di gestire più risposte a forcella (dette "finestre di dialogo iniziali"). Contattare il produttore del gateway o del PBX o del proprio ITSP per ottenere il valore per il numero massimo di finestre di dialogo iniziali che il gateway, il PBX o il SBC può accettare.

  - Il peer Mediation Server deve accettare il traffico multimediale direttamente dagli endpoint di Lync. Molti ITSPs consentono a SBC di ricevere traffico solo dal Mediation Server. Contattare il ITSP per determinare se il relativo SBC accetta il traffico multimediale direttamente dagli endpoint di Lync.

  - I client Lync e un peer di Mediation Server devono essere ben connessi, quindi si trovano nella stessa area di rete o nei siti di rete che si connettono all'area geografica con collegamenti WAN senza vincoli di larghezza di banda

<div>

## <a name="see-also"></a>Vedere anche


[Modalità di bypass multimediale in Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

