---
title: Assegnare licenze per i componenti aggiuntivi per i team agli utenti
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come assegnare licenze per i componenti aggiuntivi per i team agli utenti per le caratteristiche come l'audioconferenza, il sistema telefonico e i piani di chiamata.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868583"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Assegnare licenze per i componenti aggiuntivi per i team agli utenti

Le licenze per i componenti aggiuntivi sono licenze per specifiche caratteristiche dei team, ad esempio servizi di audioconferenza, sistema telefonico e piani per chiamate. Questo articolo descrive come assegnare licenze per i componenti aggiuntivi a singoli utenti e a set di utenti di grandi dimensioni in blocco.

> [!NOTE]
> Vedere [licenze per i componenti aggiuntivi teams](microsoft-teams-add-on-licensing.md) per le funzionalità Team disponibili con le licenze per i componenti aggiuntivi. Sono disponibili anche informazioni sulle licenze che è necessario acquistare e su come acquistarle (a seconda del piano), in modo che gli utenti possano ottenere funzionalità come i servizi di audioconferenza, i numeri verdi e la possibilità di chiamare i numeri di telefono all'esterno dell'organizzazione. Dopo aver deciso le caratteristiche desiderate per gli utenti, assegnare le licenze.

È possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Cosa è necessario sapere prima di assegnare le licenze per il sistema telefonico, il piano di chiamata e i crediti di comunicazione

Prima di iniziare, esaminare le operazioni seguenti:

- Se si usa la connettività PSTN (Public Switched Telephone Network) locale per gli utenti ibridi, è sufficiente assegnare una licenza per il sistema telefonico. Non assegnare una licenza per il piano di chiamata.

- Data la latenza tra Microsoft 365 e Microsoft teams, possono essere necessarie fino a 24 ore per consentire a un utente di assegnare un piano di chiamata dopo l'assegnazione di una licenza. Se dopo 24 ore non viene assegnato un piano per le chiamate, [contattare il supporto per i prodotti business-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Se non è stato acquistato il numero di licenze corretto, viene visualizzato un messaggio di errore. Se è necessario acquistare più licenze per il piano di chiamata, scegliere l'opzione per acquistare altro.

- Anche se agli utenti sono assegnate licenze Enterprise E5, è comunque necessario assegnare loro le licenze per i [crediti di comunicazione](../what-are-communications-credits.md) , se vogliono effettuare o ricevere chiamate dalla rete PSTN.

- Dopo aver assegnato le licenze per il piano di chiamata o per i crediti di comunicazione agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare tali numeri agli utenti. Per istruzioni dettagliate, vedere [configurare i piani](../set-up-calling-plans.md)per le chiamate.

## <a name="using-the-microsoft-365-admin-center"></a>Uso dell'interfaccia di amministrazione di Microsoft 365

Usare l'interfaccia di amministrazione di Microsoft 365 per assegnare licenze a singoli utenti o a piccoli gruppi di utenti alla volta. È possibile assegnare licenze nella pagina **licenze** (per un massimo di 20 utenti alla volta) o nella pagina **utenti attivi** . Il metodo scelto varia a seconda che si vogliano gestire le licenze di prodotto per utenti specifici o gestire le licenze utente per prodotti specifici.

Per istruzioni dettagliate, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Se è necessario assegnare licenze per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare PowerShell o le [licenze basate su gruppo in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per assegnare licenze agli utenti in blocco.  Per altre informazioni, vedere [assegnare licenze agli account utente con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script di esempio

Ecco un esempio di come usare uno script per assegnare licenze agli utenti.

1. Installare la versione a 64 bit dell' [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Installare il modulo di Microsoft Azure Active Directory per Windows PowerShell:
    1. Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).
    2. Eseguire il comando seguente:
        ```powershell
        Install-Module MSOnline
        ```
    3. Se viene richiesto di installare il provider NuGet, digitare **Y**e quindi premere INVIO.
    4. Se viene richiesto di installare il modulo da PSGallery, digitare **Y**e quindi premere INVIO.
3. Al prompt dei comandi di Windows PowerShell eseguire lo script seguente per assegnare licenze agli utenti, dove \<CompanyName:License> si trova il nome dell'organizzazione e l'identificatore per la licenza che si vuole assegnare. Ad esempio, litwareinc: MCOMEETADV.

    L'identificatore è diverso dal nome descrittivo della licenza. Ad esempio, l'identificatore per i servizi di audioconferenza è MCOMEETADV. Per altre informazioni, vedere [nomi di prodotti e identificatori SKU per le licenze](#product-names-and-sku-identifiers-for-licensing).

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

    Ad esempio, per assegnare licenze Microsoft 365 Enterprise 1 e servizi di audioconferenza, usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Per assegnare una licenza di Microsoft Business Voice (senza il piano chiamante), usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomi di prodotto e identificatori SKU per le licenze

Ecco un elenco parziale di nomi di prodotto e i relativi nomi di parti SKU che puoi usare come riferimento quando usi PowerShell per gestire le licenze in teams.

Per altre informazioni, vedere [visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomi di prodotto e identificatori del piano di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)e [riferimento per SKU per l'istruzione](../sku-reference-edu.md).

| Nome del prodotto| Nome parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con sistema telefonico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (senza servizi di audioconferenza) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con servizi di audioconferenza) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Canada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Regno Unito) | BUSINESS_VOICE  |
| Microsoft Business Voice (Stati Uniti) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (senza piano chiamante) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (senza piano chiamante) per gli Stati Uniti| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferenza | MCOMEETADV | 
| Pay-in per i servizi di audioconferenza per minuto (pay-in-go)</br>*Richiede che i crediti di comunicazione siano configurati e abilitati.* | MCOMEETACPEA |
| Sistema telefonico | MCOEV |
| Piano per chiamate nazionali e internazionali | MCOPSTN2 |
| Piano per chiamate nazionali (3000 minuti per utente/mese per US/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE) | MCOPSTN1 |
| Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN5 |
| Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile negli Stati Uniti.* | MCOPSTN6 |
| Credito per la comunicazione | MCOPSTNPP |

## <a name="related-topics"></a>Argomenti correlati

- [Gestione delle licenze per i componenti aggiuntivi di Teams](microsoft-teams-add-on-licensing.md)
- [Gestire l'accesso degli utenti a Teams](../user-access.md)
- [Visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Riferimento SKU per l'istruzione](../sku-reference-edu.md)