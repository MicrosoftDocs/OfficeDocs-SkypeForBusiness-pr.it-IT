---
title: Eliminare criteri di sito o utente per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puoi eliminare qualsiasi criterio di sito o utente elencato nel pannello di controllo di Skype for Business Server nella pagina dei criteri di accesso esterno.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188813"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="95063-103">Eliminare criteri di sito o utente per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="95063-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="95063-104">Se sono stati creati o configurati criteri di accesso degli utenti esterni che non si vuole più usare, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95063-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="95063-105">Eliminare qualsiasi criterio di sito o utente creato.</span><span class="sxs-lookup"><span data-stu-id="95063-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="95063-106">Reimpostare il criterio globale sulle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="95063-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="95063-107">Le impostazioni dei criteri globali predefinite negano l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="95063-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="95063-108">Non è possibile eliminare il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="95063-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="95063-109">Puoi eliminare qualsiasi criterio di sito o utente elencato nel pannello di controllo di Skype for Business Server nella pagina dei **criteri di accesso esterno** .</span><span class="sxs-lookup"><span data-stu-id="95063-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="95063-110">L'eliminazione del criterio globale in realtà non lo elimina, ma lo reimposta solo sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="95063-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="95063-111">Per informazioni dettagliate su come reimpostare il criterio globale, vedere [reimpostare il criterio globale per l'accesso degli utenti esterni](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="95063-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="95063-112">Per eliminare un sito o un criterio utente per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="95063-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="95063-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="95063-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95063-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="95063-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="95063-115">Fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="95063-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="95063-116">Nella scheda **criteri di accesso esterno** fare clic sul sito o sui criteri degli utenti da eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="95063-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="95063-117">Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="95063-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="95063-118">Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95063-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="95063-119">I criteri di accesso esterno possono essere eliminati tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="95063-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="95063-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95063-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="95063-121">Per rimuovere un criterio di accesso esterno specifico</span><span class="sxs-lookup"><span data-stu-id="95063-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="95063-122">Questo comando rimuove il criterio di accesso esterno applicato al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="95063-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="95063-123">Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente</span><span class="sxs-lookup"><span data-stu-id="95063-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="95063-124">Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito per utente:</span><span class="sxs-lookup"><span data-stu-id="95063-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="95063-125">Per rimuovere tutti i criteri di accesso esterno in cui l'utente esterno è disabilitato</span><span class="sxs-lookup"><span data-stu-id="95063-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="95063-126">Questo comando Elimina tutti i criteri di accesso esterno in cui l'accesso esterno dell'utente è stato disabilitato:</span><span class="sxs-lookup"><span data-stu-id="95063-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="95063-127">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="95063-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
