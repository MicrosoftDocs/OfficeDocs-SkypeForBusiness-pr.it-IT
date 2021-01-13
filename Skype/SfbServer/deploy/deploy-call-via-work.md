---
title: Distribuire la chiamata tramite il lavoro in Skype for Business Server
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
description: 'Riepilogo: informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825006"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Distribuire la chiamata tramite il lavoro in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire la chiamata tramite il lavoro in Skype for Business Server per alcuni o tutti gli utenti.
  
Attenersi alla procedura seguente per distribuire la chiamata tramite lavoro per gli utenti. Le considerazioni relative alla pianificazione sono descritte in [pianificare la chiamata tramite lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era presente una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro. 
  
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

La chiamata tramite lavoro utilizza Unified Communications Web API (UCWA), che viene automaticamente installata su tutti i Front End Server Skype for business. Per consentire agli utenti di effettuare chiamate tramite lavoro, è necessario disporre anche dei prerequisiti seguenti: 
  
- È necessario disporre di un Mediation Server distribuito, come parte di un front end server o come ruolo autonomo. È inoltre necessario distribuire un gateway IP-PBX.
    
- Tutti gli utenti abilitati per la chiamata tramite lavoro devono disporre di una composizione diretta verso l'interno (DID) nel sistema telefonico PBX. 
    
- È necessario abilitare tutte le chiamate tramite gli utenti di lavoro per VoIP aziendale. Quando si esegue questa operazione, è necessario configurare il numero DID di Skype for business per ogni utente con il relativo numero di telefono per il sistema telefonico PBX corrispondente. 
    
- Tutti gli utenti che utilizzeranno la chiamata tramite lavoro devono disporre di una **configurazione automatica** selezionata nell'opzione **connessioni avanzate** nel client Skype for business. Ciò consente al client di individuare gli URL di UCWA. La **configurazione automatica** è la selezione predefinita.
    
- Per ogni chiamata tramite l'utente di lavoro, abilitare l'inoltro di chiamata e lo squillo simultaneo. 
    
- Per ogni chiamata tramite l'utente di lavoro, assicurarsi che le conferenze telefoniche con accesso esterno e la connessione remota siano abilitate. Questo consente agli utenti di accedere e uscire dalle conferenze di Skype for business.
    
- Verificare che la delega, la chiamata del team e il Response Group siano disabilitati per ogni chiamata tramite l'utente di lavoro.
    
## <a name="deploy-call-via-work"></a>Distribuire la funzionalità Chiamata tramite ufficio

Dopo aver posizionato i prerequisiti, eseguire le operazioni seguenti:
  
- Creare un numero di telefono globale per la distribuzione che Skype for business Visualizza sull'ID chiamante del PBX degli utenti che effettuano chiamate tramite le chiamate di lavoro. 
    
- Creare una o più chiamate tramite criteri di lavoro
    
- Assegnare una chiamata tramite criteri di lavoro a ciascun utente che verrà abilitato per la chiamata tramite lavoro
    
### <a name="create-the-call-via-work-global-phone-number"></a>Creare la chiamata tramite il numero di telefono globale del lavoro

- Digitare il cmdlet seguente
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Ad esempio, il cmdlet seguente consente di impostare il numero di telefono globale su 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Creare una chiamata tramite criteri di lavoro

- Digitare il cmdlet seguente
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Ad esempio, il cmdlet seguente crea una chiamata tramite il criterio di lavoro denominato ContosoUser1CvWP, richiede all'utente di utilizzare un numero di callback di amministratore e imposta tale numero su 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Assegnare una chiamata tramite criteri di lavoro a un utente

- Digitare il cmdlet seguente
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Ad esempio, il cmdlet seguente consente di assegnare la chiamata tramite il criterio di lavoro "ContosoUser1CvWP" all'utente denominato **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite il lavoro in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

