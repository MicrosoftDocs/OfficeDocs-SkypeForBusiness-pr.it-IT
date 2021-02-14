---
title: Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828086"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7c447-103">Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c447-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7c447-104">**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c447-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7c447-105">In questo argomento viene descritto come gestire le impostazioni di configurazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7c447-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="7c447-106">Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere Pianificare le conferenze [in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Distribuire le conferenze in Skype for Business [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="7c447-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="7c447-107">Le impostazioni di configurazione delle riunioni determinano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) gli utenti anonimi e gli utenti di conferenze telefoniche con accesso esterno possono partecipare a queste riunioni.</span><span class="sxs-lookup"><span data-stu-id="7c447-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="7c447-108">Si noti che queste impostazioni influiscono solo sulle riunioni pianificate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione Riunione ora in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7c447-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="7c447-109">Le impostazioni di configurazione delle riunioni definiscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7c447-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="7c447-110">Se gli utenti con accesso esterno dalla rete PSTN (Public Switched Telephone Network) devono transitare per la sala di attesa</span><span class="sxs-lookup"><span data-stu-id="7c447-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="7c447-111">Chi può svolgere il ruolo di relatore</span><span class="sxs-lookup"><span data-stu-id="7c447-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="7c447-112">Se il tipo di conferenza viene assegnato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="7c447-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="7c447-113">Se gli utenti anonimi (non autenticati) sono ammessi per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="7c447-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="7c447-114">È possibile definire le caratteristiche delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7c447-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="7c447-115">È possibile specificare le impostazioni delle riunioni a livello globale (creato per impostazione predefinita), a livello di sito o di pool.</span><span class="sxs-lookup"><span data-stu-id="7c447-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="7c447-116">Per impostazione predefinita, le impostazioni globali definiscono l'esperienza di riunione.</span><span class="sxs-lookup"><span data-stu-id="7c447-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="7c447-117">Se si creano impostazioni a livello di pool, tali impostazioni si applicheranno a tutte le riunioni ospitate da tale pool.</span><span class="sxs-lookup"><span data-stu-id="7c447-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="7c447-118">Se invece non si creano impostazioni a livello di pool, si applicheranno le impostazioni a livello di sito, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="7c447-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="7c447-119">Se non si definiscono impostazioni a livello di sito, le impostazioni globali si applicheranno a tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="7c447-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7c447-120">Gestire le impostazioni delle riunioni tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c447-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="7c447-121">Per gestire le impostazioni delle riunioni tramite il Pannello di controllo di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="7c447-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="7c447-122">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7c447-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7c447-123">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c447-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7c447-124">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Configurazione riunione.**</span><span class="sxs-lookup"><span data-stu-id="7c447-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7c447-125">Gestire le impostazioni delle riunioni tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7c447-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7c447-126">Per gestire le riunioni tramite Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c447-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="7c447-127">**Impostazioni di configurazione delle riunioni**</span><span class="sxs-lookup"><span data-stu-id="7c447-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="7c447-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="7c447-128">**Cmdlet**</span></span>|<span data-ttu-id="7c447-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7c447-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7c447-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c447-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7c447-131">Restituisce informazioni sulle impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c447-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="7c447-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c447-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7c447-133">Crea una nuova raccolta di impostazioni di configurazione delle riunioni nell'ambito del sito o del servizio.</span><span class="sxs-lookup"><span data-stu-id="7c447-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="7c447-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c447-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7c447-135">Elimina una raccolta esistente di impostazioni di configurazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7c447-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="7c447-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c447-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="7c447-137">Modifica le impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c447-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

