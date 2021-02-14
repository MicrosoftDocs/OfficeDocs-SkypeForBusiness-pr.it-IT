---
title: Assegnare licenze di Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Impara come assegnare le licenze di Skype for Business per Sistema telefonico, Audioconferenza, Piani di chiamata e Credito per la comunicazione. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204847"
---
# <a name="assign-skype-for-business-licenses"></a>Assegnare licenze di Skype for Business

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> Consulta le licenze per i componenti aggiuntivi [Skype for](skype-for-business-and-microsoft-teams-add-on-licensing.md)  Business per informazioni sulle licenze che devi acquistare e su come acquistarle , a seconda del tuo piano Microsoft 365 o Office 365, in modo che gli utenti osercitino i servizi di audioconferenza, i numeri verde e la possibilità di chiamare numeri esterni alla tua azienda.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze

Cosa devi sapere prima di assegnare le licenze per Audioconferenza, Sistema telefonico e Piano per chiamate

- **Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza **Sistema telefonico**. **NON** dovrai invece assegnare un Piano per chiamate.

- **Latenza** dopo l'assegnazione delle licenze: a causa della latenza tra Microsoft 365 o Office 365 e Skype for Business online, l'assegnazione di un Piano per chiamate a un utente dopo l'assegnazione di una licenza può richiedere fino a 24 ore. Se dopo 24 ore all'utente non è assegnato un piano per chiamate, contatta il supporto per i prodotti aziendali [- Guida per gli amministratori.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente

I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Come assegnare licenze Sistema telefonico e Piano per chiamate in massa

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:

   In questo esempio vengono assegnate una licenza di **Enterprise E3** insieme a una licenza per **Sistema telefonico** e per un **Piano per chiamate nazionali**.

   Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo (consulta la sezione **Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script**, dopo l'esempio).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script

|**Nome del prodotto**|**Nome parte SKU**|
|:-----|:-----|
|Enterprise E5 (con Sistema telefonico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Offerta autonoma Plan 2 di Skype for Business online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefonico  <br/> |MCOEV  <br/> |
|Piano per chiamate internazionali  <br/> |MCOPSTN2  <br/> |
|Piano per chiamate nazionali (piani DA 3000 min USA/1200 min UE)  <br/> |MCOPSTN1  <br/> |
|Piano per chiamate nazionali (piano da 120 min)  <br/> |MCOPSTN5  <br/> |
|Piano per chiamate nazionali (piano da 240 min)  <br/> |MCOPSTN6  <br/> |
|Credito per la comunicazione  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza

- **Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di **Audioconferenza**, Microsoft diventa il provider di servizi di audioconferenza. Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.

- Passaggi successivi: dopo avere assegnato le licenze per i servizi **di audioconferenza,** devi assegnare un provider di servizi di audioconferenza. Vedi [Assegnare Microsoft come provider di servizi di audioconferenza].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Come assegnare una licenza di Audioconferenza a un utente

I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Come assegnare licenze di Audioconferenza in blocco

1. Scarica e installa [Assistente Microsoft Online Services Sign-In per professionisti IT - RTW.](https://go.microsoft.com/fwlink/?LinkId=625123)

2. Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta [Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni per il download e la sintassi del cmdlet.

    Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:

    Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo. Vedi [i nomi di prodotto delle audioconferenze](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) o gli SKU usati per gli script per tutti i nomi di prodotto.

    In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomi di prodotto delle audioconferenze o SKU usati per gli script
<a name="sku"> </a>

|**Nome del prodotto**|**Nome parte SKU**|
|:-----|:-----|
|Audioconferenza  <br/> |MCOMEETADV  <br/> |
|Offerta autonoma Plan 2 di Skype for Business online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (senza Audioconferenza)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (con Audioconferenza)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Credito per la comunicazione

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Ecco cosa devi sapere prima di assegnare le licenze per i Crediti comunicazioni

- **Clienti Enterprise E5:** anche se agli utenti sono assegnate licenze Enterprise E5, ti consigliamo comunque di assegnare loro **licenze di Crediti** comunicazioni.
    
- **Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, consulta [Configurare i Piani per chiamate.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Come assegnare una licenza di Servizi di conferenza PSTN a un utente

I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Come assegnare licenze di Crediti comunicazioni in blocco

Guarda lo script di esempio per l'assegnazione delle licenze di **Audioconferenza**. Aggiornalo con le informazioni per l'assegnazione di licenze di **Crediti comunicazioni**.

## <a name="related-topics"></a>Argomenti correlati
  
[Configurare i piani per chiamate](/microsoftteams/set-up-calling-plans)
  
[Aggiungere fondi e gestire Credito per la comunicazione](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
