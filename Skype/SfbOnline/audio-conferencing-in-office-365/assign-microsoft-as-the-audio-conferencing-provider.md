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
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: d6c0f4f3a8f903ff180785214d3a4e987321a5b3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider di servizi di conferenza audio

Un provider di servizi di conferenza audio fornisce di *ponte conferenza*. Bridge conferenza include i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni creati. È sufficiente assegnare un provider di servizi di conferenza audio a coloro che desidera programmare o lead Skype per le riunioni aziendali o Microsoft Teams.
  
Se si desidera essere in grado di vedere **che Microsoft** elencati come provider di audio, è necessario assegnare una licenza di **Audioconferenza** all'utente.
  
> [!NOTE]
> Se si assegna una licenza di **Audioconferenze con accesso esterno** a una persona che non dispone di un provider di servizi di conferenza audio di terze parti, Microsoft viene assegnato automaticamente come provider di servizi di conferenza audio. È possibile [assegnare una terza parte come provider di servizi di conferenza audio](assign-a-third-party-as-the-audio-conferencing-provider.md) , se necessario.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Assegnare Microsoft come provider di servizi di conferenza audio

### <a name="using-the-skype-for-business-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Skype for Business

1. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
    > [!NOTE]
    > Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. Salva queste informazioni prima di modificare il provider. 
  
2. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.
    
3. In the Action pane, click **Edit**.
    
4. Nella pagina proprietà dell'utente, sotto il **nome del Provider**, selezionare **Microsoft** nell'elenco a discesa.
    
    > [!NOTE]
    > Poiché si utilizza Microsoft come provider di servizi di conferenza audio e sono disponibili più numeri di telefono, è possibile utilizzare l'elenco a discesa **numero a pagamento predefinito** per selezionare un numero di audio predefinita per l'utente.
  
5. Fare clic su **Salva**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un numero ridotto di utenti

Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero limitato di utenti.

> [!NOTE]
> Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. Salva queste informazioni prima di modificare il provider. 
  
Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.
  
Per modificare il provider a Microsoft per un numero limitato di utenti, è possibile utilizzare [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
**Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilizzo di uno script Windows PowerShell per un grande numero di utenti
Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il seguente script di PowerShell per configurare Microsoft come provider di servizi di conferenza audio per un numero elevato di utenti.

Quando il provider viene modificato da un altro provider a **Microsoft**, le informazioni di audioconferenze con accesso esterno per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. Salva queste informazioni prima di modificare il provider. 
  
Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.

**Nell'esempio 1:** In questo esempio, è possibile utilizzare questo script per modificare il provider di servizi di conferenza audio da Intercall (o un altro provider) a **Microsoft** per un grande numero utenti nell'organizzazione.
    
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
  
## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Un utente può essere assegnato un solo provider di servizi di conferenza audio.
    
- È possibile modificare il provider di servizi di conferenza audio da Microsoft a un provider di terze parti in qualsiasi momento. Per ulteriori informazioni, consulta [Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- All'interno dell'organizzazione, è possibile avere alcune persone che utilizzano Microsoft come i provider di servizi di conferenza audio gli utenti che utilizzano un provider di terze parti. In questo caso, tuttavia, la configurazione e la gestione delle conferenze telefoniche con accesso esterno è più complessa.
    
## <a name="related-topics"></a>See also

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)