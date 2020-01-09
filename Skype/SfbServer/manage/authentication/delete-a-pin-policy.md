---
title: Eliminare un criterio PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Riepilogo: eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: cfdb14ad8107c8d3450e6d50245831f723ca1153
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992323"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="e8749-103">Eliminare un criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8749-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="e8749-104">**Riepilogo:** Eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8749-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="e8749-105">Seguire questa procedura per eliminare un criterio PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="e8749-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8749-106">Non è possibile eliminare il criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="e8749-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e8749-107">Per eliminare un criterio PIN nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8749-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e8749-108">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="e8749-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e8749-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8749-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e8749-110">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="e8749-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="e8749-111">Nella pagina **criteri PIN** e nel campo di ricerca digitare tutto o parte del nome del criterio che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="e8749-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="e8749-112">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e8749-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e8749-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8749-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8749-114">Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8749-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8749-115">È possibile eliminare i criteri di aggiunta tramite Windows PowerShell e il cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="e8749-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e8749-116">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8749-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8749-117">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e8749-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e8749-118">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8749-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="e8749-119">Per rimuovere un criterio PIN specifico</span><span class="sxs-lookup"><span data-stu-id="e8749-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="e8749-120">Questo comando rimuove il criterio PIN con l'identità RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="e8749-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="e8749-121">Per rimuovere tutti i criteri PIN applicati all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="e8749-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="e8749-122">Questo comando rimuove tutti i criteri PIN configurati nell'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="e8749-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="e8749-123">Per rimuovere tutti i criteri PIN che consentono l'uso di modelli comuni</span><span class="sxs-lookup"><span data-stu-id="e8749-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="e8749-124">E questo rimuove tutti i criteri PIN che consentono l'uso di modelli comuni: G</span><span class="sxs-lookup"><span data-stu-id="e8749-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="e8749-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e8749-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

