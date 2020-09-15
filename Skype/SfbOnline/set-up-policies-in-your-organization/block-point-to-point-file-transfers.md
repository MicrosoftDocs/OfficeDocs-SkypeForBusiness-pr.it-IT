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
description: In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814635"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="1d33d-105">Bloccare i trasferimenti di file “punto a punto”</span><span class="sxs-lookup"><span data-stu-id="1d33d-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="1d33d-106">In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti.</span><span class="sxs-lookup"><span data-stu-id="1d33d-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="1d33d-107">Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d33d-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="1d33d-108">Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.</span><span class="sxs-lookup"><span data-stu-id="1d33d-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="1d33d-109">Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P, ma bloccare il trasferimento di file con partner federati.</span><span class="sxs-lookup"><span data-stu-id="1d33d-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="1d33d-110">Per questo scenario, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d33d-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="1d33d-111">Assegnare un criterio di conferenza con il trasferimento di file P2P abilitato (_EnableP2PFileTransfer_ impostato su _true_) agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d33d-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="1d33d-112">Creare un criterio di comunicazione utente esterno globale impostato per bloccare i trasferimenti di file P2P esterni (_EnableP2PFileTransfer_ impostato su _false_) e assegnarlo a un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d33d-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="1d33d-113">Per altre informazioni su queste impostazioni, vedere [qui](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d33d-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="1d33d-114">Se un utente federato all'esterno dell'organizzazione prova a inviare un file a un utente in cui è stato applicato il criterio, riceverà un errore di **trasferimento non riuscito** .</span><span class="sxs-lookup"><span data-stu-id="1d33d-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="1d33d-115">E se un utente tenta di inviare un file, riceverà un **trasferimento di file disattivato** .</span><span class="sxs-lookup"><span data-stu-id="1d33d-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="1d33d-116">Per ottenere questo lavoro, l'utente deve usare una versione supportata di un'app Skype for business a portata di clic di 2016 che la supporta.</span><span class="sxs-lookup"><span data-stu-id="1d33d-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="1d33d-117">È necessaria la versione minima seguente di Skype for business 2016 a portata di clic:</span><span class="sxs-lookup"><span data-stu-id="1d33d-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="1d33d-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1d33d-118">**Type**</span></span>|<span data-ttu-id="1d33d-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="1d33d-119">**Release date**</span></span>|<span data-ttu-id="1d33d-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="1d33d-120">**Version**</span></span>|<span data-ttu-id="1d33d-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="1d33d-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d33d-122">First Release per il canale corrente</span><span class="sxs-lookup"><span data-stu-id="1d33d-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="1d33d-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="1d33d-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="1d33d-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="1d33d-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="1d33d-125">Versione 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="1d33d-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="1d33d-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="1d33d-126">Current Channel</span></span>  <br/> |<span data-ttu-id="1d33d-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="1d33d-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="1d33d-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="1d33d-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="1d33d-129">Versione 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="1d33d-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="1d33d-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="1d33d-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="1d33d-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="1d33d-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="1d33d-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="1d33d-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="1d33d-133">Versione 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="1d33d-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="1d33d-134">Gli utenti che usano versioni precedenti di Skype for business per le app di Windows o i client Mac saranno comunque in grado di trasferire file.</span><span class="sxs-lookup"><span data-stu-id="1d33d-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="1d33d-135">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d33d-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="1d33d-136">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="1d33d-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="1d33d-137">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d33d-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="1d33d-138">Controlla la versione digitando _Get-host_ nella finestra di **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="1d33d-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="1d33d-139">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d33d-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="1d33d-140">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="1d33d-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="1d33d-141">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="1d33d-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="1d33d-142">Sarà inoltre necessario installare il modulo di Windows PowerShell per Teams che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1d33d-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="1d33d-143">Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d33d-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="1d33d-144">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1d33d-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="1d33d-145">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d33d-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="1d33d-146">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1d33d-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="1d33d-147">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="1d33d-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="1d33d-148">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1d33d-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="1d33d-149">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1d33d-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="1d33d-150">Disabilitare i trasferimenti di file P2P per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1d33d-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="1d33d-151">Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitato nel criterio globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d33d-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="1d33d-152">Al momento della creazione, agli utenti è stato assegnato il criterio _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="1d33d-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="1d33d-153">Per consentire i trasferimenti P2P per l'interno dell'organizzazione, ma bloccare i trasferimenti di file esterni a un'altra organizzazione, è sufficiente modificarla a livello globale.</span><span class="sxs-lookup"><span data-stu-id="1d33d-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="1d33d-154">Per farlo, Esegui:</span><span class="sxs-lookup"><span data-stu-id="1d33d-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="1d33d-155">Disabilitare i trasferimenti di file P2P per un utente</span><span class="sxs-lookup"><span data-stu-id="1d33d-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="1d33d-156">Puoi applicarlo a un utente creando un nuovo criterio e conferendolo a tale utente.</span><span class="sxs-lookup"><span data-stu-id="1d33d-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="1d33d-157">Per farlo, Esegui:</span><span class="sxs-lookup"><span data-stu-id="1d33d-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1d33d-158">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d33d-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1d33d-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="1d33d-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1d33d-160">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="1d33d-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1d33d-161">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="1d33d-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1d33d-162">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1d33d-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1d33d-163">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d33d-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1d33d-164">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1d33d-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1d33d-165">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="1d33d-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1d33d-166">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d33d-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1d33d-167">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1d33d-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1d33d-168">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1d33d-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1d33d-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1d33d-169">Related topics</span></span>
[<span data-ttu-id="1d33d-170">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="1d33d-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="1d33d-171">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="1d33d-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="1d33d-172">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1d33d-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
