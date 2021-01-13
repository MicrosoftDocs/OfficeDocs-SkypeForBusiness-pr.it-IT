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
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="9375d-103">Gestire i criteri di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9375d-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="9375d-104">**Riepilogo:** Informazioni su come gestire i criteri utente per l'archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9375d-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="9375d-105">Inizialmente sono stati configurati i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare le configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9375d-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9375d-106">I criteri di archiviazione determinano se archiviare:</span><span class="sxs-lookup"><span data-stu-id="9375d-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="9375d-107">Comunicazioni interne</span><span class="sxs-lookup"><span data-stu-id="9375d-107">Internal communications</span></span>
    
- <span data-ttu-id="9375d-108">Comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="9375d-108">External communications</span></span>
    
<span data-ttu-id="9375d-109">I criteri di archiviazione possono essere impostati a livello globale, del sito o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9375d-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9375d-110">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange e le loro cassette postali sono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="9375d-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="9375d-111">Per ulteriori informazioni, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [configurare l'integrazione con l'archivio di Exchange per Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="9375d-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="9375d-112">Gestire i criteri di archiviazione utilizzando il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="9375d-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="9375d-113">È possibile gestire i criteri di archiviazione utilizzando il pannello di controllo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9375d-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="9375d-114">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9375d-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9375d-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9375d-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9375d-116">Sulla barra di spostamento sinistra fare clic su **criteri di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="9375d-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="9375d-117">Gestire i criteri di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9375d-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="9375d-118">È inoltre possibile configurare i criteri di archiviazione utilizzando i cmdlet di Windows PowerShell elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9375d-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="9375d-119">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="9375d-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="9375d-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9375d-120">**Cmdlet**</span></span>|<span data-ttu-id="9375d-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9375d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9375d-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9375d-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9375d-123">Restituisce informazioni sui criteri di archiviazione delle sessioni di messaggistica istantanea (IM) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9375d-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="9375d-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9375d-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9375d-125">Consente di assegnare criteri di archiviazione delle sessioni di messaggistica istantanea agli utenti o ai gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="9375d-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="9375d-126">Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="9375d-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="9375d-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9375d-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9375d-128">Crea nuovi criteri di archiviazione per sessioni di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="9375d-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="9375d-129">Tali criteri consentono di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e/o di archiviare tutte le sessioni di messaggistica istantanea eseguite tra utenti interni e partner esterni.</span><span class="sxs-lookup"><span data-stu-id="9375d-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="9375d-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9375d-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9375d-131">Rimuove il criterio di archiviazione dei messaggi istantanei specificato che determina se Skype for Business Server salverà automaticamente tutte le sessioni di messaggistica istantanea che si verificano tra gli utenti interni e/o tutte le sessioni di messaggistica istantanea tra gli utenti interni e i partner federati.</span><span class="sxs-lookup"><span data-stu-id="9375d-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="9375d-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9375d-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9375d-133">Modifica un criterio di archiviazione di messaggistica istantanea esistente.</span><span class="sxs-lookup"><span data-stu-id="9375d-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="9375d-134">I criteri di archiviazione offrono la possibilità di archiviare tutte le sessioni di messaggistica istantanea e le conferenze che si verificano tra gli utenti interni; è inoltre possibile archiviare le sessioni che si verificano tra gli utenti interni e i partner federati.</span><span class="sxs-lookup"><span data-stu-id="9375d-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

