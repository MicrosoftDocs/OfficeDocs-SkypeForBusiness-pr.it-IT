---
title: Assegnare un criterio di routing vocale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che usano il sistema telefonico in Office 365 con connettività PSTN locale.'
ms.openlocfilehash: fc1bf50eabc1b596ba54e3447c0357cfd304ad2c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003036"
---
# <a name="assign-a-voice-routing-policy"></a>Assegnare un criterio di routing vocale
 
**Riepilogo:** Leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che usano il sistema telefonico in Office 365 con connettività PSTN locale. 
  
Quando un utente si trova in Skype for business online e usa il sistema telefonico in Office 365 con connettività PSTN locale, verranno applicati due criteri vocali. Uno è un criterio di routing vocale locale che verrà assegnato in locale. Questo criterio può essere globale o specifico per gli utenti e definisce i record di utilizzo PSTN associati all'utente. Questo argomento spiega come assegnare questo criterio.
  
Gli altri criteri vocali definiscono le funzionalità di chiamata disponibili per l'utente. Questo criterio vocale è definito da Microsoft ed è identico per tutti i sistemi telefonici in Office 365 con gli utenti di connettività PSTN locale. Viene assegnato automaticamente al sistema telefonico negli utenti di Office 365.
  
||**Utente locale**|**Sistema telefonico in Office 365 con l'utente di connettività PSTN locale**|
|:-----|:-----|:-----|
|Funzionalità di chiamata definite in  <br/> |Criteri vocali  <br/> |Criteri vocali predefiniti, assegnati automaticamente quando l'utente ha una licenza per il sistema telefonico in Office 365.  <br/> |
|Record di utilizzo PSTN associati a  <br/> |Criteri vocali  <br/> |Criteri di routing vocale, assegnati mentre l'utente viene ancora ospitato in locale.  <br/> |
   
Eseguire la procedura seguente usando la distribuzione locale, mentre l'utente è ancora ospitato nella distribuzione locale.
  
## <a name="using-a-global-voice-routing-policy"></a>Uso di un criterio di routing vocale globale

Prima di usare un criterio di routing vocale globale per il sistema telefonico in Office 365 con gli utenti di connettività PSTN locale, è necessario aggiungere i record di utilizzo PSTN al criterio.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Per assegnare i record di utilizzo PSTN ai criteri di routing vocale globale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Aggiungere i record di utilizzo PSTN ai criteri:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Ad esempio:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Creazione di un nuovo criterio di routing vocale

### <a name="to-create-a-new-voice-routing-policy"></a>Per creare un nuovo criterio di routing vocale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Creare un nuovo criterio di routing vocale:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Ad esempio:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Questo esempio crea un nuovo criterio di routing vocale denominato HybridVoice, a cui sono associati due utilizzi PSTN.
  
## <a name="assigning-a-voice-routing-policy"></a>Assegnazione di un criterio di routing vocale

Indipendentemente dal fatto che si usi il criterio di routing vocale globale o un utente specifico, usare la procedura seguente per assegnare i criteri a un utente.
  
### <a name="to-assign-the-voice-routing-policy"></a>Per assegnare i criteri di routing vocale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Assegnare un criterio vocale esistente a un utente:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.
  
Per altre informazioni sui criteri di routing vocale, vedere [creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

