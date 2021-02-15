---
title: Gestire i criteri di conferenza in Skype for Business Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Riepilogo: informazioni su come gestire i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835276"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="24e45-103">Gestire i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="24e45-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="24e45-104">**Riepilogo:** Informazioni su come gestire i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="24e45-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="24e45-105">In questo argomento viene descritto come gestire i criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="24e45-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="24e45-106">Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere Pianificare le conferenze [in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Distribuire le conferenze in Skype for Business [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="24e45-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="24e45-107">I criteri di conferenza consentono di definire un'ampia gamma di opzioni di pianificazione e partecipazione, dalla possibilità o meno a una riunione di includere audio e video IP al numero massimo di persone che possono partecipare.</span><span class="sxs-lookup"><span data-stu-id="24e45-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="24e45-108">È possibile utilizzare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="24e45-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="24e45-109">È possibile definire un criterio di conferenza su tre livelli: ambito globale, ambito sito e ambito utente.</span><span class="sxs-lookup"><span data-stu-id="24e45-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="24e45-110">Le impostazioni si applicano a un utente specifico partendo dall'ambito più ristretto fino all'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="24e45-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="24e45-111">Se si assegna un criterio a un utente, tali impostazioni hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="24e45-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="24e45-112">Se non si assegna un criterio utente, si applicano le impostazioni sito.</span><span class="sxs-lookup"><span data-stu-id="24e45-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="24e45-113">Se non si applica alcun criterio utente o sito, le impostazioni predefinite vengono fornite dal criterio globale.</span><span class="sxs-lookup"><span data-stu-id="24e45-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="24e45-p104">Poiché esiste un criterio globale per impostazione predefinita, non è possibile crearne uno nuovo. Non è possibile inoltre eliminare il criterio globale esistente, ma è possibile modificarlo per personalizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="24e45-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="24e45-116">Gestire i criteri di conferenza tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="24e45-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="24e45-117">Per gestire i criteri di conferenza tramite il Pannello di controllo di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="24e45-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="24e45-118">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="24e45-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="24e45-119">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="24e45-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="24e45-120">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="24e45-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="24e45-121">Gestire i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="24e45-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="24e45-122">Per gestire le riunioni tramite Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="24e45-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="24e45-123">**Impostazioni dei criteri di conferenza**</span><span class="sxs-lookup"><span data-stu-id="24e45-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="24e45-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="24e45-124">**Cmdlet**</span></span>|<span data-ttu-id="24e45-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="24e45-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="24e45-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="24e45-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="24e45-127">Restituisce informazioni sui criteri conferenza configurati per l'utilizzo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24e45-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="24e45-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="24e45-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="24e45-129">Assegna un criterio di conferenza nell'ambito per utente.</span><span class="sxs-lookup"><span data-stu-id="24e45-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="24e45-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="24e45-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="24e45-131">Crea un nuovo criterio relativo alle conferenze da utilizzare all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24e45-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="24e45-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="24e45-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="24e45-133">Rimuove il criterio conferenza specificato.</span><span class="sxs-lookup"><span data-stu-id="24e45-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="24e45-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="24e45-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="24e45-135">Consente di modificare un criterio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="24e45-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

