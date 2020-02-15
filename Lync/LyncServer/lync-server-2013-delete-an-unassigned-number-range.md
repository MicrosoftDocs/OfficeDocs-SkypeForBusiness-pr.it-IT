---
title: 'Lync Server 2013: eliminare un intervallo di numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d2578d90ef710c15b6120b9a05481a974a0117
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="9ba53-102">Eliminare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ba53-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ba53-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9ba53-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9ba53-104">Per eliminare un intervallo di numeri non assegnati per gli annunci, eseguire le procedure illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ba53-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9ba53-105">Per utilizzare il pannello di controllo di Lync Server per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="9ba53-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9ba53-106">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ba53-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9ba53-107">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9ba53-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9ba53-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ba53-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ba53-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ba53-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ba53-110">Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="9ba53-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="9ba53-111">Nel campo di ricerca della pagina **Numero non assegnato** digitare per intero o in parte il nome dell'intervallo di numeri non assegnati che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="9ba53-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="9ba53-112">Nell'elenco risultante degli intervalli di numeri fare clic sul nome, su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9ba53-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="9ba53-113">Fare clic su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="9ba53-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9ba53-114">Per utilizzare Windows PowerShell per eliminare un intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="9ba53-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9ba53-115">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9ba53-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9ba53-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9ba53-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9ba53-117">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="9ba53-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="9ba53-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ba53-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ba53-119">Per informazioni dettagliate su altre opzioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="9ba53-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ba53-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ba53-120">See Also</span></span>


[<span data-ttu-id="9ba53-121">Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ba53-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="9ba53-122">Remove-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="9ba53-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="9ba53-123">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="9ba53-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

