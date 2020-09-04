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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Riepilogo: leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che utilizzano il sistema telefonico con connettività PSTN locale.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359322"
---
# <a name="assign-a-voice-routing-policy"></a>Assegnare un criterio di routing vocale
 
> [!Important]
> Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.  Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

**Riepilogo:** Leggere questo argomento per informazioni su come assegnare un criterio vocale per gli utenti che utilizzano il sistema telefonico con connettività PSTN locale. 
  
Una volta che un utente è su Skype for business online e utilizza un sistema telefonico con connettività PSTN locale, verranno applicati due criteri vocali. Uno è un criterio di routing vocale locale che verrà assegnato nei locali. Questo criterio può essere globale o specifico dell'utente e definisce quali record di utilizzo PSTN sono associati all'utente. In questo argomento viene illustrato come assegnare questo criterio.
  
Gli altri criteri vocali definiscono quali funzionalità di chiamata sono disponibili per l'utente. Questo criterio vocale è definito da Microsoft ed è identico per tutti i sistemi di telefonia con gli utenti di connettività PSTN locali. Viene assegnato automaticamente agli utenti del sistema telefonico.
  
||**Utente locale**|**Sistema telefonico con utente di connettività PSTN locale**|
|:-----|:-----|:-----|
|Funzionalità di chiamata definite in  <br/> |Criteri vocali  <br/> |Criteri vocali predefiniti, assegnati automaticamente quando l'utente viene concesso in licenza per il sistema telefonico.  <br/> |
|Record di utilizzo PSTN associati a  <br/> |Criteri vocali  <br/> |Criterio di routing vocale, assegnato mentre l'utente è ancora ospitato in locale.  <br/> |
   
È necessario eseguire i passaggi seguenti utilizzando la distribuzione locale, mentre l'utente è ancora ospitato nella distribuzione locale.
  
## <a name="using-a-global-voice-routing-policy"></a>Utilizzo di un criterio di routing vocale globale

Prima di utilizzare un criterio di routing vocale globale per il sistema telefonico con gli utenti di connettività PSTN locali, è necessario aggiungere i record di utilizzo PSTN al criterio.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Per assegnare i record di utilizzo PSTN al criterio di routing vocale globale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.
    
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

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.
    
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

Indipendentemente dal fatto che si utilizzi il criterio di routing vocale globale o quelli specifici dell'utente, utilizzare i passaggi seguenti per assegnare il criterio a un utente.
  
### <a name="to-assign-the-voice-routing-policy"></a>Per assegnare il criterio di routing vocale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.
    
3. Assegnare un criterio vocale esistente a un utente:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In questo esempio, l'utente con il nome visualizzato Bob Kelly viene assegnato al criterio vocale creato in precedenza con il nome HybridVoice.
  
Per ulteriori informazioni sui criteri di routing vocale, vedere [creare o modificare criteri vocali e configurare i record di utilizzo PSTN in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

