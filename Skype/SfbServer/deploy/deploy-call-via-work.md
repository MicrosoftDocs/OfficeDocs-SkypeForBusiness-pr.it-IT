---
title: Distribuire chiamate tramite lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Riepilogo: informazioni su come distribuire Call Via Work in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: c6113c4447e30d59a262bf2c02b3f7ff2db171f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624418"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Distribuire chiamate tramite lavoro in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire Call Via Work in Skype for Business Server per alcuni o tutti gli utenti.
  
Seguire questa procedura per distribuire Call Via Work per gli utenti. Considerazioni sulla pianificazione sono [descritte](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)in Plan for Call Via Work in Skype for Business Server . Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro. 
  
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Call Via Work usa UNIFIED Communications Web API (UCWA), che viene installato automaticamente in tutti Skype for Business Server Front End Server. Per abilitare gli utenti per La chiamata tramite lavoro, è inoltre necessario disporre dei prerequisiti seguenti: 
  
- È necessario disporre di un Mediation Server distribuito, come parte di un Front End Server o come ruolo autonomo. È inoltre necessario distribuire un gateway IP-PBX.
    
- Tutti gli utenti che saranno abilitati per La chiamata tramite ufficio devono disporre di un DID (Direct Inward Dialing) nel sistema telefonico PBX. 
    
- È necessario abilitare tutti gli utenti di Call Via Work per VoIP aziendale. In questo caso, è necessario configurare il Skype for Business DID per ogni utente sul numero DID corrispondente per il sistema telefonico PBX corrispondente. 
    
- Tutti gli utenti che utilizzano Call  Via Work devono avere la configurazione automatica selezionata nell'opzione **Connessioni** avanzate nel Skype for Business client. In questo modo il client può individuare gli URL UCWA. **Configurazione automatica** è la selezione predefinita.
    
- Per ogni utente di Call Via Work, abilita l'inoltro di chiamata e lo squillo simultaneo. 
    
- Per ogni utente di Chiamata via lavoro, verificare che le conferenze telefoniche con accesso esterno e la chiamata in uscita siano abilitate. In questo modo questi utenti possono accedere e uscire da Skype for Business conferenze.
    
- Assicurarsi che la delega, la chiamata del team e il Response Group siano disabilitati per ogni utente di Chiamata tramite lavoro.
    
## <a name="deploy-call-via-work"></a>Distribuire la funzionalità Chiamata tramite ufficio

Una volta installati i prerequisiti, eseguire le operazioni seguenti:
  
- Creare un numero di telefono globale per la distribuzione Skype for Business visualizzato nell'ID chiamante PBX degli utenti che effettuano chiamate di chiamata tramite ufficio. 
    
- Creare uno o più criteri Di chiamata tramite lavoro
    
- Assegnare un criterio Chiamata tramite lavoro a ogni utente che verrà abilitato per La chiamata tramite lavoro
    
### <a name="create-the-call-via-work-global-phone-number"></a>Creare il numero di telefono globale Chiamata tramite ufficio

- Digitare il cmdlet seguente
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Ad esempio, il cmdlet seguente imposta il numero di telefono globale su 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Creare un criterio Chiamata tramite lavoro

- Digitare il cmdlet seguente
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Ad esempio, il cmdlet seguente crea un criterio Chiamata tramite lavoro denominato ContosoUser1CvWP, richiede all'utente di utilizzare un numero di richiamata amministratore e imposta tale numero di richiamata su 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Assegnare un criterio Chiamata tramite lavoro a un utente

- Digitare il cmdlet seguente
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Ad esempio, il cmdlet seguente assegna il criterio Chiamata tramite lavoro "ContosoUser1CvWP" all'utente **denominato ContosoUser1.**
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

