---
title: Assegnare licenze di Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Informazioni su come assegnare licenze per funzionalità come audioconferenza, sistema telefonico e piani di chiamata.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d75201b7be82337898d4e9fe4feafb4de1155a9
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236836"
---
# <a name="assign-microsoft-teams-licenses"></a>Assegnare licenze di Microsoft Teams

È possibile assegnare licenze agli utenti per funzionalità come i piani di audioconferenza, sistema telefonico e chiamate. Questo articolo illustra come aggiungere queste licenze in blocco e per un singolo utente. 

> [!IMPORTANT]
> Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per informazioni sulle licenze che è necessario acquistare e su come acquistarle, a seconda del piano di Office 365, in modo che gli utenti ottengano servizi di audioconferenza, numeri verdi e la possibilità di chiamare i numeri di telefono all'esterno della propria azienda.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze

Ecco cosa è necessario sapere prima di assegnare le licenze per i servizi di audioconferenza, il sistema telefonico e il piano di chiamata.

- **Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza Sistema telefonico. NON dovrai invece assegnare un Piano per chiamate.

- **Latenza dopo l'assegnazione delle licenze**: a causa della latenza tra Office 365 e Microsoft teams, possono essere necessarie fino a 24 ore per consentire a un utente di assegnare un piano di chiamata dopo l'assegnazione di una licenza. Se dopo 24 ore non è stato assegnato un piano per le chiamate, [contattare il supporto per i prodotti business-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.

- **Passaggi successivi**: dopo avere assegnato le licenze per il Piano per chiamate agli utenti, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Assegnare un sistema telefonico e una licenza per un piano di chiamata a un utente

I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Assegnare licenze per il sistema telefonico e il piano di chiamata in blocco

1. Installa Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW. Cosa fare se il modulo non è installato? Per scaricarlo, vedere [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/?LinkId=625123) .

2. Installa il Modulo di Windows Azure Active Directory. Cosa fare se il modulo non è installato? Vedere [gestire Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per le istruzioni per il download e la sintassi dei cmdlet.

3. Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:

In questo esempio vengono assegnate una licenza di Enterprise E3 insieme a una licenza per Sistema telefonico e per un Piano per chiamate nazionali.

Il nome delle licenze o dei nomi di prodotto nello script è elencato in corsivo (Vedi il [sistema telefonico e i piani di chiamata per i nomi dei prodotti o gli SKU usati per gli script](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), dopo l'esempio).

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script

| Nome del prodotto | Nome parte SKU |
|--------------|---------------|
| Enterprise E5 (con Sistema telefonico) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Sistema telefonico | MCOEV |
| Piano di chiamate internazionali & nazionali | MCOPSTN2 |
| Piano per chiamate nazionali (3000 minuti per utente/mese per US/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE) | MCOPSTN1 |
| Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese) </br>*Nota: questo piano non è disponibile negli Stati Uniti*. | MCOPSTN5 |
| Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese) </br>*Nota: questo piano non è disponibile negli Stati Uniti*. | MCOPSTN6 |
| Credito per la comunicazione | MCOPSTNPP | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Assegnare una licenza di audioconferenza a un utente

I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Assegnare licenze per servizi di audioconferenza in blocco

1. Scaricare e installare l' [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Scarica e installa il Modulo di Windows Azure Active Directory. Vedere [gestire Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per le istruzioni per il download e la sintassi dei cmdlet.

Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:

Il nome delle licenze o dei nomi di prodotto nello script è elencato in corsivo. Vedere [nomi di prodotti per la conferenza audio o SKU usati per gli script](#audio-conferencing-product-names-or-skus-used-for-scripting) per tutti i nomi di prodotto.

In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.

```powershell
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomi dei prodotti per la conferenza audio o SKU usati per gli script

| Nome del prodotto | Nome parte SKU |
|--------------|---------------|
| Servizi di audioconferenza (abbonamento) | MCOMEETADV | 
| Pay-in per i servizi di audioconferenza per minuto (pay-in-go)</br>*Nota: richiede che i crediti di comunicazione siano configurati e abilitati*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (senza Audioconferenza) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (con Audioconferenza) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Credito per la comunicazione

Ecco cosa è necessario sapere prima di assegnare le licenze per i crediti di comunicazione.

- **Clienti Enterprise E5**: anche se agli utenti sono assegnate licenze Enterprise E5, è comunque consigliabile assegnare loro licenze per i crediti per comunicazioni.

- **Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.

## <a name="assign-a-communications-credits-license-to-one-user"></a>Assegnare una licenza per i crediti di comunicazione a un utente

I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Assegnare licenze per i crediti di comunicazione in blocco

Guarda lo script di esempio per l'assegnazione delle licenze di Audioconferenza. Aggiornalo con le informazioni per l'assegnazione di licenze di Crediti comunicazioni.

## <a name="related-topics"></a>Argomenti correlati

[Configurare i piani per chiamate](set-up-calling-plans.md)
</br>
[Aggiungere fondi e gestire i crediti per la comunicazione](add-funds-and-manage-communications-credits.md)
