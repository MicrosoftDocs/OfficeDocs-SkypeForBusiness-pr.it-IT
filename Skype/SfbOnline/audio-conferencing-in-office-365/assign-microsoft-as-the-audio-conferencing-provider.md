---
title: Assegnare Microsoft come provider di servizi di conferenza audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
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
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e68c5-104">Assegnare Microsoft come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="e68c5-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="e68c5-105">Per l'utilizzo di servizi di conferenza Audio in Office 365 con Skype per le aziende e Teams Microsoft, è necessario disporre di una licenza di audioconferenza assegnata a loro gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68c5-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="e68c5-106">Per ulteriori informazioni sulla gestione delle licenze e sul costo, vedere [prova o acquisto audioconferenza in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="e68c5-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="e68c5-107">Audioconferenze Microsoft fornisce i numeri di telefono di accesso esterno, pin e conferenza ID che può essere utilizzato per i partecipanti alla riunione per partecipare alle riunioni della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68c5-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="e68c5-108">È sufficiente assegnare agli utenti che desiderano programmare o lead Skype per le riunioni aziendali o Microsoft Teams Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="e68c5-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="e68c5-109">Se una licenza di **Audioconferenza Microsoft** viene assegnata a un utente che non dispone di un provider, provider dell'utente viene automaticamente impostato su **Microsoft** e non è necessario eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="e68c5-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="e68c5-110">Se l'utente dispone già di un provider di servizi di conferenza audio, è necessario modificare provider dell'utente a Microsoft dopo l'assegnazione di una licenza di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e68c5-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="e68c5-111">Se si desidera essere in grado di vedere che Microsoft elencati come provider di servizi di conferenza audio, è necessario assegnare una licenza di audioconferenza all'utente.</span><span class="sxs-lookup"><span data-stu-id="e68c5-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e68c5-112">Assegnare Microsoft come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="e68c5-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="e68c5-113">Utilizzo dell'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e68c5-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="e68c5-114">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e68c5-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e68c5-115">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="e68c5-115">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68c5-116">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="e68c5-116">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="e68c5-117">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**.</span><span class="sxs-lookup"><span data-stu-id="e68c5-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="e68c5-118">Se viene visualizzata un'intestazione di notifica che indica che non vi sono utenti che dispongono di un' **Audioconferenza** licenza assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **qui per spostarli**.</span><span class="sxs-lookup"><span data-stu-id="e68c5-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="e68c5-119">Se non viene visualizzata l'intestazione, in **Skype per Business admin center** fare clic su **utenti**e quindi selezionare il filtro **utenti pronti a conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="e68c5-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="e68c5-120">Nella pagina proprietà dell'utente, sotto il **nome del Provider**, selezionare **Microsoft** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e68c5-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e68c5-121">Poiché si utilizza Microsoft come provider di servizi di conferenza audio e sono disponibili più numeri di telefono, è possibile utilizzare l'elenco a discesa **numero a pagamento predefinito** per selezionare un numero di audio predefinita per l'utente.</span><span class="sxs-lookup"><span data-stu-id="e68c5-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="e68c5-122">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e68c5-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="e68c5-123">Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti</span><span class="sxs-lookup"><span data-stu-id="e68c5-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="e68c5-124">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="e68c5-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="e68c5-125">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="e68c5-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68c5-126">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="e68c5-126">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="e68c5-127">Per modificare il provider a Microsoft per un numero limitato di utenti, è possibile utilizzare il cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="e68c5-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="e68c5-128">Utilizzo di uno script Windows PowerShell per un grande numero di utenti</span><span class="sxs-lookup"><span data-stu-id="e68c5-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="e68c5-129">Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="e68c5-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="e68c5-130">Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="e68c5-130">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68c5-131">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="e68c5-131">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="e68c5-132">Si salva un file di script PowerShell lo script seguente e quindi viene eseguito tramite uno dei parametri di input.</span><span class="sxs-lookup"><span data-stu-id="e68c5-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="e68c5-133">**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e68c5-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="e68c5-134">**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e68c5-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="e68c5-135">**Con l'esempio 3:** In questo esempio, è possibile utilizzare questo script per modificare il provider di servizi di conferenza audio da Intercall (o un altro provider) a **Microsoft** per un grande numero utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68c5-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="e68c5-136">Ecco lo script:</span><span class="sxs-lookup"><span data-stu-id="e68c5-136">Here is the script:</span></span>

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
<span data-ttu-id="e68c5-137">Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="e68c5-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="e68c5-138">See also</span><span class="sxs-lookup"><span data-stu-id="e68c5-138">Related topics</span></span>

[<span data-ttu-id="e68c5-139">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="e68c5-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="e68c5-140">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e68c5-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

