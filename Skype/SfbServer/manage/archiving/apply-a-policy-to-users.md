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
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817766"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="ba6dd-103">Applicare un criterio di archiviazione agli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ba6dd-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="ba6dd-104">**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba6dd-105">Se sono stati creati uno o più criteri utente per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto dell'archiviazione per utenti specifici applicando i criteri appropriati a tali utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="ba6dd-106">Ad esempio, se si crea un criterio per supportare l'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o gruppo di utenti per supportare l'archiviazione delle comunicazioni di Skype for Business Server dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba6dd-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco di Exchange In-Place controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono In-Place archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ba6dd-108">Per informazioni dettagliate, vedere [Pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="ba6dd-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="ba6dd-109">Applicare un criterio utente tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="ba6dd-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="ba6dd-110">Per applicare un criterio utente tramite il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="ba6dd-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="ba6dd-111">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ba6dd-112">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ba6dd-113">Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="ba6dd-114">Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ba6dd-115">In **Modifica utente Lync Server** in Criteri di **archiviazione** selezionare il criterio utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba6dd-116">Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="ba6dd-117">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="ba6dd-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="ba6dd-119">Applicare un criterio utente utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba6dd-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="ba6dd-120">È inoltre possibile applicare un criterio utente utilizzando Windows PowerShell **cmdlet Grant-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="ba6dd-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ba6dd-121">Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="ba6dd-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="ba6dd-122">Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti con account ospitati nel pool di registrazione atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="ba6dd-123">Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere la documentazione del cmdlet [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ba6dd-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="ba6dd-124">Il comando seguente rimuove tutti i criteri di archiviazione per utente precedentemente assegnati a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="ba6dd-125">Una volta rimosso il criterio per utente, Ken Myer verrà gestito automaticamente utilizzando il criterio globale o, se ne esiste uno, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="ba6dd-126">I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="ba6dd-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="ba6dd-127">Per informazioni dettagliate, vedere la documentazione del cmdlet [Grant-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ba6dd-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

