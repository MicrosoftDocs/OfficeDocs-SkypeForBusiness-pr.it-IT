---
title: Applicare un criterio di archiviazione agli utenti in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Riepilogo: informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095490"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="c3156-103">Applicare un criterio di archiviazione agli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3156-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="c3156-104">**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3156-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="c3156-105">Se sono stati creati uno o più criteri utente per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto di archiviazione per utenti specifici applicando i criteri appropriati a tali utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="c3156-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="c3156-106">Ad esempio, se si crea un criterio per supportare l'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o gruppo di utenti per supportare l'archiviazione delle comunicazioni Skype for Business Server dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c3156-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3156-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco di Exchange In-Place controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e che le cassette postali vengono In-Place archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c3156-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c3156-108">Per informazioni dettagliate, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configure integration with Exchange storage for Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="c3156-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="c3156-109">Applicare criteri utente tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="c3156-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="c3156-110">Per applicare un criterio utente tramite il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="c3156-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c3156-111">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c3156-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c3156-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3156-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c3156-113">Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="c3156-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="c3156-114">Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c3156-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c3156-115">In **Modifica utente Lync Server** in Criteri di **archiviazione** selezionare il criterio utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="c3156-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3156-116">Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server.</span><span class="sxs-lookup"><span data-stu-id="c3156-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="c3156-117">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="c3156-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="c3156-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c3156-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="c3156-119">Applicare un criterio utente tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3156-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="c3156-120">È inoltre possibile applicare un criterio utente utilizzando il cmdlet **Grant-CsArchivingPolicy Windows PowerShell.CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="c3156-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c3156-121">Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="c3156-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="c3156-122">Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che dispongono di account ospitati nel pool di registrazione atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c3156-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="c3156-123">Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3156-123">For details about the Filter parameter used in this command, see the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="c3156-124">Il comando seguente consente di rimuovere tutti i criteri di archiviazione per utente precedentemente assegnati a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c3156-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="c3156-125">Dopo la rimozione dei criteri per utente, Ken Myer verrà gestito automaticamente utilizzando il criterio globale o, se esistente, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="c3156-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="c3156-126">I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="c3156-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="c3156-127">Per informazioni dettagliate, vedere la documentazione relativa al cmdlet [Grant-CsArchivingPolicy.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3156-127">For details, see the [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
