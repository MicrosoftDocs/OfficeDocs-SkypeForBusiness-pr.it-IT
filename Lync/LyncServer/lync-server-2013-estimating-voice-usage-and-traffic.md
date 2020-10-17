---
title: "Lync Server 2013: stima dell'utilizzo e del traffico vocale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9541619578c69a571d93d8c4960b3ecb33476027
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532003"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Stima dell'utilizzo e del traffico vocale per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-07_

Microsoft Lync Server 2013, strumento di pianificazione utilizza la metrica seguente per valutare il traffico degli utenti in ogni sito e il numero di porte necessarie per il supporto del traffico.

  - <span></span>  
    Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.

  - <span></span>  
    Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.

  - <span></span>  
    Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.

Il numero di porte determina il numero di Mediation Server e gateway necessari. I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte. Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.

Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.

</div>

<span> </span>

</div>

</div>

</div>

