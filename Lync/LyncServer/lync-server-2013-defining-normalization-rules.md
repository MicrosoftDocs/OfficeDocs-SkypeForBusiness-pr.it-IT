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
ms.openlocfilehash: 935df08bd1ede124b048427de21594aa6e727e7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504513"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="9b656-102">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b656-102">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b656-103">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="9b656-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="9b656-104">Le regole di normalizzazione di Lync Server 2013 utilizzano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione assumono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b656-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="9b656-105">A ogni dial plan deve essere assegnata una o più regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b656-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="9b656-106">Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9b656-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="9b656-107">Per informazioni dettagliate su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="9b656-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="9b656-108">È possibile utilizzare uno dei metodi seguenti per definire o modificare una regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b656-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="9b656-109">Utilizzare lo strumento **Crea regola di normalizzazione** per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Lync Server generi il corrispondente schema di corrispondenza e la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="9b656-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="9b656-110">Scrivere manualmente espressioni regolari per definire il formato di corrispondenza e la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="9b656-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9b656-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="9b656-111">In This Section</span></span>

  - [<span data-ttu-id="9b656-112">Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b656-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="9b656-113">Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b656-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b656-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b656-114">See Also</span></span>


[<span data-ttu-id="9b656-115">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b656-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="9b656-116">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b656-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

