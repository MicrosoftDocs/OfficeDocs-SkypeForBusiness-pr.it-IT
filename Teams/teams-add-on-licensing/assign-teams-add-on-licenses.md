---
title: Assegnare Teams licenze per i componenti aggiuntivi agli utenti
author: SerdarSoysal
ms.author: serdars
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
description: Informazioni su come assegnare Teams licenze per i componenti aggiuntivi agli utenti per funzionalità come audioconferenza, Sistema telefonico e piani per chiamate.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435840"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Assegnare Teams licenze per i componenti aggiuntivi agli utenti

Le licenze per i componenti aggiuntivi sono licenze per Teams funzionalità di audioconferenza, Sistema telefonico e piani per chiamate. Questo articolo descrive come assegnare licenze di componenti aggiuntivi a singoli utenti e a set di utenti di grandi dimensioni in blocco.

> [!NOTE]
> Vedere [Teams licenze per i](./microsoft-teams-add-on-licensing.md) componenti aggiuntivi Teams funzionalità disponibili con le licenze per i componenti aggiuntivi. Sono disponibili anche informazioni sulle licenze da acquistare e su come acquistarle, a seconda del piano. Dopo aver deciso quali funzionalità si vogliono assegnare agli utenti, assegnarle le licenze.

È possibile usare la interfaccia di amministrazione di Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Cosa è necessario sapere prima di assegnare licenze Sistema telefonico, piano chiamate e crediti comunicazioni

Prima di iniziare, esaminare i requisiti seguenti:

- Se si usa la connettività PSTN (Public Switched Telephone Network) locale per gli utenti, è necessario assegnare solo una licenza Teams Telefono Standard. NON assegnare una licenza per il piano di chiamata.

- Dopo aver assegnato un piano per chiamate Microsoft a un utente, possono essere richieste fino a 24 ore prima che vedano la tastiera del telefono nel client Teams chiamata. Se la tastiera del telefono non viene visualizzata tra 24 ore, controllare la configurazione della [tastiera del telefono](../dial-pad-configuration.md). Se necessario, è anche possibile [contattare il supporto tecnico](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Se non è stato acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze per il piano per chiamate, scegliere l'opzione per acquistarne altre.

- Anche se agli utenti sono assegnate Enterprise E5, è comunque necessario connetterli alla rete PSTN. Sono disponibili diverse [opzioni di connettività PSTN](../pstn-connectivity.md), tra cui Piani per chiamate di Microsoft Teams, Routing diretto o Connessione con operatore.

- Dopo aver assegnato licenze per piani per chiamate o crediti comunicazioni agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnarli agli utenti. Per istruzioni dettagliate, vedere [Configurare i piani per chiamate](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Uso del interfaccia di amministrazione di Microsoft 365

Usare il interfaccia di amministrazione di Microsoft 365 per assegnare licenze a singoli utenti o a piccoli set di utenti alla volta.

Le licenze vengono assegnate nella  pagina Licenze (per un massimo di 20 utenti alla volta) o nella pagina  Utenti attivi (per un massimo di 40 utenti alla volta). Il metodo scelto varia a seconda che si vogliano gestire licenze di prodotto per utenti specifici o licenze utente per prodotti specifici.

Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

Se è necessario assegnare licenze per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare PowerShell o le licenze basate su gruppo [in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per assegnare licenze agli utenti in blocco. Per altre informazioni, vedere [Assegnare licenze agli account utente con PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script di esempio

Ecco un esempio di come usare uno script per assegnare licenze agli utenti.

1. Installare la versione a 64 bit dell'Assistente Microsoft Online Services [per i professionisti IT RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Installare il modulo Microsoft Azure Active Directory per Windows PowerShell:
    1. Aprire un prompt dei comandi Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).
    2. Eseguire il comando seguente:
        ```powershell
        Install-Module MSOnline
        ```
    3. Se viene chiesto di installare il provider di NuGet, digitare **Y** e quindi premere INVIO.
    4. Se viene chiesto di installare il modulo da PSGallery, digitare **Y** e quindi premere INVIO.
3. Al prompt dei Windows PowerShell eseguire lo script seguente per assegnare licenze agli utenti, \<CompanyName:License> dove è il nome dell'organizzazione e l'identificatore della licenza da assegnare. Ad esempio, litwareinc:MCOMEETADV.

    L'identificatore è diverso dal nome descrittivo della licenza. Ad esempio, l'identificatore per le audioconferenze è MCOMEETADV. Per altre informazioni, vedere [Nomi dei prodotti e identificatori SKU per le licenze](#product-names-and-sku-identifiers-for-licensing).

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

    Ad esempio, per assegnare Microsoft 365 Enterprise E1 e audioconferenza, usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Per assegnare un Teams Telefono con licenza piano di chiamata, usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomi di prodotto e identificatori SKU per le licenze

Ecco un elenco parziale dei nomi di prodotto e dei nomi delle parti SKU corrispondenti a cui è possibile fare riferimento quando si usa PowerShell per gestire le licenze in Teams.

Per altre informazioni, vedere Visualizzare licenze e servizi con [PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)[, Nomi](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) di prodotto e identificatori del piano di servizio per le licenze e Informazioni di riferimento [su SKU education](../sku-reference-edu.md).

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
| Audioconferenza | MCOMEETADV |
| Pagamento per audioconferenza al minuto (pagamento al minuto) Richiede che i crediti per le comunicazioni siano impostati e abilitati.* | MCOMEETACPEA |
| Teams Telefono Standard | MCOEV |
| Servizi telefonici con piano per chiamate | MCOTEAMS_ESSENTIALS |
| Piano per chiamate nazionali e internazionali | MCOPSTN2 |
| Piano per chiamate nazionali (3000 minuti per utente/mese per STATI UNITI/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE) | MCOPSTN1 |
| Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN5 |
| Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN6 |
| Credito per la comunicazione | MCOPSTNPP |

## <a name="related-content"></a>Contenuti correlati

- [Gestione delle licenze per i componenti aggiuntivi di Teams](./microsoft-teams-add-on-licensing.md)
- [Gestire l'accesso degli utenti a Teams](../user-access.md)
- [Visualizzare licenze e servizi con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informazioni di riferimento su SKU education](../sku-reference-edu.md)
