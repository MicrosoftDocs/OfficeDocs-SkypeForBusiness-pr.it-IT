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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Impara come assegnare le licenze di Skype for Business per Sistema telefonico, Audioconferenza, Piani di chiamata e Credito per la comunicazione. '
ms.openlocfilehash: 8e43bba8970e03fced61620fff7b63eed893484e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598280"
---
# <a name="assign-skype-for-business-licenses"></a>Assegnare licenze di Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo articolo fornisce suggerimenti sull'assegnazione di licenze agli utenti per funzionalità come audioconferenze, Sistema telefonico e piani per chiamate. Vengono inoltre forniti gli script per assegnare le licenze in blocco.

> [!IMPORTANT]
> Vedere Skype for Business licenze per i componenti aggiuntivi per informazioni sulle  licenze da acquistare e su come acquistarle, [a](skype-for-business-and-microsoft-teams-add-on-licensing.md) seconda del piano di Microsoft 365 o Office 365, in modo che gli utenti osercitino l'audioconferenza, i numeri a numero verde e la possibilità di chiamare numeri di telefono al di fuori dell'azienda.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze

Cosa è necessario sapere prima di assegnare licenze per audioconferenza, Sistema telefonico e piano chiamate

- **Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza **Sistema telefonico**. **NON** dovrai invece assegnare un Piano per chiamate.

- **Latenza** dopo l'assegnazione delle licenze: a causa della latenza tra Microsoft 365 o Office 365 e Skype for Business Online, l'assegnazione di un piano per chiamate a un utente dopo l'assegnazione di una licenza può richiedere fino a 24 ore. Se dopo 24 ore all'utente non è assegnato un piano per chiamate, contattare il supporto per i prodotti aziendali [- Guida per gli amministratori.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.
    
- **Passaggi successivi**: dopo avere assegnato le licenze per il Piano per chiamate agli utenti, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedere [Configurare i piani per chiamate.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente

I passaggi sono gli stessi dell'assegnazione di una Microsoft 365 o Office 365 licenza. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Come assegnare licenze Sistema telefonico e Piano per chiamate in massa

1. Installa **Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW**. Cosa fare se il modulo non è installato? Vedere [Microsoft Online Services Sign-In Assistente per i professionisti IT RTW](https://go.microsoft.com/fwlink/?LinkId=625123) per scaricarlo.

2. Installa il **Modulo di Windows Azure Active Directory.** Cosa fare se il modulo non è installato? Per istruzioni sul download e la [sintassi dei cmdlet, vedere Gestire Azure AD usando Windows PowerShell.](/previous-versions/azure/jj151815(v=azure.100))

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
|Piano per chiamate nazionali (3000 min us/1200 min piani UE)  <br/> |MCOPSTN1  <br/> |
|Piano per chiamate nazionali (piano per chiamate da 120 minuti)  <br/> |MCOPSTN5  <br/> |
|Piano per chiamate nazionali (piano per chiamate di 240 minuti)  <br/> |MCOPSTN6  <br/> |
|Credito per la comunicazione  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza

- **Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di **Audioconferenza**, Microsoft diventa il provider di servizi di audioconferenza. Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.

- Passaggi successivi: dopo aver assegnato le licenze **di audioconferenza,** è necessario assegnare un provider di servizi di audioconferenza. Vedi [Assegnare Microsoft come provider di servizi di audioconferenza].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Come assegnare una licenza di Audioconferenza a un utente

I passaggi sono gli stessi dell'assegnazione di una Microsoft 365 o Office 365 licenza. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Come assegnare licenze di Audioconferenza in blocco

1. Scaricare e installare [l Microsoft Online Services Sign-In Assistant per professionisti IT RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta [Gestire Azure AD tramite Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) per ottenere istruzioni per il download e la sintassi del cmdlet.

    Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:

    Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo. Vedere [Nomi di prodotti per audioconferenze o SKU usati per gli script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) per tutti i nomi di prodotto.

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

- **Enterprise clienti E5:** anche se agli utenti sono assegnate Enterprise licenze E5, è comunque consigliabile assegnare loro licenze **crediti** comunicazioni.
    
- **Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedere [Configurare i piani per chiamate.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Come assegnare una licenza di Servizi di conferenza PSTN a un utente

I passaggi sono gli stessi dell'assegnazione di una Microsoft 365 o Office 365 licenza. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Come assegnare licenze crediti comunicazioni in blocco

Guarda lo script di esempio per l'assegnazione delle licenze di **Audioconferenza**. Aggiornalo con le informazioni per l'assegnazione di licenze di **Crediti comunicazioni**.

## <a name="related-topics"></a>Argomenti correlati
  
[Configurare i piani per chiamate](/microsoftteams/set-up-calling-plans)
  
[Aggiungere fondi e gestire Credito per la comunicazione](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
