---
title: 'Lync Server 2013: definizione di regole di normalizzazione'
description: 'Lync Server 2013: definizione di regole di normalizzazione.'
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
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542042"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="b999a-103">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b999a-103">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b999a-104">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="b999a-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="b999a-105">Le regole di normalizzazione di Lync Server 2013 utilizzano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione assumono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b999a-105">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="b999a-106">A ogni dial plan deve essere assegnata una o più regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b999a-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="b999a-107">Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b999a-107">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="b999a-108">Per informazioni dettagliate su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="b999a-108">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="b999a-109">È possibile utilizzare uno dei metodi seguenti per definire o modificare una regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="b999a-109">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="b999a-110">Utilizzare lo strumento **Crea regola di normalizzazione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Lync Server generi il corrispondente schema di corrispondenza e la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="b999a-110">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="b999a-111">Scrivere manualmente espressioni regolari per definire il formato di corrispondenza e la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="b999a-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b999a-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="b999a-112">In This Section</span></span>

  - [<span data-ttu-id="b999a-113">Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b999a-113">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="b999a-114">Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b999a-114">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b999a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b999a-115">See Also</span></span>


[<span data-ttu-id="b999a-116">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b999a-116">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="b999a-117">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b999a-117">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

