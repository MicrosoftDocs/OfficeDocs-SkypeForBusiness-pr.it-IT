---
title: 'Lync Server 2013: configurare le impostazioni del parcheggio di chiamata'
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
ms.openlocfilehash: 644ec44d4086b0acc326e043cbf63d7ceb2c640c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="60d00-102">Configurare le impostazioni del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60d00-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60d00-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60d00-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60d00-104">Se non si desidera utilizzare le impostazioni predefinite del parcheggio di chiamata, è possibile personalizzarle.</span><span class="sxs-lookup"><span data-stu-id="60d00-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="60d00-105">Quando si installa l'applicazione Parcheggio di chiamata, le impostazioni globali sono configurate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="60d00-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="60d00-106">È possibile modificarle, nonché specificare impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="60d00-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="60d00-107">Usare il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="60d00-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="60d00-108">Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="60d00-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60d00-109">È consigliabile configurare come minimo l'opzione <STRONG>OnTimeoutURI</STRONG> per la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata e la richiamata ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="60d00-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="60d00-110">Usare il cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="60d00-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60d00-111">Opzione:</span><span class="sxs-lookup"><span data-stu-id="60d00-111">This option:</span></span></th>
<th><span data-ttu-id="60d00-112">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="60d00-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60d00-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="60d00-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="60d00-114">Specifica quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.</span><span class="sxs-lookup"><span data-stu-id="60d00-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="60d00-p102">Il valore deve essere immesso nel formato hh:mm:ss per specificare le ore, i minuti e i secondi. Il valore minimo è 10 secondi e il valore massimo è 10 minuti. Il valore predefinito è 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="60d00-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d00-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="60d00-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="60d00-119">Specifica se viene riprodotto un brano musicale per il chiamante mentre una chiamata è parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="60d00-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="60d00-p103">I valori consentiti sono True o False. Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="60d00-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d00-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="60d00-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="60d00-p104">Specifica per una chiamata parcheggiata il numero di squilli sul telefono da cui è stata effettuata la risposta prima che la chiamata venga inoltrata all'URI (Uniform Resource Identifier) di fallback indicato per <strong>OnTimeoutURI</strong>. Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="60d00-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d00-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="60d00-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="60d00-126">Specifica l'indirizzo SIP dell'utente o del Response Group a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato il valore specificato per <strong>MaxCallPickupAttempts</strong>.</span><span class="sxs-lookup"><span data-stu-id="60d00-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="60d00-p105">Il valore deve essere un URI SIP che inizia con la stringa sip:, ad esempio sip:bob@contoso.com. Per impostazione predefinita, non viene specificato un indirizzo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="60d00-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="60d00-130">Per configurare le impostazioni del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="60d00-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="60d00-131">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="60d00-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="60d00-132">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="60d00-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="60d00-133">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="60d00-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="60d00-134">Utilizzare il cmdlet <STRONG>Get-CsSite</STRONG> per identificare il sito.</span><span class="sxs-lookup"><span data-stu-id="60d00-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="60d00-135">Per informazioni dettagliate, vedere Lync Server Management Shell Documentation.</span><span class="sxs-lookup"><span data-stu-id="60d00-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="60d00-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60d00-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60d00-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60d00-137">See Also</span></span>


[<span data-ttu-id="60d00-138">Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60d00-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="60d00-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="60d00-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="60d00-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="60d00-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="60d00-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="60d00-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

