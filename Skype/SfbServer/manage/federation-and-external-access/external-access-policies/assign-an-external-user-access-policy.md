---
title: Assegnare un criterio di accesso utente esterno
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso degli utenti remoti e la connettività per la messaggistica istantanea pubblica nel pannello di controllo di Skype for Business Server applicando i criteri corretti a utenti specifici.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043678"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="2d2ca-103">Assegnare un criterio di accesso utente esterno a un utente abilitato di Skype for business</span><span class="sxs-lookup"><span data-stu-id="2d2ca-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="2d2ca-104">Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso degli utenti remoti e la connettività per la messaggistica istantanea pubblica nel pannello di controllo di Skype for Business Server applicando i criteri corretti a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="2d2ca-105">Ad esempio, se è stato creato un criterio per supportare l'accesso degli utenti remoti, è necessario applicarlo all'utente prima che l'utente possa connettersi a Skype for Business Server da una postazione remota e collaborare con utenti interni dalla postazione remota.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="2d2ca-106">Per supportare l'accesso utente esterno, è necessario abilitare il supporto per ogni tipo di accesso utente esterno desiderato e configurare i criteri appropriati e altre opzioni per il controllo.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="2d2ca-107">Per informazioni dettagliate, vedere [Managing Federation and External Access to Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="2d2ca-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="2d2ca-108">Utilizzare la procedura contenuta in questo argomento per applicare criteri di accesso utente esterno creati in precedenza a uno o più account utente.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="2d2ca-109">Per applicare criteri di accesso utente esterno a un account utente</span><span class="sxs-lookup"><span data-stu-id="2d2ca-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="2d2ca-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d2ca-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d2ca-112">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="2d2ca-113">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2d2ca-114">In **modifica utente di Skype for Business Server** in **criteri di accesso esterno**, selezionare i criteri utente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="2d2ca-115">Le impostazioni del \*\* \<>automatico\*\* applicano le impostazioni predefinite del server o dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d2ca-116">Assegnazione dei criteri di accesso esterno per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d2ca-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2d2ca-117">I criteri di accesso esterno per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="2d2ca-118">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="2d2ca-119">Per assegnare un criterio di accesso esterno per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="2d2ca-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="2d2ca-120">Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="2d2ca-121">Per assegnare criteri di accesso esterno per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="2d2ca-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="2d2ca-122">Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che dispongono di account nell'unità organizzativa UnitedStates in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="2d2ca-123">Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="2d2ca-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="2d2ca-124">Per annullare l'assegnazione di un criterio di accesso esterno per utente</span><span class="sxs-lookup"><span data-stu-id="2d2ca-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="2d2ca-p105">Questo comando annulla l'assegnazione di tutti i criteri di accesso esterno per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="2d2ca-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="2d2ca-128">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="2d2ca-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


