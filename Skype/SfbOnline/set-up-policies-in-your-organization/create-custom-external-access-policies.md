---
title: Creare criteri di accesso esterno personalizzato
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype per Business Online consente di creare i criteri di accesso esterno aggiuntivi. A differenza dei criteri client o di conferenza, dove è possibile avere più combinazioni, sono disponibili tre criteri predefiniti l'accesso esterno che possono soddisfare la maggior parte degli scenari.
ms.openlocfilehash: e0af31d015c69ebd91c28a229a20d3d2c6c926c4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850158"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="eb9b8-104">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="eb9b8-104">Create custom external access policies</span></span>

<span data-ttu-id="eb9b8-105">Skype per Business Online consente di creare i criteri di accesso esterno aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="eb9b8-106">A differenza dei criteri client o di conferenza, dove è possibile avere più combinazioni, sono disponibili tre criteri predefiniti l'accesso esterno che possono soddisfare la maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="eb9b8-107">Di seguito sono:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-107">These are:</span></span>
  
- <span data-ttu-id="eb9b8-108">No federato o Access Consumer Skype (_Tag: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="eb9b8-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="eb9b8-109">Accesso federato (_Tag: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="eb9b8-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="eb9b8-110">Federati e Consumer accedere (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="eb9b8-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="eb9b8-111">Criteri personalizzati esterni consentono di creare ulteriori criteri che non sono inclusi le impostazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="eb9b8-112">Quando è stato creato il criterio, potrebbe essere necessario impostare tutti i parametri obbligatori e non modificare in seguito.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="eb9b8-113">Creazione di nuovi criteri personalizzati consentono alle funzionalità di controllo, ad esempio access consumer Skype o un criterio per disabilitare pubblica cloud audio/video, ovvero un'attività non è stato trattati con impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="eb9b8-114">Criteri di accesso esterno personalizzati seguono la stessa sintassi di criteri client, conferenze e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="eb9b8-115">È possibile trovare ulteriori informazioni su queste impostazioni [di seguito](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb9b8-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="eb9b8-116">Per ottenere questo risultato, l'utente deve utilizzando una versione supportata di 2016 Skype a portata di clic per applicazioni aziendali che supporta lo.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="eb9b8-117">La versione minima seguente di Skype per Business 2016 Click-to-Run client è necessaria:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="eb9b8-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-118">**Type**</span></span>|<span data-ttu-id="eb9b8-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-119">**Release date**</span></span>|<span data-ttu-id="eb9b8-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-120">**Version**</span></span>|<span data-ttu-id="eb9b8-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb9b8-122">Prima versione per il canale corrente</span><span class="sxs-lookup"><span data-stu-id="eb9b8-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="eb9b8-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="eb9b8-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="eb9b8-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="eb9b8-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="eb9b8-125">Versione 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="eb9b8-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="eb9b8-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="eb9b8-126">Current Channel</span></span>  <br/> |<span data-ttu-id="eb9b8-127">6/12/2016</span><span class="sxs-lookup"><span data-stu-id="eb9b8-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="eb9b8-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="eb9b8-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="eb9b8-129">Versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="eb9b8-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="eb9b8-130">Canale differito</span><span class="sxs-lookup"><span data-stu-id="eb9b8-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="eb9b8-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="eb9b8-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="eb9b8-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="eb9b8-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="eb9b8-133">Versione 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="eb9b8-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="eb9b8-134">Gli utenti che utilizzano le versioni precedenti di Skype per Mac client o app di Windows Business saranno ancora in grado di trasferire file.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="eb9b8-135">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb9b8-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="eb9b8-136">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="eb9b8-137">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="eb9b8-138">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="eb9b8-p105">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="eb9b8-p106">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="eb9b8-145">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb9b8-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="eb9b8-146">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="eb9b8-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="eb9b8-147">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="eb9b8-148">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb9b8-149">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="eb9b8-150">Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb9b8-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="eb9b8-151">Creare un criterio di accesso esterno personalizzati per un utente</span><span class="sxs-lookup"><span data-stu-id="eb9b8-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="eb9b8-152">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eb9b8-153">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb9b8-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="eb9b8-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eb9b8-155">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="eb9b8-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="eb9b8-156">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb9b8-157">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb9b8-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eb9b8-158">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="eb9b8-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="eb9b8-p108">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb9b8-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="eb9b8-161">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="eb9b8-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="eb9b8-162">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb9b8-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eb9b8-163">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb9b8-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="eb9b8-164">See also</span><span class="sxs-lookup"><span data-stu-id="eb9b8-164">Related topics</span></span>
[<span data-ttu-id="eb9b8-165">Trasferimenti di file bloccati punto-punto</span><span class="sxs-lookup"><span data-stu-id="eb9b8-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="eb9b8-166">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="eb9b8-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="eb9b8-167">Impostare i criteri relativi alle conferenze nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="eb9b8-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 