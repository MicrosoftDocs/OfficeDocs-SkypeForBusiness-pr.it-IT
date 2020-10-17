---
title: 'Lync Server 2013: controllo di ammissione di chiamata e Mediation Server'
description: 'Lync Server 2013: controllo di ammissione di chiamata e Mediation Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e4b12a11f941923d50f3ffcab7a8f9b6a9edc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569222"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il controllo di ammissione di chiamata (CAC), introdotto per la prima volta in Lync Server 2010, gestisce l'establishment delle sessioni in tempo reale, in base alla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti nelle reti congestionate. Per supportare questa funzionalità, il Mediation Server, che fornisce la segnalazione e la traduzione multimediale tra l'infrastruttura VoIP aziendale e un gateway o un provider di trunking SIP, è responsabile della gestione della larghezza di banda per le sue due interazioni sul fronte di Lync Server e sul fronte del gateway. Nel controllo di ammissione di chiamata, l'entità di terminazione di una chiamata deve gestire la prenotazione della larghezza di banda. I peer gateway (gateway PSTN, IP-PBX, SBC) su cui interagiscono i Mediation Server con il gateway non supportano il controllo di ammissione di chiamata di Lync Server 2013. Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer gateway. Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo. In caso contrario, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer gateway, la larghezza di banda viene riservata al momento dell'esecuzione della chiamata. Questo comportamento può causare una richiesta eccessiva di larghezza di banda, ma è l'unico modo per impedire squilli falsi..

Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, non è possibile effettuare il controllo di ammissione di chiamata per la chiamata. Il concetto alla base di questo comportamento è che non vi sono collegamenti con larghezza di banda limitata interessati dalla chiamata. Se il controllo di ammissione di chiamata viene utilizzato per una chiamata specifica che implica il Mediation Server, la chiamata non può impiegare il bypass multimediale.

Per informazioni dettagliate sul bypass multimediale o sul controllo di ammissione di chiamata, vedere [Planning for Media Bypass in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

