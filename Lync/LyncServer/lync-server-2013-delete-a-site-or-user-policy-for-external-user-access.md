---
title: "Lync Server 2013: eliminare criteri di sito o utente per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c21b58715814b5bf08023662bff61b004b51896
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0099d-102">Eliminare criteri di sito o utente per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0099d-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0099d-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0099d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0099d-104">È possibile eliminare tutti i criteri di sito o utente elencati nel pannello di controllo di Lync Server nella pagina **criteri di accesso esterno** .</span><span class="sxs-lookup"><span data-stu-id="0099d-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="0099d-105">L'eliminazione di criteri globali non ne implica l'effettiva rimozione, ma solo il ripristino delle impostazioni predefinite, che non includono il supporto per alcuna opzione di accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="0099d-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="0099d-106">Per informazioni dettagliate sulla reimpostazione dei criteri globali, vedere [reimpostare i criteri globali per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0099d-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="0099d-107">Per eliminare criteri sito o utente per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="0099d-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="0099d-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0099d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0099d-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0099d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0099d-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0099d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0099d-111">Fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="0099d-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0099d-112">Nella scheda **Criteri di accesso esterno** fare clic sui criteri sito o utente che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0099d-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0099d-113">Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0099d-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0099d-114">Rimozione dei criteri del PIN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0099d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0099d-115">È possibile eliminare i criteri di accesso esterno utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="0099d-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="0099d-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0099d-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0099d-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="0099d-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="0099d-118">Per rimuovere un criterio di accesso esterno specifico</span><span class="sxs-lookup"><span data-stu-id="0099d-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="0099d-119">Questo comando rimuove i criteri di accesso esterno applicati al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="0099d-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="0099d-120">Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente</span><span class="sxs-lookup"><span data-stu-id="0099d-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="0099d-121">Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito "per utente":</span><span class="sxs-lookup"><span data-stu-id="0099d-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="0099d-122">Per rimuovere tutti i criteri di accesso esterno a cui è disabilitato l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="0099d-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="0099d-123">Questo comando elimina tutti i criteri di accesso esterno dove l'accesso esterno dell'utente è stato disattivato:</span><span class="sxs-lookup"><span data-stu-id="0099d-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="0099d-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="0099d-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

