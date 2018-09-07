---
title: Assegnare Microsoft come provider dei servizi di audioconferenza
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Informazioni su come assegnare  Microsoft come provider dei servizi di conferenza telefonica per Skype for Business.
ms.openlocfilehash: efa3b1987feab2ba830f87e8fb8a402fed82684b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857260"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider dei servizi di audioconferenza

Per l'utilizzo di servizi di audioconferenza in Office 365 con Skype for Business e Microsoft Teams, è necessario disporre di una licenza di audioconferenza assegnata agli utenti dell'organizzazione. Per ulteriori informazioni sulla gestione delle licenze e sul costo, vedere [prova o acquisto audioconferenza in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .

L'audioconferenza Microsoft fornisce i numeri di telefono di accesso esterno, pin e ID conferenza che possono essere utilizzati dai partecipanti alla riunione per colegarsi alle riunioni della propria organizzazione. È sufficiente assegnare agli utenti che desiderano programmare o condurre riunioni con Skype for Business o Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider dei servizi di audioconferenza

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Utilizzo dell'interfaccia di amministrazione di Skype for Business

1. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
2. Nell' **interfaccia di amministrazione di Skype for Business**, nel menu di navigazione a sinistra, vai su **Audioconferenza**.
    
3. Se viene visualizzata un'intestazione di notifica che indica che vi sono utenti che dispongono di una licenza **Audioconferenza** assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **Clicca qui per spostarli**. Se non viene visualizzata l'intestazione, nell' **interfaccia di amministrazione di Skype for Business** fare clic su **utenti**e quindi selezionare il filtro **utenti pronti per audioconferenza** .
    
4. Nella pagina proprietà dell'utente, sotto il **nome del provider**, selezionare **Microsoft** nel menu a tendina.
    
    > [!NOTE]
    > Siccome stai utilizzando Microsoft come provider dei servizi di audioconferenza con accesso esterno e sono presenti più numeri di telefono, puoi selezionare un numero di accesso esterno predefinito per l'utente utilizzando il menu a tendina**Numero predefinito**.
  
5. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti

Per rendere automatiche queste operazioni o per risparmiare tempo, puoi utilizzare il seguente script PowerShell per impostare Microsoft come provider di audioconferenza con accesso esterno per un ridotto numero di utenti.

> [!NOTE]
> Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenza con accesso esterno per l'utente (ID conferenza, numero a tariffa e numero verde) verranno sostituiti. Salva queste informazioni prima di modificare il provider. 

  
Per modificare il provider a Microsoft per un numero ridotto di utenti, puoi utilizzare il cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un elevato numero di utenti
Per rendere automatiche queste operazioni o per risparmiare tempo, puoi utilizzare il seguente script PowerShell per impostare Microsoft come provider di audioconferenza con accesso esterno per un elevato numero di utenti.

Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenza con accesso esterno per l'utente (ID conferenza, numero a tariffa e numero verde) verranno sostituiti. Salva queste informazioni prima di modificare il provider. 
  
Si salva un file di script PowerShell lo script seguente e quindi viene eseguito tramite uno dei parametri di input.

**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Esempio 3:** in questo esempio puoi utilizzare questo script per modificare il provider di audioconferenza con accesso esterno da Intercall (o un altro provider) a **Microsoft** per un numero elevato di utenti dell'organizzazione.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Ecco lo script:

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
Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="related-topics"></a>Argomenti correlati
[Prova o acquista audioconferenza in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Configura Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

