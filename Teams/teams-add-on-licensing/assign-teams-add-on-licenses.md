---
title: Assegnare licenze per i componenti aggiuntivi di Teams agli utenti
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Scopri come assegnare licenze per i componenti aggiuntivi di Teams agli utenti per funzionalità come Audioconferenza, Sistema telefonico e Piani per chiamate.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196930"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Assegnare licenze per i componenti aggiuntivi di Teams agli utenti

Le licenze per i componenti aggiuntivi sono licenze per funzionalità specifiche di Teams come Audioconferenza, Sistema telefonico e Piani per chiamate. Questo articolo descrive come assegnare licenze per i componenti aggiuntivi a singoli utenti e a grandi set di utenti in blocco.

> [!NOTE]
> Vedere [le licenze per i componenti aggiuntivi di](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) Teams per le funzionalità di Teams disponibili con licenze per componenti aggiuntivi. Troverai anche informazioni sulle licenze che devi acquistare e su come acquistarle (a seconda del tuo piano), in modo che gli utenti possano ottenere funzionalità come i servizi di audioconferenza, numeri verde e la possibilità di chiamare numeri di telefono esterni alla tua organizzazione. Dopo aver deciso quali funzionalità assegnare agli utenti, assegnare loro le licenze.

È possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore Gestione utenti.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Cosa devi sapere prima di assegnare le licenze Sistema telefonico, Piano per chiamate e Crediti comunicazioni

Prima di iniziare, verificare i requisiti seguenti:

- Se si usa la connettività PSTN (Public Switched Telephone Network) locale per utenti ibridi, è necessario assegnare solo una licenza Sistema telefonico. NON assegnare una licenza per un Piano per chiamate.

- A causa della latenza tra Microsoft 365 e Microsoft Teams, l'assegnazione di un Piano per chiamate a un utente può richiedere fino a 24 ore dopo l'assegnazione di una licenza. Se dopo 24 ore all'utente non viene assegnato un Piano per chiamate, contatta il supporto per i prodotti per le aziende [: guida per gli amministratori.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze per il Piano per chiamate, scegli l'opzione per acquistarne altre.

- Anche se agli utenti sono assegnate licenze Enterprise [](../what-are-communications-credits.md) E5, devi comunque assegnare loro licenze di Crediti comunicazioni se vogliono effettuare o ricevere chiamate dalla rete PSTN.

- Dopo aver assegnato le licenze per Piani per chiamate o Crediti comunicazioni agli utenti, dovrai ottenere numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, consulta [Configurare i Piani per chiamate.](../set-up-calling-plans.md)

## <a name="using-the-microsoft-365-admin-center"></a>Uso dell'interfaccia di amministrazione di Microsoft 365

Usare l'interfaccia di amministrazione di Microsoft 365 per assegnare licenze a singoli utenti o a piccoli set di utenti contemporaneamente. Le licenze vengono assegnate **nella** pagina Licenze (per un massimo di 20 utenti alla volta) o nella **pagina Utenti** attivi. Il metodo scelto varia a seconda che si vogliano gestire licenze di prodotto per utenti specifici o licenze utente per prodotti specifici.

Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

Se è necessario assegnare licenze a un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare Powershell o licenze basate su gruppo [in Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per assegnare licenze agli utenti in blocco.  Per altre informazioni, vedere [Assegnare licenze agli account utente con PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Script di esempio

Ecco un esempio di come usare uno script per assegnare licenze agli utenti.

1. Installare la versione a 64 bit di Assistente per l'Microsoft Online Services accesso per [professionisti IT - RTW.](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)
2. Installare il modulo di Microsoft Azure Active Directory per Windows PowerShell:
    1. Aprire un prompt dei Windows PowerShell con privilegi elevati (Windows PowerShell amministratore).
    2. Eseguire il comando seguente:
        ```powershell
        Install-Module MSOnline
        ```
    3. Se viene richiesto di installare il provider NuGet, digitare **Y** e quindi premere INVIO.
    4. Se viene richiesto di installare il modulo da PSGallery, digitare **Y** e quindi premere INVIO.
3. Al prompt Windows PowerShell eseguire lo script seguente per assegnare le licenze agli utenti, dove si trova il nome dell'organizzazione e l'identificatore della licenza \<CompanyName:License> da assegnare. Ad esempio, litwareinc:MCOMEETADV.

    L'identificatore è diverso dal nome descrittivo della licenza. Ad esempio, l'identificatore per i servizi di audioconferenza è MCOMEETADV. Per altre informazioni, vedere Nomi [dei prodotti e identificatori di SKU per le licenze.](#product-names-and-sku-identifiers-for-licensing)

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Ad esempio, per assegnare le licenze di Microsoft 365 Enterprise 1 e audioconferenza, usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Per assegnare una licenza Microsoft Business Voice (senza piano per chiamate), usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomi di prodotto e identificatori di SKU per le licenze

Ecco un elenco parziale dei nomi di prodotto e dei nomi delle parti SKU corrispondenti che è possibile usare come riferimento quando si usa PowerShell per gestire le licenze in Teams.

Per altre informazioni, vedere Visualizzare licenze e servizi con [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)nomi dei prodotti e identificatori dei [piani](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)di servizio per le licenze e informazioni di riferimento [su SKU per Education.](../sku-reference-edu.md)

| Nome del prodotto| Nome parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con Sistema telefonico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (senza audioconferenza) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con audioconferenza) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Canada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Regno Unito) | BUSINESS_VOICE  |
| Microsoft Business Voice (Stati Uniti) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (senza piano per le chiamate) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (senza piano per le chiamate) per gli Stati Uniti| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferenza | MCOMEETADV | 
| Pagamento al minuto per i servizi di audioconferenza (a pagamento)</br>*Richiede che i Crediti comunicazioni siano impostati e abilitati.* | MCOMEETACPEA |
| Sistema telefonico | MCOEV |
| Piano per chiamate nazionali e internazionali | MCOPSTN2 |
| Piano per chiamate nazionali (3.000 minuti al mese per US/PR/CA, 1200 minuti al mese per utente/mese per i paesi dell'Unione Europea) | MCOPSTN1 |
| Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN5 |
| Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN6 |
| Credito per la comunicazione | MCOPSTNPP |

## <a name="related-topics"></a>Argomenti correlati

- [Gestione delle licenze per i componenti aggiuntivi di Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Gestire l'accesso degli utenti a Teams](../user-access.md)
- [Visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informazioni di riferimento per gli SKU di Education](../sku-reference-edu.md)