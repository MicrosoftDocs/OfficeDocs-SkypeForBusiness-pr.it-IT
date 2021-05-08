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
description: Skype for Business Online consente di creare altri criteri di accesso esterno. A differenza dei criteri client o di conferenza, in cui è possibile avere più combinazioni, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240145"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="2fcd4-104">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="2fcd4-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="2fcd4-105">Skype for Business Online consente di creare altri criteri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="2fcd4-106">A differenza dei criteri client o di conferenza, in cui è possibile avere più combinazioni, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="2fcd4-107">Di seguito sono seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-107">These are:</span></span>
  
- <span data-ttu-id="2fcd4-108">Nessun accesso federato o Skype consumer (_Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="2fcd4-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="2fcd4-109">Solo accesso federato (_Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="2fcd4-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="2fcd4-110">Accesso federato e consumer (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="2fcd4-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="2fcd4-111">I criteri esterni personalizzati consentono di creare altri criteri non coperti dalle impostazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="2fcd4-112">Quando il criterio è stato creato, è necessario impostare tutti i parametri obbligatori e non è possibile modificarli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="2fcd4-113">La creazione di nuovi criteri personalizzati consente di controllare funzionalità come l'accesso degli utenti Skype utenti o un criterio per disabilitare l'audio/video nel cloud pubblico, che non è stato coperto da impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="2fcd4-114">I criteri di accesso esterno personalizzati seguono la stessa sintassi dei criteri client, dispositivi mobili e conferenza.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="2fcd4-115">Per altre informazioni su queste impostazioni, [fare clic qui.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2fcd4-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="2fcd4-116">Per eseguire questa operazione, l'utente deve usare una versione supportata dell'app A Skype for Business 2016 che la supporta.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="2fcd4-117">È necessaria la versione minima di Skype for Business 2016 A scelta del client:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="2fcd4-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2fcd4-118">**Type**</span></span>|<span data-ttu-id="2fcd4-119">**Data di rilascio**</span><span class="sxs-lookup"><span data-stu-id="2fcd4-119">**Release date**</span></span>|<span data-ttu-id="2fcd4-120">**Versione**</span><span class="sxs-lookup"><span data-stu-id="2fcd4-120">**Version**</span></span>|<span data-ttu-id="2fcd4-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="2fcd4-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2fcd4-122">First Release per Current Channel</span><span class="sxs-lookup"><span data-stu-id="2fcd4-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="2fcd4-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="2fcd4-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="2fcd4-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="2fcd4-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="2fcd4-125">Versione 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="2fcd4-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="2fcd4-126">Canale corrente</span><span class="sxs-lookup"><span data-stu-id="2fcd4-126">Current Channel</span></span>  <br/> |<span data-ttu-id="2fcd4-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="2fcd4-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="2fcd4-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="2fcd4-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="2fcd4-129">Versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="2fcd4-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="2fcd4-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="2fcd4-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="2fcd4-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="2fcd4-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="2fcd4-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="2fcd4-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="2fcd4-133">Versione 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="2fcd4-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="2fcd4-134">Gli utenti che usano versioni precedenti di app Skype for Business Windows o client Mac saranno comunque in grado di trasferire i file.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="2fcd4-135">Avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fcd4-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="2fcd4-136">Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="2fcd4-137">Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="2fcd4-138">Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="2fcd4-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="2fcd4-139">Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="2fcd4-140">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="2fcd4-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="2fcd4-141">Creare criteri di accesso esterno personalizzati per un utente</span><span class="sxs-lookup"><span data-stu-id="2fcd4-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="2fcd4-142">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2fcd4-143">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2fcd4-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="2fcd4-144">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2fcd4-145">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="2fcd4-146">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2fcd4-147">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2fcd4-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="2fcd4-148">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2fcd4-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="2fcd4-149">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2fcd4-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2fcd4-150">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="2fcd4-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="2fcd4-151">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2fcd4-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="2fcd4-152">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2fcd4-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="2fcd4-153">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2fcd4-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="2fcd4-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2fcd4-154">Related topics</span></span>
[<span data-ttu-id="2fcd4-155">Bloccare i trasferimenti di file punto a punto</span><span class="sxs-lookup"><span data-stu-id="2fcd4-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="2fcd4-156">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="2fcd4-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="2fcd4-157">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2fcd4-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
