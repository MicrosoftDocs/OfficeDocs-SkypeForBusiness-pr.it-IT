---
title: 'Lync Server 2013: trunking SIP del sito della filiale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Trunking SIP del sito della filiale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

In alcuni casi potrebbe essere necessario implementare il trunking SIP distribuito in siti di succursale selezionati. Per determinare se è necessario un trunk SIP per un sito di succursale, esaminare le informazioni in [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione di trunk SIP nei siti di succursale, vedere soluzioni per la resilienza di siti secondari [in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Esempio di analisi dei requisiti trunk SIP del sito filiale

Quando si decide di distribuire un trunk SIP di un sito di succursale, è necessario eseguire un'analisi costi specifica del sito. Ad esempio, un'organizzazione con un sito centrale a Redmond, Washington e un sito di succursale di New York dovrebbe eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.

Per determinare se un trunk SIP distribuito a New York è economicamente vantaggioso, identificare i numeri DID (Direct inwarded Dialing) che utilizzeranno il trunk SIP e analizzare il numero di chiamate effettuate da New York in aree diverse da Redmond (425). È possibile avere terminato il sito della filiale nel sito centrale. Ad esempio, il sito centrale di Redmond può ospitare i numeri DID per il sito della filiale di New York. Se il costo per l'implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, valutare l'implementazione di un trunk SIP presso il sito della filiale di New York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Altri requisiti trunk SIP del sito di succursale

La scelta tra un trunk SIP di distribuzione invece di un gateway si basa sulla differenza tra gli oneri per il pedaggio pubblico Switched Telephone Network (PSTN) di ogni opzione. Se si distribuisce un trunk SIP del sito di succursale, è necessario determinare anche i requisiti di flessibilità e larghezza di banda. Se il collegamento tra il sito della filiale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway. Non è necessario distribuire un Survivable Branch Appliance nel sito della filiale. Se il collegamento tra il sito della filiale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance oppure distribuire un Survivable Branch Server con un gateway o un trunk SIP nel sito della filiale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

