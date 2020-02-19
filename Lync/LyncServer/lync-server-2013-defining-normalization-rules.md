---
title: 'Lync Server 2013: definizione di regole di normalizzazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19edb375235d64587c60b2abf388835ffc468e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definizione di regole di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-22_

Le regole di normalizzazione di Lync Server 2013 utilizzano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione assumono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Lync Server. A ogni dial plan deve essere assegnata una o più regole di normalizzazione.

Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework all'indirizzo.

È possibile utilizzare uno dei metodi seguenti per definire o modificare una regola di normalizzazione:

  - Utilizzare lo strumento **Crea regola di normalizzazione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Lync Server generi il corrispondente schema di corrispondenza e la regola di conversione.

  - Scrivere manualmente espressioni regolari per definire il formato di corrispondenza e la regola di conversione.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

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

