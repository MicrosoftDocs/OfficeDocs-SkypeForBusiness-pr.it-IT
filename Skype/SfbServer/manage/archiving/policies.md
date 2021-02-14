---
title: Gestire i criteri di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: "Riepilogo: informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828551"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="efd1a-103">Gestire i criteri di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="efd1a-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="efd1a-104">**Riepilogo:** Informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="efd1a-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="efd1a-105">I criteri di archiviazione vengono inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="efd1a-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="efd1a-106">I criteri di archiviazione determinano se archiviare:</span><span class="sxs-lookup"><span data-stu-id="efd1a-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="efd1a-107">Comunicazioni interne</span><span class="sxs-lookup"><span data-stu-id="efd1a-107">Internal communications</span></span>
    
- <span data-ttu-id="efd1a-108">Comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="efd1a-108">External communications</span></span>
    
<span data-ttu-id="efd1a-109">I criteri di archiviazione possono essere impostati a livello globale, di sito o di utente.</span><span class="sxs-lookup"><span data-stu-id="efd1a-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efd1a-110">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono In-Place archiviazione.</span><span class="sxs-lookup"><span data-stu-id="efd1a-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="efd1a-111">Per informazioni dettagliate, vedere [Pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="efd1a-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="efd1a-112">Gestire i criteri di archiviazione tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="efd1a-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="efd1a-113">È possibile gestire i criteri di archiviazione utilizzando il Pannello di controllo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="efd1a-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="efd1a-114">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="efd1a-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="efd1a-115">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="efd1a-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="efd1a-116">Sulla barra di spostamento sinistra fare clic su **Criteri di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="efd1a-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="efd1a-117">Gestire i criteri di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efd1a-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="efd1a-118">È inoltre possibile configurare i criteri di archiviazione utilizzando Windows PowerShell cmdlet elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="efd1a-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="efd1a-119">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="efd1a-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="efd1a-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="efd1a-120">**Cmdlet**</span></span>|<span data-ttu-id="efd1a-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="efd1a-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="efd1a-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="efd1a-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="efd1a-123">Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="efd1a-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="efd1a-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="efd1a-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="efd1a-125">Assegna i criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai set di utenti.</span><span class="sxs-lookup"><span data-stu-id="efd1a-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="efd1a-126">Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="efd1a-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="efd1a-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="efd1a-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="efd1a-128">Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="efd1a-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="efd1a-129">Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="efd1a-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="efd1a-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="efd1a-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="efd1a-131">Rimuove il criterio di archiviazione della messaggistica istantanea specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.</span><span class="sxs-lookup"><span data-stu-id="efd1a-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="efd1a-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="efd1a-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="efd1a-133">Modifica un criterio di archiviazione di messaggistica istantanea esistente.</span><span class="sxs-lookup"><span data-stu-id="efd1a-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="efd1a-134">I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra utenti interni; è inoltre possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.</span><span class="sxs-lookup"><span data-stu-id="efd1a-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

