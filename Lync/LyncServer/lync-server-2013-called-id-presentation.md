---
title: 'Lync Server 2013: chiamata presentazione ID'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Presentazione ID chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Con Lync Server 2010, il numero di telefono della festa chiamata (ovvero il numero di telefono chiamato) può essere tradotto dal formato E. 164 al formato di chiamata locale richiesto dal peer trunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP. A tale scopo, è necessario definire una o più regole di traduzione per tradurre l'URI della richiesta prima di instradarlo al peer trunk.

<div>


> [!IMPORTANT]  
> La possibilità di associare una o più regole di traduzione a una configurazione trunk VoIP aziendale è destinata a essere usata come <EM>alternativa</EM> alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk perché le due regole potrebbero essere in conflitto.



</div>

Puoi usare uno dei metodi seguenti per creare o modificare una regola di traduzione:

  - Usare lo strumento **Costruisci una regola di traduzione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi consentire al pannello di controllo di Lync Server di generare automaticamente il modello corrispondente e la regola di traduzione.

  - Scrivere manualmente le espressioni regolari per definire il modello e la regola di traduzione corrispondenti.

<div>


> [!NOTE]  
> Per informazioni su come scrivere espressioni regolari, vedere "espressioni regolari di .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Creare o modificare manualmente una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Presentazione dell'ID chiamante in Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

