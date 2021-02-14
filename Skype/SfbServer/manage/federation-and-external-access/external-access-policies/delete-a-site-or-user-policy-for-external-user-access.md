---
title: Eliminare criteri sito o utente per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile eliminare qualsiasi criterio utente o sito elencato nel Pannello di controllo di Skype for Business Server nella pagina Criteri di accesso esterno.
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817276"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="90c2c-103">Eliminare criteri sito o utente per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="90c2c-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="90c2c-104">Se sono stati creati o configurati criteri di accesso per gli utenti esterni che non si desidera più utilizzare, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90c2c-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="90c2c-105">Eliminare gli eventuali criteri a livello di sito o utente creati.</span><span class="sxs-lookup"><span data-stu-id="90c2c-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="90c2c-p101">Ripristinare le impostazioni predefinite per i criteri globali che negano qualsiasi tipo di accesso agli utenti esterni. I criteri globali non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="90c2c-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="90c2c-109">È possibile eliminare qualsiasi criterio utente o sito elencato nel Pannello di controllo di Skype for Business Server nella **pagina Criteri di accesso** esterno.</span><span class="sxs-lookup"><span data-stu-id="90c2c-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="90c2c-110">L'eliminazione di criteri globali non ne implica l'effettiva rimozione, ma solo il ripristino delle impostazioni predefinite, che non includono il supporto per alcuna opzione di accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="90c2c-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="90c2c-111">Per informazioni dettagliate sulla reimpostazione del criterio globale, vedere [Reset the global policy for external user access.](reset-the-global-policy-for-external-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="90c2c-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="90c2c-112">Per eliminare criteri sito o utente per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="90c2c-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="90c2c-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="90c2c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90c2c-114">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c2c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="90c2c-115">Fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="90c2c-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="90c2c-116">Nella scheda **Criteri di accesso esterno** fare clic sui criteri sito o utente che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="90c2c-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="90c2c-117">Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c2c-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90c2c-118">Rimozione di criteri PIN tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="90c2c-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90c2c-119">I criteri di accesso esterno possono essere eliminati utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy esterno.</span><span class="sxs-lookup"><span data-stu-id="90c2c-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="90c2c-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90c2c-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="90c2c-121">Per rimuovere un criterio di accesso esterno specifico</span><span class="sxs-lookup"><span data-stu-id="90c2c-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="90c2c-122">Questo comando rimuove i criteri di accesso esterno applicati al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="90c2c-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="90c2c-123">Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente</span><span class="sxs-lookup"><span data-stu-id="90c2c-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="90c2c-124">Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito "per utente":</span><span class="sxs-lookup"><span data-stu-id="90c2c-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="90c2c-125">Per rimuovere tutti i criteri di accesso esterno in cui l'accesso utente esterno è disabilitato</span><span class="sxs-lookup"><span data-stu-id="90c2c-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="90c2c-126">Questo comando elimina tutti i criteri di accesso esterno dove l'accesso esterno dell'utente è stato disattivato:</span><span class="sxs-lookup"><span data-stu-id="90c2c-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="90c2c-127">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="90c2c-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
