---
title: 'Lync Server 2013: Pianificazione del bypass multimediale'
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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Pianificazione del bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il bypass multimediale si riferisce alla rimozione del Mediation Server dal percorso multimediale ogni volta che è possibile per le chiamate il cui segnale attraversa il Mediation Server.

Il bypass multimediale può migliorare la qualità della voce riducendo la latenza, la traduzione inutile, la possibilità di perdita di pacchetti e il numero di punti di potenziale errore. La scalabilità può essere migliorata perché l'eliminazione dell'elaborazione multimediale per le chiamate bypassate riduce il carico sul server Mediation. Questa riduzione del carico complementa la capacità del server Mediation di controllare più gateway.

Se un sito di succursale senza un Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito della larghezza di banda consentendo agli elementi multimediali di un client in un sito di succursale di scorrere direttamente nel gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa.

Attenuando il Mediation Server dall'elaborazione multimediale, il bypass multimediale può anche ridurre il numero di server di mediazione necessari per l'infrastruttura VoIP aziendale.

Nella figura seguente vengono illustrati i percorsi multimediali e di segnalazione di base nelle topologie con e senza bypass multimediale.

**Percorsi multimediali e di segnalazione con e senza bypass multimediale**

![Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni")

Come regola generale, abilitare il bypass multimediale ovunque sia possibile.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Panoramica del bypass multimediale in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modalità di bypass multimediale in Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

[Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

