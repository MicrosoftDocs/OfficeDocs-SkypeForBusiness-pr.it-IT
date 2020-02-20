---
title: 'Lync Server 2013: eliminare un criterio PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044c8a6ac5d87723a58c1f692c5e969701b72a37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="76431-102">Eliminare un criterio PIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76431-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76431-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="76431-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="76431-104">Eseguire la procedura seguente per eliminare criteri PIN.</span><span class="sxs-lookup"><span data-stu-id="76431-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76431-105">Non è possibile eliminare criteri PIN globali.</span><span class="sxs-lookup"><span data-stu-id="76431-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="76431-106">Per eliminare un criterio PIN nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76431-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="76431-107">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76431-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="76431-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76431-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76431-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="76431-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="76431-110">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="76431-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="76431-111">Nella pagina **Criteri PIN** e nel campo di ricerca digitare il nome, o parte di esso, dei criteri che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="76431-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="76431-112">Nell'elenco di criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="76431-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="76431-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76431-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="76431-114">Rimozione dei criteri del PIN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76431-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="76431-115">È possibile eliminare i criteri PIN utilizzando Windows PowerShell e il cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="76431-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="76431-116">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76431-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76431-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="76431-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="76431-118">Per rimuovere un criterio PIN specifico</span><span class="sxs-lookup"><span data-stu-id="76431-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="76431-119">Questo comando rimuove il criterio PIN con identità (Identity) RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="76431-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="76431-120">Per rimuovere tutti i criteri PIN applicati all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="76431-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="76431-121">Questo comando rimuove tutti i criteri PIN configurati nell'ambito sito:</span><span class="sxs-lookup"><span data-stu-id="76431-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="76431-122">Per rimuovere tutti i criteri PIN che consentono l'utilizzo di modelli comuni</span><span class="sxs-lookup"><span data-stu-id="76431-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="76431-123">Questo comando rimuove tutti i criteri PIN che consentono l'utilizzo di formati comuni:G</span><span class="sxs-lookup"><span data-stu-id="76431-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="76431-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="76431-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

