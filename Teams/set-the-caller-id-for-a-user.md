---
title: Impostare l'ID chiamante per un utente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni sul numero Microsoft 365 e Office 365 l'ID chiamante predefinito (il numero di telefono assegnato dall'utente), noto anche come ID linea chiamante. È possibile modificare o bloccare l'ID chiamante di un utente.
ms.openlocfilehash: 2e94dde2c3271e2b31e4c679c5e020c121d28c25
ms.sourcegitcommit: 41e2e97b5856e727e42ebf5bfebceede9af56481
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53388651"
---
# <a name="set-the-caller-id-for-a-user"></a>Impostare l'ID chiamante per un utente

Sistema telefonico in Microsoft 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dall'utente. È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente. Per altre informazioni su come usare l'ID chiamante nell'organizzazione, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)
  
Per impostazione predefinita, le impostazioni dell'ID chiamante seguenti **sono disattivate.** Questo significa che il Teams di telefono dell'utente può essere visualizzato quando l'utente effettua una chiamata a un telefono PSTN. È possibile modificare queste impostazioni nel modo seguente:
  
- **ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il numero di telefono, con un altro numero di telefono. Ad esempio, è possibile modificare l'ID chiamante dell'utente dal suo numero di telefono a un numero di telefono principale per l'azienda o a un numero di telefono principale per il reparto legale. Inoltre, è possibile impostare il numero ID chiamata su qualsiasi numero di servizio online (a pagamento o numero verde) o su un numero di telefono locale tramite Instradamento diretto assegnato a un account della risorsa usato da un Operatore automatico o da una coda di chiamata.
    
  > [!NOTE]
  > Se si vuole usare il parametro *Service,* è necessario specificare un numero di servizio valido.
  > È necessario usare i cmdlet di PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity nel modulo di PowerShell di Teams 2.3.1 o versione successiva per il numero di account della risorsa, se non è visibile nell'elenco a discesa.
  
- **Bloccare l'ID chiamante in uscita.** È possibile bloccare l'invio dell'ID chiamante in uscita nelle chiamate PSTN in uscita di un utente. In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.
    
- **Bloccare l'ID chiamante in arrivo.** È possibile impedire a un utente di ricevere l'ID chiamante in qualsiasi chiamata PSTN in arrivo.

- **Impostare il nome della parte chiamante (CNAM).** Per gli Microsoft Teams utenti è possibile inviare un CNAM sulle chiamate PSTN in uscita.
    
> [!IMPORTANT]
> Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante). 
  

  
Per altre informazioni su queste impostazioni e su come usarle, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Impostare il criterio ID chiamante

> [!NOTE]
> Per impostare l'ID chiamante su un numero di telefono dell'account della risorsa e per impostare il nome della parte chiamante, usare i cmdlet di PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity nel modulo di PowerShell 2.3.1 o versione successiva di Teams. Queste opzioni non sono attualmente disponibili nell'Microsoft Teams di amministrazione. 

Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Visualizzare, creare e applicare le impostazioni dei criteri

1. Per visualizzare tutte le impostazioni dei criteri id chiamante nell'organizzazione, eseguire:

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Per altre informazioni, vedere [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).
    
2. Per creare un nuovo criterio id chiamante per l'organizzazione, usare il cmdlet New-CsCallingIdentity:
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    In qualsiasi caso, il campo "Numero di servizio" non deve iniziare con un "+".

   Per altre informazioni, vedere [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).
    
3. Applicare il nuovo criterio creato usando il cmdlet Grant-CsCallingIdentity. Ad esempio, l'esempio seguente applica il nuovo criterio all'utente Amos Marble.
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Per altre informazioni, vedere [Cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    

4. Se si vuole bloccare l'ID chiamante in arrivo, eseguire:
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Per altre informazioni, vedere [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).
    
5. Per applicare l'impostazione dei criteri creata a un utente dell'organizzazione, eseguire:
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Per altre informazioni, vedere [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).

6. Per creare un nuovo criterio ID chiamante che imposta l'ID chiamante sul numero di telefono dell'account della risorsa specificato e imposta il nome della parte chiamante su Contoso:

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) per applicare le impostazioni agli utenti.
    
### <a name="remove-a-policy-setting"></a>Rimuovere un'impostazione dei criteri

Per rimuovere un criterio dalla tua organizzazione, esegui:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Per rimuovere un criterio da un utente, esegui:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire i Microsoft 365 con un unico punto di amministrazione che semplifica il lavoro quotidiano. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
- [Introduzione alla Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
- [Modi migliori per gestire Microsoft 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Ulteriori informazioni su ID linea chiamante e nome del chiamante](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
