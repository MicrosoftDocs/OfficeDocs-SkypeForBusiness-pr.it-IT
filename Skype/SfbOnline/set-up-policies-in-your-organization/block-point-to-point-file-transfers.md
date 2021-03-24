---
title: Bloccare i trasferimenti di file “punto a punto”
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: In Skype for Business online è possibile controllare i trasferimenti di file P2P (Point-to-Point) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, consente o blocca i trasferimenti di file per gli utenti, indipendentemente dal fatto che trasferiscono o meno file a un utente all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo la procedura seguente, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100622"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="f09a3-105">Bloccare i trasferimenti di file “punto a punto”</span><span class="sxs-lookup"><span data-stu-id="f09a3-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="f09a3-106">In Skype for Business online è possibile controllare i trasferimenti di file P2P (Point-to-Point) come parte delle impostazioni dei criteri di conferenza esistenti.</span><span class="sxs-lookup"><span data-stu-id="f09a3-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="f09a3-107">Tuttavia, consente o blocca i trasferimenti di file per gli utenti, indipendentemente dal fatto che trasferiscono o meno file a un utente all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f09a3-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="f09a3-108">Seguendo la procedura seguente, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.</span><span class="sxs-lookup"><span data-stu-id="f09a3-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="f09a3-109">Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P ma bloccare il trasferimento di file con partner federati.</span><span class="sxs-lookup"><span data-stu-id="f09a3-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="f09a3-110">Per questo scenario, è necessario eseguire le seguenti operazione:</span><span class="sxs-lookup"><span data-stu-id="f09a3-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="f09a3-111">Assegnare un criterio di conferenza con il trasferimento di file P2P abilitato (_EnableP2PFileTransfer_ impostato su _True_) agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f09a3-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="f09a3-112">Creare un criterio di comunicazione utente esterno globale impostato per bloccare i trasferimenti di file P2P esterni (_EnableP2PFileTransfer_ impostato su _False_) e assegnarlo a un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f09a3-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="f09a3-113">Per altre informazioni su queste impostazioni, [fare clic qui.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f09a3-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="f09a3-114">Se un utente federato esterno all'organizzazione prova a inviare un file a un utente a cui è stato applicato il criterio, riceverà un **errore Trasferimento non** riuscito.</span><span class="sxs-lookup"><span data-stu-id="f09a3-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="f09a3-115">Inoltre, se un utente prova a inviare un file, riceverà un **messaggio di errore Trasferimento file disattivato.**</span><span class="sxs-lookup"><span data-stu-id="f09a3-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="f09a3-116">Per farlo funzionare, l'utente deve usare una versione supportata di un'app Skype for Business 2016 a scelta che la supporta.</span><span class="sxs-lookup"><span data-stu-id="f09a3-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="f09a3-117">È necessaria la versione minima seguente del client Skype for Business 2016 A scelta:</span><span class="sxs-lookup"><span data-stu-id="f09a3-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="f09a3-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f09a3-118">**Type**</span></span>|<span data-ttu-id="f09a3-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="f09a3-119">**Release date**</span></span>|<span data-ttu-id="f09a3-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="f09a3-120">**Version**</span></span>|<span data-ttu-id="f09a3-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="f09a3-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f09a3-122">First Release per Current Channel</span><span class="sxs-lookup"><span data-stu-id="f09a3-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="f09a3-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="f09a3-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="f09a3-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="f09a3-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="f09a3-125">Versione 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="f09a3-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="f09a3-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="f09a3-126">Current Channel</span></span>  <br/> |<span data-ttu-id="f09a3-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="f09a3-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="f09a3-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="f09a3-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="f09a3-129">Versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="f09a3-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="f09a3-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="f09a3-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="f09a3-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="f09a3-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="f09a3-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="f09a3-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="f09a3-133">Versione 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="f09a3-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="f09a3-134">Gli utenti che usano versioni precedenti delle app Skype for Business per Windows o i client Mac saranno comunque in grado di trasferire i file.</span><span class="sxs-lookup"><span data-stu-id="f09a3-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="f09a3-135">Avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f09a3-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="f09a3-136">Skype for Business Online Connector fa attualmente parte dell'ultimo modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="f09a3-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f09a3-137">Se si usa l'ultima versione pubblica di Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="f09a3-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="f09a3-138">Installare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="f09a3-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="f09a3-139">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f09a3-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="f09a3-140">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi [di Microsoft 365 o Office 365 in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) un'unica finestra di Windows PowerShell o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="f09a3-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="f09a3-141">Disabilitare i trasferimenti di file P2P per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f09a3-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="f09a3-142">Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitato nei criteri globali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f09a3-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="f09a3-143">Al momento della creazione, agli utenti è stato assegnato il _criterio BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="f09a3-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="f09a3-144">Per consentire i trasferimenti P2P all'interno dell'organizzazione, ma bloccare i trasferimenti di file esterni a un'altra organizzazione, è sufficiente modificarlo a livello globale.</span><span class="sxs-lookup"><span data-stu-id="f09a3-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="f09a3-145">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="f09a3-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="f09a3-146">Disabilitare i trasferimenti di file P2P per un utente</span><span class="sxs-lookup"><span data-stu-id="f09a3-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="f09a3-147">È possibile applicarlo a un utente creando un nuovo criterio e concedendo il criterio a tale utente.</span><span class="sxs-lookup"><span data-stu-id="f09a3-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="f09a3-148">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="f09a3-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f09a3-149">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f09a3-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f09a3-150">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="f09a3-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f09a3-151">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f09a3-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f09a3-152">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="f09a3-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f09a3-153">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f09a3-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="f09a3-154">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f09a3-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="f09a3-155">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f09a3-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f09a3-156">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f09a3-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="f09a3-157">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f09a3-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="f09a3-158">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f09a3-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="f09a3-159">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f09a3-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="f09a3-160">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f09a3-160">Related topics</span></span>
[<span data-ttu-id="f09a3-161">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="f09a3-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f09a3-162">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="f09a3-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="f09a3-163">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f09a3-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
