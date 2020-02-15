---
title: 'Lync Server 2013: eliminare un criterio versione client esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e18cf2aa76ada1d3ab42d16f68d902ad3a41eae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="ff9f6-102">Eliminare un criterio di versione client esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff9f6-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff9f6-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ff9f6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ff9f6-104">Se si desidera eliminare un criterio di versione client precedentemente configurato, è possibile eliminarlo dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="ff9f6-105">Per eliminare i criteri di versione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff9f6-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ff9f6-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff9f6-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff9f6-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ff9f6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff9f6-109">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **criteri versione client** .</span><span class="sxs-lookup"><span data-stu-id="ff9f6-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="ff9f6-110">Nella pagina **criteri versione client** selezionare i criteri di versione client o i criteri che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff9f6-111">Eliminazione dei criteri di versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff9f6-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff9f6-112">È possibile eliminare i criteri di versione client utilizzando il cmdlet **Remove-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ff9f6-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="ff9f6-113">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ff9f6-114">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="ff9f6-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="ff9f6-115">Per rimuovere un criterio di versione client specifico</span><span class="sxs-lookup"><span data-stu-id="ff9f6-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="ff9f6-116">Questo comando consente di eliminare i criteri di versione client applicati al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="ff9f6-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="ff9f6-117">Per rimuovere tutti i criteri di versione client applicati all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="ff9f6-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="ff9f6-118">Questo comando consente di rimuovere tutti i criteri di versione client configurati nell'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="ff9f6-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="ff9f6-119">Per rimuovere i criteri di versione client che non includono un agente utente specifico</span><span class="sxs-lookup"><span data-stu-id="ff9f6-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="ff9f6-120">Questo comando rimuove tutti i criteri di versione client che non includono una regola per l'agente utente di Windows Phone Lync (WPLync):</span><span class="sxs-lookup"><span data-stu-id="ff9f6-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="ff9f6-121">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="ff9f6-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

