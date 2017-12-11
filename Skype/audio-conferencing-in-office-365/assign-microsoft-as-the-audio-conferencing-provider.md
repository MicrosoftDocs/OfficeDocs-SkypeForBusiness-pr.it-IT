---
title: "Assegnare Microsoft come provider di conferenze audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Assegnare Microsoft come provider di conferenze audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d). 
  
Un provider di conferenze audio fornisce il  *bridge di conferenza*  . Il bridge di conferenza fornisce i numeri di telefono di accesso esterno, pin e conferenza ID per le riunioni che vengono creati. È sufficiente assegnare un provider di conferenze audio agli utenti che si desidera pianificare o un cliente potenziale Skype for Business o riunioni Teams Microsoft.
  
Se si desidera elencato **Microsoft** come provider di audio, è necessario assegnare una licenza di ** Conferenze Audio** all'utente.
  
> [!NOTE]
> Se si assegna una licenza di **Conferenze Audio** a una persona che non dispone di un provider di conferenze audio di terze parti, viene assegnato automaticamente Microsoft come provider di conferenze audio. È possibile[Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md) , se necessario.
  
## Assegnare Microsoft come provider di conferenze audio

### Utilizzo dell'interfaccia di amministrazione di Skype for Business

1. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
    > [!NOTE]
    > Quando il provider di servizi viene modificato da un altro provider a **Microsoft**, le informazioni di conferenze audio per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. È consigliabile salvare queste informazioni prima di modificare il provider. 
  
2. Nel **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti** e quindi selezionare l'utente dall'elenco degli utenti disponibili.
    
3. Nel riquadro Azione, fai clic su **Modifica**.
    
4. Nella pagina delle proprietà per l'utente, in **nome Provider**, selezionare **Microsoft** nell'elenco a discesa.
    
    > [!NOTE]
    > Poiché si sta utilizzando Microsoft come provider di conferenze audio e sono presenti più numeri di telefono, è possibile utilizzare l'elenco a discesa **numero a pagamento predefinito** per selezionare un numero di audio predefinito per l'utente.
  
5. Fare clic su **Salva**.
    
### Utilizzo di uno script di Windows PowerShell per un numero limitato di utenti

Per risparmiare tempo o automatizzare questa operazione, è possibile usare il seguente script di PowerShell per impostare Microsoft come provider di conferenze audio per un numero limitato di utenti.
  
> [!NOTE]
> Quando il provider di servizi viene modificato da un altro provider a **Microsoft**, le informazioni di conferenze audio per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. È consigliabile salvare queste informazioni prima di modificare il provider. 
  
Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.
  
Per modificare il provider a Microsoft per un numero ridotto di utenti, puoi utilizzare [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
> **Esempio 1:** puoi eseguire questo script fornendo un elenco di utenti che desideri aggiornare.
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **Esempio 2:** puoi eseguire questo script fornendo un file .csv che contiene l'indirizzo e-mail (alias) di ciascun utente che desideri aggiornare.
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### Utilizzo di uno script Windows PowerShell per un grande numero di utenti

Per risparmiare tempo o automatizzare questa operazione, è possibile usare il seguente script di PowerShell per impostare Microsoft come provider di conferenze audio per un numero elevato di utenti.
  
> [!NOTE]
> Quando il provider di servizi viene modificato da un altro provider a **Microsoft**, le informazioni di conferenze audio per l'utente (ID conferenza, a pagamento e numeri verdi) verranno sostituite. È consigliabile salvare queste informazioni prima di modificare il provider. 
  
Puoi salvare uno o più dei seguenti script come file di script PowerShell e quindi eseguirlo.
  
> **Esempio 1:** In questo esempio, è possibile usare questo script per modificare il provider di conferenze audio da Intercall (o un altro provider) a **Microsoft** per un grande numero di utenti dell'organizzazione.
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **Questo è lo script:**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## Quali altre informazioni sono necessarie?

- Un utente può essere assegnato solo un provider di conferenze audio.
    
- È possibile modificare il provider di conferenze audio da Microsoft a un provider di terze parti in qualsiasi momento. Per ulteriori informazioni, vedere [Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- All'interno dell'organizzazione, è possibile impostare alcune persone che utilizzano Microsoft come provider di conferenze audio e gli altri utenti che utilizzano un provider di terze parti. Si tratta di più complicata configurare e gestire.
    
## Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

