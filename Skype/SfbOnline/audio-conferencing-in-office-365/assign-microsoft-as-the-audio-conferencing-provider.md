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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 982d0515468109d1adf8ac2d7f00cce36732faf7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620302"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider di servizi di audioconferenza

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Per usare i servizi di audioconferenza in Microsoft 365 o Office 365 con Skype for Business e Microsoft Teams, gli utenti dell'organizzazione devono avere una licenza di audioconferenza assegnata. Vedere [Provare o acquistare audioconferenze in Microsoft 365 o Office 365](try-or-purchase-audio-conferencing-in-office-365.md) per altre informazioni sulle licenze e sul costo.

L'audioconferenza Microsoft fornisce i numeri di telefono di accesso esterno, pin e ID conferenza che possono essere utilizzati dai partecipanti alla riunione per colegarsi alle riunioni della propria organizzazione. È sufficiente assegnare agli utenti che desiderano programmare o condurre riunioni con Skype for Business o Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider di servizi di audioconferenza

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Icona che mostra il logo Skype for Business](../images/sfb-logo-30x30.png) Utilizzo dell'interfaccia di amministrazione di Skype for Business

1. Passare **all'interfaccia Microsoft Teams di amministrazione**  >  **legacy**.
    
2. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Servizi di audioconferenza.**
    
3. Se viene visualizzata un'intestazione di notifica che indica che vi sono utenti che dispongono di una licenza **Audioconferenza** assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **Clicca qui per spostarli**. Se non viene visualizzata l'intestazione, nell' **interfaccia di amministrazione di Skype for Business** fare clic su **utenti** e quindi selezionare il filtro **utenti pronti per audioconferenza** .
    
4. Nella pagina delle proprietà dell'utente, in **Nome provider,** selezionare **Microsoft** nell'elenco a discesa.
    
    > [!NOTE]
    > Poiché si usa Microsoft come provider di servizi di audioconferenza  e sono presenti più numeri di telefono, è possibile usare l'elenco a discesa Numero a pedaggio predefinito per selezionare un numero audio predefinito per l'utente.
  
5. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti

Per risparmiare tempo o automatizzare questa operazione, è possibile usare lo script di PowerShell seguente per impostare Microsoft come provider di servizi di audioconferenza per un numero limitato di utenti.

> [!NOTE]
> Quando il provider viene cambiato da un altro provider a **Microsoft,** le informazioni di audioconferenza per l'utente (ID conferenza, numeri a pagamento e numero verde) verranno sostituite. Salva queste informazioni prima di modificare il provider. 

  
Per impostare il provider su Microsoft per un numero limitato di utenti, è possibile usare il cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un grande numero di utenti
Per risparmiare tempo o automatizzare questa operazione, è possibile usare lo script di PowerShell seguente per impostare Microsoft come provider di servizi di audioconferenza per un numero elevato di utenti.

Quando il provider viene cambiato da un altro provider a **Microsoft,** le informazioni di audioconferenza per l'utente (ID conferenza, numeri a pagamento e numero verde) verranno sostituite. Salva queste informazioni prima di modificare il provider. 
  
Si salva un file di script PowerShell lo script seguente e quindi viene eseguito tramite uno dei parametri di input.

**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Esempio 3:** In questo esempio è possibile usare questo script per modificare il provider di audioconferenza da Intercall (o da un altro provider) a **Microsoft** per un numero elevato di utenti dell'organizzazione.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Ecco lo script:

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
Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Argomenti correlati
[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurare Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
