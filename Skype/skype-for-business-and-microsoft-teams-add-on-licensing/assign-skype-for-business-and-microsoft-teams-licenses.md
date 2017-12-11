---
title: "Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/fd41934d-f2eb-4a1b-89d8-32cb37702b33). 
  
In questo articolo offre suggerimenti per l'assegnazione di licenze agli utenti per le caratteristiche come conferenze Audio, il sistema telefonico e si chiama plan di messaggistica unificata. Inoltre, sono disponibili gli script per l'assegnazione di licenze in blocco.
  
 **Importante**: vedere[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](skype-for-business-and-microsoft-teams-add-on-licensing.md) per informazioni su quali licenze si necessario acquistare e **come acquistare**, a seconda del piano di Office 365 - in modo che gli utenti ricevano conferenze Audio, numeri verdi, e la possibilità di chiamare i numeri di telefono a propria azienda.
  
## Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze

### Che cos'è necessario sapere prima di assegnare conferenze Audio, sistema telefonico e pianificare la chiamata licenze

- **IMPORTANTE**: per visualizzare l'opzione **Voce** nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Skype for Business, è necessario acquistare almeno una **licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per il componente aggiuntivo **Audioconferenza**.
    
- **Con la connettività PSTN locale per gli utenti ibrido?** In caso affermativo, è sufficiente assegnare una licenza di **Sistema telefonico**. È consigliabile **non** assegnare un piano di chiamata.
    
- **Latenza dopo l'assegnazione di licenze**: a causa della latenza tra Office 365 e Skype for Business online, probabilmente può richiedere fino a 24 ore per un utente da assegnare un piano di chiamata dopo avere assegnato una licenza. Se dopo 24 ore l'utente non è assegnata a un piano di chiamata, fare[Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Messaggi di errore**: verrà visualizzato un messaggio di errore se non è stato acquistato il numero di licenze corretto. Se è necessario acquistare altre licenze di pianificare la chiamata, scegliere **acquistare ulteriori**.
    
- **Passaggi successivi**: dopo aver assegnato la chiamata a pianificare licenze agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare questi numeri per le persone dell'organizzazione. Per istruzioni dettagliate, vedere[Configurare la chiamata plan di messaggistica unificata](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente

I passaggi sono diverso da quello di assegnazione di una licenza di Office 365. Vedere [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Come assegnare licenze Sistema telefonico e Piano per chiamate in massa

1. Installare **Microsoft Online Services Assistente per l'accesso per i professionisti IT RTW**. Non è installato il modulo? Vedere[Assistente Microsoft Online Services accesso per RTW professionisti IT](https://go.microsoft.com/fwlink/?LinkId=625123) per scaricarlo.
    
2. Installa il **Modulo di Windows Azure Active Directory.** Cosa fare se il modulo non è installato? Vedi[Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni sul download e la sintassi del cmdlet.
    
3. Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:
    
    In questo esempio vengono assegnate una licenza di **Enterprise E3** insieme a una licenza per **Sistema telefonico** e per un **Piano per chiamate nazionali**.
    
    Il nome delle licenze o i nomi dei prodotti lo script sono elencati in testo in corsivo (vedere **sistema telefonico e si chiama pianificare i nomi di prodotto o SKU utilizzati per gli script**, dopo l'esempio).
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice.
Connect-MSOLService

#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users.
$users = Get-Content $OFD.filename

#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script

|**Nome del prodotto**|**Nome parte SKU**|
|:-----|:-----|
|Enterprise E5 (con Sistema telefonico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Offerta autonoma Plan 2 di Skype for Business online  <br/> | MCOSTANDARD <br/> |
| Sistema telefonico <br/> |MCOEV  <br/> |
|Piano per chiamate internazionali  <br/> |MCOPSTN2  <br/> |
|Piano per chiamate nazionali  <br/> |MCOPSTN1  <br/> |
|Crediti comunicazioni  <br/> |MCOPSTNPP  <br/> |
   
## Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze

### Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza

- **Provider di conferenze audio di terze parti**: se un utente è già configurato per utilizzare un provider di conferenze audio di terze parti, quando si assegna loro una licenza di **Audioconferenza**, verrà modificati per utilizzare Microsoft come conferenze audio provider. È possibile modificarli al provider di terze parti.
    
- Passaggi successivi: dopo l'assegnazione di licenze di **Conferenze Audio**, è necessario assegnare un provider di conferenze audio. Eseguire una delle operazioni seguenti:
    
  - [Assegnare Microsoft come provider di conferenze audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - O [Assegnare una terza parte come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Come assegnare una licenza di Audioconferenza a un utente

I passaggi sono diverso da quello di assegnazione di una licenza di Office 365. Vedere [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Come assegnare licenze di Audioconferenza in blocco

1. Scaricare e installare [Microsoft Online Services Assistente per l'accesso per RTW professionisti IT](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta[Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni per il download e la sintassi del cmdlet.
    
    Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:
    
    Il nome delle licenze o i nomi dei prodotti lo script sono elencati in testo in corsivo. Vedere [Nomi di prodotto delle audioconferenze o SKU usati per gli script](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) per tutti i nomi di prodotto.
    
    In questo esempio assegna una licenza Enterprise E3 insieme a una licenza di conferenze Audio.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService

#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 

  ```

### Nomi di prodotto delle audioconferenze o SKU usati per gli script
<a name="sku"> </a>

|**Nome del prodotto**|**Nome parte SKU**|
|:-----|:-----|
| Audioconferenza <br/> |MCOMEETADV  <br/> |
|Offerta autonoma Plan 2 di Skype for Business online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> | STANDARDPACK <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (senza Audioconferenza)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (con Audioconferenza)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Crediti comunicazioni

### Ecco cosa devi sapere prima di assegnare le licenze per i Crediti comunicazioni

- **I clienti Enterprise E5**: anche se gli utenti assegnati licenze E5 dell'organizzazione, è comunque consigliabile assegnare loro **Crediti comunicazioni** licenze.
    
- **Passaggi successivi**: dopo aver assegnato queste licenze, sarà necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare questi numeri per le persone dell'organizzazione. Per istruzioni dettagliate, vedere[Configurare la chiamata plan di messaggistica unificata](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Come assegnare una licenza di Servizi di conferenza PSTN a un utente

I passaggi sono diverso da quello di assegnazione di una licenza di Office 365. Vedere [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Come assegnare licenze di comunicazioni crediti in blocco

Esaminare lo script di esempio per l'assegnazione di licenze di **Conferenze Audio**. Aggiornare con le informazioni per l'assegnazione di licenze **Crediti comunicazioni**.
  
## Articoli correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurare la chiamata plan di messaggistica unificata](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Aggiungere e i fondi e gestire le comunicazioni crediti](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

