---
title: Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: cefdf304d8cf5ed6ff4560dd5416283d733c3db2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818527"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6ab50-103">Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6ab50-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6ab50-104">**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ab50-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6ab50-105">Questo argomento descrive come gestire le impostazioni di configurazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="6ab50-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="6ab50-106">Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="6ab50-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="6ab50-107">Le impostazioni di configurazione della riunione dettano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) utenti anonimi e servizi di conferenza telefonica con accesso esterno possono partecipare a queste riunioni.</span><span class="sxs-lookup"><span data-stu-id="6ab50-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="6ab50-108">Tieni presente che queste impostazioni influenzano solo le riunioni programmate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione incontra ora in Skype for business.</span><span class="sxs-lookup"><span data-stu-id="6ab50-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="6ab50-109">Le impostazioni di configurazione della riunione definiscono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ab50-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="6ab50-110">Se gli utenti che effettuano la chiamata dalla rete PSTN (Public Switched Telephone Network) accedono alla sala di attesa</span><span class="sxs-lookup"><span data-stu-id="6ab50-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="6ab50-111">Chi può essere un relatore</span><span class="sxs-lookup"><span data-stu-id="6ab50-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="6ab50-112">Se il tipo di conferenza è assegnato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="6ab50-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="6ab50-113">Se gli utenti anonimi (non autenticati) sono ammessi per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="6ab50-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="6ab50-114">Puoi definire le caratteristiche delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6ab50-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="6ab50-115">Puoi specificare le impostazioni delle riunioni a livello globale (creato per impostazione predefinita), livello di sito o livello di pool.</span><span class="sxs-lookup"><span data-stu-id="6ab50-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="6ab50-116">Per impostazione predefinita, le impostazioni globali definiscono l'esperienza della riunione.</span><span class="sxs-lookup"><span data-stu-id="6ab50-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="6ab50-117">Se crei impostazioni a livello di pool, queste impostazioni si applicano a tutte le riunioni ospitate da tale pool.</span><span class="sxs-lookup"><span data-stu-id="6ab50-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="6ab50-118">Se non si creano impostazioni a livello di pool, le impostazioni a livello di sito si applicano, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="6ab50-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="6ab50-119">Se non si definiscono le impostazioni a livello di sito, le impostazioni globali si applicano a tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="6ab50-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ab50-120">Gestire le impostazioni delle riunioni tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6ab50-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="6ab50-121">Per gestire le impostazioni delle riunioni tramite il pannello di controllo di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="6ab50-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="6ab50-122">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6ab50-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6ab50-123">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ab50-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6ab50-124">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="6ab50-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ab50-125">Gestire le impostazioni delle riunioni tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6ab50-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6ab50-126">Per gestire le riunioni tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ab50-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="6ab50-127">**Impostazioni di configurazione delle riunioni**</span><span class="sxs-lookup"><span data-stu-id="6ab50-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="6ab50-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6ab50-128">**Cmdlet**</span></span>|<span data-ttu-id="6ab50-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6ab50-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6ab50-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ab50-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6ab50-131">Restituisce informazioni sulle impostazioni di configurazione della riunione attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ab50-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="6ab50-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ab50-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6ab50-133">Crea una nuova raccolta di impostazioni di configurazione della riunione nell'ambito del sito o del servizio.</span><span class="sxs-lookup"><span data-stu-id="6ab50-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="6ab50-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ab50-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6ab50-135">Elimina una raccolta esistente di impostazioni di configurazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="6ab50-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="6ab50-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ab50-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6ab50-137">Modifica le impostazioni di configurazione della riunione attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ab50-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

