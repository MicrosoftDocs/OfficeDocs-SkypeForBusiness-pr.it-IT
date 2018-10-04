---
title: Bloccare i trasferimenti di file “punto a punto”
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: In Skype Business online, è necessario possibilità di controllare i trasferimenti di file da punto a punto (P2P) come parte di impostazioni di criteri di conferenza esistente. Tuttavia, in questo modo o blocchi file trasferimenti per gli utenti sono o meno sono trasferimento di file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguire la procedura riportata di seguito, è possibile bloccare i trasferimenti di file P2P con organizzazioni federate o partner.
ms.openlocfilehash: 6ca79b45c4e068ae6999db24cf6a0dd54e9e3aa6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372104"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="c4267-105">Bloccare i trasferimenti di file “punto a punto”</span><span class="sxs-lookup"><span data-stu-id="c4267-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="c4267-106">In Skype Business online, è necessario possibilità di controllare i trasferimenti di file da punto a punto (P2P) come parte di impostazioni di criteri di conferenza esistente.</span><span class="sxs-lookup"><span data-stu-id="c4267-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="c4267-107">Tuttavia, in questo modo o blocchi file trasferimenti per gli utenti sono o meno sono trasferimento di file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4267-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="c4267-108">Seguire la procedura riportata di seguito, è possibile bloccare i trasferimenti di file P2P con organizzazioni federate o partner.</span><span class="sxs-lookup"><span data-stu-id="c4267-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="c4267-109">Una situazione molto comune è quando si desidera consentire agli utenti interni per il trasferimento di file utilizzare P2P ma trasferimento di file bloccati con i partner federati.</span><span class="sxs-lookup"><span data-stu-id="c4267-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="c4267-110">Per questo scenario, è necessario eseguire:</span><span class="sxs-lookup"><span data-stu-id="c4267-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="c4267-111">Assegnare un criterio di conferenza con P2P trasferimento di file abilitato (_EnableP2PFileTransfer_ impostata su _True_) per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4267-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="c4267-112">Creare un criterio di comunicazione globale degli utenti esterni impostato per bloccare i trasferimenti di file esterni P2P (_EnableP2PFileTransfer_ impostato su _False_) e assegnarlo a un utente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4267-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="c4267-113">È possibile trovare ulteriori informazioni su queste impostazioni [di seguito](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="c4267-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="c4267-114">Se un utente federato all'esterno dell'organizzazione tenta di inviare un file a un utente di cui è stato applicato il criterio, ricevono un errore di **Trasferimento ha avuto esito negativo** .</span><span class="sxs-lookup"><span data-stu-id="c4267-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="c4267-115">E se un utente tenta di inviare un file, verrà visualizzato un errore di **trasferimento di File è disattivato** .</span><span class="sxs-lookup"><span data-stu-id="c4267-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="c4267-116">Per ottenere questo risultato, l'utente deve utilizzare una versione supportata di un Skype Click-to-Run 2016 per applicazioni aziendali che supporta lo.</span><span class="sxs-lookup"><span data-stu-id="c4267-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="c4267-117">La versione minima seguente di Skype per Business 2016 Click-to-Run client è necessaria:</span><span class="sxs-lookup"><span data-stu-id="c4267-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="c4267-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c4267-118">**Type**</span></span>|<span data-ttu-id="c4267-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="c4267-119">**Release date**</span></span>|<span data-ttu-id="c4267-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="c4267-120">**Version**</span></span>|<span data-ttu-id="c4267-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="c4267-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4267-122">Prima versione per il canale corrente</span><span class="sxs-lookup"><span data-stu-id="c4267-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="c4267-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="c4267-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="c4267-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="c4267-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="c4267-125">Versione 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="c4267-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="c4267-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="c4267-126">Current Channel</span></span>  <br/> |<span data-ttu-id="c4267-127">6/12/2016</span><span class="sxs-lookup"><span data-stu-id="c4267-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="c4267-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="c4267-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="c4267-129">Versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="c4267-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="c4267-130">Canale differito</span><span class="sxs-lookup"><span data-stu-id="c4267-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="c4267-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="c4267-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="c4267-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="c4267-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="c4267-133">Versione 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="c4267-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="c4267-134">Gli utenti che utilizzano le versioni precedenti di Skype per Mac client o app di Windows Business saranno ancora in grado di trasferire file.</span><span class="sxs-lookup"><span data-stu-id="c4267-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="c4267-135">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4267-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="c4267-136">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="c4267-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="c4267-137">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c4267-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c4267-138">Verificare la versione digitando _Get-Host_ nella finestra di **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="c4267-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c4267-p106">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="c4267-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c4267-p107">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="c4267-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="c4267-145">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="c4267-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="c4267-146">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c4267-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="c4267-147">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c4267-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c4267-148">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="c4267-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4267-149">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c4267-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="c4267-150">Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c4267-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="c4267-151">Disattivare i trasferimenti di file P2P per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c4267-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="c4267-152">Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitata sul criterio globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4267-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="c4267-153">Quando è stata creata, gli utenti sono stati assegnati i criteri _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="c4267-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="c4267-154">Per consentire i trasferimenti P2P per interno i trasferimenti di file esterno organizzazione ma blocco a un'altra organizzazione, è necessario modificare a livello globale.</span><span class="sxs-lookup"><span data-stu-id="c4267-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="c4267-155">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c4267-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="c4267-156">Disattivare i trasferimenti di file P2P per un utente</span><span class="sxs-lookup"><span data-stu-id="c4267-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="c4267-157">È possibile applicare a un utente crea un nuovo criterio e concedere a tale utente.</span><span class="sxs-lookup"><span data-stu-id="c4267-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="c4267-158">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c4267-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c4267-159">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4267-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c4267-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="c4267-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c4267-161">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="c4267-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c4267-162">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="c4267-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c4267-163">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4267-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c4267-164">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c4267-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c4267-p112">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4267-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c4267-167">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="c4267-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c4267-168">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4267-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c4267-169">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4267-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c4267-170">See also</span><span class="sxs-lookup"><span data-stu-id="c4267-170">Related topics</span></span>
[<span data-ttu-id="c4267-171">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="c4267-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="c4267-172">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c4267-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="c4267-173">Impostare i criteri relativi alle conferenze nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c4267-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 