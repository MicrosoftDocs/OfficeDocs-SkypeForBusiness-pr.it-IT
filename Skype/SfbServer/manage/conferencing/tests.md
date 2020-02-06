---
title: Testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Riepilogo: informazioni su come testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 838e04d7cb6d17e98df2b6fa0dbe3f3d46a5ecad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818467"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Come verifica finale della configurazione dei servizi di conferenza telefonica con accesso esterno, è possibile cercare piani di chiamata con un'area dei servizi di conferenza telefonica con accesso esterno non utilizzata da qualsiasi numero di Access e per i numeri di Access che non hanno specificato un'area di conferenza telefonica con chiamata in ingresso. È inoltre necessario verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri delle connessioni in ingresso funzionino correttamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Trovare i piani di chiamata con un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Questo cmdlet restituisce tutti i dial plan che hanno un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access.
    
Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Trovare i numeri di accesso senza aree assegnate

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Questo cmdlet restituisce tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso che non sono associati a un'area geografica.
    
Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Testare i numeri di pagina Web e di accesso

Per verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri per le connessioni in ingresso funzionino correttamente, è necessario eseguire le operazioni seguenti:
  
- Testare la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno accedendo all'URL semplice.
    
- Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script più avanti in questo argomento. Questo script simula le chiamate ai numeri di accesso. È necessario l'indirizzo SIP e le credenziali di un client Unified Communications (UC) ospitato nel pool specifico per l'uso di questo script.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Per testare i numeri di accesso per un pool specifico

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Il report risultante Mostra l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica. Il contrassegno-Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.
    
Per altre informazioni, vedere [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

