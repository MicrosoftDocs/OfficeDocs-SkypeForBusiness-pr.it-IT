---
title: Distribuire una chiamata tramite il lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791084"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Distribuire una chiamata tramite il lavoro in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.
  
Seguire questi passaggi per distribuire la chiamata tramite lavoro per gli utenti. Le considerazioni sulla pianificazione sono discusse in [piano per la chiamata tramite lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server questa funzionalità è stata sostituita da chiamata tramite lavoro. 
  
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Chiamata tramite lavoro usa Unified Communications Web API (UCWA), che viene automaticamente installata in tutti i server front-end di Skype for Business Server. Per consentire agli utenti di effettuare chiamate tramite lavoro, è necessario disporre anche dei prerequisiti seguenti: 
  
- È necessario disporre di un Mediation Server distribuito, sia come parte di un front end server che come ruolo autonomo. Devi anche distribuire un gateway IP-PBX.
    
- Tutti gli utenti che verranno abilitati per la chiamata tramite lavoro devono avere un accesso diretto (DID) nel sistema telefonico PBX. 
    
- È necessario abilitare tutte le chiamate tramite gli utenti del lavoro per VoIP aziendale. Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for business per ogni utente al numero DID corrispondente per il sistema telefonico PBX corrispondente. 
    
- Tutti gli utenti che useranno la chiamata tramite lavoro devono avere la **configurazione automatica** selezionata nell'opzione **connessioni avanzate** nel client Skype for business. Questo consente al client di individuare gli URL di UCWA. La **configurazione automatica** è la selezione predefinita.
    
- Per ogni chiamata tramite l'utente del lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo. 
    
- Per ogni chiamata tramite l'utente del lavoro, assicurati che i servizi di conferenza telefonica con accesso esterno siano abilitati. Questo consente agli utenti di accedere e disconnettersi dalle conferenze di Skype for business.
    
- Assicurarsi che la delega, la chiamata del team e il gruppo di risposte siano disabilitati per ogni chiamata tramite l'utente del lavoro.
    
## <a name="deploy-call-via-work"></a>Distribuire la funzionalità Chiamata tramite ufficio

Dopo aver effettuato i prerequisiti, eseguire le operazioni seguenti:
  
- Creare un numero di telefono globale per la distribuzione visualizzata da Skype for business nell'ID chiamante PBX degli utenti che effettuano una chiamata tramite chiamate aziendali. 
    
- Creare una o più chiamate tramite i criteri di lavoro
    
- Assegnare una chiamata tramite i criteri di lavoro a ogni utente che verrà abilitato per la chiamata tramite lavoro
    
### <a name="create-the-call-via-work-global-phone-number"></a>Creare la chiamata tramite numero di telefono globale dell'ufficio

- Digitare il cmdlet seguente
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Ad esempio, il cmdlet seguente imposta il numero di telefono globale su 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Creare una chiamata tramite i criteri di lavoro

- Digitare il cmdlet seguente
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Ad esempio, il cmdlet seguente crea una chiamata tramite il criterio di lavoro denominato ContosoUser1CvWP, richiede all'utente di usare un numero di callback di amministratore e imposta il numero di callback su 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Assegnare una chiamata tramite criteri di lavoro a un utente

- Digitare il cmdlet seguente
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Ad esempio, il cmdlet seguente assegna la chiamata tramite il criterio di lavoro "ContosoUser1CvWP" all'utente denominato **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite il lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

