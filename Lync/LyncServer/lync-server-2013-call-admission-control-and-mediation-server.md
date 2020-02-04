---
title: 'Lync Server 2013: Controllo di ammissione di chiamata e Mediation Server'
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
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il controllo di ammissione alle chiamate (CAC), introdotto per la prima volta in Lync Server 2010, gestisce lo stabilimento in tempo reale della sessione, basato sulla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti sulle reti congestionate. Per supportare questa funzionalità, il Mediation Server, che consente la traduzione di segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e un gateway o un provider di trunking SIP, è responsabile della gestione della larghezza di banda per le due interazioni in Lync Lato server e lato gateway. In controllo di ammissione di chiamata, l'entità di terminazione per una chiamata gestisce la prenotazione della larghezza di banda. I peer gateway (gateway PSTN, IP-PBX, SBC) con cui interagisce il Mediation Server sul lato gateway non supportano il controllo di ammissione alle chiamate di Lync Server 2013. Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer del gateway. Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo. Se non è possibile, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer del gateway, la larghezza di banda viene riservata quando viene inserita la chiamata. Questo comportamento può causare un sovraabbonamento della larghezza di banda, ma è l'unico modo per evitare anelli falsi.

Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda. Se per una chiamata viene impiegato un bypass multimediale, il controllo di ammissione delle chiamate non viene eseguito per la chiamata. Il presupposto è che non ci sono collegamenti con larghezza di banda limitata coinvolta nella chiamata. Se per una determinata chiamata viene usato il controllo di ammissione alle chiamate che coinvolge il Mediation Server, tale chiamata non può impiegare il bypass multimediale.

Per informazioni dettagliate sul controllo di bypass multimediale o sull'ammissione alle chiamate, vedere [pianificazione di un bypass multimediale in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [pianificazione per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

</div>

<span> </span>

</div>

</div>

</div>

