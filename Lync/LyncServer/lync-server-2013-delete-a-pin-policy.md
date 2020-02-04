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
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="cce6d-102">Eliminare un criterio PIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cce6d-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cce6d-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cce6d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cce6d-104">Seguire questa procedura per eliminare un criterio PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="cce6d-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cce6d-105">Non è possibile eliminare il criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="cce6d-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="cce6d-106">Per eliminare un criterio PIN nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cce6d-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="cce6d-107">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cce6d-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cce6d-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cce6d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cce6d-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cce6d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cce6d-110">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="cce6d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="cce6d-111">Nella pagina **criteri PIN** e nel campo di ricerca digitare tutto o parte del nome del criterio che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="cce6d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="cce6d-112">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cce6d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="cce6d-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cce6d-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cce6d-114">Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cce6d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cce6d-115">È possibile eliminare i criteri di aggiunta tramite Windows PowerShell e il cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="cce6d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="cce6d-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cce6d-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cce6d-117">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="cce6d-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="cce6d-118">Per rimuovere un criterio PIN specifico</span><span class="sxs-lookup"><span data-stu-id="cce6d-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="cce6d-119">Questo comando rimuove il criterio PIN con l'identità RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="cce6d-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="cce6d-120">Per rimuovere tutti i criteri PIN applicati all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="cce6d-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="cce6d-121">Questo comando rimuove tutti i criteri PIN configurati nell'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="cce6d-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="cce6d-122">Per rimuovere tutti i criteri PIN che consentono l'uso di modelli comuni</span><span class="sxs-lookup"><span data-stu-id="cce6d-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="cce6d-123">E questo rimuove tutti i criteri PIN che consentono l'uso di modelli comuni: G</span><span class="sxs-lookup"><span data-stu-id="cce6d-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="cce6d-124">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="cce6d-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

