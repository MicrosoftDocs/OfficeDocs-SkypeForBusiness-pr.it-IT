---
title: Assegnare licenze per i componenti aggiuntivi di Teams agli utenti
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Informazioni su come assegnare licenze per i componenti aggiuntivi di Teams agli utenti per funzionalità come Audioconferenza, Sistema telefonico e Piani per chiamate.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 635280582796f2b373efc0c763fea0887bcd6e42
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307781"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Assegnare licenze per i componenti aggiuntivi di Teams agli utenti

Le licenze per componenti aggiuntivi sono licenze per funzionalità specifiche di Teams, ad esempio Audioconferenza, Sistema telefonico e Piani per chiamate. Questo articolo descrive come assegnare licenze per componenti aggiuntivi a singoli utenti e grandi gruppi di utenti in blocco.

> [!NOTE]
> Vedere Licenze per i [componenti aggiuntivi di Teams](./microsoft-teams-add-on-licensing.md) per le funzionalità di Teams disponibili con licenze per i componenti aggiuntivi. Sono inoltre disponibili informazioni sulle licenze da acquistare e su come acquistarle, a seconda del piano. Dopo aver deciso le funzionalità desiderate per gli utenti, assegnargli le licenze.

È possibile usare il interfaccia di amministrazione di Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore gestione utenti.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Cosa devi sapere prima di assegnare le licenze Sistema telefonico, Piano per chiamate e Crediti comunicazioni

Prima di iniziare, esaminare i requisiti seguenti:

- Se si usa la connettività PSTN (Public Switched Telephone Network) locale per gli utenti, è necessario assegnare solo una licenza di Teams Phone Standard. NON assegnare una licenza per il Piano per chiamate.

- Dopo aver assegnato un piano per chiamate Microsoft a un utente, possono essere necessarie fino a 24 ore prima che visualizzi la tastiera nel client teams. Se la tastiera del telefono non viene visualizzata tra 24 ore, verificare la [configurazione della tastiera del telefono](../dial-pad-configuration.md). Se necessario, è anche possibile [contattare il supporto tecnico](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se devi acquistare altre licenze per il Piano per chiamate, scegli l'opzione per acquistarne altre.

- Anche se agli utenti sono assegnate licenze Enterprise E5, è comunque necessario connetterle alla rete PSTN. Sono disponibili diverse [opzioni di connettività PSTN](../pstn-connectivity.md), tra cui Piani per chiamate di Microsoft Teams, Routing diretto o Operator Connect.

- Dopo aver assegnato le licenze Piano per chiamate o Crediti comunicazioni agli utenti, dovrai ottenere i numeri di telefono per la tua organizzazione e quindi assegnarli agli utenti. Per istruzioni dettagliate, vedi [Configurare i piani per chiamate](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Uso della interfaccia di amministrazione di Microsoft 365

Usare la interfaccia di amministrazione di Microsoft 365 per assegnare licenze a singoli utenti o a piccoli gruppi di utenti contemporaneamente.

Le licenze vengono assegnate nella pagina **Licenze** (per un massimo di 20 utenti alla volta) o nella pagina **Utenti attivi** (per un massimo di 40 utenti alla volta). Il metodo scelto dipende dalla gestione delle licenze di prodotto per utenti specifici o dalla gestione delle licenze utente per prodotti specifici.

Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

Se è necessario assegnare licenze a un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare PowerShell o [le licenze basate su gruppo in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per assegnare licenze agli utenti in blocco. Per altre informazioni, vedere [Assegnare licenze agli account utente con PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script di esempio

Ecco un esempio di come usare uno script per assegnare licenze agli utenti.

1. [Installare il modulo Microsoft Azure Active Directory per Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. Al prompt dei comandi di Windows PowerShell eseguire lo script seguente per assegnare licenze agli utenti, dove `CompanyName:License` si trova il nome dell'organizzazione e l'identificatore della licenza da assegnare. Ad esempio, `litwareinc:MCOMEETADV`.

    L'identificatore è diverso dal nome descrittivo della licenza. Ad esempio, l'identificatore per i servizi di audioconferenza è `MCOMEETADV`. Per altre informazioni, vedere [Nomi di prodotto e identificatori SKU per le licenze](#product-names-and-sku-identifiers-for-licensing).

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

    Ad esempio, per assegnare Microsoft 365 Enterprise licenze E1 e Audioconferenza, usare la sintassi seguente nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Per assegnare un telefono Teams con licenza Piano per chiamate, usare la seguente sintassi nello script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomi di prodotto e identificatori SKU per la licenza

Ecco un elenco parziale dei nomi dei prodotti e dei nomi delle parti di SKU corrispondenti a cui puoi fare riferimento quando usi PowerShell per gestire le licenze in Teams.

Per altre informazioni, vedere [Visualizzare licenze e servizi con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomi di prodotto e identificatori del piano di servizio per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) e [Informazioni di riferimento su SKU education](../sku-reference-edu.md).

| Nome del prodotto| Nome parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con sistema telefonico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (senza audioconferenza) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con audioconferenza) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Audioconferenza | MCOMEETADV |
| Audioconferenza con tariffa al minuto (pagamento a consumo) Richiede la configurazione e l'abilitazione dei Crediti comunicazioni.* | MCOMEETACPEA |
| Teams Phone Standard | MCOEV |
| Servizi telefonici con piano per chiamate | MCOTEAMS_ESSENTIALS |
| Piano per chiamate internazionali | MCOPSTN2 |
| Piano per chiamate nazionali (3000 minuti per utente/mese per US/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE) | MCOPSTN1 |
| Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile nel Stati Uniti.* | MCOPSTN5 |
| Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese) </br>*Questo piano non è disponibile nel Stati Uniti.* | MCOPSTN6 |
| Credito per la comunicazione | MCOPSTNPP |
| Piani per chiamate con pagamento in base al costo (zona 1 paesi) | MCOPSTN_PAYG_1 |
| Piani per chiamate con pagamento in base al pagamento (paesi della zona 2) | MCOPSTN_PAYG_2 |
| Microsoft Teams Rooms Basic | Microsoft_Teams_Rooms_Basic |
| Microsoft Teams Rooms Basic senza audioconferenza | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Microsoft Teams Rooms Pro | Microsoft_Teams_Rooms_Pro |
| Microsoft Teams Rooms Pro senza audioconferenza | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |
| Microsoft Teams Premium | Microsoft_Teams_Premium |

## <a name="related-content"></a>Contenuti correlati

- [Gestione delle licenze per i componenti aggiuntivi di Teams](./microsoft-teams-add-on-licensing.md)
- [Gestire l'accesso degli utenti a Teams](../user-access.md)
- [Visualizzare licenze e servizi con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informazioni di riferimento su SKU education](../sku-reference-edu.md)
