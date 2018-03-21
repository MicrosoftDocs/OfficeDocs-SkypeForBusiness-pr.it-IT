---
title: Assegnare Microsoft come provider di servizi di conferenza audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: 0193743f9dd2ed6486d93d55c881f3e582e4eb04
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="6c73c-104">Assegnare Microsoft come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="6c73c-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="6c73c-105">Un provider di servizi di conferenza audio fornisce di *ponte conferenza*.</span><span class="sxs-lookup"><span data-stu-id="6c73c-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="6c73c-106">Bridge conferenza include i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni creati.</span><span class="sxs-lookup"><span data-stu-id="6c73c-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="6c73c-107">È sufficiente assegnare un provider di servizi di conferenza audio a coloro che desidera programmare o lead Skype per le riunioni aziendali o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c73c-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="6c73c-108">Se si desidera essere in grado di vedere **che Microsoft** elencati come provider di audio, è necessario assegnare una licenza di **Audioconferenza** all'utente.</span><span class="sxs-lookup"><span data-stu-id="6c73c-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c73c-109">Se si assegna una licenza di **Audioconferenze con accesso esterno** a una persona che non dispone di un provider di servizi di conferenza audio di terze parti, Microsoft viene assegnato automaticamente come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="6c73c-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="6c73c-110">È possibile [assegnare una terza parte come provider di servizi di conferenza audio](assign-a-third-party-as-the-audio-conferencing-provider.md) , se necessario.</span><span class="sxs-lookup"><span data-stu-id="6c73c-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="6c73c-111">Assegnare Microsoft come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="6c73c-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="6c73c-112">Utilizzo dell'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6c73c-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="6c73c-113">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6c73c-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c73c-114">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="6c73c-114">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="6c73c-115">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="6c73c-115">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="6c73c-116">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="6c73c-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="6c73c-117">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="6c73c-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="6c73c-118">Nella pagina proprietà dell'utente, sotto il **nome del Provider**, selezionare **Microsoft** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c73c-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c73c-119">Poiché si utilizza Microsoft come provider di servizi di conferenza audio e sono disponibili più numeri di telefono, è possibile utilizzare l'elenco a discesa **numero a pagamento predefinito** per selezionare un numero di audio predefinita per l'utente.</span><span class="sxs-lookup"><span data-stu-id="6c73c-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="6c73c-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6c73c-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="6c73c-121">Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti</span><span class="sxs-lookup"><span data-stu-id="6c73c-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="6c73c-122">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="6c73c-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="6c73c-123">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="6c73c-123">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="6c73c-124">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="6c73c-124">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="6c73c-125">Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="6c73c-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="6c73c-126">Per modificare il provider a Microsoft per un numero limitato di utenti, è possibile utilizzare [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span><span class="sxs-lookup"><span data-stu-id="6c73c-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="6c73c-127">**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c73c-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="6c73c-128">**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c73c-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="6c73c-129">Utilizzo di uno script Windows PowerShell per un grande numero di utenti</span><span class="sxs-lookup"><span data-stu-id="6c73c-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="6c73c-130">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="6c73c-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="6c73c-131">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="6c73c-131">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="6c73c-132">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="6c73c-132">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="6c73c-133">Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="6c73c-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="6c73c-134">**Nell'esempio 1:** In questo esempio, è possibile utilizzare questo script per modificare il provider di servizi di conferenza audio da Intercall (o un altro provider) a **Microsoft** per un grande numero utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6c73c-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="6c73c-135">Ecco lo script:</span><span class="sxs-lookup"><span data-stu-id="6c73c-135">Here is the script:</span></span>

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="6c73c-136">Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="6c73c-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="6c73c-137">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="6c73c-137">What else should I know?</span></span>

- <span data-ttu-id="6c73c-138">Un utente può essere assegnato un solo provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="6c73c-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="6c73c-139">È possibile modificare il provider di servizi di conferenza audio da Microsoft a un provider di terze parti in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="6c73c-139">You can change the audio conferencing provider from Microsoft to a third-party provider at any time.</span></span> <span data-ttu-id="6c73c-140">Per ulteriori informazioni, consulta [Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="6c73c-140">To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="6c73c-141">All'interno dell'organizzazione, è possibile avere alcune persone che utilizzano Microsoft come i provider di servizi di conferenza audio gli utenti che utilizzano un provider di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6c73c-141">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="6c73c-142">In questo caso, tuttavia, la configurazione e la gestione delle conferenze telefoniche con accesso esterno è più complessa.</span><span class="sxs-lookup"><span data-stu-id="6c73c-142">But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6c73c-143">See also</span><span class="sxs-lookup"><span data-stu-id="6c73c-143">Related topics</span></span>

[<span data-ttu-id="6c73c-144">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c73c-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="6c73c-145">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6c73c-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

