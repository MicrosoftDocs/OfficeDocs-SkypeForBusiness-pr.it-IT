---
title: Gestire i criteri di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: "Riepilogo: informazioni su come gestire i criteri degli utenti per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818888"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="badd0-103">Gestire i criteri di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="badd0-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="badd0-104">**Riepilogo:** Informazioni su come gestire i criteri degli utenti per l'archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="badd0-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="badd0-105">I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="badd0-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="badd0-106">I criteri di archiviazione determinano se eseguire l'archiviazione:</span><span class="sxs-lookup"><span data-stu-id="badd0-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="badd0-107">Comunicazioni interne</span><span class="sxs-lookup"><span data-stu-id="badd0-107">Internal communications</span></span>
    
- <span data-ttu-id="badd0-108">Comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="badd0-108">External communications</span></span>
    
<span data-ttu-id="badd0-109">I criteri di archiviazione possono essere impostati a livello globale, del sito o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="badd0-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="badd0-110">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="badd0-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="badd0-111">Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="badd0-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="badd0-112">Gestire i criteri di archiviazione tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="badd0-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="badd0-113">È possibile gestire i criteri di archiviazione usando il pannello di controllo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="badd0-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="badd0-114">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="badd0-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="badd0-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="badd0-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="badd0-116">Sulla barra di spostamento sinistra fare clic su **criteri di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="badd0-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="badd0-117">Gestire i criteri di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="badd0-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="badd0-118">È anche possibile configurare i criteri di archiviazione usando i cmdlet di Windows PowerShell elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="badd0-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="badd0-119">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="badd0-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="badd0-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="badd0-120">**Cmdlet**</span></span>|<span data-ttu-id="badd0-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="badd0-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="badd0-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="badd0-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="badd0-123">Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea (IM) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="badd0-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="badd0-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="badd0-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="badd0-125">Assegna criteri di archiviazione delle sessioni di messaggistica istantanea a utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="badd0-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="badd0-126">Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="badd0-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="badd0-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="badd0-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="badd0-128">Crea nuovi criteri di archiviazione della sessione messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="badd0-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="badd0-129">Questi criteri offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="badd0-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="badd0-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="badd0-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="badd0-131">Rimuove i criteri di archiviazione di messaggistica istantanea specificati che determinano se Skype for Business Server Salva automaticamente tutte le sessioni di messaggistica istantanea che si svolgono tra utenti interni e/o tutte le sessioni di messaggistica istantanea tra utenti interni e partner federati.</span><span class="sxs-lookup"><span data-stu-id="badd0-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="badd0-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="badd0-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="badd0-133">Modifica un criterio di archiviazione della messaggistica istantanea esistente.</span><span class="sxs-lookup"><span data-stu-id="badd0-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="badd0-134">Un criterio di archiviazione offre la possibilità di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si svolgono tra gli utenti interni; è anche possibile archiviare le sessioni che si svolgono tra utenti interni e partner federati.</span><span class="sxs-lookup"><span data-stu-id="badd0-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

