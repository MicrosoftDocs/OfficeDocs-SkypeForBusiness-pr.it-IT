---
title: 'Lync Server 2013: creare o modificare un intervallo di codici orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd2e91ac2ae56d7ddffcaa8688ca305a6d377ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="e17e9-102">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e17e9-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e17e9-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e17e9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e17e9-104">Per creare o modificare un intervallo orbit del parcheggio di chiamata, usare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="e17e9-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="e17e9-105">Per utilizzare il pannello di controllo di Lync Server per creare o modificare un intervallo di numeri per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e17e9-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="e17e9-106">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e17e9-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e17e9-107">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e17e9-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e17e9-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e17e9-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e17e9-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e17e9-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e17e9-110">Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Parcheggio di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="e17e9-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="e17e9-111">Nella pagina **Parcheggio di chiamata** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e17e9-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e17e9-p103">Per creare un nuovo intervallo orbit, fare clic su **Nuovo**. In **Nome** digitare un nome per identificare l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="e17e9-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e17e9-114">Dopo l'esecuzione del commit dell'intervallo orbit nel database non sarà possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="e17e9-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="e17e9-p104">Per modificare un intervallo orbit esistente, digitarne il nome, per intero o in parte, nel campo di ricerca. Nell'elenco dei codici orbit risultante fare clic sul codice desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e17e9-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e17e9-117">Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo di estensioni per i codici orbit di parcheggio di chiamata e nel secondo campo **Intervallo numeri** digitare il numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e17e9-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="e17e9-118">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.</span><span class="sxs-lookup"><span data-stu-id="e17e9-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e17e9-119">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="e17e9-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e17e9-p105">L'intervallo di codici orbit deve essere univoco. Tale intervallo non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="e17e9-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e17e9-122">Se l'intervallo di codici orbit inizia con il carattere \* oppure #, l'intervallo deve essere superiore a 100.</span><span class="sxs-lookup"><span data-stu-id="e17e9-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e17e9-123">Valori validi: deve corrispondere alla stringa di espressione regolare (\*[| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="e17e9-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="e17e9-124">In pratica, il valore deve essere una stringa che inizia con il carattere \* o # oppure con un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="e17e9-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="e17e9-125">Se il primo carattere è \* o #, il carattere successivo deve essere un numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="e17e9-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="e17e9-126">I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad esempio "#6000", "*92000", "* 95551212" e "915551212".</span><span class="sxs-lookup"><span data-stu-id="e17e9-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="e17e9-127">Se il primo carattere non è \* o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="e17e9-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e17e9-p107">In totale non vi possono essere più di 50.000 codici orbit per ogni pool. Ogni intervallo di codici orbit in genere comprende al massimo 100 codici orbit, ma può essere anche molto più esteso, purché non superi i 10.000 codici orbit. Ad esempio, anziché specificare "7000000" come numero iniziale e "8000000" come numero finale, considerare la possibilità di specificare "7000000" e "7000100" rispettivamente come numero iniziale e numero finale.</span><span class="sxs-lookup"><span data-stu-id="e17e9-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="e17e9-p108">In **FQDN del server di destinazione** fare clic sul nome di dominio completo (FQDN) o sull'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate nei numeri dell'intervallo specificato dal numero iniziale e dal numero finale dell'intervallo di codici orbit saranno instradate a tale server o pool.</span><span class="sxs-lookup"><span data-stu-id="e17e9-p108">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="e17e9-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e17e9-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="e17e9-134">Per utilizzare Windows PowerShell per creare o modificare un intervallo di numeri per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e17e9-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="e17e9-135">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e17e9-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e17e9-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e17e9-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e17e9-137">Usare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbit.</span><span class="sxs-lookup"><span data-stu-id="e17e9-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="e17e9-138">Usare **Set-CsCallParkOrbit** per modificare un intervallo di numeri orbit esistente.</span><span class="sxs-lookup"><span data-stu-id="e17e9-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="e17e9-139">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e17e9-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="e17e9-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e17e9-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="e17e9-141">L'esempio seguente mostra come modificare i numeri di un intervallo orbit esistente.</span><span class="sxs-lookup"><span data-stu-id="e17e9-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e17e9-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e17e9-142">See Also</span></span>


[<span data-ttu-id="e17e9-143">Eliminare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e17e9-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="e17e9-144">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="e17e9-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="e17e9-145">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="e17e9-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

