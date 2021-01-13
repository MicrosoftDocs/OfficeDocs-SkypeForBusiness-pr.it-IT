---
title: Distribuire la chiamata tramite il lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Riepilogo: informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825006"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="9c058-103">Distribuire la chiamata tramite il lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9c058-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="9c058-104">**Riepilogo:** Informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9c058-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="9c058-105">Attenersi alla procedura seguente per distribuire la chiamata tramite lavoro per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9c058-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="9c058-106">Le considerazioni relative alla pianificazione sono descritte in [pianificare la chiamata tramite lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="9c058-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="9c058-107">Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era presente una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c058-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="9c058-108">In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="9c058-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="9c058-109">Prerequisiti per la chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="9c058-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="9c058-110">La chiamata tramite lavoro utilizza Unified Communications Web API (UCWA), che viene automaticamente installata su tutti i Front End Server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="9c058-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="9c058-111">Per consentire agli utenti di effettuare chiamate tramite lavoro, è necessario disporre anche dei prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c058-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="9c058-112">È necessario disporre di un Mediation Server distribuito, come parte di un front end server o come ruolo autonomo.</span><span class="sxs-lookup"><span data-stu-id="9c058-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="9c058-113">È inoltre necessario distribuire un gateway IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="9c058-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="9c058-114">Tutti gli utenti abilitati per la chiamata tramite lavoro devono disporre di una composizione diretta verso l'interno (DID) nel sistema telefonico PBX.</span><span class="sxs-lookup"><span data-stu-id="9c058-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="9c058-115">È necessario abilitare tutte le chiamate tramite gli utenti di lavoro per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9c058-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="9c058-116">Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for business per ogni utente con il relativo numero di telefono per il sistema telefonico PBX corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9c058-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="9c058-117">Tutti gli utenti che utilizzeranno la chiamata tramite lavoro devono disporre di una **configurazione automatica** selezionata nell'opzione **connessioni avanzate** nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="9c058-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="9c058-118">Ciò consente al client di individuare gli URL di UCWA.</span><span class="sxs-lookup"><span data-stu-id="9c058-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="9c058-119">La **configurazione automatica** è la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9c058-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="9c058-120">Per ogni chiamata tramite l'utente di lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="9c058-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="9c058-121">Per ogni chiamata tramite l'utente di lavoro, assicurarsi che le conferenze telefoniche con accesso esterno e la connessione remota siano abilitate.</span><span class="sxs-lookup"><span data-stu-id="9c058-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="9c058-122">Questo consente agli utenti di accedere e uscire dalle conferenze di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="9c058-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="9c058-123">Verificare che la delega, la chiamata del team e il Response Group siano disabilitati per ogni chiamata tramite l'utente di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9c058-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="9c058-124">Distribuire la funzionalità Chiamata tramite ufficio</span><span class="sxs-lookup"><span data-stu-id="9c058-124">Deploy Call Via Work</span></span>

<span data-ttu-id="9c058-125">Dopo aver posizionato i prerequisiti, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c058-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="9c058-126">Creare un numero di telefono globale per la distribuzione che Skype for business Visualizza sull'ID chiamante del PBX degli utenti che effettuano chiamate tramite le chiamate di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9c058-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="9c058-127">Creare una o più chiamate tramite criteri di lavoro</span><span class="sxs-lookup"><span data-stu-id="9c058-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="9c058-128">Assegnare una chiamata tramite criteri di lavoro a ciascun utente che verrà abilitato per la chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="9c058-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="9c058-129">Creare la chiamata tramite il numero di telefono globale del lavoro</span><span class="sxs-lookup"><span data-stu-id="9c058-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="9c058-130">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="9c058-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="9c058-131">Ad esempio, il cmdlet seguente consente di impostare il numero di telefono globale su 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="9c058-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="9c058-132">Creare una chiamata tramite criteri di lavoro</span><span class="sxs-lookup"><span data-stu-id="9c058-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="9c058-133">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="9c058-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="9c058-134">Ad esempio, il cmdlet seguente crea una chiamata tramite il criterio di lavoro denominato ContosoUser1CvWP, richiede all'utente di utilizzare un numero di callback di amministratore e imposta tale numero su 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="9c058-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="9c058-135">Assegnare una chiamata tramite criteri di lavoro a un utente</span><span class="sxs-lookup"><span data-stu-id="9c058-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="9c058-136">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="9c058-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="9c058-137">Ad esempio, il cmdlet seguente consente di assegnare la chiamata tramite il criterio di lavoro "ContosoUser1CvWP" all'utente denominato **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="9c058-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="9c058-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c058-138">See also</span></span>

[<span data-ttu-id="9c058-139">Pianificare la chiamata tramite il lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9c058-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

