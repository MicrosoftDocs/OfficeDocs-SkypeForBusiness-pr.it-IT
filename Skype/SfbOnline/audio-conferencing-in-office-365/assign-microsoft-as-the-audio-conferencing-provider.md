---
title: Assegnare Microsoft come provider di servizi di audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 8ce128c2fa19668ed93c6ad387feecbee2e00a8d
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164519"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="5f1d4-103">Assegnare Microsoft come provider di servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5f1d4-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="5f1d4-p101">Per usare le audioconferenze in Microsoft 365 o Office 365 con Skype for Business e Microsoft Teams, gli utenti dell'organizzazione devono avere una licenza per i servizi di audioconferenza assegnata. Per altre informazioni sulle licenze e sul costo, vedi Provare o acquistare le audioconferenze [in Microsoft 365 o Office 365.](try-or-purchase-audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5f1d4-p101">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them. See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="5f1d4-p102">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization. You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-p102">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization. You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="5f1d4-108">Assegnare Microsoft come provider di servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5f1d4-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) <span data-ttu-id="5f1d4-110">Utilizzo dell'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5f1d4-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="5f1d4-111">Vai al portale **legacy dell'interfaccia di amministrazione** di Microsoft  >  Teams.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="5f1d4-112">**Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, passa a **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="5f1d4-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="5f1d4-p103">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**. If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-p103">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**. If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="5f1d4-115">Nella pagina delle proprietà dell'utente, in **Nome provider,** selezionare **Microsoft** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f1d4-116">Poiché utilizzi Microsoft come provider di servizi di audioconferenza e  sono presenti più numeri di telefono, puoi utilizzare l'elenco a discesa Numeri di telefono predefiniti per selezionare un numero audio predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="5f1d4-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="5f1d4-118">Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti</span><span class="sxs-lookup"><span data-stu-id="5f1d4-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="5f1d4-119">Per automatizzare questa operazione o per risparmiare tempo, puoi utilizzare il seguente script PowerShell per impostare Microsoft come provider di servizi di audioconferenza per un piccolo numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="5f1d4-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="5f1d4-122">Per impostare il provider su Microsoft per un numero limitato di utenti, puoi utilizzare il cmdlet [Enable-CsOnlineDialInConferencingUser.](https://technet.microsoft.com/library/mt243813.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f1d4-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="5f1d4-123">Utilizzo di uno script Windows PowerShell per un grande numero di utenti</span><span class="sxs-lookup"><span data-stu-id="5f1d4-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="5f1d4-124">Per automatizzare questa operazione o per risparmiare tempo, puoi utilizzare il seguente script PowerShell per impostare Microsoft come provider di servizi di audioconferenza per un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="5f1d4-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="5f1d4-127">Si salva un file di script PowerShell lo script seguente e quindi viene eseguito tramite uno dei parametri di input.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="5f1d4-128">**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="5f1d4-129">**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="5f1d4-130">**Esempio 3:** In questo esempio puoi usare questo script per modificare il provider di servizi di audioconferenza da Intercall (o un altro provider) a **Microsoft** per un numero elevato di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1d4-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="5f1d4-131">Ecco lo script:</span><span class="sxs-lookup"><span data-stu-id="5f1d4-131">Here is the script:</span></span>

  ```PowerShell
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
<span data-ttu-id="5f1d4-132">Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="5f1d4-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5f1d4-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5f1d4-133">Related topics</span></span>
<span data-ttu-id="5f1d4-134">[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="5f1d4-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

