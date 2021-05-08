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
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237762"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c8fc8-103">Assegnare Microsoft come provider di servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="c8fc8-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="c8fc8-104">Per usare i servizi di audioconferenza in Microsoft 365 o Office 365 con Skype for Business e Microsoft Teams, gli utenti dell'organizzazione devono avere una licenza di audioconferenza assegnata.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="c8fc8-105">Vedere [Provare o acquistare audioconferenze in Microsoft 365](try-or-purchase-audio-conferencing-in-office-365.md) o Office 365 per altre informazioni sulle licenze e sul costo.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="c8fc8-106">L'audioconferenza Microsoft fornisce i numeri di telefono di accesso esterno, pin e ID conferenza che possono essere utilizzati dai partecipanti alla riunione per colegarsi alle riunioni della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="c8fc8-107">È sufficiente assegnare agli utenti che desiderano programmare o condurre riunioni con Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c8fc8-108">Assegnare Microsoft come provider di servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="c8fc8-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Icona che mostra il logo Skype for Business](../images/sfb-logo-30x30.png) <span data-ttu-id="c8fc8-110">Utilizzo dell'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c8fc8-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c8fc8-111">Passare **all'interfaccia Microsoft Teams di amministrazione**  >  **legacy**.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="c8fc8-112">**Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Servizi di audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="c8fc8-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c8fc8-113">Se viene visualizzata un'intestazione di notifica che indica che vi sono utenti che dispongono di una licenza **Audioconferenza** assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **Clicca qui per spostarli**.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="c8fc8-114">Se non viene visualizzata l'intestazione, nell' **interfaccia di amministrazione di Skype for Business** fare clic su **utenti** e quindi selezionare il filtro **utenti pronti per audioconferenza** .</span><span class="sxs-lookup"><span data-stu-id="c8fc8-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="c8fc8-115">Nella pagina delle proprietà dell'utente, in **Nome provider,** selezionare **Microsoft** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8fc8-116">Poiché si usa Microsoft come provider di servizi di audioconferenza  e sono presenti più numeri di telefono, è possibile usare l'elenco a discesa Numero a pedaggio predefinito per selezionare un numero audio predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="c8fc8-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="c8fc8-118">Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti</span><span class="sxs-lookup"><span data-stu-id="c8fc8-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="c8fc8-119">Per risparmiare tempo o automatizzare questa operazione, è possibile usare lo script di PowerShell seguente per impostare Microsoft come provider di servizi di audioconferenza per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="c8fc8-120">Quando il provider viene cambiato da un altro provider a **Microsoft,** le informazioni di audioconferenza per l'utente (ID conferenza, numeri a pagamento e numero verde) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c8fc8-121">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="c8fc8-122">Per impostare il provider su Microsoft per un numero limitato di utenti, è possibile usare il cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="c8fc8-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="c8fc8-123">Utilizzo di uno script Windows PowerShell per un grande numero di utenti</span><span class="sxs-lookup"><span data-stu-id="c8fc8-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="c8fc8-124">Per risparmiare tempo o automatizzare questa operazione, è possibile usare lo script di PowerShell seguente per impostare Microsoft come provider di servizi di audioconferenza per un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="c8fc8-125">Quando il provider viene cambiato da un altro provider a **Microsoft,** le informazioni di audioconferenza per l'utente (ID conferenza, numeri a pagamento e numero verde) verranno sostituite.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c8fc8-126">Salva queste informazioni prima di modificare il provider.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="c8fc8-127">Si salva un file di script PowerShell lo script seguente e quindi viene eseguito tramite uno dei parametri di input.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="c8fc8-128">**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="c8fc8-129">**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="c8fc8-130">**Esempio 3:** In questo esempio è possibile usare questo script per modificare il provider di audioconferenza da Intercall (o da un altro provider) a **Microsoft** per un numero elevato di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8fc8-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="c8fc8-131">Ecco lo script:</span><span class="sxs-lookup"><span data-stu-id="c8fc8-131">Here is the script:</span></span>

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
<span data-ttu-id="c8fc8-132">Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c8fc8-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c8fc8-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c8fc8-133">Related topics</span></span>
<span data-ttu-id="c8fc8-134">[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurare Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="c8fc8-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
