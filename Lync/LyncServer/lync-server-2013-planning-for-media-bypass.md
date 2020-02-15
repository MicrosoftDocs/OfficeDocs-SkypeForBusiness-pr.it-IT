---
title: 'Lync Server 2013: pianificazione del bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Pianificazione del bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il termine bypass multimediale indica la rimozione del Mediation Server dal percorso multimediale in tutti i casi possibili per le chiamate con segnale che attraversa il Mediation Server.

Media Bypass consente di migliorare la qualità vocale riducendo la latenza, le conversioni inutili, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore. Può inoltre essere migliorata la scalabilità, in quanto l'eliminazione dell'elaborazione multimediale per le chiamate ignorate consente di ridurre il carico di Mediation Server. Questa riduzione del carico è complementare alla capacità del Mediation Server di controllare più gateway.

Se un sito di succursale privo di Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito di succursale di fluire direttamente sul gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa.

Se si allevia il Mediation Server dall'elaborazione multimediale, il bypass multimediale potrebbe anche ridurre il numero di server Mediation che un'infrastruttura VoIP aziendale richiede.

Nella figura seguente sono illustrati i percorsi multimediali e di segnalazione di base in topologie con e senza Media Bypass.

**Percorsi multimediali e di segnalazione con e senza Media Bypass**

![Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC")

In generale, è consigliabile abilitare Media Bypass quando possibile.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Panoramica del bypass multimediale in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modalità di bypass multimediale in Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

[Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

