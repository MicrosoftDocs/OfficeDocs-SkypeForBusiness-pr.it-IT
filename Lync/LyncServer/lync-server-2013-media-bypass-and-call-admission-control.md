---
title: 'Lync Server 2013: Bypass multimediale e controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Bypass multimediale e controllo di ammissione alle chiamate (CAC) collaborare per gestire il controllo della larghezza di banda per il supporto delle chiamate. Il bypass multimediale facilita il flusso multimediale sui collegamenti collegati correttamente; CAC gestisce il traffico sui collegamenti con vincoli di larghezza di banda. Poiché il bypass multimediale e il CAC si escludono a vicenda, è necessario essere consapevoli di uno durante la pianificazione per l'altro. Sono supportate le combinazioni seguenti:

  - CAC e bypass multimediale sono entrambi abilitati. Il bypass multimediale deve essere impostato per l' **uso di informazioni sul sito e sulle aree**geografiche. Le informazioni di questo sito e area geografica sono le stesse usate per CAC.
    
    Se si Abilita CAC, non è possibile selezionare **sempre l'esclusione**e viceversa, perché le due configurazioni si escludono a vicenda. Vale a dire che solo uno dei due verrà applicato a qualsiasi chiamata PSTN specificata. Viene innanzitutto eseguito un controllo per determinare se il bypass multimediale si applica alla chiamata. In caso affermativo, il CAC non viene usato. Questo ha senso, perché se una chiamata è idonea per il bypass, è per definizione usando una connessione in cui CAC non è necessario. Se non è possibile applicare l'esclusione alla chiamata, ovvero se gli ID di bypass del client e del gateway non corrispondono, viene applicato il CAC alla chiamata.

  - CAC non abilitato e il bypass multimediale impostato su **Ignora sempre**.
    
    In questa configurazione, sia le subnet client che quelle trunk sono mappate a uno e solo un ID di bypass, calcolato dal sistema.

  - CAC non abilitato e bypass multimediale impostato per l' **uso di informazioni sul sito e sulle aree**geografiche.
    
    Dove è abilitata l' **uso delle informazioni sul sito e sull'area geografica** , la determinazione di bypass funziona essenzialmente allo stesso modo, indipendentemente dal fatto che CAC sia abilitato. Per qualsiasi chiamata PSTN, la subnet del client viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet. Analogamente, la subnet del gateway viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet. Solo se i due ID di bypass sono identici verranno ignorati per la chiamata. Se non sono identici, il bypass multimediale non si verificherà.
    
    Anche se CAC è disabilitato a livello globale, è necessario definire i criteri di larghezza di banda per ogni sito e collegamento se si vuole usare la configurazione del sito e dell'area geografica per controllare la decisione di esclusione. Il valore effettivo del vincolo di larghezza di banda o della relativa modalità non ha importanza. L'obiettivo finale è quello di far calcolare automaticamente i diversi ID di bypass da associare a impostazioni locali diverse che non sono ben connesse. La definizione di un vincolo di larghezza di banda per definizione significa che un collegamento non è ben connesso.

  - CAC è abilitato e il bypass multimediale non è abilitato. Questo problema si applica solo quando tutti i gateway e i PBX IP non sono ben connessi o non soddisfano altri requisiti per il bypass multimediale. Per informazioni dettagliate sui requisiti per il bypass multimediale, vedere [requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del bypass multimediale in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modalità di bypass multimediale in Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

