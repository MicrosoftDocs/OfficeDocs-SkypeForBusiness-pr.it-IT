---
title: 'Lync Server 2013: configurare le impostazioni del parcheggio delle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="3ffe8-102">Configurare le impostazioni di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ffe8-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ffe8-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ffe8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3ffe8-104">Se non si vogliono usare le impostazioni predefinite di Call Park, è possibile personalizzarle.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="3ffe8-105">Quando si installa l'applicazione Call Park, le impostazioni globali sono configurate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="3ffe8-106">È possibile modificare le impostazioni globali ed è anche possibile specificare impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="3ffe8-107">Usa il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="3ffe8-108">Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ffe8-109">È consigliabile configurare almeno l'opzione <STRONG>OnTimeoutURI</STRONG> per la destinazione di fallback da usare quando si verifica un timeout per una chiamata parcheggiata e la risponderia non riesce.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="3ffe8-110">USA cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ffe8-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ffe8-111">Questa opzione:</span><span class="sxs-lookup"><span data-stu-id="3ffe8-111">This option:</span></span></th>
<th><span data-ttu-id="3ffe8-112">Specifica questo:</span><span class="sxs-lookup"><span data-stu-id="3ffe8-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ffe8-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="3ffe8-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffe8-114">La quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="3ffe8-115">Il valore deve essere immesso nel formato HH: mm: SS per specificare le ore, i minuti e i secondi.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-115">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds.</span></span> <span data-ttu-id="3ffe8-116">Il valore minimo è di 10 secondi e il valore massimo è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-116">The minimum value is 10 seconds, and the maximum value is 10 minutes.</span></span> <span data-ttu-id="3ffe8-117">Il valore predefinito è 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-117">The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffe8-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="3ffe8-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffe8-119">Se la musica viene riprodotta per un chiamante mentre viene parcheggiata una chiamata.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="3ffe8-120">I valori sono true o false.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-120">Values are True or False.</span></span> <span data-ttu-id="3ffe8-121">Il valore predefinito è true.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-121">The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffe8-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="3ffe8-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffe8-123">Il numero di squilli di una chiamata parcheggiata torna al telefono che risponde prima che venga inoltrato all'URI (Uniform Resource Identifier) di fallback specificato per <strong>OnTimeoutURI</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-123">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>.</span></span> <span data-ttu-id="3ffe8-124">Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-124">The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffe8-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="3ffe8-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffe8-126">Indirizzo SIP dell'utente o del gruppo di risposte a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato <strong>MaxCallPickupAttempts</strong> .</span><span class="sxs-lookup"><span data-stu-id="3ffe8-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="3ffe8-127">Value deve essere un URI SIP che inizia con la stringa SIP:.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-127">Value must be a SIP URI beginning with the string sip:.</span></span> <span data-ttu-id="3ffe8-128">Ad esempio, sip:bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-128">For example, sip:bob@contoso.com.</span></span> <span data-ttu-id="3ffe8-129">L'impostazione predefinita non è l'indirizzo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-129">The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="3ffe8-130">Per configurare le impostazioni di Call Park</span><span class="sxs-lookup"><span data-stu-id="3ffe8-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="3ffe8-131">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3ffe8-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3ffe8-132">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3ffe8-133">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3ffe8-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3ffe8-134">Usa il cmdlet <STRONG>Get-CsSite</STRONG> per identificare il sito.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="3ffe8-135">Per informazioni dettagliate, vedere documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3ffe8-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="3ffe8-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3ffe8-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ffe8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ffe8-137">See Also</span></span>


[<span data-ttu-id="3ffe8-138">Personalizzare la musica di Call Park in attesa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ffe8-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="3ffe8-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ffe8-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="3ffe8-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ffe8-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="3ffe8-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="3ffe8-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

