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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti Sistema telefonico con connettività PSTN locale.'
ms.openlocfilehash: a3524c77cf27dc4fd9ab3a4f74211fc9040aad75
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582540"
---
# <a name="assign-a-voice-routing-policy"></a>Assegnare un criterio di routing vocale
 
> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

**Riepilogo:** Leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti Sistema telefonico con connettività PSTN locale. 
  
Quando un utente si trova Skype for Business Online e usa Sistema telefonico con connettività PSTN locale, verranno applicati due criteri vocali. Uno è un criterio di routing vocale locale che verrà assegnato in locale. Questo criterio può essere globale o specifico dell'utente e definisce quali record di utilizzo PSTN sono associati all'utente. In questo argomento viene illustrato come assegnare questo criterio.
  
Gli altri criteri vocali definiscono le funzionalità di chiamata disponibili per l'utente. questo criterio vocale è definito da Microsoft ed è identico per tutte le Sistema telefonico utenti di connettività PSTN locali. Viene assegnato automaticamente agli Sistema telefonico utenti.
  
||**Utente locale**|**Sistema telefonico con l'utente di connettività PSTN locale**|
|:-----|:-----|:-----|
|Funzionalità di chiamata definite in  <br/> |Criteri vocali  <br/> |Criteri vocali predefiniti, assegnati automaticamente quando l'utente ha una licenza per Sistema telefonico.  <br/> |
|Record di utilizzo PSTN associati a  <br/> |Criteri vocali  <br/> |Criterio di routing vocale, assegnato mentre l'utente è ancora in locale.  <br/> |
   
Eseguire i passaggi seguenti usando la distribuzione locale, mentre l'utente è ancora presente nella distribuzione locale.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilizzo di un criterio di routing vocale globale

Prima di utilizzare un criterio di routing vocale globale per il Sistema telefonico con gli utenti di connettività PSTN locale, è necessario aggiungere i record di utilizzo PSTN al criterio.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Per assegnare record di utilizzo PSTN al criterio di routing vocale globale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Aggiungere i record di utilizzo PSTN al criterio:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Ad esempio:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Creazione di un nuovo criterio di routing vocale

### <a name="to-create-a-new-voice-routing-policy"></a>Per creare un nuovo criterio di routing vocale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Creare un nuovo criterio di routing vocale:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Ad esempio:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

In questo esempio viene creato un nuovo criterio di routing vocale denominato HybridVoice, a cui sono associati due utilizzi PSTN.
  
## <a name="assigning-a-voice-routing-policy"></a>Assegnazione di un criterio di routing vocale

Indipendentemente dal fatto che si utilizzi il criterio di routing vocale globale o quelli specifici dell'utente, eseguire la procedura seguente per assegnare il criterio a un utente.
  
### <a name="to-assign-the-voice-routing-policy"></a>Per assegnare il criterio di routing vocale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Assegnare un criterio vocale esistente a un utente:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In questo esempio, l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.
  
Per ulteriori informazioni sui criteri di routing vocale, vedere Create [or modify a voice policy and configure PSTN usage records in Skype for Business 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy.](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)
