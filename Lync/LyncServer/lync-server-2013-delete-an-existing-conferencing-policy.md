---
title: 'Lync Server 2013: eliminare un criterio di conferenza esistente'
description: 'Lync Server 2013: eliminare un criterio di conferenza esistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b64e51acc6e6dc91b938244da28057b01957069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572832"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="3c96d-103">Eliminare un criterio di conferenza esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c96d-103">Delete an existing conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c96d-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3c96d-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3c96d-105">Eseguire questa procedura per eliminare un criterio di conferenza a livello di utente o di sito.</span><span class="sxs-lookup"><span data-stu-id="3c96d-105">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c96d-106">Non è possibile eliminare il criterio di conferenza globale.</span><span class="sxs-lookup"><span data-stu-id="3c96d-106">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="3c96d-107">Per eliminare un criterio di conferenza a livello di utente o di sito</span><span class="sxs-lookup"><span data-stu-id="3c96d-107">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="3c96d-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3c96d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3c96d-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c96d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3c96d-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c96d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3c96d-111">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="3c96d-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="3c96d-112">Nell'elenco dei criteri conferenza fare clic sul criterio sito o utente che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3c96d-112">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3c96d-113">Rimozione dei criteri di conferenza tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c96d-113">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3c96d-114">È possibile eliminare i criteri di conferenza utilizzando Lync Server Management Shell e il cmdlet **Remove-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3c96d-114">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="3c96d-115">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c96d-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3c96d-116">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3c96d-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="3c96d-117">Per rimuovere un criterio di conferenza specifico.</span><span class="sxs-lookup"><span data-stu-id="3c96d-117">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="3c96d-118">Il comando seguente rimuove il criterio di conferenza con identità (Identity) RedmondConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="3c96d-118">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="3c96d-119">Per rimuovere tutti i criteri di conferenza applicati all'ambito "per utente"</span><span class="sxs-lookup"><span data-stu-id="3c96d-119">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="3c96d-120">Questo comando rimuove tutti i criteri di conferenza configurati nell'ambito "per utente":</span><span class="sxs-lookup"><span data-stu-id="3c96d-120">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="3c96d-121">Per rimuovere tutti i criteri di conferenza che consentono la registrazione da parte degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3c96d-121">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="3c96d-122">Questo comando rimuove tutti i criteri di conferenza configurati che consentono la registrazione da parte degli utenti esterni:</span><span class="sxs-lookup"><span data-stu-id="3c96d-122">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="3c96d-123">Per informazioni dettagliate, vedere [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span><span class="sxs-lookup"><span data-stu-id="3c96d-123">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

