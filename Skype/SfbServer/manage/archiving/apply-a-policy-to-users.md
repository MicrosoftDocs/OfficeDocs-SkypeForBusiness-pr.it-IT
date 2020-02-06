---
title: Applicare un criterio di archiviazione agli utenti in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Riepilogo: informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819008"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="f85bc-103">Applicare un criterio di archiviazione agli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f85bc-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="f85bc-104">**Riepilogo:** Informazioni su come assegnare un criterio di archiviazione agli utenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f85bc-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="f85bc-105">Se sono stati creati uno o più criteri per l'archiviazione per gli utenti ospitati in Skype for Business Server, è possibile implementare il supporto per l'archiviazione per utenti specifici applicando i criteri appropriati a tali utenti o a gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="f85bc-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="f85bc-106">Ad esempio, se crei un criterio per supportare l'archiviazione delle comunicazioni interne, puoi applicarlo ad almeno un utente o un gruppo di utenti per supportare l'archiviazione delle comunicazioni di Skype for Business Server dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f85bc-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f85bc-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="f85bc-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f85bc-108">Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="f85bc-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="f85bc-109">Applicare un criterio utente tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="f85bc-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="f85bc-110">Per applicare un criterio utente tramite il pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="f85bc-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="f85bc-111">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f85bc-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f85bc-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f85bc-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f85bc-113">Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="f85bc-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="f85bc-114">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f85bc-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f85bc-115">In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="f85bc-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f85bc-116">Le \*\* \<impostazioni\> automatiche\*\* applicano le impostazioni di installazione del server predefinite.</span><span class="sxs-lookup"><span data-stu-id="f85bc-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="f85bc-117">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="f85bc-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="f85bc-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f85bc-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="f85bc-119">Applicare un criterio utente tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f85bc-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="f85bc-120">Puoi anche applicare un criterio utente usando il cmdlet **Grant-CsArchivingPolicy** di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f85bc-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f85bc-121">Con il comando seguente viene assegnato il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="f85bc-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="f85bc-122">Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che hanno account assegnati nel pool di registrazione atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f85bc-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="f85bc-123">Per informazioni dettagliate sul parametro Filter usato in questo comando, vedere la documentazione del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f85bc-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="f85bc-124">Il comando seguente rimuove tutti i criteri di archiviazione per utente assegnati in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="f85bc-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f85bc-125">Dopo che il criterio per utente viene rimosso, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="f85bc-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f85bc-126">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="f85bc-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="f85bc-127">Per informazioni dettagliate, vedere la documentazione del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f85bc-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

