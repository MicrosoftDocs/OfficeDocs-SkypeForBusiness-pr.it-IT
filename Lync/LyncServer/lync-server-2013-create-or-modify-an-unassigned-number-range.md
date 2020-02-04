---
title: 'Lync Server 2013: creare o modificare un intervallo di numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="3496f-102">Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3496f-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3496f-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3496f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3496f-104">Usare una delle procedure seguenti per configurare gli intervalli di numeri non assegnati per l'applicazione di annuncio.</span><span class="sxs-lookup"><span data-stu-id="3496f-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3496f-105">Prima di configurare la tabella dei numeri non assegnati, è necessario avere già definito uno o più annunci o configurare un operatore automatico di messaggistica UNIFICAta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3496f-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="3496f-106">Per usare il pannello di controllo di Lync Server per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="3496f-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="3496f-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3496f-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3496f-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3496f-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3496f-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3496f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3496f-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3496f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3496f-111">Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali**e quindi su **numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="3496f-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="3496f-112">Nella pagina **numero non assegnati** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3496f-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3496f-113">Per creare un nuovo intervallo di numeri, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3496f-113">To create a new number range, click **New**.</span></span> <span data-ttu-id="3496f-114">In **nome**Digitare un nome identificativo per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="3496f-114">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3496f-115">Dopo aver eseguito il commit del nuovo intervallo di numeri non assegnati al database, non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="3496f-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="3496f-116">Per modificare un intervallo di numeri esistente, digitare tutto o parte del nome dell'intervallo di numeri nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="3496f-116">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="3496f-117">Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3496f-117">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3496f-118">Nel campo primo **intervallo di numeri** Digitare il numero iniziale dell'intervallo, quindi digitare il numero finale dell'intervallo nel secondo campo **intervallo di numeri** .</span><span class="sxs-lookup"><span data-stu-id="3496f-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="3496f-119">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="3496f-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="3496f-120">Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.</span><span class="sxs-lookup"><span data-stu-id="3496f-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="3496f-121">Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="3496f-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="3496f-122">Questo significa che il numero può iniziare con la stringa tel: (se non specifichi quella stringa, verrà automaticamente aggiunta per te), un segno più (+) e una cifra da 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="3496f-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="3496f-123">Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</span><span class="sxs-lookup"><span data-stu-id="3496f-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="3496f-124">In **servizio annunci**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3496f-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="3496f-125">Fare clic su **annuncio**.</span><span class="sxs-lookup"><span data-stu-id="3496f-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="3496f-126">Fare clic su **messaggistica unificata di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3496f-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="3496f-127">Se nel passaggio precedente è stato fatto clic su **annuncio**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3496f-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="3496f-128">In **FQDN del server di destinazione**, fare clic su **Seleziona**, fare clic sull'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3496f-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="3496f-129">In **annuncio**fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="3496f-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="3496f-130">Se nel passaggio precedente è stato fatto clic su **um Exchange**, in **numero di telefono operatore automatico**fare clic su **Seleziona**, fare clic sul numero di telefono da usare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3496f-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="3496f-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3496f-131">Click **OK**.</span></span>

10. <span data-ttu-id="3496f-132">Nella pagina **numero non assegnati** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="3496f-132">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="3496f-133">Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="3496f-133">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3496f-134">Lync Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="3496f-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="3496f-135">Se si hanno intervalli sovrapposti e un intervallo specifica un'ultima azione di ricorso, verificare che l'intervallo sia nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3496f-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="3496f-136">Quando si hanno gli intervalli di numeri non assegnati nell'ordine desiderato, fare clic su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="3496f-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="3496f-137">Per usare Windows PowerShell per configurare i numeri di telefono non assegnati</span><span class="sxs-lookup"><span data-stu-id="3496f-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="3496f-138">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3496f-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3496f-139">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3496f-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3496f-140">USA **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="3496f-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="3496f-141">Usare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.</span><span class="sxs-lookup"><span data-stu-id="3496f-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3496f-142">Se si hanno intervalli sovrapposti e si vogliono applicare gli intervalli in un ordine specifico, includere il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="3496f-142">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="3496f-143">L'intervallo con la priorità più alta verrà applicato alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="3496f-143">The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="3496f-144">Nella riga di comando eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3496f-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="3496f-145">Per creare un intervallo di numeri per un servizio di annuncio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3496f-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="3496f-146">In alternativa, per creare un intervallo di numeri per l'operatore automatico di messaggistica unificata di Exchange, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3496f-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="3496f-147">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3496f-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="3496f-148">O</span><span class="sxs-lookup"><span data-stu-id="3496f-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="3496f-149">L'esempio seguente mostra come modificare i numeri in un intervallo di numeri non assegnati esistente:</span><span class="sxs-lookup"><span data-stu-id="3496f-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3496f-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3496f-150">See Also</span></span>


[<span data-ttu-id="3496f-151">Eliminare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3496f-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="3496f-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3496f-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="3496f-153">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3496f-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="3496f-154">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3496f-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

