---
title: Testare le conferenze telefoniche con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Riepilogo: informazioni su come testare le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096732"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Testare le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come testare le conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Come verifica finale della configurazione delle conferenze telefoniche con accesso esterno, è possibile cercare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso e numeri di telefono per i quali non è specificata un'area di conferenza telefonica con accesso esterno. È inoltre necessario verificare che la pagina Web Impostazioni conferenza telefonica con accesso esterno e i numeri di accesso esterno funzionino correttamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Trovare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da un numero di accesso

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Questo cmdlet restituisce tutti i dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso.
    
Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Trovare numeri di accesso senza aree assegnate

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Questo cmdlet restituisce tutti i numeri di accesso per conferenze telefoniche con accesso esterno non associati ad alcuna area.
    
Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Testare la pagina Web e i numeri di accesso

Per verificare che la pagina Web Impostazioni conferenza telefonica con accesso esterno e i numeri di accesso esterno funzionino correttamente, è necessario eseguire le operazioni seguenti:
  
- Testare la pagina Web Impostazioni conferenza telefonica con accesso esterno eseguendo l'accesso all'URL semplice.
    
- Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script riportato più avanti in questo argomento. Questo script simula le chiamate ai numeri di accesso. Per utilizzare lo script, sono necessari l'indirizzo SIP e le credenziali di un client per comunicazioni unificate ospitato nel pool specifico.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Per testare i numeri di accesso per un pool specifico

1. Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Al prompt dei comandi eseguire il comando seguente:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Nel rapporto risultante viene mostrato l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica. Il flag -Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.
    
Per ulteriori informazioni, vedere [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
