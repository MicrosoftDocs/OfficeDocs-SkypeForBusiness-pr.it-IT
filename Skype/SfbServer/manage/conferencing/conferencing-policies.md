---
title: Gestire i criteri di conferenza in Skype for Business Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Riepilogo: informazioni su come gestire i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818647"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="dd1d2-103">Gestire i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd1d2-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="dd1d2-104">**Riepilogo:** Informazioni su come gestire i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="dd1d2-105">Questo argomento descrive come gestire i criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="dd1d2-106">Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="dd1d2-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="dd1d2-107">I criteri di conferenza consentono di definire una vasta gamma di opzioni di pianificazione e partecipazione, che vanno dal fatto che una riunione possa includere l'audio e il video IP al numero massimo di persone che possono partecipare.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="dd1d2-108">È possibile usare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="dd1d2-109">È possibile definire i criteri di conferenza su tre livelli: ambito globale, ambito del sito e ambito utente.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="dd1d2-110">Le impostazioni si applicano a un utente specifico dall'ambito più stretto all'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="dd1d2-111">Se si assegna un criterio a un utente, queste impostazioni hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="dd1d2-112">Se non si assegna un criterio utente, le impostazioni del sito si applicano.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="dd1d2-113">Se non si applicano criteri per l'utente o il sito, i criteri globali forniscono le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="dd1d2-114">Un criterio globale esiste per impostazione predefinita, quindi non è possibile creare un nuovo criterio globale.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="dd1d2-115">Non è inoltre possibile eliminare i criteri globali esistenti, ma è possibile modificare i criteri globali esistenti per personalizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dd1d2-116">Gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd1d2-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="dd1d2-117">Per gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="dd1d2-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="dd1d2-118">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="dd1d2-119">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="dd1d2-120">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dd1d2-121">Gestire i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="dd1d2-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="dd1d2-122">Per gestire le riunioni tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd1d2-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="dd1d2-123">**Impostazioni dei criteri di conferenza**</span><span class="sxs-lookup"><span data-stu-id="dd1d2-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="dd1d2-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="dd1d2-124">**Cmdlet**</span></span>|<span data-ttu-id="dd1d2-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd1d2-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dd1d2-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="dd1d2-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="dd1d2-127">Restituisce informazioni sui criteri di conferenza configurati per l'uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="dd1d2-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="dd1d2-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="dd1d2-129">Assegna un criterio per i servizi di conferenza nell'ambito per utente.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="dd1d2-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="dd1d2-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="dd1d2-131">Crea un nuovo criterio di conferenza per l'uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="dd1d2-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="dd1d2-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="dd1d2-133">Rimuove i criteri di conferenza specificati.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="dd1d2-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="dd1d2-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="dd1d2-135">Modifica un criterio di conferenza esistente.</span><span class="sxs-lookup"><span data-stu-id="dd1d2-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

