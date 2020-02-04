---
title: 'Lync Server 2013: Definizione di regole di normalizzazione'
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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="099f2-102">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099f2-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="099f2-103">_**Argomento Ultima modifica:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="099f2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="099f2-104">Le regole di normalizzazione di Lync Server 2013 usano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione accettano il numero di telefono composto da un utente e convertono tale numero nel formato usato internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="099f2-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="099f2-105">A ogni dial plan devono essere assegnate una o più regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="099f2-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="099f2-106">Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="099f2-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="099f2-107">Per informazioni dettagliate su come scrivere espressioni regolari, vedere "espressioni regolari di .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span><span class="sxs-lookup"><span data-stu-id="099f2-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="099f2-108">Per definire o modificare una regola di normalizzazione, è possibile usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="099f2-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="099f2-109">Usare lo strumento **Costruisci una regola di normalizzazione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi consentire al pannello di controllo di Lync Server di generare automaticamente il modello corrispondente e la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="099f2-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="099f2-110">Scrivere manualmente le espressioni regolari per definire il modello e la regola di traduzione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="099f2-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="099f2-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="099f2-111">In This Section</span></span>

  - [<span data-ttu-id="099f2-112">Creare o modificare una regola di normalizzazione tramite Build una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099f2-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="099f2-113">Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099f2-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="099f2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="099f2-114">See Also</span></span>


[<span data-ttu-id="099f2-115">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099f2-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="099f2-116">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099f2-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

