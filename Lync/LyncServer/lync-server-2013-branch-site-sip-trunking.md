---
title: 'Lync Server 2013: trunking SIP del sito di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1c9e4c5c8ca64e1b7f2014821cc61fa2655c9f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535193"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Trunking SIP del sito di succursale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

In alcuni casi, potrebbe essere necessario implementare il trunking SIP distribuito in siti di succursale selezionati. Per determinare se è necessario un trunk SIP per un sito di succursale, esaminare le informazioni in [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione di trunk SIP nei siti di succursale, vedere [soluzioni di resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Analisi dei requisiti di un trunk SIP per un sito di succursale di esempio

Quando si decide di distribuire un trunk SIP di un sito di succursale, è necessario eseguire un'analisi costi specifica del sito. Ad esempio, un'organizzazione che dispone di un sito centrale a Redmond, Washington e di un sito di succursale di New York dovrebbe eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.

Per stabilire se l'implementazione nel sito di Roma di un trunk SIP distribuito è una soluzione conveniente, identificare i numeri DID (Direct Inward Dialing) che utilizzeranno il trunk SIP e quindi analizzare il numero di chiamate effettuate dal sito di Roma ad aree diverse da Milano. È possibile disporre di una terminazione per il sito di succursale nel sito centrale. Ad esempio, il sito centrale Redmond può ospitare numeri DID per il sito di succursale di New York. Se il costo di implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, è consigliabile implementare un trunk SIP nel sito di succursale di New York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Altri requisiti per il trunk SIP di un sito di succursale

La scelta tra la distribuzione di un trunk SIP anziché di un gateway si basa sulla differenza tra i costi delle chiamate interurbane PSTN per ogni opzione. Se si distribuisce un trunk SIP di un sito di succursale, è inoltre necessario determinare la resilienza e i requisiti di larghezza di banda. Se il collegamento tra il sito di succursale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway. Non è necessario distribuire un Survivable Branch Appliance nel sito di succursale. Se il collegamento tra il sito di succursale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance o distribuire un Survivable Branch Server con un gateway o un trunk SIP nel sito di succursale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

