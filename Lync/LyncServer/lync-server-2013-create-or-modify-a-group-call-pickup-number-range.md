---
title: 'Lync Server 2013: creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="a399c-102">Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a399c-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a399c-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a399c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a399c-104">Utilizzare la procedura seguente per creare o modificare un intervallo di numeri del gruppo di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a399c-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a399c-105">È necessario utilizzare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a399c-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="a399c-106">Gli intervalli di numeri di prelievo delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a399c-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a399c-107">L'intervallo di numeri del gruppo di prelievo delle chiamate deve essere assegnato a un tipo di GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="a399c-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="a399c-108">Gli utenti sono abilitati per il ritiro delle chiamate di gruppo solo se il numero di gruppo a cui sono stati assegnati è di tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="a399c-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="a399c-109">Gli intervalli di numeri del gruppo di prelievo delle chiamate devono essere conformi alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="a399c-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="a399c-110">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.</span><span class="sxs-lookup"><span data-stu-id="a399c-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="a399c-111">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="a399c-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="a399c-p103">L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="a399c-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="a399c-114">Se l'intervallo di numeri inizia con il \* carattere \#o, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="a399c-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="a399c-115">Valori validi: deve corrispondere alla stringa di espressione regolare\[\\\*|\#\](\[ ? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="a399c-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="a399c-116">Questo significa che il valore deve essere una stringa che inizia con il \* carattere \# o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="a399c-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="a399c-117">Se il primo carattere è \* o \#, il carattere seguente deve essere un numero compreso tra 1 e 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="a399c-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="a399c-118">I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad\#esempio "6000"\*, "92000"\*, "95551212" e "915551212".</span><span class="sxs-lookup"><span data-stu-id="a399c-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="a399c-119">Se il primo carattere non \* è o \#, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="a399c-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="a399c-120">Per creare o modificare un intervallo di gruppi di prelievo di chiamata</span><span class="sxs-lookup"><span data-stu-id="a399c-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="a399c-121">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a399c-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a399c-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a399c-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a399c-123">Utilizzare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a399c-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="a399c-124">Utilizzare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a399c-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="a399c-125">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a399c-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="a399c-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a399c-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="a399c-127">Nell'esempio seguente viene illustrato come modificare un intervallo di numeri dalle orbite del parcheggio di chiamata ai gruppi di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a399c-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a399c-128">Utilizzare questo cmdlet per modificare il tipo assegnato agli intervalli di numeri solo se inizialmente è stato specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="a399c-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="a399c-129">Se si modifica l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il servizio parcheggio di chiamata o di chiamata di gruppo smetterà di funzionare per tale intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="a399c-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="a399c-130">Ad esempio, se si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione Parcheggio di chiamata non è più in grado di utilizzare l'intervallo di orbite per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="a399c-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a399c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a399c-131">See Also</span></span>


[<span data-ttu-id="a399c-132">Eliminare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a399c-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="a399c-133">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a399c-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="a399c-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="a399c-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

