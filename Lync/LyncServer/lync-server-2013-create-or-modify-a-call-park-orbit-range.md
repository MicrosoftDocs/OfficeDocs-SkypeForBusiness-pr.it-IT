---
title: 'Lync Server 2013: creare o modificare un intervallo orbit di Call Park'
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
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="71082-102">Creare o modificare un intervallo orbit di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71082-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71082-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="71082-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="71082-104">Usare una delle procedure seguenti per creare o modificare un intervallo di orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="71082-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="71082-105">Per usare il pannello di controllo di Lync Server per creare o modificare un intervallo di numeri per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="71082-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="71082-106">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71082-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="71082-107">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="71082-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="71082-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71082-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71082-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="71082-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71082-110">Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **Call Park**.</span><span class="sxs-lookup"><span data-stu-id="71082-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="71082-111">Nella pagina **Call Park** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71082-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="71082-112">Per creare un nuovo intervallo di Orbit, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="71082-112">To create a new orbit range, click **New**.</span></span> <span data-ttu-id="71082-113">In **nome**Digitare un nome identificativo per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="71082-113">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="71082-114">Dopo aver eseguito il commit dell'intervallo di Orbit nel database, non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="71082-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="71082-115">Per modificare un intervallo di orbit esistente, digitare tutto o parte del nome dell'intervallo di Orbit nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="71082-115">To modify an existing orbit range, type all or part of the name of the orbit range in the search field.</span></span> <span data-ttu-id="71082-116">Nell'elenco risultante di orbite fare clic sull'orbita desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="71082-116">In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="71082-117">Nel campo primo **intervallo di numeri** Digitare il numero di inizio dell'intervallo di estensioni per l'orbita del parcheggio di chiamata, quindi digitare il numero finale dell'intervallo nel secondo campo dell' **intervallo di numeri** .</span><span class="sxs-lookup"><span data-stu-id="71082-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="71082-118">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="71082-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71082-119">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="71082-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71082-120">L'intervallo di orbit deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="71082-120">The orbit range must be unique.</span></span> <span data-ttu-id="71082-121">Questo intervallo non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="71082-121">This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71082-122">Se l'intervallo di Orbit inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="71082-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71082-123">Valori validi: deve corrispondere alla stringa di espressione regolare (\*[| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="71082-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="71082-124">Questo significa che il valore deve essere una stringa che inizia con il carattere \* o # o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="71082-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="71082-125">Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="71082-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="71082-126">I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000", "*92000", "* 95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="71082-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="71082-127">Se il primo carattere non è \* o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</span><span class="sxs-lookup"><span data-stu-id="71082-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71082-128">Non dovresti avere più di un totale di 50.000 orbite per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="71082-128">You should not have more than a total of 50,000 orbits per pool.</span></span> <span data-ttu-id="71082-129">Ogni intervallo orbit include in genere 100 o meno orbite, ma può essere molto più grande purché includa meno di 10.000 orbite.</span><span class="sxs-lookup"><span data-stu-id="71082-129">Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits.</span></span> <span data-ttu-id="71082-130">Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".</span><span class="sxs-lookup"><span data-stu-id="71082-130">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="71082-131">In **FQDN del server di destinazione**, fare clic sul nome di dominio completo (FQDN) o sull'ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="71082-131">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="71082-132">Tutte le chiamate parcheggiate in numeri compresi nell'intervallo specificato dal numero di inizio e dal numero finale nell'intervallo di Orbit verranno indirizzate a questo server o pool.</span><span class="sxs-lookup"><span data-stu-id="71082-132">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="71082-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="71082-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="71082-134">Per usare Windows PowerShell per creare o modificare un intervallo di numeri per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="71082-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="71082-135">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="71082-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="71082-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="71082-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="71082-137">USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbitali.</span><span class="sxs-lookup"><span data-stu-id="71082-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="71082-138">Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di orbita.</span><span class="sxs-lookup"><span data-stu-id="71082-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="71082-139">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="71082-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="71082-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="71082-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="71082-141">L'esempio seguente mostra come modificare i numeri in un intervallo di orbit esistente,</span><span class="sxs-lookup"><span data-stu-id="71082-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71082-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71082-142">See Also</span></span>


[<span data-ttu-id="71082-143">Eliminare un intervallo di Orbit di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71082-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="71082-144">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="71082-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="71082-145">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="71082-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

