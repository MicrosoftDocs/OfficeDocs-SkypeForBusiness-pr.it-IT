---
title: 'Lync Server 2013: Definizione di regole di normalizzazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9406e4fa7445242ae3f112ebfb772713d9d2219c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definizione di regole di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-22_

Le regole di normalizzazione di Lync Server 2013 usano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione accettano il numero di telefono composto da un utente e convertono tale numero nel formato usato internamente da Lync Server. A ogni dial plan devono essere assegnate una o più regole di normalizzazione.

Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate su come scrivere espressioni regolari, vedere "espressioni regolari di .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

Per definire o modificare una regola di normalizzazione, è possibile usare uno dei metodi seguenti:

  - Usare lo strumento **Costruisci una regola di normalizzazione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi consentire al pannello di controllo di Lync Server di generare automaticamente il modello corrispondente e la regola di traduzione.

  - Scrivere manualmente le espressioni regolari per definire il modello e la regola di traduzione corrispondenti.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creare o modificare una regola di normalizzazione tramite Build una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

