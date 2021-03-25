---
title: Impostare l'ID chiamante per un utente
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni sull'ID chiamante predefinito di Microsoft 365 e Office 365 (numero di telefono assegnato da un utente), noto anche come ID linea chiamante. È possibile modificare o bloccare l'ID chiamante di un utente.
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117154"
---
# <a name="set-the-caller-id-for-a-user"></a>Impostare l'ID chiamante per un utente
Sistema telefonico in Microsoft 365 e Office 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dall'utente. È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente. Per altre informazioni su come usare l'ID chiamante nell'organizzazione, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)
  
> [!TIP]
> Al momento non è possibile bloccare le chiamate in arrivo in Skype for Business online. 
  
Ci sono impostazioni che possono essere modificate:
  
> [!NOTE]
> Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.
  
- **Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).
    
    > [!NOTE]
    > Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido.
  
- **Bloccare l'ID chiamante in uscita** È possibile bloccare l'invio dell'ID chiamante in uscita nelle chiamate PSTN in uscita di un utente. In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.
    
- **Bloccare l'ID chiamante in arrivo** È possibile impedire a un utente di ricevere l'ID chiamante in qualsiasi chiamata PSTN in arrivo.
    
> [!IMPORTANT]
> Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante). 
  
Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.
  
Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Impostare il criterio ID chiamante

> [!NOTE]
> Per tutte le impostazioni **dell'ID** chiamante in Skype for Business online, è necessario usare Windows PowerShell e non è possibile usare l'interfaccia di amministrazione **di Skype for Business.** 
  
### <a name="start-powershell"></a>Avviare PowerShell

- Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione

- Per visualizzare tutte le impostazioni dei criteri id chiamante nell'organizzazione, eseguire:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Vedere altri esempi e dettagli [per Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Creare un nuovo criterio ID chiamante per la propria organizzazione


- Per creare un nuovo criterio id chiamante che imposta l'ID chiamante su anonimo, eseguire:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > In qualsiasi caso, il campo "Numero di servizio" non deve iniziare con un "+".

  Vedere altri esempi e dettagli [per New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).
    
- Per applicare il nuovo criterio creato ad Amos Marble, eseguire:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) per applicare le impostazioni agli utenti.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Impostare in modo che l'ID chiamante in entrata venga bloccato

- Per bloccare l'ID chiamante in arrivo, esegui:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Vedere altri esempi e dettagli [per Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).
    
- Per applicare l'impostazione dei criteri creata a un utente dell'organizzazione, eseguire:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).
    
### <a name="remove-a-caller-id-policy"></a>Rimuovere un criterio ID chiamante

Per rimuovere un criterio dalla tua organizzazione, esegui:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Per rimuovere un criterio da un utente, esegui:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Ulteriori informazioni su ID linea chiamante e nome del chiamante](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
