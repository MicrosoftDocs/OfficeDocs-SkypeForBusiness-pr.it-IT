---
title: Distribuire una chiamata tramite il lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791084"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="d4d35-103">Distribuire una chiamata tramite il lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d4d35-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="d4d35-104">**Riepilogo:** Informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d4d35-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="d4d35-105">Seguire questi passaggi per distribuire la chiamata tramite lavoro per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d4d35-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="d4d35-106">Le considerazioni sulla pianificazione sono discusse in [piano per la chiamata tramite lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="d4d35-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="d4d35-107">Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4d35-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="d4d35-108">In Skype for Business Server questa funzionalità è stata sostituita da chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4d35-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="d4d35-109">Prerequisiti per la chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="d4d35-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="d4d35-110">Chiamata tramite lavoro usa Unified Communications Web API (UCWA), che viene automaticamente installata in tutti i server front-end di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d4d35-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="d4d35-111">Per consentire agli utenti di effettuare chiamate tramite lavoro, è necessario disporre anche dei prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4d35-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="d4d35-112">È necessario disporre di un Mediation Server distribuito, sia come parte di un front end server che come ruolo autonomo.</span><span class="sxs-lookup"><span data-stu-id="d4d35-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="d4d35-113">Devi anche distribuire un gateway IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d4d35-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="d4d35-114">Tutti gli utenti che verranno abilitati per la chiamata tramite lavoro devono avere un accesso diretto (DID) nel sistema telefonico PBX.</span><span class="sxs-lookup"><span data-stu-id="d4d35-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="d4d35-115">È necessario abilitare tutte le chiamate tramite gli utenti del lavoro per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d4d35-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="d4d35-116">Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for business per ogni utente al numero DID corrispondente per il sistema telefonico PBX corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d4d35-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="d4d35-117">Tutti gli utenti che useranno la chiamata tramite lavoro devono avere la **configurazione automatica** selezionata nell'opzione **connessioni avanzate** nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d4d35-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="d4d35-118">Questo consente al client di individuare gli URL di UCWA.</span><span class="sxs-lookup"><span data-stu-id="d4d35-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="d4d35-119">La **configurazione automatica** è la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d4d35-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="d4d35-120">Per ogni chiamata tramite l'utente del lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="d4d35-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="d4d35-121">Per ogni chiamata tramite l'utente del lavoro, assicurati che i servizi di conferenza telefonica con accesso esterno siano abilitati.</span><span class="sxs-lookup"><span data-stu-id="d4d35-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="d4d35-122">Questo consente agli utenti di accedere e disconnettersi dalle conferenze di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d4d35-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="d4d35-123">Assicurarsi che la delega, la chiamata del team e il gruppo di risposte siano disabilitati per ogni chiamata tramite l'utente del lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4d35-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="d4d35-124">Distribuire la funzionalità Chiamata tramite ufficio</span><span class="sxs-lookup"><span data-stu-id="d4d35-124">Deploy Call Via Work</span></span>

<span data-ttu-id="d4d35-125">Dopo aver effettuato i prerequisiti, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4d35-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="d4d35-126">Creare un numero di telefono globale per la distribuzione visualizzata da Skype for business nell'ID chiamante PBX degli utenti che effettuano una chiamata tramite chiamate aziendali.</span><span class="sxs-lookup"><span data-stu-id="d4d35-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="d4d35-127">Creare una o più chiamate tramite i criteri di lavoro</span><span class="sxs-lookup"><span data-stu-id="d4d35-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="d4d35-128">Assegnare una chiamata tramite i criteri di lavoro a ogni utente che verrà abilitato per la chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="d4d35-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="d4d35-129">Creare la chiamata tramite numero di telefono globale dell'ufficio</span><span class="sxs-lookup"><span data-stu-id="d4d35-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="d4d35-130">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="d4d35-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="d4d35-131">Ad esempio, il cmdlet seguente imposta il numero di telefono globale su 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="d4d35-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="d4d35-132">Creare una chiamata tramite i criteri di lavoro</span><span class="sxs-lookup"><span data-stu-id="d4d35-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="d4d35-133">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="d4d35-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="d4d35-134">Ad esempio, il cmdlet seguente crea una chiamata tramite il criterio di lavoro denominato ContosoUser1CvWP, richiede all'utente di usare un numero di callback di amministratore e imposta il numero di callback su 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="d4d35-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="d4d35-135">Assegnare una chiamata tramite criteri di lavoro a un utente</span><span class="sxs-lookup"><span data-stu-id="d4d35-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="d4d35-136">Digitare il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="d4d35-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="d4d35-137">Ad esempio, il cmdlet seguente assegna la chiamata tramite il criterio di lavoro "ContosoUser1CvWP" all'utente denominato **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="d4d35-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="d4d35-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4d35-138">See also</span></span>

[<span data-ttu-id="d4d35-139">Pianificare la chiamata tramite il lavoro in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d4d35-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

