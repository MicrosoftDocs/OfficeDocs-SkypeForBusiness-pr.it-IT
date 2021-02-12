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
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Riepilogo: informazioni su come distribuire Call Via Work in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825006"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Distribuire chiamate tramite lavoro in Skype for Business Server
 
**Riepilogo:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.
  
Seguire questa procedura per distribuire La chiamata tramite lavoro per gli utenti. Considerazioni sulla pianificazione sono descritte in [Plan for Call Via Work in Skype for Business Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama da lavoro. 
  
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Call Via Work usa Unified Communications Web API (UCWA), che viene installato automaticamente in tutti i Front End Server di Skype for Business Server. Per abilitare gli utenti alla funzionalità Chiama da lavoro, è inoltre necessario disporre dei prerequisiti seguenti: 
  
- È necessario disporre di un Mediation Server distribuito come parte di un Front End Server o come ruolo autonomo. È inoltre necessario distribuire un gateway IP-PBX.
    
- Tutti gli utenti che saranno abilitati per La chiamata tramite ufficio devono disporre di un DID (Direct Inward Dialing) nel sistema telefonico PBX. 
    
- È necessario abilitare tutti gli utenti chiamata tramite l'VoIP aziendale. Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for Business per ogni utente al numero DID corrispondente per il sistema telefonico PBX corrispondente. 
    
- Tutti gli utenti che usano La  chiamata tramite il lavoro devono avere la configurazione automatica selezionata nell'opzione **Connessioni** avanzate nel client Skype for Business. In questo modo il client può individuare gli URL UCWA. **Configurazione automatica** è la selezione predefinita.
    
- Per ogni utente chiamata tramite lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo. 
    
- Per ogni utente chiamata tramite lavoro, verificare che le conferenze telefoniche con accesso esterno e le chiamate in uscita siano abilitate. In questo modo questi utenti possono accedere e uscire da conferenze Skype for Business.
    
- Assicurarsi che la delega, la chiamata al team e il Response Group siano disabilitati per ogni utente chiamata tramite lavoro.
    
## <a name="deploy-call-via-work"></a>Distribuire la funzionalità Chiamata tramite ufficio

Una volta installati i prerequisiti, eseguire le operazioni seguenti:
  
- Creare un numero di telefono globale per la distribuzione visualizzato da Skype for Business sull'ID chiamante PBX degli utenti che effettuano chiamate Di chiamata tramite ufficio. 
    
- Creare uno o più criteri Chiamata tramite lavoro
    
- Assegnare un criterio Chiamata tramite lavoro a ogni utente che sarà abilitato per La chiamata via lavoro
    
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

