---
title: Creare criteri di accesso esterno personalizzato
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype for business online consente di creare altri criteri di accesso esterno. A differenza dei criteri per i client o i servizi di conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti in grado di coprire la maggior parte degli scenari.
ms.openlocfilehash: 02fba48a6b8acf2a2b66078624ab36eb7453df0c
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164645"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="a417c-104">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="a417c-104">Create custom external access policies</span></span>

<span data-ttu-id="a417c-105">Skype for business online consente di creare altri criteri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a417c-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="a417c-106">A differenza dei criteri per i client o i servizi di conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti in grado di coprire la maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="a417c-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="a417c-107">Questi sono:</span><span class="sxs-lookup"><span data-stu-id="a417c-107">These are:</span></span>
  
- <span data-ttu-id="a417c-108">Nessun accesso dei consumatori federati o Skype (_Tag: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="a417c-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="a417c-109">Solo accesso federativo (_Tag: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="a417c-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="a417c-110">Accesso federativo e consumer (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="a417c-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="a417c-111">I criteri esterni personalizzati consentono di creare altre forze di polizia che non sono coperte dalle impostazioni descritte sopra.</span><span class="sxs-lookup"><span data-stu-id="a417c-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="a417c-112">Quando il criterio è stato creato, è necessario impostare tutti i parametri obbligatori e non è possibile modificarli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a417c-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="a417c-113">La creazione di nuovi criteri personalizzati consente di controllare funzionalità come l'accesso dei consumatori Skype o un criterio per disabilitare l'audio/video del cloud pubblico, un aspetto che non è stato incluso nelle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="a417c-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="a417c-114">I criteri di accesso esterno personalizzati seguono la stessa sintassi dei criteri client, mobilità e conferenza.</span><span class="sxs-lookup"><span data-stu-id="a417c-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="a417c-115">Per altre informazioni su queste impostazioni, vedere [qui](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="a417c-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="a417c-116">Per fare questo lavoro, l'utente deve usare una versione supportata di 2016 a portata di clic di Skype for business app che lo supporta.</span><span class="sxs-lookup"><span data-stu-id="a417c-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="a417c-117">È necessaria la versione minima seguente di Skype for business 2016 a portata di clic:</span><span class="sxs-lookup"><span data-stu-id="a417c-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="a417c-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a417c-118">**Type**</span></span>|<span data-ttu-id="a417c-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="a417c-119">**Release date**</span></span>|<span data-ttu-id="a417c-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="a417c-120">**Version**</span></span>|<span data-ttu-id="a417c-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="a417c-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a417c-122">First Release per il canale corrente</span><span class="sxs-lookup"><span data-stu-id="a417c-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="a417c-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="a417c-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="a417c-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="a417c-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="a417c-125">Versione 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="a417c-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="a417c-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="a417c-126">Current Channel</span></span>  <br/> |<span data-ttu-id="a417c-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="a417c-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="a417c-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="a417c-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="a417c-129">Versione 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="a417c-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="a417c-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="a417c-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="a417c-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="a417c-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="a417c-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="a417c-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="a417c-133">Versione 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="a417c-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="a417c-134">Gli utenti che usano versioni precedenti di Skype for business per le app di Windows o i client Mac saranno comunque in grado di trasferire file.</span><span class="sxs-lookup"><span data-stu-id="a417c-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="a417c-135">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a417c-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="a417c-136">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="a417c-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="a417c-137">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a417c-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a417c-138">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a417c-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="a417c-139">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a417c-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="a417c-140">Vedere [Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="a417c-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="a417c-141">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="a417c-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="a417c-p106">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="a417c-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="a417c-145">Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="a417c-145">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="a417c-146">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a417c-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="a417c-147">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a417c-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a417c-148">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="a417c-148">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a417c-149">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="a417c-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="a417c-150">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a417c-150">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="a417c-151">Creare un criterio di accesso esterno personalizzato per un utente</span><span class="sxs-lookup"><span data-stu-id="a417c-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="a417c-152">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a417c-152">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a417c-153">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a417c-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="a417c-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="a417c-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a417c-155">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="a417c-155">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a417c-156">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="a417c-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a417c-157">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a417c-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a417c-158">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a417c-158">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a417c-159">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a417c-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a417c-160">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="a417c-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a417c-161">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a417c-161">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a417c-162">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="a417c-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a417c-163">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="a417c-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a417c-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a417c-164">Related topics</span></span>
[<span data-ttu-id="a417c-165">Bloccare i trasferimenti di file Point-to-Point</span><span class="sxs-lookup"><span data-stu-id="a417c-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="a417c-166">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="a417c-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="a417c-167">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a417c-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
