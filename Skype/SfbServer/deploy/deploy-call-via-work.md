---
title: Distribuire chiamate tramite lavoro in Skype for Business Server
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
description: 'Riepilogo: informazioni su come distribuire Call Via Work in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825006"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="ea880-103">Distribuire chiamate tramite lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ea880-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="ea880-104">**Riepilogo:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span><span class="sxs-lookup"><span data-stu-id="ea880-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="ea880-105">Seguire questa procedura per distribuire La chiamata tramite lavoro per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ea880-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="ea880-106">Considerazioni sulla pianificazione sono descritte in [Plan for Call Via Work in Skype for Business Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)</span><span class="sxs-lookup"><span data-stu-id="ea880-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="ea880-107">Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea880-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ea880-108">In Skype for Business Server, questa funzionalità è stata sostituita con Chiama da lavoro.</span><span class="sxs-lookup"><span data-stu-id="ea880-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="ea880-109">Prerequisiti per la chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="ea880-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="ea880-110">Call Via Work usa Unified Communications Web API (UCWA), che viene installato automaticamente in tutti i Front End Server di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea880-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="ea880-111">Per abilitare gli utenti alla funzionalità Chiama da lavoro, è inoltre necessario disporre dei prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea880-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="ea880-112">È necessario disporre di un Mediation Server distribuito come parte di un Front End Server o come ruolo autonomo.</span><span class="sxs-lookup"><span data-stu-id="ea880-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="ea880-113">È inoltre necessario distribuire un gateway IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ea880-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="ea880-114">Tutti gli utenti che saranno abilitati per La chiamata tramite ufficio devono disporre di un DID (Direct Inward Dialing) nel sistema telefonico PBX.</span><span class="sxs-lookup"><span data-stu-id="ea880-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="ea880-115">È necessario abilitare tutti gli utenti chiamata tramite l'VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ea880-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="ea880-116">Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for Business per ogni utente al numero DID corrispondente per il sistema telefonico PBX corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ea880-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="ea880-117">Tutti gli utenti che usano La  chiamata tramite il lavoro devono avere la configurazione automatica selezionata nell'opzione **Connessioni** avanzate nel client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea880-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="ea880-118">In questo modo il client può individuare gli URL UCWA.</span><span class="sxs-lookup"><span data-stu-id="ea880-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="ea880-119">**Configurazione automatica** è la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ea880-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="ea880-120">Per ogni utente chiamata tramite lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="ea880-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="ea880-121">Per ogni utente chiamata tramite lavoro, verificare che le conferenze telefoniche con accesso esterno e le chiamate in uscita siano abilitate.</span><span class="sxs-lookup"><span data-stu-id="ea880-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="ea880-122">In questo modo questi utenti possono accedere e uscire da conferenze Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea880-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="ea880-123">Assicurarsi che la delega, la chiamata al team e il Response Group siano disabilitati per ogni utente chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="ea880-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="ea880-124">Distribuire la funzionalità Chiamata tramite ufficio</span><span class="sxs-lookup"><span data-stu-id="ea880-124">Deploy Call Via Work</span></span>

<span data-ttu-id="ea880-125">Una volta installati i prerequisiti, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea880-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="ea880-126">Creare un numero di telefono globale per la distribuzione visualizzato da Skype for Business sull'ID chiamante PBX degli utenti che effettuano chiamate Di chiamata tramite ufficio.</span><span class="sxs-lookup"><span data-stu-id="ea880-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="ea880-127">Creare uno o più criteri Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="ea880-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="ea880-128">Assegnare un criterio Chiamata tramite lavoro a ogni utente che sarà abilitato per La chiamata via lavoro</span><span class="sxs-lookup"><span data-stu-id="ea880-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="ea880-129">Creare il numero di telefono globale Chiamata tramite ufficio</span><span class="sxs-lookup"><span data-stu-id="ea880-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="ea880-130">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="ea880-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="ea880-131">Ad esempio, il cmdlet seguente imposta il numero di telefono globale su 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="ea880-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="ea880-132">Creare un criterio Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="ea880-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="ea880-133">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="ea880-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="ea880-134">Ad esempio, il cmdlet seguente crea un criterio Chiamata tramite lavoro denominato ContosoUser1CvWP, richiede all'utente di utilizzare un numero di richiamata amministratore e imposta tale numero di richiamata su 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="ea880-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="ea880-135">Assegnare un criterio Chiamata tramite lavoro a un utente</span><span class="sxs-lookup"><span data-stu-id="ea880-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="ea880-136">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="ea880-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="ea880-137">Ad esempio, il cmdlet seguente assegna il criterio Chiamata tramite lavoro "ContosoUser1CvWP" all'utente **denominato ContosoUser1.**</span><span class="sxs-lookup"><span data-stu-id="ea880-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="ea880-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea880-138">See also</span></span>

[<span data-ttu-id="ea880-139">Pianificare la chiamata tramite lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ea880-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

