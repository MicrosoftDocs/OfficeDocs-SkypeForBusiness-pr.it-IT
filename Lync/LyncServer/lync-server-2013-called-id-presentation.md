---
title: 'Lync Server 2013: presentazione ID denominata'
description: 'Lync Server 2013: chiamata presentazione ID.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b438c7c19bc3c4ad641a8b9f8dac319c9fc2b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565202"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="70bdf-103">Presentazione ID denominata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bdf-103">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70bdf-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="70bdf-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="70bdf-105">Con Lync Server 2010, il numero di telefono della parte chiamata, ovvero il numero di telefono chiamato, può essere convertito dal formato E. 164 al formato di composizione locale richiesto dal peer trunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="70bdf-105">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="70bdf-106">A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="70bdf-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70bdf-107">La possibilità di associare una o più regole di conversione a una configurazione trunk VoIP aziendale è destinata a essere utilizzata come <EM>alternativa</EM> alla configurazione delle regole di conversione nel peer trunk.</span><span class="sxs-lookup"><span data-stu-id="70bdf-107">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="70bdf-108">Non associare regole di conversione a una configurazione trunk VoIP aziendale se sono state configurate regole di conversione nel peer trunk perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="70bdf-108">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="70bdf-109">È possibile utilizzare uno dei metodi seguenti per creare e modificare una regola di conversione:</span><span class="sxs-lookup"><span data-stu-id="70bdf-109">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="70bdf-110">Utilizzare lo strumento **Crea regola di conversione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Lync Server generi il corrispondente modello e la regola di conversione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="70bdf-110">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="70bdf-111">Scrivere manualmente espressioni regolari per definire il formato di corrispondenza e la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="70bdf-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70bdf-112">Per informazioni su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .</span><span class="sxs-lookup"><span data-stu-id="70bdf-112">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="70bdf-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="70bdf-113">In This Section</span></span>

  - [<span data-ttu-id="70bdf-114">Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bdf-114">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="70bdf-115">Creare o modificare manualmente una regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bdf-115">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70bdf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70bdf-116">See Also</span></span>


[<span data-ttu-id="70bdf-117">Presentazione dell'ID chiamante in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bdf-117">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

